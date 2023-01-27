# Adding mods to AVO

**NO SUPPORT IS PROVIDED FOR ANY MODIFICATIONS THAT YOU UNDERTAKE. BY UNDERTAKING ANY MODIFICATIONS YOU VOID ALL SUPPORT BOTH ON GITHUB AND IN THE ANIMONCULORY SERVER.**

## Disclaimer

No modifications are supported as we cannot track down what everyone has done. If you have modified your list, you void your support and bug reporting.

## Things to Know Before Modifying

AVO uses **Skyrim version 1.6.640/659**. This means that **you need to use plugins that are made for Skyrim version 1.6.6xx**. If your desired plugin does not exist for 1.6.640/659 (commonly referred to as AE) then you cannot use it.

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

## Regenerating AVO's Lods

After positioning these in the correct section, open up [this guide](https://github.com/The-Animonculory/Modding-Resources/blob/main/DynDOLOD.md) and follow the steps below.

**NOTE: Ignore any references to SSE-Terrain-Tamriel in the guide.**

1) Skip Installing Everything and go straight to xLodGen. All of the tools you need are already downloaded as part of AVO.
2) Activate `Majestic Landscapes xLodGen` in Mod Organizer 2.
3) Follow xLodGen as normal
4) Launch `A Clear Map of Skyrim Road Generator Tool`. Follow instructions as normal.
- Choose "Paths only" under the "Select roads" option. The browse button you want  is the one next to `Path to LOD`. The file you want should be ...AVO/tools/xLodGen/Output.
- When installing it as a new mod, it should replace AVO - xLodGen in Mod Organizer 2.
5) Deactivate `Majestic Landscapes xLodGen` in Mod Organizer 2.
6) Remove `AVO - TexGen Output` in Mod Organizer 2. Pay attention to where it is in the load order (it's just above `AVO - DynDOLOD Output`).
7) Follow TexGen instructions as normal.
- When installing it as a new mod, it should go where `AVO - TexGen Output` went.
8) Go here: https://github.com/The-Animonculory/Animonculory-Visual-Overhaul/blob/main/.github/AVO_Preset.ini.
9) Click on "Raw" in the top right. Right click anywhere in the page and choose "Save Page As..." and download the file. Move the downloaded file to `...AVO\tools\DynDOLOD\Edit Scripts\DynDOLOD\Presets`.
10) Run `DynDOLODx64`. In the top left section where it lists worldspaces, right click and press select all. At the bottom, select "Load preset", and load the file you just downloaded.
11) Skip down to "Once you have configured the settings" in the DynDOLOD & Occlusion section under Generation and follow instructions as normal.
- When installing it as a new mod, it should replace `AVO - DynDOLOD Output`.

## Changing the Graphical Post Processing

By default, AVO comes with 2 Reshade presets and a pre-configured ENB to make switching much easier. By default, AVO uses [Rustic Weathers](https://www.nexusmods.com/skyrimspecialedition/mods/8398) and [Ambience](https://www.nexusmods.com/skyrimspecialedition/mods/46383) for lighting so, if you wish to not replace them, you will want a preset that works with them.

**NOTE! I DO NOT PROVIDE SUPPORT FOR THIS.**

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

#### Moving it to work with Root Builder

Now that you have the preset installed, it's time to move it to be managed by the manager so it can easily be enabled and disabled. **NOTE**: This process also applies to ENB presets as well.

1. Create a new folder somewhere safe and call it the name of your preset. 
2. Navigate to where your copy of Skyrim Special edition is installed.
3. Select the files shown in the screenshot below.

![Reshade move these files](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/ReshadeCopyThese.png)

4. Move those files into your new folder. It should look something like the picture shown below.

![Reshade Preset files](https://raw.githubusercontent.com/The-Animonculory/Animonculory-Visual-Overhaul/main/.github/Reshade%20Preset%20Files.png)

5. Zip up that folder and call it the name of your new preset.
6. Launch Mod Organizer 2.
7. Click on the `Spanner and Screwdriver` icon in MO2 and select `Root Builder`.
8. Tick the `Installer` checkbox under `Settings`.

![Rootbuilder config](https://raw.githubusercontent.com/The-Animonculory/ADT/main/.github/RootbuilderConfig.webp)

9. Add the ENB as a new mod in MO2. Rootbuilder should assign it properly.
10. Verify that Rootbuilder has installed the ENB properly. It should look similar to the picture below:

![ENB Rootbuilder Check](https://raw.githubusercontent.com/The-Animonculory/ADT/main/.github/ENBRootBuild.webp)

12. Activate your new preset **DO NOT DEACTIVATE THE OLD PRESET. THERE ARE REQUIRED DLL FILES IN THERE.**
13. Enjoy your new preset.

## Adding Mods

Move every addition you make **above** the Synthesis and DynDOLOD esps. There is 214 free `ESP/ESM` slots in AVO V3 for you to use. Don't consider that a competition though as less is more and ESPFE (ESP flagged ESL) are often a better choice.

### DLL Plugins

For mods that include SKSE Plugins, **you need to use plugins that are made for Skyrim version 1.6.640/659**. This is mandatory and if your desired plugin does not exist for 1.6.640/659 (commonly refered as AE), then you can't use it.

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

These are more involved as you will need to regenerate the LOD files to ensure there is consistency across the worldspace. Please follow the Regenerating lods section.

#### NPC Replacers

These are mods that change things relating to:
- NPC's
- Facedata

AVO uses a custom curated mix of NPC overhaul mods however, they may not be to your taste. Should you wish to change them, deactivate them and then add your own. Resolve any conflicts that arise and then you should be fine. If you wish to create new facegen via the CK, please follow [this guide](https://github.com/The-Animonculory/Modding-Resources/blob/main/Regenerating%20Faces%20in%20the%20Creation%20Kit.md) which details the process of doing so.
