---
title: Ashita Quickstart
layout: post
nav_order: 9
---
# Quick Ashita Guide

###### Author: Arieh @ Bahamut, suggestions added from Eierkuhle @ Bahamut

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

## What plugins exist?

Plugins are separately loaded to addons, as they are dll files stored in the `plugin` folder.

If there is not a link on the plugin name itself, it is already included in v4 repository that you downloaded in order to use Ashita.

* [Bellhop](https://github.com/ThornyFFXI/Bellhop/)
    * A tool to manage inventory using chat commands
    * Be extremely careful with this tool, as you can remove/sell all of your items with this if you are not careful.
* [FindAll](https://github.com/ThornyFFXI/FindAll/)
    * Helps you find things all of your inventories, both accessible from mog house and while you're in the field
* [Lootwhore](https://github.com/ThornyFFXI/Lootwhore)
    * Automate handling loot that comes into treasure menu.
* Minimap
    * Adds a minimap to your screen. Configs for this are stored in `config` folder.
* [Multisend](https://github.com/ThornyFFXI/Multisend)
    * A plugin for sending commands between characters when multiboxing.
* [Nameplate](https://github.com/Shirk/Nameplate)
    * Corrects the nameplate aspect ratio for XI so they look less stretched
* [Packer](https://github.com/ThornyFFXI/Packer)
    * Helps with rearranging validating that gear you have/need is in your inventory/wardrobe when you change jobs.
* [PacketFlow](https://github.com/ThornyFFXI/PacketFlow)
    * Adjusts the ratio at which the client and server exchange information leading to less dropped packets especially in instances. It also removes the packet delay upon zoning, allowing zone and inventory data to populate very quickly. Safe to use on retail.
* Screenshot
    * Takes a screenshot when you hit printscreen and saves it to `screenshots` folder in the Ashita directory.
* [Sequencer](https://github.com/ThornyFFXI/Sequencer)
    * Changes the sequence id on equipment change packets specifically in conjunction with Luashitacast/Ashitacast to prevent the server from having to process the same action twice in laggy situations. Used in conjunction with [Luashitacast](https://github.com/ThornyFFXI/LuAshitacast), safe to use on retail.
* [Shorthand](https://github.com/ThornyFFXI/Shorthand)
    * Shorthand lets you write shortcuts for casting spells/ja's/ws's and so on.
* [Uberwarp](https://github.com/ThornyFFXI/Uberwarp)
    * Use warp systems with the command line.

In `polplugins` folder, these 2 addons also exist which handle interactions in the PlayOnline Launcher itself.
* quicky
    * Boots up FFXI automatically after logging into PlayOnline. Will not let you use the PlayOnline interface after you login while this is active.
* sandbox
    * Used for sandboxing instances of Ashita, required when you are running multiple instances of FFXI.

## What addons exist?

Addons should be extracted to a folder which is stored within `addons` folder.

If there's no link for the addon, then it is already included in the main Ashita repo that you downloaded. Or I forgot to link it, so please tell me and I'll add the link in.

* ahcolors
    * Changes the auction house listing colors for better readability
* aspect
    * Fixes aspect ratio automatically based on screen resolution.
* [auctioneer](https://github.com/loonsies/Auctioneer/releases/latest)
    * An Auction House UI tool to make it easier to check AH prices etc. This has been checked by the devs and Thorny to make sure it is safe but read the disclaimer and use this one at your own risk.
* [autohide](https://github.com/Lumariano/misc-ashitav4/tree/main/addons/autohide)
    * Hides elements which are placed onto screen by Ashita during certain menus/states of the game.
* autologin
    * Automatically logs you into a specific character. Needs to be used as part of a startup script.
* [balloon](https://github.com/onimitch/ffxi-balloon-ashitav4)
    * Add FFXIV style cutscene dialog windows for NPC dialogue in quests
* blucheck / blumon / blusets
    * Makes managing spells/spell sets for blue mage much easier
* [cbind](https://github.com/ThornyFFXI/cBind)
    * Bind controller buttons to ingame commands. Does not support combo buttons like how can be done in the gamepad configuration tool currently.
* [chains](https://github.com/Sippius/Ashita-v4-addons/tree/main/chains)
    * Displays a text object containing skillchain elements resonating on current target, timer for skillchain window and a list of weapon skills that can skillchain based on the weapon you have currently equipped.
    * It's based on the skillchains addon by Ivaar for Ashita-v3.
    * An [updated version](https://github.com/Lumariano/Ashita-v4-addons/tree/main/chains) was created by Lumaro (Eierkeule @ Bahamut) which includes the Prime/Bonanza Weaponskills that are missing from the initial repository. It also fixes a packet duplication issue present.
* checker
    * Gives more information when you check information for a mob
* cleancs
    * Removes elements drawn by ashita from cutscenes
* [colure](https://github.com/mousseng/xitools/tree/master/addons/colure)
    * A way to quickly select/cast indi/geo spells with a mouse UI
    * included in the [xitools](https://github.com/mousseng/xitools/) repository
* drawdistance
    * Change the render draw distance with a text command
* [Emotes](https://github.com/tirem/Emotes/)
    * Places a button on screen which opens an Emote menu that can be navigated with your mouse (like in FF14).
* enternity
    * It will press enter automatically during npc dialog/cutscenes
* equipmon
    * Shows currently equipped items in a box you can move around the window, helpful when you are swapping gearsets for macros or using luashitacast
* [find](https://github.com/Sippius/Ashita-v4-addons/tree/main/find)
    * A port of the `find` addon from Ashita V3.
* filterscan
    * filter out enemies from widescan list to make it easier to track specific monsters.
* [Focuser](https://github.com/ThornyFFXI/Focuser)
    * Swap between different open FFXI windows using text commands. Requires configuration and an extra DLL included with the repo when setting up.
* fps
    * Configure the fps limit from here, and also show/hide the fps on screen
* gearfinder
    * Helps you find gear based on specific criteria, can also look in storage slips
* [HXUI](https://github.com/onimitch/HXUI/releases/tag/onimitch4)
    * Full UI replacement, [xitools](https://github.com/mousseng/xitools) is also ok but hasn't been updated in a while
* invmon
    * Show remaining slots for any inventories you specify in a positionable window
* instantah
    * See results from any auction house bids you make much quicker than default
* instantchat
    * Removes the delay from messages adding into chat window, so it makes it easier to parse
* ime
    * Lets you type in japanese without needing to use the Japanese client.
* itemwatch
    * This will let you track item counts ingame based on what is in your inventory
* links
    * Retrieves URLs from ingame chat window and creates a new window to enable user to open the links in a browser.
* [Luashitacast](https://github.com/ThornyFFXI/LuAshitacast)
    * It's the gearswap addon for Ashita, written in lua. Very customisable, click [here](https://thornyffxi.github.io/LuAshitacast/) for link to the documentation on how to write lua gearswap scripts
* macrofix
    * Removes the delay in showing macro bar window when pressing a macro bar key on your keyboard or controller.
* [metrics](https://github.com/RaraProjects/metrics)
    * Tracks metrics in combat, there's a lot here that can be tracked, but main things are DPS and Accuracy. Read the readme for more info, haven't used this one myself personally.
* [minimap-helper](https://github.com/mousseng/xitools/tree/master/addons/minimap-helper)
    * A different minimap configuration tool
    * it's included in the [xitools](https://github.com/mousseng/xitools/) repository
* [minimapcontrol](https://github.com/onimitch/ffxi-ashita-minimapcontrol)
    * Also a different minimap conifguration tool
* minimapmon
    * Configure settings for the minimap plugin.
* [mobdb](https://github.com/ThornyFFXI/mobdb)
    * Show information for currently targeted mob/npc/player. Includes a simple and advanced mode, so can be helpful for tracking down Placeholder NM's in lottery pop farming.
* [namecolors](https://discord.com/channels/264673946257850368/723259779971022979/1234972923580645550)
    * Allows you to change colors of nameplates for basically every type of PC/NPC in the game, helpful for accesibility purposes.
* [nocombat](https://github.com/ThornyFFXI/MiscAshita4/tree/main/addons/nocombat)
    * Disables combat music when engaged in combat, so you hear zone music instead.
* [nomount](https://github.com/ThornyFFXI/MiscAshita4/tree/main/addons/NoMount)
    * This is similar to the MountMuzzle addon available for Windower but for Ashita. It blocks default mount music when using a mount.
* [omen](https://github.com/mousseng/xitools/tree/master/addons/omen)
    * omen objective tracker
    * included in the [xitools](https://github.com/mousseng/xitools/) repository.
* [partybuffs](https://github.com/ThornyFFXI/MiscAshita4/tree/main/addons/partybuffs)
    * Show party buffs and distance to party member next to the main party window.
* [porter](https://github.com/ThornyFFXI/porter)
    * Makes managing items stored in porter moogles easier, almost entirely script based.
* [pupsets](https://github.com/Sippius/Ashita-v4-addons/tree/main/pupsets)
    * Manage pup attachments with slash commands.
* [relicge](https://github.com/mousseng/xitools/blob/master/addons/relicge/relicge.lua)
    * helps you track statistics for farming currencies for relic weapon
    * included in the [xitools](https://github.com/mousseng/xitools/) repository
* rolltracker
    * Let's you track corsair rolls
    * An [updated version](https://github.com/Lumariano/Ashita-v4-addons/tree/main/RollTracker) was created by Lumaro (Eierkeule @ Bahamut) which fixes some issues.
* [repeater](https://github.com/Sippius/Ashita-v4-addons/tree/main/RollTracker)
    * Lets you repeat commands multiple times (helpful for skill books)
* [skillchain](https://github.com/mousseng/xitools/tree/master/addons/skillchain)
    * Track skillchains with a UI
* [simplelog](https://github.com/Spike2D/SimpleLog)
    * Condenses the battle messages into something more readable. Filtering can be kind of a pain for other parties trusts. The latest commit has a fix for the duplicated messages bug which exists in the latest release.
* [Smart.LAC](https://github.com/ChristopherJTrent/Smart.LAC)
    * An extension for LuAshitacast allowing for declarative management of sets to make lac files easier to manage.
    * Warning: If you use this and have issues *do not send support requests into in the ashita discord*, make an issue on this github instead.
* [statustimers](https://github.com/HealsCodes/statustimers)
    * A very configurable replacement for status icons
* [tCrossBar](https://github.com/ThornyFFXI/tCrossBar)
    * Similar to [tHotBar](https://github.com/ThornyFFXI/tHotBar) but aimed at controller players and uses a crossbar interface similar to what controller players can use in FFXIV.
* [tHotBar](https://github.com/ThornyFFXI/tHotBar)
    * Displays a hotbar on screen  for binding and more importantly, visualising macros.
* [trials](https://github.com/mousseng/xitools/tree/master/addons/trials)
    * track weaponskill points for ws trials
    * included in the [xitools](https://github.com/mousseng/xitools/) repository
* tparty
    * shows tp next to party members, useful when you don't want to use a full UI
* [ttimers](https://github.com/ThornyFFXI/tTimers)
    * Track recast timers. This will not hide when addons like autohide are used, so I tend to enable it as/when I need it.
* [trustcheck](https://github.com/Lumariano/trustcheck)
    * Outputs a file with what trusts you have/don't have, handy for the 86 Trust RoE requirment
* [trustme](https://github.com/loonsies/trustme)
    * UI for summoning/managing trust sets. Let's you queue trust calls and will tell you what trusts you do/don't have.
* watchdog
    * Let's you track basically anything in widescan with text commands
* [wheel](https://github.com/mousseng/xitools/tree/master/addons/wheel)
    * A wheel for people who play ninja to show cooldowns for skills on it.
    * included in the [xitools](https://github.com/mousseng/xitools/) repository
* [XIPivot](https://github.com/HealsCodes/XIPivot)
    * A DAT file replacement mod, so you don't have to replace your actual XI files for HD mod packs / UI replacements etc
    * You should really use the [large aware address patch](https://github.com/ThornyFFXI/LargeAddressAware/releases/tag/1.00) if you intend to use this.
* [xitools](https://github.com/mousseng/xitools/)
    * Another UI replacement (like HXUI)
    * Personally I've had a few issues with this UI replacement personally so I swapped to HXUI, but I prefer the look of this one
    * This repository also includes a looot of other addons which may be useful that I've described above as well.
* [whereisdi](https://github.com/loonsies/whereisdi)
    * It is [https://whereisdi.com](https://whereisdi.com) in addon form, replicates functionality of the site ingame. For the truly lazy among us (or for those who cannot alt tab out of the game).

## What addons should you *not* run on Retail?

You could be banned permanently if you enable these on retail, so use them at your own risk.

Also I'm not going to link to these directly, since they are not necessary for playing on retail.

* ahgo
    * It let's you move around while having auction house window open
* casper
    * it's a noclip mod.
* chatfix
    * Private server specific fix for fixing an issue with chat.
* fastswap
    * fixes a bug with job change packets, but can also DDoS a server if used improperly
* gateway
    * Forces all doors to be always open
* nokb
    * Disables knockback effects to local player
* nomad
    * Enables mog house functionality in any zone
* peekaboo
    * Forces all entities the client obtains data for to be visible.
* Scenthound
    * Addon that can help with tracking monsters that spawn. 

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