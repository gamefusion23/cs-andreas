**Download:** see [Releases](https://github.com/gamefusion23/cs-andreas/releases) - get `CS-Andreas-1.2.2.zip`. Also on Melty: https://melty.gg/m/cs-andreas

# CS Andreas 1.2.2

CS Andreas is a free, non-commercial fan-made modification for Grand Theft Auto: San Andreas.
The project combines Counter-Strike 1.6 gameplay mechanics with the world and story of GTA San Andreas.

Players must provide their own copies of the required games. This project does not distribute original game files.

CS Andreas is an independent fan project and is not affiliated with, endorsed by, or sponsored by
Rockstar Games, Take-Two Interactive, or Valve Corporation.
All trademarks and copyrights belong to their respective owners.

## Requirements
- Grand Theft Auto: San Andreas for PC, version **1.0 US or 1.01 EU**. The Steam / Rockstar Launcher versions
  (2.0 and later) and the Definitive Edition are different programs and are not supported.
- Counter-Strike 1.6, installed (Steam or non-Steam). Its `cstrike` and `valve` folders are read; it is never started
  or changed.
- Windows 10 or 11.

## Install and play
1. Unpack the ZIP into any folder of its own (for example `Documents\CS Andreas`).
2. Start `csandreas.exe`.
3. The launcher looks for both games by itself: its own folder and the one above it, Rockstar's registry entry,
   the Steam libraries and the usual folders on your drives. If it does not find one, it asks you once to choose its
   folder (San Andreas: the folder with `gta_sa.exe`; Counter-Strike 1.6: the folder with `cstrike` and `valve`,
   for Steam `steamapps\common\Half-Life`). The choice is kept in `%LOCALAPPDATA%\CSAndreas\launcher.ini`.
4. San Andreas starts as usual. Press `]` to switch into CS mode and back.

You can also give the folders yourself:
`csandreas.exe --game "<GTA San Andreas folder>" --cs "<Counter-Strike 1.6 folder>"`

**How it runs:** `csandreas.exe` starts your `gta_sa.exe` and loads `csandreas.dll` into it before the game runs
(this is called DLL injection). Nothing is written into the game folders. Some antivirus programs warn about
programs that load a DLL into another program; check the files against the SHA-256 sums given with the release.

## What CS mode is
One key (`]`, on a Russian layout `Ъ` - it is the physical key) switches between San Andreas and CS mode. In CS mode
on foot you play with Counter-Strike 1.6's weapons, first-person view, HUD, buy menu, grenades and C4, all read from
your own Counter-Strike 1.6. In vehicles, cutscenes and scripted mission moments San Andreas takes over and CS mode
comes back afterwards.

- **All 24 CS 1.6 guns**, the knife, HE / flash / smoke grenades and C4, with their own animations, timings and
  sounds. Reloading works as in CS 1.6: an empty magazine reloads by itself once you let go of the trigger, `R`
  reloads by hand, shotguns load shell by shell.
- **Health and armour:** 100 HP and up to 100 armour in CS mode, as in CS 1.6. Back in San Andreas CJ has his San
  Andreas health and armour again; a death in CS mode (CS's death and respawn) costs him nothing there.
- **Money:** the CS buy menu spends CJ's own money and every kill gives him $300. As in CS 1.6 the CS view shows and
  can spend at most $16000 of it - whatever CJ has above that stays his. `\` switches to the view of all of CJ's
  money and back.
- **Respect:** it is San Andreas' own and is earned as in San Andreas; the mod never changes it. `E` on a Grove Street
  member recruits him - as many as San Andreas allows with your respect (none under a small respect, 7 at most).
- **F7 crates:** in CS mode on foot `F7` puts a crate in front of CJ to jump on (again on the same spot: on top of
  it). They stay where you put them (`%LOCALAPPDATA%\CSAndreas\box_points_world.txt`) and are never written into
  your San Andreas saves.
- **CS Mode for NPCs:** in story missions the fighters, your recruits and allies fight with CS 1.6 animations, guns
  and sounds. `'` (on a Russian layout `Э`) or Esc > Options > Multiplayer > "CS Mode for NPCs" turns that off and
  on at any moment - off, they look, shoot and sound as in plain San Andreas. CJ is not affected. Kept in
  `csandreas.ini` (`NpcCsMode`).
- **Police:** San Andreas' own wanted level works in CS mode too (`MaxWantedInCsMode` / `NoWantedInCsMode` in
  `csandreas.ini` change that).

## Keys (CS mode, on foot)
`]` CS mode on / off · `\` money view · `'` CS Mode for NPCs · `B` buy menu · `M` team / class · `LMB` fire · `RMB` silencer / scope /
burst / stab / shield · `R` reload · wheel or `1`-`5` weapons · `Q` last weapon · `G` drop · `E` use / defuse /
recruit · `F` flashlight · `N` night vision · `Z` `X` `C` radio · `T` spray · `F7` crate · `Esc` CS game menu ·
`WASD` move · `Space` jump · `Ctrl` duck · `Shift` walk. In San Andreas mode and in vehicles every key is San
Andreas' own. Keys and settings: `%LOCALAPPDATA%\CSAndreas\csandreas.ini`.

## Your saves
- San Andreas saves as always (at a safehouse). CS Andreas keeps its own scripts and crates out of every save, and the
  save gets CJ's San Andreas health and armour, so a save made with the mod opens in San Andreas without it.
- Saves made with **earlier** CS Andreas builds may hold leftover crates. They are found after loading and listed in
  `%LOCALAPPDATA%\CSAndreas\csandreas.log`. To remove them set `CrateCleanup=1` in `csandreas.ini` (section `[game]`),
  load the save and save it again - keep a copy of the save first.
- Your own data (CS inventory, settings, crates) lives in `%LOCALAPPDATA%\CSAndreas`, never in the save.

## Uninstall
Delete the CS Andreas folder and `%LOCALAPPDATA%\CSAndreas`. The game folders were never changed. (If you moved
the music volume or brightness sliders in the CS options, San Andreas keeps those in its own settings, as if you had
set them in its menu.)

## Known limits
- Only the PC versions 1.0 US and 1.01 EU of San Andreas.
- CS player models in third person move with CJ's San Andreas animations.
- Single player only.

## Tested with
GTA San Andreas 1.01 EU and a non-Steam Counter-Strike 1.6 on Windows 11. Other set-ups have not been tested yet.

## License
CS Andreas is free to download and play. All rights to the CS Andreas code are reserved by its author; no open-source
license is given. This covers only CS Andreas itself, not the games, their content or their trademarks.
Third-party components: see `THIRD_PARTY_NOTICES.txt` and `CREDITS.md`.
