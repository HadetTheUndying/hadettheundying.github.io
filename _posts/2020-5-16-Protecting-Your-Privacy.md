---
layout: post
title: Protecting Your Privacy
---

If you live in The United States, I have some unsurprising news for you, [Senate just Voted that the FBI can seize your Browsing and Search History without a Warrant.](https://www.vice.com/en_us/article/jgxxvk/senate-votes-to-allow-fbi-to-look-at-your-web-browsing-history-without-a-warrant). [Here's another link so you know who's responsible.](https://gizmodo.com/heres-who-just-voted-to-let-the-f-b-i-seize-your-searc-1843445032). Normally I'd want to avoid conspiracy terms in this Tech Oriented Blog but this is another example of the American Police State, and Dystopian Cyberpunk Nightmare Society we seem to be on a fast track towards. 

# Privacy Practices

These things and steps you can take to better secure your privacy. I'll be discussing each one in a section below.

+ Don't use Windows
+ Encrypt your data(Even on Windows)
+ Hardware 2FA for PC Logins
+ Use TOR or a Quality VPN
+ Use a safe and trusted Web Browser
+ Zero Persistence Systems
+ **BE LOUD AND COMPLAIN!**


# Don't use Windows

It should go without saying that if you value your privacy and are serious about it that Windows 10 is entirely out of the question. Microsoft is generally 100% compliant with Law Enforcement. Windows 10 is closed source, and there are numerous examples of people using Man-in-the-Middle devices to monitor the amount of data that Windows 10 sends out when idle.

If Windows is Required for your work, I recommend at the very least setting it up as a Virtual Machine and doing your Web Browsing from a more secure system.

There are a lot of Privacy Oriented Open Source Operating Systems, and I recommend doing some research. I will talk about Zero Persistence further in this article.

That being said many regular use Linux Distributions are fine for taking an extra step in protecting your privacy, especially large ones where thousands of people are reviewing the code on a daily basis.


# Encrypted your Data

Even if you don't care about warrantless seizure of your data because you're a boot licking moron, you should still care about your data being stolen if your machine is physically compromised. If you have an Unencrypted Drive and you use the default password storage for Google Chrome or Firefox, your passwords are stored in **plaintext** in your application data folders.

### On Windows

1. Press the Windows Key.
2. Type "Bitlocker" in the search field.
3. Click "Click Turn On Bitlocker" for any Fixed Disks with Sensitive Data.

### On MacOS

[Follow this guide and pray.](https://support.apple.com/guide/disk-utility/encrypt-protect-a-storage-device-password-dskutl35612/mac)

### On Linux

[LVM]("https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)")+[LUKS](https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup) is your best bet and many popular distributions like Debian, Fedora and Ubuntu have options for this in their graphical installers. I will not write a step by step guide for doing this. I recommend an encrypted boot partition that requires a Hardware Two Factor Key like a Yubikey or Google Titan Key for work sensitive data.


# Hardware 2FA

I use Hardware Keys as an additional step for Login on my system. I have three Yubikeys for this. One that sits in my laptop permanently, one that's on my keychain, and one that is my backup key for both systems that sits in my safe.

What this means is that I cannot log in on my machines without one of these keys inserted. I need a password and the key to authorize a login. The key is also required to unlock my Encrypted drives on my Work Laptop.

This is important because if I wanted to block someone's access to the machine, I could physically destroy the main key for it. 

**ALWAYS BUY AT LEAST TWO KEYS IF YOU WANT TO DO THIS**


# Use Quality Premium VPN or TOR

I did a video on VPNs awhile back on YouTube. It's entirely irrelevant now given the subject matter of this blog post. The reason why I recommend a VPN is to help obfuscate your data by blending it with data from other users. This doesn't entirely stop digital fingerprinting but it's a good step in the right direction.

I really can only recommend two Premium VPN Services these days.
+ [Mullvad VPN](https://mullvad.net/en/)
        Mullvad is a Premium and Totally Anonymous VPN with a Zero Logging Policy that can be paid for entirely in CryptoCurrency.

+ [ProtonVPN](https://protonvpn.com/)
        ProtonVPN is the Sister Project to ProtonMail. Both are Privacy Oriented Projects. While I think Encrypted Email is totally pointless, I still use both because they are quality services. They have Open Sourced their projects now under GPLv3 and offer TOR Exit Nodes on their Paid Tier.

You can use TOR on almost any Operating System by just downloading and installing TOR Browser, it's based on Firefox, it bounces you through the TOR Network, It is good, and it is free. Many Linux Distributions include a base TOR package which can be executed manually to generate a secure TOR SOCKS connection if you're interested in using TOR for all of your internet traffic.


## Privacy Respecting Web Browsers

If you're not using TOR Browser, I highly recommend Firefox with some extensions like [AdNauseam](https://addons.mozilla.org/en-US/firefox/addon/adnauseam/) and one of the wonderful script blocking plugins out there. Be sure to change your default search engine to [Duck Duck Go](https://help.duckduckgo.com/duckduckgo-help-pages/desktop/firefox/) while you're at it.

Some other Browsers I can recommend if you're locked into your Chrome Extensions are [Vivaldi](https://vivaldi.com/) and [Brave](https://brave.com/). Both projects are run by Former Opera and Mozilla developers and both are fairly nice. Brave offers a rewards program which I've never used.

Your Web Browser is a big part of your digital finger print and these Browsers and Plugins make an effort to obscure that fingerprint whenever possible, as well as minimize tracking and play the role of watchdog between you and malicious sites.


## Zero Persistence Systems

If you really want to go to extremes you can combine all of the above mentioned things in a Zero Persistence System. I feel like this subject matter is probably deserving of its own blog post so I will briefly sum up the concept.

Zero Persistence Operating Systems are very common among activists and government intelligence organizations. The NSA has their own Linux Distribution for this. The basic idea is that you boot your system from a small disposable medium such as a Disc or USB Drive, the system either boots into your RAM or Directly off of the USB Drive and stores no data after you shut the system down, or boots the System Volume with "Read Only" permissions and you are expected to store any persistent data on an additional Storage Medium. Many Linux Distributions offer Live Images with Zero Persistence for example.

Some Linux Distributions that specialize in this are:
+ [Tails](https://tails.boum.org/)
        Tails is probably the most popular solution for this usecase. It is lightweight and can boot on almost any Personal Computer from the past 20 years or so.

+ [Kali Linux](https://www.kali.org/)
        Kali Linux is a Penetration Testing Tool Kit used by many industry professionals. You've likely seen it mentioned a lot by the Media as the Hacker Operating System and even seen its logo on television shows like Mr. Robot. Kali is inteded to be run with Zero Persistence and is a good alternative to Tails if you need more software available to you on boot. Anything packaged for Debian *should* also be available for Kali.

+ [Alpine Linux](https://alpinelinux.org/)
        Alpine Linux is a lightweight Privacy Focussed distribution with multiple install options, a wide range of Software and CPU Architecture Support. Alpine is somewhat of an outlier as it uses OpenRC for its init system, uses musl-libc, and BusyBox instead of GNU CoreUtils. I use Alpine every day for non privacy oriented tasks, it is a very well put together distribution.


## BE LOUD AND ANNOYING!

Finally, you need to be loud. You need to let your representatives know that this kind of unwarranted wiretapping and spying is **not okay** and never will be. This is the kind of **BULLSHIT** the FBI and NSA have been getting away with since the Civil Rights Movement under the guise of locating *Domestic Terrorists* and protecting America from *Communist Interests*.

Being Loud, spreading information about Data Privacy and steps the government is taking to eliminate encryption are the most important part of this entire process. A properly informed society is a very powerful society, Iceland is a great example of this. We need to start holding politicians accountable for the Bills they sign that violate our Civil Liberties and Personal Privacy.

I don't think that everyone needs to go to the lengths that I or other Privacy Advocates generally go through, but taking some steps if you're researching controversial or anti-government ideas or concepts are now an absolute requirement, and you need to be careful. **YOU DO NOT HAVE TO HAVE DONE SOMETHING WRONG TO GET IN TROUBLE! THE POLICE LIE ALL THE TIME, THEY GET PAID WHETHER THEY CATCH THE RIGHT PERSON OR THE WRONG PERSON! DO NOT EVER TRUST AUTHORITY! TRUST AND RESPECT ARE EARNED! OUR TRUST AND RESPECT IS USED AS A TOOL TO MAKE US FEEL GUILTY AND HAS BEEN REPEATEDLY VIOLATED SINCE SEPTEMBER 11TH, 2001!**

Thank you for reading as always and feel free to contact me if you have any questions or suggestions. As always you can catch me in my Discord or on Freenode in #cyberpunk or #voidlinux-ppc.
