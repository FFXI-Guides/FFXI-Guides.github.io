---
title: Ashita Quickstart
layout: post
nav_order: 9
---
# Quick Ashita Guide

###### Author: Arieh @ Bahamut

## What is Ashita?

Ashita, like Windower is an addon/plugin loader for Final Fantasy XI Online. The difference between using Ashita and Windower when not a plugin/addon developer is basically personal preference at this point. My personal reasoning is because some UI mods exist on Ashita which don't on Windower.

Ashita v4 currently has no GUI to help you get started with setting everything up/make configuration changes. If you don't want to mess with files/editing scripts, that is completely ok! Windower lets you change the settings with GUI and handles separate profiles in GUI as well.

## Where can I get Ashita?

You can download Ashita from [this link](https://docs.ashitaxi.com/installation/). They recommend keeping it up to date via [git](https://git-scm.com/) and I recommend the same if you are willing. Git install instructions are [here](https://docs.ashitaxi.com/installation/install_git/) and install instructions for installing via zip are [here](https://docs.ashitaxi.com/installation/install_zip/).

Don't worry if things break while you are setting up Ashita. That's normal and it'll take you a few hours to do basic setup and then like 10-15 minutes to keep it up to date afterwards.

Keep a backup when you do updates against the repo and everything will be ok. If you're reading this guide and need help, ping me and I will do my best to help you out.

Additionally this guide is not aimed at multiboxers, so I don't cover anything to do with that here, but this is covered in the main Ashita docs under the `sandbox` feature and people in the discord can help for this.

## Setting up boot configuration and ashita configuration.

Quickstart guide for setting up configurations:

1. Create a copy of both the boot script in `configs/boot` and the config script in `scripts`
2. In the boot script:
    1. Change the `script` variable below `ashita.boot` in the new boot script you create to the name of the new config file in the `scripts` folder
    2. Change the variables `0001` and `0002` to the resolution you want to have the window at (width and then height).
    3. Change the value for `0029` to `20` to allow for maximum sounds to be played at any one time.
    4. For UI scaling, change `0037` and `0038` in 5% increments to make UI larger or smaller. Numbers closer to the resolution you set in the above step will make UI smaller, numbers further away will make the UI larger.
3. In the config script:
    1. Load any plugins you want using `/load` command
    2. Load any addons you want using `/addon` command

Once you have set up your configurations, create a shortcut like shown in the guide [here](https://docs.ashitaxi.com/usage/running/) and then you will be able to launch FFXI with Ashita hooked in via this shortcut.

There's some explanations for the [configurations](https://docs.ashitaxi.com/usage/configurations/) overall on the ashita documentation website for and I highly recommend reading this page if you need more information.

### Boot script tips not mentioned in the documentation

* If you don't use a controller at all, change the setting `gamepad.disableenumeration` to `1` so that FFXI will not check for a controller at all. This can also be changed ingame by entering the `/ashita` command to open the config window.

* If you want to keep configure all the settings for gamepads with the ingame gamepad configuration, always set the following below settings to -1 in the boot script. That way it will not be overwritten when you launch via ashita again, as mentioned [here](https://docs.ashitaxi.com/usage/configurations/#section-ffxiregistry).
```
padmode000 = -1
padsin000 = -1
padguid000 = -1
```

* If you experience a lot more lag than you should, change the keys `0003` and `0004` to 1024/1024 or 2048/2048 from whatever number you chose before.

* Change key `0029` to `20` so that the maximum amount of sounds will play.

* If you put values into the boot file and you wonder why settings you set ingame or on FFXI tool are overwritten, make sure you check what you placed into the file first.

### Ashita configuration script quick info

* The configuration script is not located in the `config` folder! It is located in the `scripts` folder

* The following 2 plugins are *required* if you want to use addons on Ashita. Same config line also works ingame for loading plugins (the .dll files in `plugins`) in Ashita
```
/load thirdparty
/load addons
```

* Additionally you can load addons in with the following syntax both ingame and in the configuration script
```
/addon load addonname
```

## Troubleshooting
* My game crashes randomly / has a black screen when loading into a zone while using Ashita, why?
    * Apply the large address patch (you should do regardless of if you use windower/ashita/no launcher anyways)
        * Get the patch from [here](https://github.com/ThornyFFXI/LargeAddressAware/releases/tag/1.00)
   * Disable addons if you think they are causing you issues
   * If you're using XIPivot or any sort of DAT replacements, disable them to see if it is an issue with XIPivot instead.
* I copied my setup from one PC to another and I can't launch the game anymore!
    * Make sure you reinstall FFXI, it's reliant on being installed to the PC it's being launched from specifically. Or you can use the sandbox plugin.
    * Check your boot script if you pointed any configurations to a directory which doesn't exist anymore on the current PC you are using.

## Handy dandy links
* [Ashita v4 docs](https://docs.ashitaxi.com)
* [Luashitacast Readme](https://thornyffxi.github.io/LuAshitacast/)
* [Ashita Discord](https://discord.com/invite/ashita)

## Shoutouts / Thanks
* Daleterrance @ Bahamut for proof reading
* Eierkuhle @ Bahamut for the explanation of Sequencer/PacketFlow plugins + fix for the `chains` plugin.
* arkervorhat @ Bahamut for Smart.LAC