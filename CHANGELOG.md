# Changelog

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
