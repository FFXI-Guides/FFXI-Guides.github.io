---
title: Final Fantasy XI on Linux Guide
layout: post
nav_order: 13
---

# How to set up Final Fantasy XI on Linux

Alternatively: Yet Another FFXI Linux Guide

###### Author: Arieh @ Bahamut

Setting up Final Fantasy XI on Linux can be frustrating for someone who is technical and far more so for a non-technical person, so here is a guide to help with that. If you find any of this daunting, I would recommend asking for help through the process. This game has a lot of issues on modern Windows PC's already, so it is completely ok to ask for help / check other guides if you have issues following this one, everyone's PC is different and that becomes exponentially more true when using a Linux system.

Will also shoutout the [Windower](https://discord.gg/aUrHCvk) / [Ashita](https://discord.gg/Ashita) Discord servers here for being helpeful places to ask when you run into technical issues on Linux. Please try to include all relevant information you can when you ask for help (what you tried to do, what happened including error messages/screenshots/logs).

And fromt his point onwards, I will be shortening Final Fantasy XI to FFXI in all cases.

## How do I install FFXI onto Linux?

### TL;DR (short guide)

Personally I recommend avoiding using Steam to install FFXI and instead installing via [Lutris](https://lutris.net/). Lutris has a bunch of scripts available for [installing Final Fantasy XI](https://lutris.net/games/final-fantasy-xi-online/) which you can use. If you are unsure of what version to install, I recommend using the `Full (US)` or `Full (EU)` option to install FFXI. When picking a Wine runner, Wine versions 9.15-9.21 and 10+ are good, and also any proton version 10.3 or newer. Some users have reported more success with the CachyOS builds of Proton but this is device/user dependent. Basically what works for you might not work for someone else. Additionally, some users reported memory leaks when using dgvoodoo2, so it can be worthwhile to set up atom0s' proxy (found in the Ashita discord). Ridge wrote a good guide for this (linked 2 sentences below) in their Ashita setup guide as well.

For Windower you can then install the `Windower 4 Live version` after this. There's a few extra steps and troubleshooting tips mentioned on the [Windower guide](https://docs.windower.net/linux/) as well if you run into any issues.

For Ashita, after installing FFXI, using [Ridge's guide](https://bin.68degrees.no/?678efeeb84b354e8#5ehU14BvFHo5MBwSMJ4RBwRPwhW9QaF83BJiXR7E3CzL) to Linux/Ashita is a recommended option. 

### Long guides

For these guides, I did these steps on a Dell XPS 15 9560 laptop running CachyOS with the following specs, however I have also set up FFXI on SteamOS on my Steam Deck OLED using similar steps.

```bash
CPU: Intel Core i7-7700HQ 
Integrated GPU: Intel HD Graphics 630
Discrete GPU: NVIDIA GeForce GTX 1050 Mobile
Memory: 16GB
Locale: en_GB.UTF-8
Kernel: Linux 6.16.5-2-cachyos
```

#### Installing FFXI via Lutris

For *all* commands which require you to download or install packages, please check what you are installing/downloading yourself. 

This guide also assumes you have not already installed Lutris and use your PC in English. If you have installed Lutris already, you can skip the first step. This guide is also a prerequisite for setting up a copy of FFXI that uses Windower/Ashita on your Linux PC if you are unsure of what to do in this case.

1. Install Lutris using the package manager for your distros. If you prefer using the GUI to install the packages, open that and use that to install Lutris. Otherwise here are some commands for popular distros/base distros if you wish to install from the terminal.
    * For debian-based distros: `sudo apt get update && sudo apt install lutris`
    * For arch-based distros: 
        * Using pacman: `sudo pacman -Sy lutris`
        * Using paru `paru -Sy lutris`
    * For fedora-based distros: `sudo dnf install lutris`
2. Open up Lutris and click on the `+` button in the top left hand corner.
3. A new window will open, click on the first option `Search the Lutris website for installers`.
4. Enter the search term `Final Fantasy XI Online` and click on the first option.
5. Once the next page loads with the options of what version to pick, pick `Full (US)` and click install.
6. It will now prompt you to pick an install location (use the default if you are unsure) and whether you want to create shortcuts elsewhere on your system for this. Click `Continue` to proceed to the next screen.
7. Lutris will now ask you whether you wish to provide files locally or whether it should download the files while doing the install process. Unless you're on a metered internet conneciton, I recommend downloading the files fresh so that it can install a fresh copy of FFXI. Currently this download is around 7.5GB.
8. Click `Install` to begin the installation process. This will take some time (like possibly 15 - 20 minutes), so just keep an eye on it for any errors that may occur during the installation process.
    * If errors do occur, check below in the Troubleshooting selection to see if your error was covered otherwise copy the error log to a text file and have it handy for if someone asks "what error happened?"
9. If no errors occurred and you see the following screen, then you now have a copy of FFXI installed onto your PC! 

#### Installing and configuring Windower in Lutris

1. Open up Lutris and click on the `+` button in the top left hand corner.
2. A new window will open, click on the first option `Search the Lutris website for installers`.
3. Enter the search term `Final Fantasy XI Online` and click on the first option.
4. Search for the option called `Windower 4 Live` in the list and click `Install` on that option.
5. It will now prompt you to pick an install location (use the default if you are unsure) and whether you want to create shortcuts elsewhere on your system for this. Click `Continue` to proceed to the next screen.
6. Lutris will now install `Windower 4` based on your already existing FFXI installation.
7. After that, you should see `Windower 4` in the main window on Lutris.

#### Installing and configuring Ashita v4 in Lutris

TODO: Soon

### Should I swap distro to make FFXI run better?
No. Unless FFXI is that important to you, I do not think it's worth doing that. 

## FAQ

### Should I use dgvoodoo2 from Lutris?
The dgvoodoo2 version in Lutris directly is not for games which use DirectX 8, only up to DirectX 7. While it can work in some cases, you will run into more issues instead of using a newer version of dgvoodoo2. Avoid versions after v2.8.2, they will not work. 

### Which wine/proton version should I use?
There are various versions you should not use without specific fixes due to a stuttering issue that exists in some versions of Wine. From experience / other members of the FFXI Community, these are the versions of Wine/Proton that are recommended for playing FFXI with.

* `proton-cachyos`
* Wine `9.15-9.21` or `10.x` 

## Troubleshooting

### Why does my Lutris install fail?

#### Sanity checks
* Make sure some form of `wine` is installed separately to Lutris. 
* Please set the default Wine version to the `System` Wine and not the wine version lutris installs automatically.
* Disable any VPN connections during the download step, or download the files separately. This is because GitHub will block connections over VPNs automatically. 

#### The downloaded files already exist.
You can either clear the files from the Lutris cache, or you can link to them directly when trying to install FFXI.

#### Error log shows "Accessing game config while runner wasn't given one."
* The default Lutris wine runner occasionally has issues with setting up this game depending on distribution because Lutris will install it's own version of Wine which may not have all the same permissions as Wine installed directly onto your system.
* You can change the default wine runner with the following steps:
    1. Open Lutris
    2. Open Preferences within Lutris
    3. Click on the Runners tab
    4. Scroll down to Wine and click on the left button on the right hand side
    5. In the tab `Runner options`, set the Wine version to `System (10.x)`

## I've installed FFXI but my game won't launch, what should I check?

TODO: add here

## Glossary

Will add basic explanations of terms used in the guide for those who are unaware of what the terminology means.

### Distro / Distribution
    * Distrubtion (often abbreviated as distro) is an operating system that includes the Linux kernel for its kernel functionality and is commonly used to refer to different versions of Linux that people may use. Popular ones include Debian, Ubuntu, Pop_OS!, Arch Linux and Fedora. Popular gaming-focused distros are Bazzite (based on Fedora), CachyOS (based on Arch Linux), SteamOS (based on Arch Linux) and Nobara (based on Fedora).

### Wine

WINE is an acronym for WINE Is Not (an) Emulator. It is a compatibility layer which lets Windows programs run on Linux.

### Proton

Valve's gaming-focused fork of Wine which is the backbone of Linux gaming as we know it today. There are a few different forks of Proton as well, but these are less used by the wider community except in specific cases. 

### Lutris

Lutris is a game manager which lets you manage installing & configuring games on your Linux system.
