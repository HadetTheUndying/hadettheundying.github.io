---
layout: post
title: mesa-git in Userland
---

So some of you probably saw me posting about running Cyberpunk 2077 on Linux using the latest commits to mesa on my AMD Graphics Card. This was actually quite a pain to get going at first because I wasn't thinking, and ended up heavily modifying the `srcpkg` template in the Void repos to install the driver system-wide.

`mesa` does not need to be installed system-wide and the drivers are fully swappable in userland. So below I'm going to walk you through how to prepare a userland install of mesa and how to use it to run 3D applications independently of your system's mesa. Enabling you to keep the stable mesa release as your system-wide drivers, which will prevent a lot of headaches and crashing. I personally experienced a Visual Artifact Special Rainbow Crash on my RX Vega card for example, which would require a powercycle to fix every other time it would happen. 

# The build Process

I'm going to assume you know how to fetch the required dependencies for mesa on whichever distribution you are running. You can reference the extended build doc [HERE]('https://docs.mesa3d.org/install.html') if you don't know which packages you will need. The packages are also listed in the meson file. On Void all of the dependencies are listed in the srcpkgs repo under `void-packages/srcpkgs/mesa/template` Assume that anything with a trailing # is a comment for explanation your shell should but if it doesn't remove the comments from the command list I'm about to provide below.

We're going to clone and build the latest commit with the default configuration arguments now.

```bash
git clone https://gitlab.freedesktop.org/mesa/mesa.git mesa-git
cd mesa-git
meson --prefix=/tmp/mesa-git git-build # Pick a different directory if you wanna need it to stick around
ninja -C git-build install
```

If everything went well you should have just built mesa and installed it and all of the default x86_64 drivers to `/tmp/mesa-git`. You can can change the install location with the prefix argument. I would use `/tmp/` if you're expecting to rebuild a lot. If you're expecting to stick with that build for awhile just drop it in another directory.

# Overriding OpenGL Drivers

Now we've compiled with the latest commit, we want to be able to use it. By default your system will still favor the libraries installed by your package manager. Luckily we can override this easily even on a per application basis.

Depending on how you compiled these file paths my be different only use these for a reference.

To preload your newly built drivers use `LIBGL_DRIVERS_PATH=/tmp/mesa-git/lib/dri/` followed by the application you want to run.

For example: `LIBGL_DRIVERS_PATH=/tmp/mesa-git/lib/dri/ glxgears -info`

# Overriding Vulkan Drivers

This is pretty similar you just need to use the `VK_ICD_FILENAMES` override.

For example: `VK_ICD_FILENAMES=/tmp/mesa-git//share/vulkan/icd.d/radeon_icd.x86_64.json`

# Quality of Life Practices

First I'm going to provide a shell script for doing this to make your live a little easier and provide an example for executing it on an application.

Here is the Script you should create and make executable:

```sh
#!/bin/sh

MESAENV=/tmp/mesa-git
LIB64=$MESAENV/lib/
export LD_LIBRARY_PATH=$LIB64/
export LIBGL_DRIVERS_PATH=$LIB64/dri
export VK_ICD_FILENAMES=$MESAENV/share/vulkan/icd.d/radeon_icd.x86_64.json

exec "$@"
```

An Example of running this would be `./scriptname.sh vkcube`. This will load `RADV` from the driver we just built instead of your system's mesa install. It will also select OpenGL Drivers for OpenGL applications, for example `./scriptname.sh supertuxkart` Will load the radeon drive we just built.

## Using with Steam

Using the newly compiled drivers with steam is also very easy. All you need to do is go into the game properties, click "SET LAUNCH OPTIONS" and paste this string `LIBGL_DRIVERS_PATH=/tmp/mesa-git/lib/dri/ VK_ICD_FILENAMES=/tmp/mesa-git/share/vulkan/icd.d/radeon_icd.x86_64.json %command%` , once again the file paths I'm using are for example purposes, if you changed them you will have to change them here as well. You can also just launch Steam with the script provided above, but doing so may have undesired results if you don't need the latest driver for more than one specific game.

# Conclusion 

I wish I had done a little more research about mesa before installing from the latest commit system-wide, as downgrading is a bigger pain than using a few overrides most of the time. I've been doing this to play Cyberpunk 2077 for a few days now, rebuilding the driver every day, it's been really useful for performance testing, and I was also able to do this to test the new `zink` option in mesa without causing too much trouble with the rest of my system. 

If you found this guide helpful or informative considering checking out my About page and subscribing to my social media, maybe even backing me on Patreon or just buying me a coffee. I do stream sometimes and I am trying to post at least one Video on my youtube a month currently, I just need some help picking topics.

Thank you.
