# GLE Guide
This guide can help you do the following with the Galaxy Level Engine:
- Set up a riivolution patch with GLE included for your mod
- Set up a hubworld
- Get a galaxy working

Other stuff may be read about on the [official wiki](https://github.com/SuperHackio/GalaxyLevelEngine/wiki).

# What you will need
- [GLE](https://github.com/SuperHackio/GalaxyLevelEngine/releases) (Make sure not to download the template hack by accident!)
- [Dolphin](https://dolphin-emu.org/)
- [Whitehole](https://github.com/SunakazeKun/Whitehole-Despaghettification/releases)
- A bit of knowledge on SMG2. 

<sub>Read more on the necessary knowledge [here](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/SavePointList).</sub>

# "Initializing" GLE & Making an XML for your mod
First, [download GLE](https://github.com/SuperHackio/GalaxyLevelEngine/releases).
Make a new folder just for this. 
Go to `GLE-V2\Riivolution` and copy "GLE_V2" into your new folder.

Additionally, make a `riivolution` folder inside the new folder.

Inside the `riivolution` folder you just created, create a new xml. You can call it whatever.

<sub>Refer to [this](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/Setup-Guide#making-a-riivolution-xml) for the layout of the xml</sub>

Rename `GLE_V2` to whatever you called `[YourHackName]`.

Edit your xml and put the xml lines where it specifies. You can get this code from `GLE-V2\Riivolution\GLEV2_[REGION]-SB4[R]01.xml`.

Make a copy for every region of your hack (USA, PAL, JPN, ... TWN and KOR are not supported atm, but should be in the future)

Add your ISO/WBFS to dolphin's game path. (Config->Paths->Add...)

Right click on your ISO/WBFS and click "Start with Riivolution Patches...".

![image](https://user-images.githubusercontent.com/38051573/206037241-16e1b2fd-f139-4927-b2c9-95ada33c7b82.png)

<sub>If this does not show up you are on an OUTDATED version of dolphin!</sub>

Open the XML that you just created and save a preset. Name it whatever your hack's name is. Then enable it and click start. 

The game should be able to boot up, but won't be able to load a file. If this is the case...
## GLE is now initialized!
**Congratulations!** Next we will be adding a hubworld.

## Problem: Black Screen Loading Screen
This happens because your XML is setup wrong. Make sure the folder name matches what you set `[YourHackName]` to.

# Adding a hubworld

To make the BCSVs easy to edit, simply copy the files in `GLE_V2` into `SMG2/data/files` (Replace if asked). You will have to these files over to the riivolution path anytime you change something.

Open your workspace and add [the hubworld template](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/Template-Files#new-hubworld-template). Then, follow [this guide](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/Creating-a-New-Galaxy#giving-your-galaxy-a-name). Be sure to also change `YourHubworldGalaxyScenario.arc`'s root name. 

Add some entries for the galaxy in `GalaxyName.msbt`, `GalaxyNameShort.msbt`, and `ScenarioName.msbt`, and we're done with that!

Now we are going to set up the SavePointList. 

Archive: `/ObjectData/SystemDataTable.arc`, File: `/SystemDataTable/SavePointList.bcsv`

## Recommended Values For Your Hubworld
| ID    | GalaxyName | ScenarioNo | ZoneName | MarioNo | Player | ResultPathId | EntryPathId | EntireLevelFlag |
|:-------------:|:-------------:|:-------------:| -------------| -------------| -------------| -------------| -------------| -------------|
| 0 - Default      | [YourHubworldName] | 1 |  | 0 | -1 | 0 | 0 | 1 |

<sub>Read more about the SavePointList [here](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/SavePointList)</sub>

To make the menu say "Save And Quit" instead of "Return to World Map" open:

Archive: `/StageData/[YourHubworldName]/[YourHubworldName]Map.arc`, File: `/Stage/jmp/List/ScenarioSettings`

Add a new field and activate whatever you want [on this list](https://github.com/SuperHackio/GalaxyLevelEngine/wiki/Stages#available-settings).

## Congratulations!
There have been no common errors on this yet. Let me know if you have a problem.
