---
layout: post
title: OSGrid Simulator Setup Guide
---

**THIS GUIDE ASSUMES YOU KNOW HOW TO USE SSH IF YOU DON'T LOOK UP A GUIDE FOR THAT**

Get a Fresh Debian Install either on Bare metal, a VPS or in a VM. Make sure you have at least port 9000 forwarded. I forwarded the port range 9000-9100

I recommend following [Linode's Guide on Hardening SSH Access]("https://www.linode.com/docs/security/basics/securing-your-server/")

# Now that your server install is ready let's install dependencies:

```
sudo apt install  atool mono ufw screen libturbojpeg0 unzip
```

Press **Y**.

Allow the Ports through ufw(the firewall we installed)

```
sudo ufw allow 9000:9100/tcp
sudo ufw allow 9000:9100/udp
```

# Set up a user for OSGrid's OpenSim binary to run as:

```
sudo adduser --disabled-login osgrid
```

You can just leave all the prompts blank.


# Let's Switch to that user and get OpenSim For OSGrid:

```bash
sudo su osgrid
cd # Will take you to the osgrid user's home directory, Remember this
wget http://danbanner.onikenkon.com/osgrid/osgrid-opensim-10172020.v0.9.2.3049658.zip
aunpack osgrid-opensim-10172020.v0.9.2.3049658.zip
mv osgrid-opensim-10172020.v0.9.2.3049658.zip osgrid
```

Now We're gonna run it for the first time. It'll have you go through some prompts. The documentation for these prompts are [HERE]("https://wiki.osgrid.org/index.php/Tutorial01")

```
cd osgrid/bin/
mono OpenSim.exe
```
1. Name the Estate/Region
2. Accept UUID by pressing Enter
3. Pick Grid Coordinates
4. Leave Internal IP 0.0.0.0 by pressing Enter
5. We're not running inside docker just press Enter
6. Make sure you give it your publick IP Address for the machine or the domain name you directed at the Server
7. It'll ask you if you want to create an Estate propbably, say yes make yourself Estate owner

That should do it, but we want this thing running all the time. Once it's up, verify you can access it by teleporting to it in your Client,

If you can, good job, next we want to shut it down in the console type `shutdown` and it should go down.

# SystemD Service and Screen:

Now we're going to create a SystemD service.a

First press **CTRL+D** to exit the osgrid user session and get back to your main user.

By default Debian Comes with `nano` I hate `nano` but we'll use it anyway.

Run: 

```sudo nano /lib/systemd/system/opensim.service
```

Then paste this in pressing SHIFT+CTRL+V

```ini
[Unit]
Description=OpenSim Service
After=syslog.target network.target

[Service]
User=osgrid
LimitSTACK=1048576
WorkingDirectory=/home/osgrid/osgrid/bin
ExecStart=/usr/bin/screen -S OpenSimService -D -m mono OpenSim.exe -gui=true
ExecStop=/usr/bin/screen -d -r OpenSimService -X stuff "shutdown" ; /usr/bin/screen -d -r OpenSimService -X eval "stuff ^M"
KillMode=none

[Install]
WantedBy=multi-user.target
```

**PRESS CTRL+O TO SAVE THEN CTRL+X TO EXIT**

Now Let's enable and start the service

type: 
```
`sudo systemctl enable opensim.service
```

then type: 
```
sudo systemctl start opensim.service
``` 
It might have started running when you enabled it.

You can check the status of it with `sudo systemctl status opensim.service` Read the systemctl manual for more understanding.

That's it you should be good.

You can access the server console with screen like this:

```
sudo su osgrid -c 'screen -r OpenSimService'
```

You can quit the console without killing the server by pressing **CTRL+A** and then hitting **D** on the keyboard. 

You're done. If you need additional help message me.
