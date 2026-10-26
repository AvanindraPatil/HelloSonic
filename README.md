# HelloSonic

**Sonic the Hedgehog in Hello Neighbor, and optionally Dr. Eggman as the Neighbor.** Sonic runs through the Neighbor's
house with his Sonic Adventure 2 model, motions, speed, moves, sounds and voice lines. With Dr. Eggman on, he takes the
Neighbor's place: his SA2 model and voice, homing missiles, and a hover pod he rides once Sonic has knocked him down.

<!-- screenshot here -->

> Unofficial fan project, not affiliated with SEGA, tinyBuild or Dynamic Pixels. The download contains **no SEGA
> files**: the installer builds Sonic and Eggman from **your own copy of Sonic Adventure 2**, on your PC.

## Features

- **Sonic from Sonic Adventure 2**: his real model, animations and physics numbers. Run, jump (hold for height),
  homing attack and jump dash, boost, walk and sneak, spin dash and roll on a pad, taunts and shouts, grinding on railings.
- **He plays the house**: doors, ladders, windows, picking up and throwing items, being caught by the Neighbor, and
  Sonic stands in for the kid in cutscenes.
- **Knock the Neighbor down** with your attacks.
- **Dr. Eggman as the Neighbor** (your choice at install): his SA2 model on the Neighbor's own skeleton and animations,
  in gameplay and cutscenes; fifty of the Neighbor's voice lines replaced with Eggman's; homing
  missiles; a hover pod once he has been knocked down. Switch him off and on again with `Switch-Eggman.bat`.

## Requirements

- **Hello Neighbor** (full game) on Steam, on Windows
- **Sonic Adventure 2** on Steam. It can be in any Steam library; it only has to be installed.

## Install

1. Download `HelloSonic-1.0.0.zip` from [Releases](../../releases) and unzip it anywhere.
2. Close Hello Neighbor, then double-click **`Install.bat`**. It finds both games through Steam and asks what you want:
   **1 = Sonic only**, **2 = Sonic + Dr. Eggman**. Then it builds everything from your SA2 files (about a minute) and
   installs the mod with [UE4SS](https://github.com/UE4SS-RE/RE-UE4SS) into Hello Neighbor.
   - Windows may warn about running a script from the internet. Choose "More info", then "Run anyway".
   - It downloads two things from their makers if you do not have them yet: [SA Tools](https://github.com/X-Hax/sa_tools)
     (13 MB, checked against a fixed checksum) and Microsoft's .NET 8 Desktop Runtime (55 MB; it asks first).
3. Start Hello Neighbor from Steam as usual and load a level. Sonic stands in front of you.

## Controls

| Key | |
|---|---|
| WASD / pad stick | run |
| Space | jump (hold = higher); in the air: homing attack / jump dash |
| Shift | boost |
| Ctrl | walk / sneak |
| T | taunt |
| F | shout |
| E | doors, ladders, pick up (as in the game) |
| F6 | Sonic in cutscenes on / off |
| F7 | Sonic in front of you again |
| F8 | the mod on / off |

## Dr. Eggman on / off

Run **`Switch-Eggman.bat`** (Hello Neighbor closed) to get the normal Neighbor back, and again to bring Eggman back.
It only renames his pak. To change between "Sonic only" and "Sonic + Dr. Eggman" for good, run `Install.bat` again.

## Uninstall

Double-click **`Uninstall.bat`**. It removes everything the installer added to Hello Neighbor. That includes UE4SS if
the installer put it there. A UE4SS you had before stays, and any file the installer replaced is put back. Sonic
Adventure 2 itself is never changed.

## What it changes

Only Hello Neighbor's folder:
- UE4SS: `dwmapi.dll` and the `ue4ss` folder in `HelloNeighbor\Binaries\Win64`
- the mod's two UE4SS mods (`HnSonic`, `HnSonicNative`)
- with Eggman: one content pak in `HelloNeighbor\Content\Paks\EggmanNeighbor`

Replaced files are kept as `*.before-hellosonic`, and `installed.txt` lists everything that was added.

## Troubleshooting

- **"missing ... not a Sonic Adventure 2 (Steam) folder?"**: point the installer at the folder that contains `resource\gd_PC`.
- **Antivirus / SmartScreen warnings**: UE4SS loads as a `dwmapi.dll` next to the game, and the installer runs a small
  Python program (included, plain source in `scripts\` and `tools\scripts\`) and SA Tools. Check that your download
  matches the SHA-256 on the release page (PowerShell: `Get-FileHash HelloSonic-1.0.0.zip`).
- **Bug reports**: please attach these logs from `<Hello Neighbor>\HelloNeighbor\Binaries\Win64`: `hnsonic_lua.log`,
  `ue4ss\UE4SS.log` and `ue4ss\Mods\HnSonicNative\dlls\hnsonic.log`.

Single-player only.

## Credits

- **Sonic the Hedgehog**, Dr. Eggman and **Sonic Adventure 2**: SEGA. Their content is read from your own copy of the game.
- **Hello Neighbor**: tinyBuild / Dynamic Pixels.
- **[UE4SS](https://github.com/UE4SS-RE/RE-UE4SS)** (MIT): the scripting system the mod runs on.
- **[SA Tools](https://github.com/X-Hax/sa_tools)** by X-Hax, **[vgmstream](https://github.com/vgmstream/vgmstream)**:
  read SA2's model and sound files (the installer downloads or bundles them; see `THIRD-PARTY-NOTICES.txt`).
- Made with the help of AI coding tools.

Licence: MIT (see `LICENSE`). The game content it reads stays SEGA's and tinyBuild's.
