# IslandsOfInsight-Unpacked-Assets
The process of unpacking UE (Unreal Engine) .pak files can vary a lot depending on the version of UE and settings used while packing.

Islands of Insight was developed using UE version 4.27, it's pak files use Oodle compression, and are encrypted using AES-256.
All the game's vanilla .pak files are found in "C:\Program Files (x86)\Steam\steamapps\common\Islands of Insight\IslandsofInsight\Content\Paks" (windows location).

Each pakchunk contains specific asset files, but they are not separated by folder. So one chunk might have half the files in a given folder and a different chunk will have the rest.
Thus, to recreate the games file structure we unpack each chunk and then merge them together.

To unpack the .pak files I used unrealpak, but since the game uses oodle compression, which is a separate plugin for UE 4.27 and not included in unrealpak, you need to either create a UE project or install the oodle files yourself.
This github packages the unrealpak tool with the plugin needed for oodle compression: [UnpealPak_4.27_with_Oodle](https://github.com/Punpude/UnrealPakTool/tree/UnrealPak_4.27_with_Oodle)

The .pak files are also encrypted, so you need to add a crypto.json file as per the UnrealPak readme. The encryption key is "WdfQ3j05cE9UYDVcpsECuY/ruTPNBXyfkRm9uCZn4f8="
