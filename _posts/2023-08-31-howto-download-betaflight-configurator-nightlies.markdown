---
title: "HOWTO: Download Betaflight Configurator Nightlies"
permalink: "/howto-download-betaflight-configurator-nightlies/"
---
Getting errors in Betaflight Configurator? Confused as to what Configurator even is?

## What is Betaflight Configurator?

Say you wandered into the Betaflight world browsing the [official GitHub repo](https://github.com/betaflight/betaflight). You head to the [releases page](https://github.com/betaflight/betaflight/releases), look at the Assets and see a bunch of hex files.

![assets](/assets/images/Screenshot%202023-08-31%20102654.png)
*Betaflight Assets*

You blindly download the files, but what the heck do you do with them? Well, nothing really. This is the first frustrating barrier to entry into the Betaflight world. What you actually need is Betaflight *Configurator*.

So, where is it?

In a [separate repo](https://github.com/betaflight/betaflight-configurator). Yeah, I know--confusing. It's not immediately apparent depending on what page you land on in your quest to put Betaflight on your new FC. In fact, due to the design of Configurator most end users would never need to manually download the actual firmware hex files (especially with the new cloud build system) as it is all integrated into the Firmware Flasher tab.

There are some reasons you would actually need a hex file, but that is beyond the scope of this article.

## What version is good?

As of the writing of this article, the current *Release* version of configurator is [10.9.0](https://github.com/betaflight/betaflight-configurator/releases/tag/10.9.0)

10.9.0 is fine for all version of BF up to 4.3 (Edit: not true, there is a point where the firmware is too old for Configurator to talk to it through the API) and probably works with most versions of 4.4 (releases or otherwise). However, I see an increasing number of problems with end users that could probably benefit from downloading [Configurator Nightlies](https://github.com/betaflight/betaflight-configurator-nightlies) especially if playing around with special builds of 4.4 or newer (4.5 zulu, etc).

Configurator Nightlies are light years ahead ([161+ commits](https://github.com/betaflight/betaflight-configurator/compare/10.9-maintenance...master)) of the old 10.9.0 release.

![commits](</assets/images/Screenshot 2023-08-31 105708.png>)
*Nightlies Commits compared to 10.9.0 release*

You should be aware that these are bleeding edge versions and should not be considered stable software. If you are afraid of bugs or are in a production environment like a film set or whatever you might not want to use these builds. On the flip side, these nightlies sometimes fix bugs from stable versions and all bleeding edge versions of betaflight related software I have used usually work properly.

## Run Release & Nightlies side by side

You can run the scary new versions of Configurator without blowing out your old 10.9.0 version that still works.

Download the "portable" version as shown in the screenshot below:

![10.10.0 assets](</assets/images/Screenshot 2023-08-31 105951.png>)
*10.10.0 assets*

The portable version is just an archive of the whole program without an installer included. This lets you extract it wherever you want so it doesn't mess with the official install you have going on in the official directory.

What I have done is created a new directory next to the default directory the installer uses: `C:\Program Files\Betaflight\Betaflight Configurator 10.10.0` and then extracted `betaflight-configurator_10.10.0-debug-172cb0b_win64-portable.zip` into it. I then created a shortcut on my desktop linking to that instance and placed it next to the default shortcut.

![directory structure](</assets/images/Screenshot 2023-08-31 111109.png>)
*Directory Structure*

This is all for Windows of course. Do whatever you have to do for Linux. macOS or Android users: good luck, lol. I'm assuming you can only have one version installed on Android unless you are using some type of side-loading solution.

## Why Nightlies?

For some reason the BF devs haven't pushed a new official release in a while (since January). Resources are thin and they seem to focus on the main branch of the firmware itself, leaving configurator (and blackbox explorer) to get little attention. As the firmware revisions press on you can be left in the dust on the Configurator side.

Putting it in a separate repo seems to be standard procedure for many projects, but personally seems a bit pointless to me especially with the GitHub release tagging system. This leads to further confusion, depending on where you land with your search results, as to whether or not you realize nightlies are even a thing at all. Sometimes the link to it and the explanation why you would need it is buried down in the documentation.

## Notes

I have personally tested [v20230827.520 aka c82116d](https://github.com/betaflight/betaflight-configurator-nightlies/releases/tag/v20230827.520) and it seems to work well for me. I'm connecting to a FC with 4.4.0

This advice is generally good for Blackbox Explorer also! Many times I could not read my blackbox logs unless I went and downloaded [blackbox-log-viewer-nightlies](https://github.com/betaflight/blackbox-log-viewer-nightlies)
