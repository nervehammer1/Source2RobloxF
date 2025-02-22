# Source2Roblox

## ⚠️ THIS IS A FORK ⚠️
- This project is a fork of MaximumADHD's Source2Roblox. This aims to fix the automatic asset uploading and getting the project to work.
- Steps on how to make the project work are provided below (fixes missing Source2Roblox.exe error).
- Please respect the original creator's wishes and not use this to rip levels for your own profit.

<hr/>

Source2Roblox is a super awesome C# console application that can:
- Rip data from Valve's game files (*.VPK, *.VMT, *.VTF, *.BSP)
- Compile that data into files that Roblox can work with (*.RBXM, *.RBXL, *.MESH, *.PNG, *.OBJ)

# Usage

This program is not user-friendly and will not be made easier to use.<br/> But if you're feeling brave enough, you can set it up with the following steps:

1. You'll need to install the [Roblox Studio Mod Manager](https://github.com/MaximumADHD/Roblox-Studio-Mod-Manager) since the program currently targets `%localappdata%\Roblox Studio\content` for deploying local files.
2. Install [Visual Studio 2019](https://c2rsetup.officeapps.live.com/c2r/downloadVS.aspx?sku=community&channel=Release&source=VSLandingPage&version=VS2019&cid=2030) with `Visual C#` and `.NET Framework 4.7.2`
3. Clone the following GitHub repositories into a single directory on your file system:
   - https://github.com/nervehammer1/Source2Roblox
   - https://github.com/MaximumADHD/ValveKeyValue
   - https://github.com/MaximumADHD/Roblox-File-Format
   - They should look like this:
   	- FolderHoldingRepos >
   		- Source2Roblox
   		- ValveKeyValue
   		- Roblox-File-Format
   		- (plus any other folders)
4. Open the solution file `Source2Roblox.sln`
5. Right click on the `Source2Roblox` project and click Properties
6. Navigate to the `Debug` tab, and use some of the following command line arguments to get things up and running:

| **Argument**                         | **Required?** | **Example**                                                                         |
|--------------------------------------|---------------|-------------------------------------------------------------------------------------|
| `-game "PATH/TO/GAME/FOLDER"`        | **YES**       | `-game "C:\Program Files (x86)\Steam\steamapps\common\Half-Life 2\hl2"`             |
| `-model "path/to/local/model.mdl"`   | No            | `-model` for real-time model searching,<br/>`-model gman_high` for a specific model |
| `-vtf "path/to/local/image.vtf"`     | No            | `-vtf "editor/obsolete.vtf"`                                                        |
| `-map "map_name"`                    | No            | `-map kulcs`                                                                        |

With the command line arguments set, press the `Debug` button to run the program and have it work some magic!

If you end up getting an error, you may need to update Roblox-File-Format's packages using NuGet.
Figure that out yourself.
Once you update it, delete the Source2Roblox folder and clone it again, then follow steps 4-6. The program should run.

## File Generation Notes

- PNG files generated from `-vtf` will be sent to a new folder on your desktop called `ExamineVTF`
- OBJ/MTL files generated from `-map` will be sent to a new folder on your desktop called `SourceMaps`
- OBJ/MTL files generated from `-model` will be sent to a new folder on your desktop called `SourceModels`
- RBXL/RBXM/PNG files generated from either `-map` or `-model` will be sent to `%localappdata%\Roblox Studio\content\source`.
