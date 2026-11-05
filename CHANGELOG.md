# Changelog

## 1.2.0
- The installer can download content from its original authors (checked file by file against the original) and refuses to install a mod without content it needs -- POSTMORTEM 0.9.4-beta uses this for its collab content.
- Older Mod Drive versions skip mods that need this one instead of installing them half-way.
- (2026-11-06 refresh of the 1.2.0 download) `ModDriveInstaller\THIRD-PARTY-NOTICES.txt` and the `licenses` folder: the licences of Node.js, UELib, the .NET runtime and lzo1x, which ship in this download. `ModDrive9000.exe` now carries full version information and a Windows manifest. Nothing else changed.

## 1.1.0
- Supports the LET IT DIE update of 2026-10-20 (Steam build 25923506).
- **The Mod Drive 9000 app** (`ModDriveInstaller\ModDrive9000.exe`): one window for your mods, updates (tick the ones you want), applying them to the game, the health check and repair, and save backups. The .bat files moved to `ModDriveInstaller\cmd`.
- After a game update, the game now asks "Do you want to quit the game and open Mod Drive 9000?" and the app continues once the game has closed.
- POSTMORTEM and other plug-in notices work without Let Us Die installed.
- "Open Mod Drive 9000" from inside the game, and a desktop shortcut.

## 1.0.0 (first public release)
- The Mod Drive 9000 tab in the options screen: plug-in list, details (X), on/off (Y).
- Plug-in host with a stable plug-in API.
- Installer:
  - applies packs to your own game files (no game files distributed);
  - SQL, bytecode, package, ini and generated-package support;
  - patches the exe's hash checks.
- **Backups:**
  - the original game files, backed up once;
  - your saves (normal and POSTMORTEM), backed up automatically before every change, newest 10 kept;
  - restore all saves or just one of them.
- **Integrity scanner** (`Verify.bat`) and **repair** (`Repair.bat`).
- **Updater** (`Update.bat`) for Mod Drive 9000 itself and every plug-in, from GitHub releases. Downloads are checked against their SHA-256 digests.
- **Game-update guard:** an unknown game version switches Mod Drive off instead of hooking the wrong code.
- Quick Start pack: skips the splash screens, the title movies and the press-any-key screen, and removes the title's fixed waits when a game starts.
