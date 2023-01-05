# Adding mods to AVO

## Disclaimer

No modifications are supported as we cannot track down what everyone has done. If you have modified your list, you void your support and bug reporting.

## Things to Know Before Modifying

AVO uses **Skyrim version 1.6.353**. This means that **you need to use plugins that are made for Skyrim version 1.6.6xx**. If your desired plugin does not exist for 1.6.353 (commonly referred to as AE) then you cannot use it.

AVO is `method` patched which means that you can, within reason, remove or change near enough anything. No modgroups are included as they can complicate matters for newer modders. 

The only things that are not method patched are the generated outputs. These **will need to be regenerated** depending on what you change. More details are given in the relavant sections.

## Before You Begin

You may have seen us say "the left should match the right" when it comes to modlists, but what does this actually mean?

What it essentially means is that your mod order on the left hand side of MO2 matches the plugin order on the right. For example, USMP is designed to load after USSEP and on the right hand plugin view side will load like that. Therefore, we should place the USMP mod on the left hand below USSEP in priority. Whatever loads lower in priority (higher number) will be what is loaded in the game.

### Bash & Smash

**NEVER** attempt to create a Bash or Smashed patch on AVO. You should **ONLY** use Wrye Bash to swap masters on a plugin or use the mod-checker and **NEVER** attempt to use Smash on this list. Bash and smash patches are, for Skyrim Special/Anniversary Edition, broken and **SHOULD NOT** be used. You can do almost everything they do via a custom patch in xEdit.

Neither tool is included with the list as they are not required. If you do wish to add Bash, **you will need to reroute the managed game to your vanilla install**. If you do not, you will break the load order.

### Loot

No.

Do not use Loot. Use xEdit, follow the "left matching right" philosophy and also use common sense.

### Synthesis

If you add any mod with a plugin, it's recommended to re-run Synthesis. The patchers are split into 2 groups and are as follows:

__Synthesis__
- SynFloraFix
- khajiitearsshow
- nodragonlods

No custom data is used in these patches so you can just simply run them.

## Changing the Graphical Post Processing

By default, AVO comes with 2 Reshade presets and an ENB/Reshade manager to make switching much easier. By default, AVO uses [Rustic Weathers](https://www.nexusmods.com/skyrimspecialedition/mods/8398) and [Ambience](https://www.nexusmods.com/skyrimspecialedition/mods/46383) for lighting so, if you wish to not replace them, you will want a preset that works with them.

### Adding a new Reshade preset

In order for your Reshade preset to work properly, you will likely need to get some more shaders from the various repository's. Fortunately, the Reshade installer makes this very easy to do. 

#### Getting the shaders

1. Download Reshade from [their website](https://reshade.me/downloads/ReShade_Setup_5.5.2_Addon.exe)
2. Run the installer. Press `ok` when the prompt about singleplayer games comes up.
3. Click on `Browse` and select the `Skyrim.exe` found in the Game Root folder of AVO. It should look the picture below once completed.

![Reshade game choice](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Setup.png)

4. Make sure `DirectX 10, 11 & 12` is selected on the next screen.
5. It is possible that it may come up saying that it is already installed and offer to "Update". Select this.
5. Navigate to your newly installed preset. It will be located in `x:\Path\To\AVO\Mods\Reshade Preset`
6. Make sure that the shaders required are ticked and then press `install`.
7. Once Reshade is done installing, close the application.

#### Moving it to work in the manager

Now that you have the preset installed, it's time to move it to be managed by the manager so it can easily be enabled and disabled. **NOTE**: This process also applies to ENB presets as well.

1. Create a new folder somewhere safe and call it the name of your preset. 
2. Navigate to where AVO is installed and open the `Game Root` folder.
3. Select the files shown in the screenshot below.

![Reshade move these files](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/ReshadeCopyThese.png)

4. Move those files into your new folder. It should look something like the picture shown below.

![Reshade Preset files](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Preset%20Files.png)

5. Launch Mod Organizer 2.
6. There will be a dropdown box on the top right and a big `Run` button next to it. 
7. Run the program named `Manage ENB/Reshade Presets` from Mod Organizer 2.

![Select the manager](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Select%20ER%20Manager.png)

8. If the image below comes up, simply press OK. It is nothing to be concerned about.

![Ignore the warning](https://github.com/The-Animonculory/Animonculory-Visual-Overhaul/blob/main/.github/Ignore%20Warning.png?raw=true)

9. Navigate to the Presets menu by pressing the symbol in the top left (the three lines). The menu should look like this:

![Get to presets](https://github.com/The-Animonculory/Animonculory-Visual-Overhaul/blob/main/.github/ENB%203.png?raw=true)

10. Once in the presets menu, click on the `Add` button and select the top option.

![Reshade preset install 1](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Add%20Preset.png)

11. Navigate to your new preset and select it.

![Find and select the preset](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Preset%20Config.webp)

12. Make sure the source folder is correct and name your preset accordingly.

![Check the details](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Preset%20Config%202.png)

13. Your preset has now been added and can be activated. **Make sure to deactivate the one that is currently active!**

![Preset installed](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Preset%20Added.webp)

### Installing an ENB

**NOTE! This is NOT OFFICIALLY SUPPORTED. BY UNDERTAKING THIS CHANGE YOU VOID SUPPORT. AVO **does not** include any ENB files!**

Not convinced by Reshade? That's ok, it's not for everyone. Before going to add an ENB however, please do try it out. The results may surprise you. 

...Still here? Alright. Here's how to do it for a preset that's compatible.

1. Disable `Reshade Helper` & `Vanilla POM`. Remove `d3dcompiler_47.dll` from the Game Root folder.
2. Download [ENB binaries](http://enbdev.com), [ENB Helper](https://www.nexusmods.com/skyrimspecialedition/mods/23174) and [NVT ENB](https://www.nexusmods.com/Core/Libs/Common/Widgets/DownloadPopUp?id=75345&game_id=1704). Install ENB helper as normal in MO2.
3. Create a new folder in a safe location called `NVT`.
4. Copy `d3d11.dll` and `d3dcompiler_46e.dll` from the ENB binaries zip folder into there.
5. Open the zipped folder of the ENB preset and copy the files from `Main File\Quality` into the folder you just placed the dll files in. 
6. Follow the steps in [Moving it to work in the manager](#moving-it-to-work-in-the-manager).
7. Adjust any other settings you wish to.
8. Enjoy your new Preset.

## Adding Mods

Move every addition you make **above** the Synthesis and DynDOLOD esps. There is 214 free `ESP/ESM` slots in AVO V3 for you to use. Don't consider that a competition though as less is more and ESPFE (ESP flagged ESL) are often a better choice.

### DLL Plugins

For mods that include SKSE Plugins, **you need to use plugins that are made for Skyrim version 1.6.353**. This is mandatory and if your desired plugin does not exist for 1.6.353 (commonly refered as AE), then you can't use it.

Should you wish to use a plugin that is for on older version of Skyrim, you will need to downgrade the stock game folder and replace **ALL** dll mods 

### Armors and Weapons

Anything that replaces vanilla armors and weapons should be placed **after** Cathedral armory. **NOTE**: The Bodyslide output is mapped to use Cathedral armory textures except for a few certain mods. Should you wish your new armor mod to be used in Bodyslide, place it after `Poppy's Assorted CBBE Patches - Stalhrim Refrozen` on the left pane and then rebuild Bodyslide. There are numerous tutorial on how to do this online so we will not cover this here.

Any new weapons that are added should have a `Believable Weapons` patch merged in with them to provide consistency.

### Non Armor/Weapons Mesh/Texture Replacers

This is where things can get a bit complicated. What action you'll need to take depends on what your mesh/texture does. Mesh/texture replacer mods tend to fall into three categories: worldspace, non worldspace and NPC replacers. 

#### Non Worldspace Meshes/Textures

These are mods that change things relating to: 
- Interiors
- Food

Simply position these in the correct section as indicated on the left hand side. If there are any esp's present, move them to the correct position and resolve any conflicts that arise in xEdit.

**Note**: Make sure that the normal maps match for the texture/mesh you are using. If they do not, you will see some weird looking things. NifSkope and Nif Preview are inlcuded so that you can look at meshes/textures easily.

#### Worldspace Mesh/Texture Replacers

These are mods that change things relating to
- Landscape
- Trees
- Architecture incl: Cities, towns and villages
- Mountains

These are more involved as you will need to regenerate the LOD files to ensure there is consistency across the worldspace. After positioning these in the correct section, please follow [this guide](https://github.com/The-Animonculory/Modding-Resources/blob/main/DynDOLOD.md) for regenerating the LOD files.

**NOTE**: AVO uses [Worldspace Transition Tweaks](https://www.nexusmods.com/skyrimspecialedition/mods/48889) and thus does not come with `SSE-TERRAIN-TAMRIEL.ESM` as that is included in the aforementioned mod. Ignore any sections that refer to enabling `SSE-TERRAIN-TAMRIEL.ESM`.

**NOTE**: AVO uses custom tree rules which can be found on the [Happy Little Trees Add-On - DynDOLOD 3](https://www.nexusmods.com/skyrimspecialedition/mods/56907) page. It uses the `Optimal` settings with the Lod32 settings from A Clear Map of Skyrim. You can get the preset used for DynDOLOD from [here](https://github.com/The-Animonculory/Animonculory-Visual-Overhaul/blob/main/.github/AVO_Preset.ini). Place it in `X:\Path\To\AVO\tools\DynDOLOD\Edit Scripts\DynDOLOD\Presets`.

#### NPC Replacers

These are mods that change things relating to:
- NPC's
- Facedata

As of AVO 2.0, you no longer need to regenerate all of the facegen for newly added quest mods or have to contend with it. By default, AVO uses HMB II which has the option of assets to create new facegen. If you wish to do this, please follow [this guide](https://github.com/The-Animonculory/Modding-Resources/blob/main/Regenerating%20Faces%20in%20the%20Creation%20Kit.md) which details the process of doing so.
