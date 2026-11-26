# CS Andreas 1.2.2

CS Andreas is a free, non-commercial fan-made modification for Grand Theft Auto: San Andreas.
The project combines Counter-Strike 1.6 gameplay mechanics with the world and story of GTA San Andreas.

Players must provide their own copies of the required games. This project does not distribute original game files.

CS Andreas is an independent fan project and is not affiliated with, endorsed by, or sponsored by
Rockstar Games, Take-Two Interactive, or Valve Corporation.
All trademarks and copyrights belong to their respective owners.

> **Please read first: CS Andreas is a fan project in active development, and you may run into bugs.** The game can
> crash or close, a mission can behave oddly, CS mode can clash with other San Andreas mods (CLEO, Mod Loader, ENB,
> widescreen / windowed-mode plugins ...), and Windows or an antivirus can warn about the launcher. **Keep a copy of
> your saves** (Documents\GTA San Andreas User Files) before you play. If something goes wrong, see
> [Reporting a problem](#reporting-a-problem) - every report with its log helps fix it.

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

## If Windows or your antivirus stops it
- **"Windows protected your PC"** (a blue SmartScreen window) on the first start: `csandreas.exe` is new and not
  signed, so Windows does not know it yet. Click **More info**, then **Run anyway**. It is asked only once.
- **The antivirus deleted or quarantined `csandreas.exe` or `csandreas.dll`:** loading a DLL into a game is also
  what some malware does, so some antivirus programs flag it - a false alarm. Restore the file from quarantine and
  allow it, or unpack the ZIP again. You do not need to switch your antivirus off.
- Check that your ZIP is the real one: its SHA-256 is given on the release page (PowerShell:
  `Get-FileHash CS-Andreas-<version>.zip`).
- "This gta_sa.exe is not supported": your San Andreas is the Steam / Rockstar Launcher version (2.0 or later). A
  copy can be turned back into 1.0 with a downgrader made by the GTA modding community.

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

## Story missions in CS mode
- **The missions' NPCs fight the CS way:** the armed people a mission's script creates, your Grove Street allies and
  recruits, and in some missions the gangs and police that join the fight. They get CS 1.6 poses and gait, CS guns
  and sounds, CS impacts and deaths, and drop a CS weapon box. Their weapons become the CS counterparts: 9mm - Glock
  18 (twin 9mm - Dual Berettas), silenced 9mm - USP, Desert Eagle - Deagle, shotguns - M3 / XM1014, Micro Uzi - MAC-10,
  MP5, AK-47, M4 - M4A1, Tec-9 - TMP, country rifle - Scout, sniper rifle - AWP, bats, clubs and blades - the knife.
  Passers-by and the police outside missions are never changed.
- **CS bots:** enemies fire only at a CJ they can see; bot difficulty (easy / normal / hard / expert) in the Esc
  menu. Mission enemies have CS's 100 HP and 100 armour, the bosses keep their own. A flashbang blinds them, a smoke
  grenade blocks their shots. Enemies who just stood on their spot come for CJ.
- **`'` (Russian `Э`) - CS Mode for NPCs:** all of the above off or on at any moment.
- **Recruiting:** `E` on a Grove Street member under the crosshair recruits him (as many as your respect allows),
  `E` on a recruit lets him go. Recruits fight with CS guns; an unarmed homie gets the knife in a fight.
- **Automatic CS mode:** after a mission's cutscene CS mode comes back by itself; `[` turns that off.
- **Rides:** where CJ shoots from a car in CS mode he gets a CS gun that never runs dry; the enemies' fire on him
  there is San Andreas' own:
  - *Just Business* - TMP, with endless spare ammo;
  - *Reuniting the Families* and other rides - the CS counterpart of San Andreas' gun (AK-47);
  - the finale's chase and Sweet's rides - M4A1;
  - *The Da Nang Thang* helicopter - M249;
  - *Freefall* - a pistol.
- **Bosses keep their own health** (Forelli in Saint Mark's Bistro and the like); everyone else has CS health.
- **Mission by mission** (in story order):
  - *Tagging Up Turf* - choose Grove Street's tag as your spray (Esc > Options > Multiplayer), then `T` at a
    gang tag paints the whole tag at once; San Andreas counts it for the mission.
  - *Drive-By* - only the gang members holding guns fight the CS way; while CJ is in a car they shoot at the car.
  - *Sweet's Girl* - the kill feed names the enemies Seville Families.
  - *Doberman* - the Ballas waves fight the CS way.
  - *Los Sepulcros*, *House Party* - the homies are allies and fight the CS way.
  - *Wrong Side of the Tracks* - the Vagos (and their bodies) ride the train; CJ is carried on the train's roof; Big
    Smoke stays San Andreas'.
  - *Just Business* - endless spare ammo; the mafia men have no radio labels.
  - *Reuniting the Families* - the police at the motel fight the CS way.
  - *The Meat Business* - the enemies stand and fight instead of running; bats stay bats; Rosenberg keeps his
    extinguisher.
  - *Mountain Cloud Boys* - Woozie stays San Andreas'.
  - *Against All Odds* - the CS C4 blows the betting shop's back door; Catalina is safe from the blast.
  - *Toreno's Last Flight*, *Interdiction* - CS has no rocket launcher, so M249 bullets hit helicopters harder.
  - *Black Project* (Area 69) - the scientists act as CS hostages; the soldiers move properly on the walkways.
  - *The Da Nang Thang* - the helicopter's minigun is an endless CS M249; climbing crates on the ship; the knife takes
    the shotgun guard in one blow.
  - *Breaking the Bank at Caligula's* - the satchel charge to pick up looks like CS's C4 pack and gives the C4; the C4
    blows the wall the mission wants blown; a CS smoke grenade thrown into the vent counts as the tear gas; `E` uses the
    swipecard doors; climbing crates stand at the roof ledges. Croupiers and dealers are not CS; the mafia men with two
    pistols carry Dual Berettas; Woozie, Zero and the janitor stay San Andreas'; the SWAT and motorbike police engage;
    night vision looks as in San Andreas.
  - *Freefall* - the cabin fight is a pistol fight.
  - *Saint Mark's Bistro* - the enemies engage CJ (Forelli keeps his boss health); CJ is put straight into the jet to
    Liberty City.
  - *Stowaway* (Toreno's Andromada plane) - the guard drops the parachute as a San Andreas pickup; plant the CS C4 in
    the plane's hold instead of the satchel charge - it rides along with the plane and goes off once CJ has jumped out.
  - *Home Coming*, *Beat Down on B Dup*, *Grove 4 Life* - Sweet fights the CS way while he holds his gun.
  - *Los Desperados* - Cesar and the Aztecas fight the CS way for the whole mission; a katana becomes the knife.
  - *End of the Line* - all three parts are recognised.
  - Everywhere: the kill feed names the enemies by their gang.
- **No automatic CS mode** (turn it on with `]` if you want): Catalyst, Robbing Uncle Sam, Drive-Thru, Ryder's pizza
  scene, Explosive Situation.
- **Kept San Andreas':** cutscenes and scenes, getting in and out of cars, races and missions without a fight on
  foot (Cesar Vialpando, the lowrider races, Home Invasion, Running Dog, Life's a Beach, Management Issues, Explosive
  Situation, OG Loc), Ryder with his bat in Cleaning the Hood, and characters who don't fight (Tenpenny, Woozie, Ken
  Rosenberg, the girls you rescue).
- **F7 crates** work in every mission too (Da Nang Thang and Caligula's keep their own sets).

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

## Reporting a problem
Open an issue on GitHub (https://github.com/gamefusion23/cs-andreas/issues) with your San Andreas version, what you
did and what happened, and attach `%LOCALAPPDATA%\CSAndreas\csandreas.log` (and `csandreas-prev.log` if the game was
started again since). The log holds the mod's version, the game's exe, the plugins in the game folder and what went
wrong; its folder paths may show your Windows user name - you can blank it out before you post the log.

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
