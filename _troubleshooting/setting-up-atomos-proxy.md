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

    a. (my path looks like this, yours may look a bit different, all that matters is that the playonlineviewer folder looks correct)

        /home/deck/Games/final-fantasy-xi-online/drive_c/Program Files (x86)/PlayOnline/SquareEnix/PlayOnlineViewer/

4. From the folder which you have extracted that contains the atom0s proxy, copy the d3d8.dll and d3d8.ini into the same folder, your playonline viewer folder should contain the files like the image below.
![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-1.png)

5. Open lutris and click once on the ffxi launcher you are using, then open the arrow next to the wine bottle and click configuration.
![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-2.png)

6. after the wine configuration window opens, click on the Libraries  tab and then write the following line into the dropdown below New override for library : *d3d8 . The * must be included. Then click Add.
![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-3.png)

7. After this, scroll through the list to find *d3d8 and click on it. It will either be at the bottom of the list or at the top of the list. Then click on Edit to the right hand side of the list and change the setting to the following option: Native (Windows).
![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-4.png)

    * note: if this doesn't work, try it with native then builtin as a fallback

8. Then click Ok in the Edit Override Window, then Apply in the main Wine Configuration window and then ok again to close it.

9. Open up the settings again for the FFXI Lutris profile and in Runner settings tab disable dgvoodoo2 in the options.

    - Additionally you can disable all 5 switches in the 2nd image as well, since they are unused by ffxi anyhow

![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-5.png)

![image 1](/assets/images/troubleshooting/setting-up-atomos-proxy/atomos-6.png)

10. Then without windower/ashita try to open FFXI again and see if it runs without stuttering/hitching. I use city areas (Jeuno/Western Adoulin work great for this). If this works, try it with windower/ashita and see if it works also. Then lastly, try it in game mode to see if same result happens.,

    - Lots of testing will be required in this case, but it's important to rule out possible variables when seeing what causes issues for xi in this case.

    - If the framerate is consistently low, this is different from hitching/stuttering, where the game will run fine and then consistently stop for 0.25-0.5s every few seconds.

