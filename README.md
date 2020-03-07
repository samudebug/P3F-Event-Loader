# P3F-Event-Loader
Script modification to insert an event loader in Persona 3 FES

To build it, you'll need:
1. [AtlusScriptToolchain](https://ci.appveyor.com/project/TGEnigma/atlusscripttoolchain/build/artifacts).
2. [Persona Patcher](https://puu.sh/wCmzs/6979184574.zip). Technically, you may only need the cvm tool, but this makes a bit easier.
3. [Persona Editor](https://drive.google.com/open?id=1Xh5d5H4sHksqzWTuoOlbASXz_g0CKGSp).
4. [UltraISO](https://www.ultraiso.com/download.html) (needs license)
5. An ISO dump of the game.

Now, to the build:
1. Extract the DATA.CVM file from game's iso using UltraISO and place it on the 'cvm' folder on the Persona Patcher folder
2. Run the Split CVM.bat file and wait
3. Go to the 'Split' folder inside the 'cvm' folder and open the data.iso file. Also, extract the file starting with "SLUS" and place it on the 'slus' folder
4. Extract the file called "F007_002.PAC" inside 'FIELD/PACK'
5. Compile the script using the following command:
`[path to your AtlusScriptToolchain folder]\AtlusScriptCompiler.exe "[path to the .flow file]" -Compile -Library P3F -OutFormat`
Notes:
- The .msg file must be in the same folder as the .flow one
6. It'll create a file called `f007.bf.flow.bf`, rename it just to be `f007.bf`
7. Open the F007_002.PAC file you extracted using Persona Editor
8. Right click at the 'f007.bf' file inside F007_002.PAC and click on Replace
9. Select the file you just compiled and then save the .PAC file
10. Replace the .PAC file in the data.iso, save it and run 'Make and Patch.bat' in the Persona Patcher's root folder
11. After it's done, get the file called 'data_repacked.cvm' inside the 'cvm' folder, move it to somewhere else and rename it to just 'data.cvm'
12. Get the SLUS file inside the 'slus' folder and replace it and the 'data.cvm' file you just renamed on the game's iso
13. Run the game, go to the dorm and interact with the save point and the option should be there

Alternatively, you can build a mod from it with Mod Compendium, but it never worked for me on PS2 games, so I can't test it.
