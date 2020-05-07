---
layout: post
title: Three Years Windows Free
---

I have spent the last 3 years mostly Windows free. In April of 2017 my boot files on my     Windows 7 install got corrupted. I had been mostly using Linux for work at this point. I had the  urge to move back to Linux as my desktop after a long hiatus after the growing pains Gentoo and Fedora had between 2006-2009, had long since been overcome. The one thing that was holding me back up until then was a number of games; of which I was hardly playing.

Around this time a project had popped up on GitHub and was being posted about called [DXVK](https://github.com/doitsujin/dxvk). The project's intent was to provide a translation layer between DirectX 11 API calls and convert them to Vulkan, as opposed to the old method of using the dated OpenGL API, with limited success. DXVK did not see its first release in 0.2.0 for nearly 8 months after I decided to switch, but Wine was also making a lot of progress in game compatibility at the time too, and many users had gotten one of my favorite games, Overwatch, working at the time. These factors on top of Valve supplying Native Ports for almost their entire Library since the release of Steam for Linux and SteamOS were also major motivating factors in making the switch. I decided that I would just ignore any games that I couldn't run on the chance that they would certainly run in the future. 


## Making the Switch:

I initially decided to install Kubuntu, the KDE Plasma flavor of Ubuntu. I gave this a try for a few months before deciding I didn't like KDE very much anymore. Primarily due to a **still present** bug where Baloo file indexer will recursively index files, and cause your disk I/O to be at 100% constantly. This was causing my system to perform almost as poorly as it did on Windows.

After deciding that KDE was not for me, I switched stock Ubuntu with Gnome for some time with xfce4 installed to test out as well. I stuck with this setup for 4 months. It was great, I have almost nothing bad to say about the Ubuntu landscape, other than the mess that is getting up-to-date Graphics Drivers, and having to resort to using 3rd Party PPA's at the time.

I had been entertaining the idea of switching back to Gentoo for most of this time, however I was very bandwidth and time limited and did not feel like waiting for source downloads and compile times for every package on my system. I also think `portage` is the absolute worst package manager ever devised, and I will stand by this for the rest of forever until it is rewritten in something that isn't python2.

## Switching to Arch Linux

I ended up making a compromise and switching to Arch Linux instead. I mostly enjoyed Arch linux but I'm going to list a few problems I had as an experienced Linux user right from the start with just my installation.

1. Copious amounts of Documentation on a Wiki is no substitute for concise and easy to follow Documentation.
2. The Arch Live image comes with a tool called `wifi-menu`, which allows you to get networking to get your system installed. The `base` metapackage at the time included `wifi-menu` but none of its dependencies. This went unfixed for **2 years!**  This meant that when you finished your installation, if you did not have access to an ethernet port or have not manually installed an application like `NetworkManager`, you were about to end up being very frustrated.
3. Arch has a very limited amount of software in its `core`, `community` and `extra` repositories. This makes Arch very dependent on the Arch User Repository, which has absolutely no oversight for packaging quality. Meaning if you don't know how the Arch Build System works you're basically trusting a package not to break your machine.

All of this being said my experience on Arch Linux was incredibly good. I was always able to find or package software I wanted because the Arch Build System is very easy to learn. Having the latest packages was very nice since I do a moderate amount of gaming. Arch encouraged me to fiddle with my system a lot too, and I was able to learn a lot more about how I wanted my workflow to be. I stuck with Arch for about a year, with the only major problems I had being the occasional random black screen on boot because of **NVIDIA!**

## PROTON

In April of 2018 Valve released a Beta Steam Client update that allowed users to test their new Compatibility Layer called [Proton](https://github.com/ValveSoftware/Proton). Along with Hiring the developer of DXVK. This has drastically improved the Gaming Landscape on Linux in ways i would have never imagined after the collapse of Loki Games, in the early 2000s. I cannot express how happy I am with Proton, I have done 3 Youtube videos on Proton, covering how incredible it is for gaming on Linux. The number of people that have switched to Linux as their primary Desktop Operating System thanks to Valve's efforts with Proton is nothing short of amazing.

My experience with Proton on Arch Linux was pretty great until I had to deal with Proton running the Esync patches for wine, and Arch was using the default file descriptor limit sizes. This was a huge pain to figure out how to change because Arch Uses SystemD which overrides the default method for changing hard and soft descriptor limits.

As of writing this most of my game library is Compatible. You can check yours on [ProtonDB](https://www.protondb.com/). 

## Void Linux

In September of 2018 I switched from Arch Linux to Void Linux on my Desktop, after running Void with [musl-libc](https://www.musl-libc.org/) on my laptop for most of the summer. My experience on Void Linux is probably the closest I've gotten to my enjoyment of learning things and using Linux since the time I first installed Slackware on a Machine in 1999. I would not recommend Void Linux for everyone or even as their first Linux Distribution but It is an incredibly well put together Distribution. 

Some things I really like about Void:

+ The Package Manager
+ Support for a wide variety of CPU Architectures.
+ The New Handbook and the way they approach Documentation
+ The way they maintain and oversee the repositories.
+ The community in general seems to be a lot more mature and professional
+ Using [runit](http://smarden.org/runit/) as its init system

I am able to run Void on a variety of systems because of the portability of the package manager.

Currently I'm running Void on:
+ My Main Desktop and Work Laptop
+ 3 raspberry pi 3Bs
+ 2 PowerMac G5 towers
+ 3 PowerBook G4s 
+ My 2u Frankenstein Server

I have only had Void break from updating one time in the nearly 2 years I have been using it. While there has been a fair bit of public drama regarding the distribution recently, things on the end that matters, which is maintenance continue to go forward as normal.


## The Desktop Experience

This post primarily addressed gaming because the regular Desktop experience on Linux with a full Desktop Environent is honestly much better than it currently is on Windows. Using a fully featured and developed Desktop Environment like Gnome 3 or KDE Plasma you can expect a very professional and modern experience on Linux. Most Distribution's Package Managers are far superior to Windows, since you  can source your software directly from the people maintaining your operating system, as opposed to finding executables and installers on the web. This is a much more sane approach to installing software, it's easier, it's safer, it's much more modern. 

The only bad thing that I can really say about this would be the nearly overwhelming number of choices you have. When making the switch I did a little research and ended up grabbing the software that sounded appealing to me for the tasks I was doing. 

In the  end I decided to use Gnome 3 as it is the default environment on many Distributions and I work with remote workstations a lot. In my opinion this is the most feature complete Environment on Linux, even if other people are very opinionated against it.


## I won't be returning to Windows

Here is a short list of reasons why I won't return to Windows:
+ Reformatting should not be a recommended Maintenance Step
+ Windows Update is undeniably broken,
+ NTFS is almost as old as I am, has notoriously slow I/O and leads to horrible disk fragmentation.
+ Bloatware on a "Professional" Operating System.
+ Lack of Standardization
+  Shady data collection

I am willing to give up the 10 or so games I might not be able to play right now for the quality of life I have when working on my system now. When I do run into a problem it's much easier to track down the issue and correct it. It is mind boggling to me that Windows users are terrified of opening the CLI but don't bat an eye following some sketchy forum post telling them to run some software as Administrator to fix their system problem, or open up the Registry and edit a specific file. That is in no way easier than the few maintenance tasks I have to run twice a month on my system.

## Conclusion

After 3 years using a Linux Distribution as my daily Operating System for work. I can certainly recommend that you give it a try unless you are doing Audio Production, which is a miserable experience and there's a reason why Apple is praised in this field. 

I hope in 3 years time I won't be back here eating my words like I was with Gentoo and Fedora in 2009, but I don't really foresee that happening. Things have improved so much, the world runs on Open Source now.

If you want any advice on making the switch, feel free to contact me. I will be posting about my experience on PowerPC very soon.
