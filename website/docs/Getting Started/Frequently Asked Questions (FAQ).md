---
slug: /faq
sidebar_position: 3
---

![FAQ](https://user-images.githubusercontent.com/98862735/178853267-a5d384f8-ad62-4ffa-a8e7-45abf38e742d.png)


## <sup><img align="left" src="https://user-images.githubusercontent.com/44569252/189906668-cf6a57d5-075a-4894-8af0-906282bd8ae2.png" width="54" /></sup>Organizing games


### How can I <u>add box art</u> or screenshot images for my games?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

<sup>(Credit: Julian)</sup>

The file format is PNG with a max size of 250×360. The images need to be placed into the `Roms/<gamesystem>/Imgs` folder. 

The `Imgs` folder name is case sensitive (must have a capital `I`). Examples would be like the following:    
`Roms/FC/Imgs`  
`Roms/SFC/Imgs`  
`Roms/GB/Imgs`  

You can scrape your box art or screenshots automatically by following the below process:

- Use https://www.skraper.net/   
- Log in and select "Recalbox"   
- Check "Include non-Recalbox rom folders"   
   > (Some systems aren't recognized because their folder-names are non-standard. To add those systems, press the `+` symbol on the bottom left, select the systems that are missing & hit "OK". Then click the added systems in the bar on the left, and correct the system's folders in the "Games/Roms folder" bar or by clicking the file-icon to the right of it.
[You can find a list of all Rom folder names here](https://github.com/OnionUI/Onion/wiki/2.-Emulators-and-Ports)   
- Go to the "media" tab -> Enable & set "Resize width to" to 250 and enable "Keep Image Ratio"    
- Select the image type you don't want in the "Fetched Media List" and press the "minus" button, so there's only one picture.   
   > You can change how the image mix looks with the two buttons under "Media type",  I recommend changing "4 IMAGES MIX" to "Screenscraper's Recalbox Mix V2", but use whatever you prefer.
   > If you choose a picture that's taller than it's wide, like the boxart, set "Resize height to" to 360 and disable "Keep Image Ratio"
- Change "Output folder" to `%ROMROOTFOLDER%\Imgs`, with a capital `I`.
- Under 'Gamelist Link' ensure that "Link from node '&lt;thumbnail&gt;'" is ticked as well as 'Optimize media storage' (these are important if you wish to use the generated gamelist.xml to create a miyoogamelist.xml for use in Onion (more info on this below on this page).    
- Now click the system you want to scrape for on the left side, or "all system", and press the play button in the bottom right corner.    

This will automatically scrape images to the correct folders for Miyoo Mini. 

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How can I use a `miyoogamelist.xml` to <u>customise game names</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

Onion uses a 'miyoogamelist.xml' (in the same format as the more common 'gamelist.xml').
To create a miyoogamelist, review [the guide here](https://github.com/OnionUI/Onion/files/9050638/miyoogamelist.20220607.pdf).

> Troubleshooting: 
> After adding the miyoogamelist.xml to your rom folder you will need to `Refresh all roms` from the Games tab (press <kbd>SELECT</kbd> to open the context menu). 
> If the list is still not being loaded, ensure that the `extlist` in the `Emu/<systemname>/config.json` is populated with all appropriate rom extensions for your games (i.e. `"extlist":"zip|ZIP"`)

> Important: 
> The guide includes a "cleanup" script for use with [xmlstarlet](http://xmlstar.sourceforge.net/) but an issue with viewing PDF files in a browser means the script does not copy well. Either open the PDF in a reader application (i.e. Adobe Acrobat) or use [this batch file](https://github.com/OnionUI/Onion/files/9050636/gamelist.xml-to-miyoogamelist.xml-Clean-Up-Script.zip) to run the script

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### I have added new roms to my SD card, why are the <u>games not showing up</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

Any time you add more roms you will need to refresh your roms. From the `Games` tab, highlight the system and press the <kbd>SELECT</kbd> button to evoke the 'Refresh All Roms' option and press <kbd>A</kbd>. If your newly added games are still not appearing, ensure that you have placed your roms in the [correct rom folders](https://github.com/OnionUI/Onion/wiki/Emulators#rom-folders---quick-reference). Rom folders for each system must be named in capitals and they will differ from those on the stock Miyoo Mini SD Card. 

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I add game <u>cheats</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

<sup>(Credit: Erazemk)</sup>

This guide will teach you how to add cheats for your RetroArch emulators.

Your first task is to find cheat files for your games (usually provided in `.cht` format). You can find them fairly easily online, but the recommended source is [LibRetro database](https://github.com/libretro/libretro-database), which has up-to-date cheats for most LibRetro supported emulators.

1. Download the [whole repository as a ZIP file](https://github.com/libretro/libretro-database/archive/refs/heads/master.zip) (Code -> Download ZIP),
2. Extract it and go into the `cht` directory (you will see cheats sorted by console),
3. Copy directories for consoles you want to your Miyoo Mini's SD card, into the `RetroArch/.retroarch/cheats` directory (you might have to enable showing hidden directories if you can't see the `.retroarch` directory),
4. Inside the `.retroarch` directory there will be a `retroarch.cfg` file, which you need to open in a text editor. Find the line with the option `quick_menu_show_cheats` and set it to `"true"` (so the whole line should be `quick_menu_show_cheats = "true"`),
5. Eject your SD card from your computer and plug it into the Miyoo Mini, then open up your favourite game (for which you have downloaded cheats),
6. Enter the RetroArch menu (press `Menu`, hold it, then press `Select`) and find the `Cheats -> Load Cheat File (Replace)` option. There you can find the cheat file in one of the directories. After choosing it you will be returned back to the cheats menu, but now you should see a number of cheats at the bottom (e.g. `Cheat #0`),
7. Select one of them, then toggle the `Enabled` switch to enable it.

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### What is the optimal way to <u>organize multi-disk games</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

<sup>(Credit: Dwmccoy)</sup>

My solution for multi-disc games was to store the Roms in a different folder. 

**Example:** Driver 2

Copy the bin/cue files for the multi-disc game *Driver 2* into the following folder of `Roms/PSX/Driver 2`

I had two disc files to copy into the `Roms/PSX/Driver 2` folder `Driver 2 (Disc 1) (v1.1)` and `Driver 2 (Disc 2) (v1.1)`
I then created an m3u file named `Driver 2 (v1.1).m3u` with the following content and placed it into the /Roms/PS folder

`../../Roms/PSX/Driver 2/Driver 2 (Disc 1) (v1.1).cue`  
`../../Roms/PSX/Driver 2/Driver 2 (Disc 2) (v1.1).cue`

Launch the PlayStation Emulator and the only file you should see for the "Driver 2" game is the m3u file since the disc(s) for the game reside in a different folder.

You can store the files in whatever folder you want as long as the path to the cue file is correct. I created the folder PSX to store the multi-disc images in for simplicity. It's a bit of a hassle but it does work.

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How can I <u>rename consoles</u> or systems?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

The name of each console or system is defined in `Emu/[systemname]/config.json` 
You can edit this file with a text editor on your PC and apply a new name by updating the 'label' field.

To easily make bulk changes to your console or system names you can use the excellent python scripts below by Andrea922.
Visit the [onionos-console-renamer github](https://github.com/Andrea922/onionos-console-renamer) to download and follow the instructions detailed there.  

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>



## <sup><img align="left" src="https://user-images.githubusercontent.com/44569252/189905823-71a7f1bf-9eea-410f-b5e8-5b62d4dbc4fd.png" width="54" /></sup>Troubleshooting


### I just installed Onion, why do some <u>games no longer launch</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

There can be a few reasons why you may find a specific system does not launch games after installing Onion:  
* If you have added games post installation, you may need to update your rom caches, from the `Games` tab press the <kbd>SELECT</kbd> button to open the context menu and choose the `Refresh all roms` option.
* Ensure you are using supported rom extensions and that both your rom folder and Bios file(s) are named exactly as detailed in our [Emulators Section](https://github.com/OnionUI/Onion/wiki/Emulators).  
* Save states can, on occasion, be incompatible between core versions/updates. Delete the `Saves/CurrentProfile/states/[system]` folder for the given system.
* If none of the above points have resolved your issue, it is recommended to source and test with alternative roms (those that come with the Mini are of very poor quality). 

> Notes:  
> Rom folder and Bios filenames are case sensitive.  
> It is strongly recommended not to use the Miyoo provided SD Card or USB Card Reader as both are very prone to data corruption and failure and will cause issues.  

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### I have upgraded to a newer version of Onion and some <u>games are running slower or too fast</u>? 

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

If you experience slower (or faster) gameplay than usual for some games following an Onion upgrade, we recommend that you create an in-game Save and then delete your Save States. Save States are stored inside `Saves/CurrentProfile/states/[CORENAME]/`

> Please see other solutions here within this FAQ with regards to managing Save States and Saves.

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### I am stuck in a <u>black screen boot-loop</u>, how can I get back into Onion?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

If you launched a rom or a file that is incompatible with the core, it can cause a black screen. Onion's auto-resume feature can mean you returning to this same black screen on each boot. 

You can hold down <kbd>POWER</kbd> for 10+ seconds to break out of this behaviour and return you to MainUI

If this still does not work for you, you can disable the next auto-resume by inserting your SD card into your PC and deleting the file `cmd_to_run.sh` inside the `.tmp_update` folder

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### Why is my <u>battery percentage fluctuating</u> and how do I know if the device is fully charged?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

**Charging Indicators**  
The left most LED on the top of the Mini will turn blue when a full charge is reached.  

![LED Indicators-500](https://user-images.githubusercontent.com/98862735/189775988-b6b4062d-f231-4351-9a79-6920498f1554.png)

**Battery Percentage Fluctuations**  
The Mini has no Battery Management System so Onion calculates the remaining battery percentage based on the voltage.  
Environment changes and power draw will affect the determined percentage which can fluctuate greatly.  
> This may appear jarring but is perfectly normal. If you go from playing a resource hungry system (PS1), to playing something less intensive (GB) then you will likely see an increase in percentage. 
> Depending on the health (and thus voltage output) of your battery, it may not reach 100% in Onion when fully charged.   
>  
> The Onion battery capacity estimation is constantly pooling in the background for more precise results over time. This is the best method that is possible on this device, improved over stock and the same method used by the RA build and in MiniUI. 

**Reducing Battery Usage**  
The display in the Mini is old technology and draws a lot of power. Lowering display brightness will increase battery life.   
The below testing output demonstrates GBA running at 50% display brightness for almost 8hrs of play time.  

![battery-600](https://user-images.githubusercontent.com/98862735/189774379-33b77793-bc36-4563-acbe-357713b4964e.png)

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### I just downloaded an app or a standalone emulator and <u>the sound seems broken</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

It is likely due to a lack of compatibility with the Miyoo audio server.
To cope with this, just rename the `launch.sh` file in your app folder to `launch2.sh`, then extract this file to the app folder: 
[launch.zip](https://github.com/OnionUI/Onion/files/9041212/launch.zip)

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>



## <sup><img align="left" src="https://user-images.githubusercontent.com/44569252/189906120-248301c7-373e-482c-9c67-11f0faab9f39.png" width="54" /></sup>Saves


### How do I <u>add game saves</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

You can copy game save files from another device or emulator for use in OnionOS. 
* In most cases, Save files should be in `.srm` format, named identically to the rom and are case sensitive. Note that `.sav` files can be renamed to `.srm`, other formats may require a conversion tool. 
* To add your saves to OnionOS just copy your individual save files into the correct emulator folder in: `Saves/CurrentProfile/saves/[CORENAME]`
* If you have already launched the game prior to adding your saves then you will also need to go to the `Saves/CurrentProfile/states/[CORENAME]` folder ...and delete any Save States here for the same game(s) in order for your newly added game saves to be recognised.

> `[CORENAME]` = the folder with name of the core for the particular emulator or system 'core', the save file(s) relates to   
> If copying saves from your Miyoo stock SD Card, you will find them in `RetroArch/.retroarch/saves/[CORENAME]`

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>delete save states</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

Save States are stored inside `Saves/CurrentProfile/states/[CORENAME]/`

> Notes:
> `[CORENAME]` = the folder with name of the core for the particular emulator or system 'core', the save state file(s) relates to

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>disable auto-load</u> save states?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

- Launch the game and press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch menu.  
- Press <kbd>B</kbd> to go back one level.  
- Go to `Setting` › `Saving` › `Load State Automatically` (and turn it off).  
- Press <kbd>B</kbd> twice to go back to the main menu.  
- Then go to `Quick Menu` › `Overrides` and select one of the following:  
      - `Save Game Overrides` - for just this game.  
      - `Save Core Overrides` - for everything the core plays.  
      - `Save Content Overrides` - for everything in the same Rom folder.  

> Notes:  
> `Content Overrides` are recommended over `Core Overrides` since some cores serve multiple systems. 
> For more information regarding RetroArch overrides please review the [libretro documentation here](https://docs.libretro.com/guides/overrides/).

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### Why does my <u>state slot number</u> get so high? Does it take up a lot of space on my SD?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

Onion enables a feature that retains your old Save States.  
  
In case of manipulation error, file corruption, or simply because you want to return to an earlier section of the game, it is possible to go back in time to select an earlier Save State. This takes up very little space on your SD as even if your Save State slot number is high, RetroArch will only retain the last 10 files.  

To manage your current Save State slot:  

- Launch the game and press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch menu. 
- Go to `Save States` > `State Slot` and change the slot number with <kbd>Dpad Left</kbd> or <kbd>Dpad Right</kbd>  
  (Tip: Pressing <kbd>Y</kbd> here will show a full screen image capture for the Save State) 
- You can alternatively manage the slot number 'in-game' by pressing <kbd>MENU</kbd>+<kbd>Dpad Left</kbd> or <kbd>MENU</kbd>+<kbd>Dpad Right</kbd> and then pressing either:  
   - <kbd>MENU</kbd>+<kbd>L2</kbd> to load from the slot you selected  
   - <kbd>MENU</kbd>+<kbd>R2</kbd> to save to (and overwrite) the slot you selected  

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>



## <sup><img align="left" src="https://user-images.githubusercontent.com/44569252/189906362-b76f72fe-b6a9-4843-bc8a-9d024fb235f4.png" width="54" /></sup>Emulator settings


### How can I change a game's <u>scaling or make it fullscreen</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

- Launch the game and press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch menu.  
- Press <kbd>B</kbd> to go back one level in the RA menu and select `Settings` › `Video` › `Scaling`   
- Here you can toggle:  
      - `Integer Scale` - show the game in its original resolution (scale only in whole pixels).  
      - `Keep Aspect Ratio` - **enabled:** fit to screen, **disabled:** stretch.  

> Notes:  
> You will need to save overrides to commit this change, see 'How do I save RetroArch settings?' below for instructions.

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>save RetroArch settings</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

When you make changes in RetroArch you must apply these using "Overrides" for them to take effect. 

- Launch the game and press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch menu. 
- Make your desired changes.
- Then go to `Quick Menu` › `Overrides` and select one of the following:  
      - `Save Game Overrides` - for just this game.  
      - `Save Core Overrides` - for everything the core plays.  
      - `Save Content Overrides` - for everything in the same Rom folder.  

> Notes:  
> `Content Overrides` are recommended over `Core Overrides` since some cores serve multiple systems. 
> For more information regarding RetroArch overrides please review the [libretro documentation here](https://docs.libretro.com/guides/overrides/).

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>reset RetroArch settings</u> to the Onion defaults?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

Resetting your global configuration from within RA itself will break Onion functionality as this restores 'out of the box' RA defaults. Instead:
 
- Go to your Apps section and open `Tweaks`. 
- Scroll to `Advanced`  and choose `Reset Settings...` › `Reset RetroArch main configuration`

> Notes:  
> You should always in the first instance, save your changes to Retroarch settings as "Overrides" rather than saving changes to the main (global) configuration (see other questions in this FAQ re saving RetroArch settings).
> This will make it far easier to revert a change by deleting the overrides from within the RA `Overrides` menu.

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>bind `Fast Forward`</u> to a single button?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

To do this, launch a game from the system to want to change.

- Press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch quick menu
- Choose `Controls` › `Port 1 Controls`.
- Navigate to the key you wish to assign and press <kbd>A</kbd> to view a list of the various available functions (i.e. `Fast Forward`)
- Confirm your selection with <kbd>A</kbd>.
- The changes are saved automatically, just go back two levels and choose `Resume`.

> Notes:  
> This only works for certain systems (e.g. GB, GBC, GBA, etc.), and you have to hold the button to fast forward, whereas the global shortcut <kbd>MENU</kbd>+<kbd>R</kbd> is "press to toggle".  
> For more information regarding RetroArch inputs and controls please review the [libretro documentation here](https://docs.libretro.com/guides/input-and-controls/).

<p align="center"><img src="https://user-images.githubusercontent.com/44569252/189953701-265409db-d081-4c3b-bfc1-fb051af70f08.png" width="320px" /></p>


<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>


### How do I <u>remap in-game controls</u>?

<details>
<summary align="right"><i>Click to see answer</i></summary>
<table><td>

To do this, launch a game from the system to want to change.

- Press <kbd>MENU</kbd>+<kbd>SELECT</kbd> to go into the RetroArch quick menu
- Choose `Controls` › `Port 1 Controls`.
- Navigate to the key you wish to reassign and press <kbd>A</kbd> to view a list of the various in-game controls available.
- Confirm your selection with <kbd>A</kbd>.
- The changes are saved automatically when exiting the menu.

**Saving individual game, core, or content remaps**
   - After making the changes as above, press <kbd>B</kbd> to go back one level.
   - Then go to `Manage Remap Files` and choose one of the following:
      - `Save Game Remap File` - for just this game.
      - `Save Core Remap File` - for everything the core plays.
      - `Save Content Remap File` - for everything in the same Rom folder.

> Notes:  
> `Content Remap File` is recommended over `Core Remap File` since some cores serve multiple systems.  
> For more information regarding RetroArch inputs and controls please review the [libretro documentation here](https://docs.libretro.com/guides/input-and-controls/).

<img src="https://user-images.githubusercontent.com/44569252/189995592-9d9e4702-e237-40a2-a0b7-b5e4578f0d7d.png" />
</td></table>
<p>&nbsp;</p>
</details>