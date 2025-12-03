---
title: How to setup Remapster for Windower
layout: post
nav_order: 12
---
Setting up Remapster for Windower
========================================
###### Author: Daleterrence @ Bahamut

[Remapster](https://remapster.com/) is a project to greatly improve the quality and readability of FFXI's in-game maps, whilst preserving the feel of those maps. This guide will teach you how to install and use the project, for Windower. This particular version uses the 1024 x 1024 maps, but there are 2048 x 2048 [files available](https://remapster.com/downloads/) if you would prefer an even higher resolution. (the HQ versions may introduce lag to opening and closing maps)

As the modded map files are bigger than the game normally handles, you will need to also patch your game to use more RAM than usual to prevent any "black screen" crashes.

## Setup Guide

1. Download the .zip file at the from this [link](https://cdn.discordapp.com/attachments/1355156642299383969/1355156646476906727/Remapster_Mod_with_XIPivot__4_GB_Patcher.zip?ex=68cf46ba&is=68cdf53a&hm=bba03449831270342dbc0362275c719c2db8455153c57a3f27c8d1020f499dc4&).
2. Extract the entire contents of the .zip file somewhere safe.
3. SHUT FFXI DOWN COMPLETELY, THIS INCLUDES PLAYONLINE.
4. Go into the "4 GB RAM Mod" folder and right click on the .exe, and click run as Administrator.
5. Once the program opens, point it at your pol.exe file, this is typically found at C:\Program Files (x86)\PlayOnline\SquareEnix\PlayOnlineViewer.
    - The directory may differ depending on how you installed the game. Feel free to ask me if you cannot find your pol.exe.
6. Click Patch, and the mod should be applied successfully. You will need to do this again after each FFXI version update, so keep hold of the patcher .exe. Close the patcher program.
7. Copy the entire XIPivot folder as it is to your Windower\addons\ directory, this is by default at C:\Program Files (x86)\Windower\.
    -  This has already been setup to use the Remapster mod correctly.
8. Open init.txt in the Windower\scripts folder, and add the line lua load XIPivot and save the file.
9. Reopen your game to ensure the patch has worked by opening your map.

Done! Any issues, please drop me a message on Discord or drop me a /tell in-game. Remapster have also posted [a guide](https://remapster.com/2022/7/26/map-pack-2/) of their own which includes all zones they have made maps for, if you would prefer to follow that.