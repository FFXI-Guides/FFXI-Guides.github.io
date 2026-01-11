---
title: Recommended Windower Plugins and Addons
layout: post
nav_order: 9
---
Windower Recommended Plugins & Addons
========================================
###### Author: Daleterrence @ Bahamut

<sub>Unsure on what Windower is or how to set it up? Click [here](/windower/windower-quickstart.html)!</sub>

This list is sorted into two categories, addons, and plugins. Addons are files wrote in Lua that anyone can make, if they know how. Any addons available in the Windower launcher will be kept up to date automatically, whereas any plugins available from other sources will need to be manually updated if they break. Plugins are the older form of addons, and are only available from the Windower launcher, they are kept up to date automatically.

This list is a "best-of", so to speak, anything that is significant and vital, has been marked with a ⭐.

## Plugins

<sub>All plugins are available on the Windower launcher, links go to their documentation, if they require it.</sub>

* [Config](https://docs.windower.net/plugins/config/) ⭐
    - Does many helpful things to your game such as auto-detecting and fixing your aspect ratio, altering your draw-distance beyond the game's default maximum, and most importantly, allowing you to play the game at 60 FPS. Requires some setup to get as you want it.
* [ChatMon](https://docs.windower.net/plugins/chatmon/)
    - Plays a sound when you are examined, or receive a tell. No documentation, is configured through its XML file after installation (just uses true/false statements to turn features on or off).
* [DelayMeNot](https://docs.windower.net/plugins/delaymenot/) ⭐
    - Removes the visual delay when opening a macro bar with CTRL or ALT when using the keyboard. Works out of the box and requires no configuration.
* [FFXIDB](https://docs.windower.net/plugins/ffxidb/) ⭐
    - Displays a zoomable mini-map you can position anywhere on your screen. Requires some fiddling with commands to get it where you want it.
* [SSOrganizer](https://docs.windower.net/plugins/ssorganizer/) 
    - Sorts your screenshots into character, and zone folders, very helpful for keeping track. Works out of the box.
* [Sandbox](https://docs.windower.net/plugins/sandbox/) 
    - Stops the game melting if you are running multiple copies of the game. Only needed if you are playing multiple accounts, or plan to. Works out of the box.
* [FishingCrashFix](https://docs.windower.net/plugins/fishingcrashfix/) 
    - Does what it says on the tin, only use if you experience crashes when fishing when using Windower. Works out of the box.

There are some hidden plugins available on the launcher, made visible by inputting the konami code whilst on the plugins tab. These are unsupported officially by the Windower team, so caution is advised. I have only provided explanations of all, since all are made visible. Please read descriptions of each carefully before installing and using. I will not be providing any support or answering any questions about these plugins apart from PacketFlow.

* JA0Wait 
    - Removes the animation lock from most combat actions (spells will still be interrupted if you move during casting), allowing free movement during the animation. Valuable for harder endgame content, not required at all. IS REPORTABLE AND CAN GET YOU IN TROUBLE AS OTHERS WILL SEE YOU SCOOTING AROUND WITH NO ANIMATION LOCK, DO NOT USE GENERALLY UNLESS AROUND PEOPLE YOU TRUST.
* Bidder 
    - Allows you to use the Auction House and Delivery system from anywhere within a zone that has an Auction House or delivery NPC, including attached Mog Houses. NOT RECOMMENDED TO USE, IS TECHNICALLY DETECTABLE BY SQUARE ENIX
* PacketFlow ⭐
    - The only reason I'm actually mentioning the hidden plugins at all. The game is strongly rate-limited with transmissions from and to the server, anything that exceeds that limit is dropped, so you will not be told about it by the server. In busier combat scenarios, this can be a significant issue and cause a lot of general lag. PacketFlow mitigates this somewhat, by allowing more data to be received from the server, leading to a better gameplay experience. A much better, slightly technical explanation is available here. This should be safe to use, it has been in-use by the wider community for years now with no bans or other account actions reported.

## Addons

### Updated automatically in the Windower launcher
* [autojoin](https://docs.windower.net/addons/autojoin/) 
    - Allows you to automatically accept party invites, with a whitelist feature so only specific party invites will be auto-accepted. Will not auto-join any party whilst there is loot in the treasure pool (as the pool is lost when joining a party).
* [AutoRA](https://docs.windower.net/addons/autora/) ⭐
    - Adds a toggleable text command and keyboard shortcut to make ranged attacks work automatically like auto-attack. Requires no configuration apart from knowing the commands and keyboard shortcuts.
* [barfiller](https://docs.windower.net/addons/barfiller/) ⭐
    - Gives you a graphical experience bar like FFXIV's so you can see your level progress easier.
* [battlemod](https://docs.windower.net/addons/battlemod/) ⭐
    - Completely changes how battle messages appear to make them more readable, less spammy, and provides custom filters. Works mostly out of the box but customisation is done by the settings files for it, which requires a small amount of technical understanding.
* [boxdestroyer](https://docs.windower.net/addons/boxdestroyer/) 
    - Helps you work out the correct combination for brown treasure caskets that appear from defeated enemies out in the world. Works out of the box.
* [ConsoleBG](https://docs.windower.net/addons/consolebg/) 
    - Displays a background on the Windower console, so you can read it easier. Works out of the box.
* Debuffed ⭐
    - Tracks debuffs on an enemy, making it easier to work out how long you have before they need to be refreshed.
* [DistancePlus](https://docs.windower.net/addons/distanceplus/) ⭐
    - Shows your distance to a target in the game's measurement unit, yalms, very important for fights with specific AoE ranges, learning melee attack range, casting range, all sorts. Absolutely vital. Works out of the box with some minor config.
* [enemybar](https://docs.windower.net/addons/enemybar/) ⭐
    - Provides a much more visible health bar for your current target, akin to FFXIV's. Works out of the box.
* [enternity](https://docs.windower.net/addons/enternity/) 
    - Automatically presses enter on dialogue when the game allows it, very useful for cutscenes you don't really care about, will make dialogue VERY fast.
* [equipviewer](https://docs.windower.net/addons/equipviewer/) ⭐
    - Shows your current equipment in a grid on screen, allowing you to very quickly see what you're currently wearing. Incredibly useful for ensuring macros and/or GearSwap is correctly changing your equipment when it should be. Requires a small amount of config to get in the right place on your screen.
* [FastCS](https://docs.windower.net/addons/fastcs/) 
    - Makes use of the config plugin to automatically disable the framerate cap during cutscenes, which vastly speeds the game up. If you do not care about FFXI's story, this addon alongside enternity is the closest you'll get to a cutscene skip in FFXI. Works out of the box, requires the config plugin to be installed to work.
* [findAll](https://docs.windower.net/addons/findall/) ⭐
    - Adds a text command to quickly and easily search all of your bags and your key items. Absolutely vital since the item search built into FFXI isn't great.
* [GearSwap](https://docs.windower.net/addons/gearswap/) ⭐
    - The big one. GearSwap allows you to make use of Lua files either written by yourself, or using a template someone has made to basically do absolutely anything in response to something happening in the game. Widely used by the community to change equipment easily and seamlessly, without making use of gear changing macros, which can be slow and sometimes not work at all. You will need coding knowledge to write your own Lua file, or you can use one of the many many templates available that you simply place your equipment into. Takes some work to setup, but is absolutely worth the effort. This addon is so significant it will probably get its own guide eventually.
* [giltracker](https://docs.windower.net/addons/giltracker/) 
    - Displays your gil the same way as FFXIV does. Works out of the box. settings are changed in its XML file.
* [instaLS](https://docs.windower.net/addons/instals/) ⭐
    - Lets you use your linkshell channels as soon as you change area, instead of having to wait for your bags to load. Works out of the box.
* invtracker 
    - Shows your inventory slots in a grid like FFXIV. Works out of the box, settings are changed in its XML file.
* [JobChange](https://docs.windower.net/addons/jobchange/) 
    - Lets you change jobs via a text command when in your Mog House, or near a Nomad Moogle. Also provides a "reset" command to quickly change jobs, and back to your original job to reset ability cooldowns. Works out of the box apart from having to know the text commands.
* [latentchecker](https://docs.windower.net/addons/latentchecker/) ⭐
    - Has the ability to check the exact number of WS points on a latent weapon (typically used for the quested weapon skills) and display it to you. Works out of the box apart from having to know the text command.
* MountMuzzle 
    - Disables the mount music so you can listen to the zone music, this is not required, but a personal choice. Requires a small amount of setup via text commands.
* MyHome ⭐
    - Automatically equips and/or uses an available warp item in your bags when you type //warp. Will cast the spell if you currently have access to it. That's it.
* [ohShi](https://docs.windower.net/addons/ohshi/) 
    - Shows a variety of important gameplay related procs, abilities, etc in a box on screen for easy tracking and visibility. More important in endgame. Works out of the box.
* Silence ⭐
    - Supresses all of the "equipment changed" spam, useful for later on when you're switching gear a lot. Works out of the box.
* [timestamp](https://docs.windower.net/addons/timestamp/) ⭐
    - Gives chat messages a customisable timestamp. Shows timestamp lines on more stuff than the in-game version and is much more configurable.
* [TParty](https://docs.windower.net/addons/tparty/) ⭐
    - Shows current TP for party and alliance members, and HP% for your target. The game has a built in feature for TP display but not HP% which can be very important, absolutely vital, works out of the box.
* Trusts 
    - Allows you to save your current summoned trusts as a set, and recall that set by a single text command, very very helpful. Works out of the box apart from learning the text commands.

### Requires manual updating from other sources
<sub>Please let me know if there are any addons you would add to this part of the list, along with their source. Thank you!</sub>

* [Superwarp](https://github.com/AkadenTK/superwarp) ⭐
    - Use basically anything that teleports you via text command instead of interacting with it, supports fuzzy completion so you could type //hp southsan 2 by a Home Point to immediately go to Southern San d'Oria, Homepoint #2. Incredibly helpful. A lot of commands to learn however.
* [PhantomGem](https://github.com/ffWiener/PhantomGem) 
    - Allows you to buy key-items for High-tier Battlefields via text command. Be warned this also allows you to buy key-items for battlefields you don't have access to. Use caution and your best judgment.
* [Skillchains](https://github.com/Ivaar/Skillchains) ⭐
    - Shows timing and options for skillchains after a weapon skill is used, absolutely vital for keeping track of skillchains.
* [XIPivot](https://github.com/HealsCodes/XIPivot) 
    - Allows you to load and use DAT modifications for FFXI without editing your game files. Required for some larger mods that the game can't natively load without exploding. Basically Penumbra from FFXIV, for FFXI. Requires some setup.
* [XICamera](https://github.com/Hokuten85/XICamera) 
    - Change the max distance of your camera, allows you to change what distance it is during battle and out of battle, and camera panning speed. Requires some setup to personal taste.
* [PartyBuffs](https://github.com/KenshiDRK/Addons/tree/master/PartyBuffs) ⭐
    - Displays active buffs on party members by the list in the bottom right. Works out of the box, but has lots of settings to configure it.
* [Whereisdi](https://github.com/aphung/whereisdi) 
    - Allows you to see where the current Domain Invasion boss is spawning, or about to spawn when typing //di, saves you trying to get into Unity chat if you're in a busy Unity. Relies on crowdsourced data from other users of the addon, so the more people that have it, the more accurate it is!
* [Balloon](https://github.com/StarlitGhost/Balloon) 
    - Displays NPC dialogue in a speech balloon in the middle of your screen, like FFXIV does. (Shared by @Palmira, thank you!)
* [Reraise](https://github.com/Daleterrence/Reraise)
    - Helps you keep up Reraise. This addon will use your best available Reraise spell or item based on a priority system.
* [MuffinCounter](https://github.com/Daleterrence/MuffinCounter)
    - Tracks gallimaufry (also known in the community as muffins) collected during your Sortie runs.
* [SpamBlock](https://github.com/Daleterrence/SpamBlock) ⭐
    - Spam filter which makes yell chat usable.