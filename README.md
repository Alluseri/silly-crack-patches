# silly-crack-patches
Silly crack patches for super old apps. I will not be providing binaries for any of these!

# Quest3D v5.0
The original idea was to crack this and import AudioSurf to find out how it works, but apparently once the game resources are "protected" you can't import them into Quest3D even if you additionally patch out the protection check. That sucks.
## Patches
### Quest3D.exe
Address|Length|Original bytes|Patched bytes
-|-|-|-
0040545C|0x2|74 3F|90 90
0040633E|0x6|0F 84 A4 FC FF FF|90 90 90 90 90 90
004063CC|0x2|74 4C|90 90
00406408|0x2|75 3F|90 90
004238F0|0x6|51 68 80 38 42 00|EB 2A 90 90 90 90

## Notes
Might be imperfect, app reports itself as "Illegal Edition", but that might be because of the build I used for base.

# RPG Maker VX Ace
The good old RPG Maker VX Ace. I still prefer it to MV or, god forbid, MZ. All the OG FNAFb games were made here, and most of the fanmade ones too.
## Patches
### SciLexer.dll
Address|Length|Original bytes|Patched bytes
-|-|-|-
0005B383|0x5|0F B6 C3 5B C3|E9 C1 6C 01 00
00072049|0x12|00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00|53 BB 7E 1E 40 00 C7 03 B8 01 00 00 5B 0F B6 C3 5B C3

## Notes
Main binary is protected with ASProtect, didn't bother unpacking or fixing dump. SciLexer.dll is loaded after the binary is unpacked in memory, so I just made use of that. No ASLR either. This method doesn't require a patched version of CoGenDrm.dll and is launchable even if RPG Maker VX Ace is not properly installed(i.e. the COM classes are missing, like they were in my case).

# Lossless Scaling
Funny useless thing.
## Patches
### Lossless.dll
Address|Length|Original bytes|Patched bytes
-|-|-|-
1800201CD|0x6|0F 84 EE 02 00 00|90 90 90 90 90 90 

## Notes
Checks the registry for Steam ownership, doesn't even use steam_api.dll.
