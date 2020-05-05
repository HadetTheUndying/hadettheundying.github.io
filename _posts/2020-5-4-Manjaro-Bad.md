---
layout: post
title: Don't Install Manjaro
---

# Why Manjaro is bad:

Manjaro markets itself as a new user friendly distribution. It attempts to cater to the the same demographic of users as Mint(a conversation for another time.) and Ubuntu. The Manjaro maintainers are however very bad at doing this at anything deeper than a surface level. This makes the concept fundamentally fall apart.

## Things to consider(in no particular order):

This is a brief rundown of things over the past five years or so.

### It is not stable

+ The Manjaro developers hold packages behind a week from the upstream for *stability*. However there is little evidence of them ever intervening when there is an actual problem. This actually leads to more problems than it solves.

+ Manjaro has their own AUR helper. AUR Packages expect you to have an up-to-date Arch System. Since Manjaro holds packages for a week, this can and does lead to breakage from mismatched dependencies.

### Poor Maintenance Practices:

**Example;**
+ The totally **INSANE** way they went about reverting a SystemD vulnerability. Which caused a lot of the core system to break because they changed the version number instead of using an epoch. [Reference](https://old.reddit.com/r/linux/comments/ajclsq/manjaro_stable_requires_users_to_manually/)

+ Up until recently they had documentation that would lead to partial system updates, which Arch Based Distributions just cannot do reliably, and could cause all sorts of problems. The lead developer was receptive about changing this documentation, but it's mind boggling to me how they can be maintaining this project and not know how the system they forked works.

### Bad Security Practices

+ Manjaro's SSL Certificates have expired twice in the past. These things happen and that's okay. What was not okay was what they suggested doing to get around this temporary issue. [They recommended users change their system time.](https://web.archive.org/web/20150409095421/https://manjaro.github.io/expired_SSL_certificate/) Yes this was 5 years ago but if you browse their forums or blog posts these kind of horrible recommendations are still the norm.

+ Their updater executes commands with the `--no-confirm` flag by default. This is bad because it is essentially a "forced" command and will force updates even if their are errors, without notifying the user of any detected errors.[Reference](https://gitlab.manjaro.org/packages/core/manjaro-system/blob/master/manjaro-update-system.sh#L34)

+ They *accidentally* pushed a beta feature of `pamac`(their AUR Helper) which allowed for passwordless AUR package updates. I could write an entire book on why the AUR is unsafe. Why AUR helpers in general are bad. The potential damage that can be done to your machine is significant if you were to download a malicious AUR package update you system could easily be rooted. Their reaction from their community to people criticizing this was to call experienced Arch Linux Maintainers biased for pointing out why this was an incredibly bad idea. [Reddit](https://www.reddit.com/r/linux/comments/eks6iw/major_security_flaw_with_manjaro_pamac/) 

# Conclusion:

Every FOSS Project and Linux Distribution goes through growing pains and problems. My Distribution of choice, Void Linux, is now stranger to this. However, these situations with poor maintenance practices have been happening for 5 years and it seems they just can't get past them. I personally believe Arch is a barely functioning mess to begin withi, so basing a distribution for new users around it is only relevant because of the amount of software that's available in the AUR. You will learn a lot of very bad practices going forward if you decide to stick with Manjaro. 

If you are looking for a new user friendly distribution with a friendly installation process I really recommend picking an Ubuntu flavor, or using Fedora if you want newer packages.

Thanks for reading.
