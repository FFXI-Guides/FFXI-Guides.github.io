---
title: Setting up atom0s D3D8 proxy on Linux/Steam Deck for FFXI
layout: post
nav_order: 12
---
###### Author: Arieh @ Bahamut

While I personally use Ashita (as shown in screenshots), this proxy also works fine with Windower.

Additionally, this guide was made using a Steam Deck, but you can follow similar steps on any Linux distro if you have installed FFXI via Lutris as well.

## Guide for installing

1. Download atom0s d3d8 proxy from here: [⁠Ashita⁠ RELEASE Proxy v1.1.0.0](https://discord.com/channels/264673946257850368/1127340838918291606/1127340838918291606), you will need to join the [Ashita Discord](https://discord.gg/ashita) in order to download this.

2. Open up dolphin / file explorer of your choice and navigate to your downloads folder, extract these 2 zip files into separate folders,

3. Go to the FFXI prefix folder, which can be done by this can be done by right clicking the ffxi setup you use in lutris and selecting "Browse files". Navigate to PlayOnlineViewer folder, within the window that opens.

    a. (The path from my Steam Deck is below, the path you would need to look in will likely look a bit different but all that matters is that the playonlineviewer folder looks correct)

        /home/deck/Games/final-fantasy-xi-online/drive_c/Program Files (x86)/PlayOnline/SquareEnix/PlayOnlineViewer/

4. From the folder which you have extracted that contains the atom0s proxy, copy the d3d8.dll and d3d8.ini into the same folder, your playonline viewer folder should contain the files like the image below.

![A view of the PlayOnlineViewer folder with the following files selected: D3D8.dll, d3d8.ini, D3DImm.dll and DDraw.dll](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-1.png)

5. Open lutris and click once on the FFXI game you are using to play FFXI (whether this is FINAL FANTASY XI Online or Windower or Ashita does not matter in this case). Then click on the the arrow next to the wine bottle and click the option labelled `Wine configuration`.

![Lutris window open with Ashita program selected and the configuration menu next to the wine bottle open.](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-2.png)

6. Once the `Wine configuration` window opens, click on the tab named Libraries and then write the following line into the dropdown below `New override for library`: `*d3d8`. The `*` must be included. Then click Add which is next to the dropdown/input field.

![A screenshot of the Wine configuration window with the Libraries tab selected. There is a description of what the DLL overrides list does and inside the dropdown box below "New override for library:" *d3d8 is written into the dropdown menu.](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-3.png)

7. After the override has been added into the list; scroll through the list to find `*d3d8` and click on it to select it. This will either be at the bottom of the list or at the top of the list. After you have selected `*d3d8` click on `Edit` to the right hand side of the list and change the setting to the following option: `Native (Windows)`.

![A screenshot of the Wine configuration window with the Libraries tab selected. Overlayed on top of this is a smaller window with the title Edit Override. There is a box inside with the title Load order and a set of 5 options where only one option can be selected between them: Builtin (Wine), Native (Windows), Builtin then Native, Native then Builtin and Disable. Native (Windows) is the selected option.](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-4.png)

    * Extra note: if this doesn't work, try it with native then builtin as a fallback

8. Click `Ok` in the `Edit Override` window, then click Apply in the main `Wine configuration` window and then click `Ok` again to close the window.

9. Open up the main settings window again for FFXI in Lutris and then click on the `Runner options` tab. Disable `dgvoodoo2` in the options if it exists. Only DXVK/D8VK should be enabled, the version does not matter. For newer wine versions this may not exist at all, so you can skip this step without problem.

    - Additionally you can disable all other switches in the 2nd image as well, since they are unused by FFXI regardless.

![Lutris runner options settings window for the wine version wine-proton-9.0-3-amd64. There is a group of options called graphics and some checkboxes. The only enabled checkbox is for DXVK. The DXVK version here is dxvk-2.5.1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-5.png)

![Lutris runner options settings window for the wine version wine-proton-9.0-3-amd64. There are multiple checkboxes for options which are all disabled.](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-6.png)

10. Once this is all done, you can open FFXI again to see if it runs without stuttering/hitching. I use city areas (Jeuno/Western Adoulin work great for this). If this does not work, try it without windower/ashita and see if it works when running the game in vanilla. Try both of these options in desktop mode first before trying to run in game mode (if you're playing using SteamOS/Steam Deck or Big Picture Mode).

    - Lots of testing will be required in this case, but it's important to rule out possible variables when seeing what causes issues for FFXI in this case.

    - If the framerate is consistently low this is different from hitching/stuttering, where the game will run fine and then consistently stop for 0.25-0.5s every few seconds.

