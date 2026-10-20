# Mod Drive 9000

A mod manager, plug-in host, installer and updater for **LET IT DIE** (Steam, PC).

Mod Drive 9000 loads plug-ins (DLLs) into the game and lists them on a **Mod Drive 9000** tab in the game's own options screen. There you can see each plug-in's details and switch it on or off. Plug-ins that need changes inside the game files (the title menu, the database, textures) bring a **pack**. The installer applies the packs to *your own* copy of the game files, so no game file is ever distributed.

| Plug-in | What it is |
|---|---|
| [DeatHUD](https://github.com/kevinsnagy-del/DeatHUD) | HUD and minimap overhaul |
| [Heavenly Designs](https://github.com/kevinsnagy-del/HeavenlyDesigns) | Visuals and performance |
| [POSTMORTEM](https://github.com/kevinsnagy-del/Postmortem) *(beta)* | A roguelike mode with its own save |
| [Let Us Die](https://github.com/kevinsnagy-del/LetUsDie) *(beta)* | Online co-op through Steam |

## Install

1. Download `ModDrive9000-<version>.zip` from [Releases](../../releases) and close the game.
2. Unzip it **into the LET IT DIE folder** (Steam: right-click LET IT DIE, then *Manage*, then *Browse local files*).
3. Unzip any plug-ins you want into the same folder.
4. Run `ModDriveInstaller\Install.bat`. It does the following:
   - checks that your game files are an unmodified, supported version;
   - backs up the files and your saves;
   - applies every pack.

   It takes a few minutes and needs about 3.5 GB of free space in your temp folder while it runs.
5. Start the game. The options screen has a **Mod Drive 9000** tab.

## The ModDriveInstaller buttons

| | |
|---|---|
| `Install.bat` | Applies the packs of every installed plug-in. Run it again after adding a plug-in. |
| `Update.bat` | Updates Mod Drive 9000 and every plug-in from their GitHub releases, then re-applies the packs. |
| `Status.bat` | Shows what is installed and whether updates are available. |
| `Verify.bat` | **Integrity scan.** Checks every file Mod Drive manages: game files, packages, plug-in files, backups and saves. |
| `Repair.bat` | Runs Verify, then fixes what it can: re-applies packs, refreshes a damaged backup, re-downloads damaged plug-in files. |
| `Backup.bat` | Backs up your saves now: the normal save **and** the POSTMORTEM save. This also happens automatically before every install, update and uninstall. The newest 10 are kept. |
| `RestoreSaves.bat` | Puts a save backup back: all saves, only the normal one, or only the POSTMORTEM one. |
| `Remove.bat` | Removes one plug-in, both its files and its game-file changes. |
| `Uninstall.bat` | Puts your original game files back. |

## When LET IT DIE updates

Steam replaces the patched game files, so the mods switch off until they are re-applied. If the new game version is one Mod Drive 9000 does not know yet, it switches itself off completely, so the game runs unmodded. You get a message once.

When support for the new version is released, run `Update.bat`, then `Install.bat`. Nothing large is downloaded again, because the packs are rebuilt from your own files.

**Supported game version:** Steam build 25767944 (the 2026-10-08 update).

## Notes

- The installer only ever starts from the original files it backed up. Running it twice is safe.
- Backups and logs are in `Binaries\Win64\ModDrive\installer\`.
- If Steam reports a cloud-save conflict after you restore a save, choose the **local** files.
- `node.exe` (Node.js, MIT licence) runs the installer. The bytecode assembler is a self-contained .NET build.

LET IT DIE belongs to GungHo Online Entertainment / Supertrick Games. This is an unofficial fan project.
