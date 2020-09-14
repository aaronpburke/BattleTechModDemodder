# BattleTech Mod Demodder

A do-nothing "mod" for BattleTech by Harebrained Schemes.

Have a saved game that uses an old mod that you no longer want to use, but can't disable it because otherwise your saved game won't load? Use this do-nothing mod as a replacement!

This mod literally *does nothing*! It's a DLL that satisfies the mod loader interface required by BattleTech, but literally doesn't do anything when it's loaded. Seriously. Look at the source code. Here it is:

```
namespace BTModDemodder
{
    public class BTModDemodder
    {
        public static void Init(string directory, string settingsJSON)
        {
        }
    }
}
```

That's it. That's the whole source.

I made this "mod" (if you can even call it that!) because I had [FastSaveDelete](https://github.com/janxious/FastSaveDelete) installed before the 1.2 patch, but once 1.2 came out, it was not only no longer necessary, but it broke the entire save game delete button! I couldn't disable the mod because my saved games already referenced it, so BattleTech refused to load my saves because a required mod was disabled.

## Download
Downloads can be found on [Github](https://github.com/aaronpburke/BTModDemodder/releases).

## Install
- Download `BTModDemodder.dll` into the `\BATTLETECH\Mods\HBS` folder.
- Find the mod you want to "demod" in the `mod.json` file and change the following settings:
  1. "DLL": "BTModDemodder.dll"
  2. "DLLEntryPoint": "BTModDemodder.BTModDemodder.Init",
