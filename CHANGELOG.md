# Changelog

## 1.3.8
- Plug-in API: LidAddScriptResultCall -- a plug-in can read and change the answer a game script function gives to its script caller (Heavenly Designs 1.3.0 needs it: bare-fist guard, stealth finisher).
- Freeze notes (nativehook-hitch-stacks.txt) now also record the video memory in use against its budget, the free RAM, and where the graphics threads were standing.
- Update Heavenly Designs to 1.3.0 together with this version (it does not load on an older Mod Drive 9000).

## 1.3.7
- Fixed: the host could hold only 16 function hooks and the mods ask for 24, so the last ones were refused at every start. In POSTMORTEM that had switched off the run-start mushroom clearing, boss rush's fresh floors, the bank and tank caps, the achievement descriptions and reward texts, and the daily box / Reward Box filters. The host now holds 64 (and more frame ticks, overrides and code patches).
- Update Postmortem to 0.9.9-beta together with this version.

## 1.3.6
- Plug-in API: LidHudAnchorRect and LidHudWorldRect -- a filled box at an offset from a point of the screen or of the world (used by Heavenly Designs' posture bars).
- When the game freezes for more than a second, where it was stuck is noted in nativehook-hitch-stacks.txt (helps find the cause of lag spikes).
- Faster lookups of game objects by name (a 45 to 100 ms hitch each, several at the first floor of a session).
- A list screen opened during a scripted scene no longer returns the fighter to normal play when it closes (the scene does that).
- The name index no longer rebuilds itself in the middle of the hub load.
- Fixed a stall of about one second on the first floor of every session, and many shorter ones in a session's first minutes: looking a game name up no longer walks the whole name table.
- Fixed: the host could hold only 64 function overrides, and the mods together had reached that number. Later ones were refused silently.
- Fewer small hitches during play: the game's manager objects are looked up once per map instead of every 10 seconds.
- The hitch notes (nativehook-hitch-stacks.txt) also name the two busiest other threads during a freeze (the rendering thread, a loader), with their CPU time.

## 1.3.5
- Fewer stutters when a floor starts: plug-ins looking up a game function for the first time no longer search the whole game (each lookup used to freeze a frame for about 40 ms, and a new floor made dozens of them).

## 1.3.4
- **Update setting** (next to Check for updates): *tell me* (as before), *install automatically* (updates and applies them when Mod Drive 9000 opens), or *do not check* (only the button checks).
- **Select all** and **Remove selected**: tick several mods and remove them in one go (your saves are backed up first and are not deleted).
- Clicking a mod's row now selects it. The mod's page (features and changelog) opens from its new **More info** button.
- Faster object lookups for every plug-in (lookups for things that are not there, and lookups by exact name, are cached).

## 1.3.3
- After an update, the mod shows "Updated" straight away instead of "Update ready" for a few seconds; the list stays on screen while Mod Drive checks GitHub again.
- Fixed: the game's Mod Drive 9000 tab said Quick Start was not installed when it was (and the log warned about it every start).
- Less noise in the game's log (a menu check no longer reports a "problem" on every pause menu).
- Fixed: plug-in pop-up messages were never shown in POSTMORTEM (a filter for the game's old raid notices hid them too).
- Fixed: text in the game's own font (used by plug-ins) could go missing for a while after a map change or on returning to the hub. Mod Drive now keeps the font, so the text always shows in the game's font.
- Fixed a memory leak: text the game handed back to plug-ins was never freed. In long sessions it added up.
- Slow-down reports in the log now name the plug-in function responsible, not Mod Drive's own lookup code.

## 1.3.2
- **Progress bar:** applying, adding and updating mods show a percentage and the time taken; other actions show a moving bar.
- "Reading your game folder" counts the seconds, so you can see it is working (the first time can take a minute).
- **Mod Drive 9000 keeps its own log** (`app.log`, in the Logs tab): each start, which window it opened, anything that failed or was slow, and errors in the window itself. Reports from the app include it.
- The version in the header is Mod Drive 9000's own again (it showed the installer's).

## 1.3.1
- **Mod Drive 9000 opens in its own window on every PC.** It used to need Microsoft Edge in its usual place, and opened as a browser tab without it. The window is now Mod Drive 9000's own (built on Microsoft WebView2, part of Windows 10 and 11), with its icon in the taskbar.
- Updates replace the window program even while it is open.

## 1.3.0
- **Install from anywhere:** unzip the download anywhere (Downloads is fine) and open `ModDriveInstaller\ModDrive9000.exe`. It finds LET IT DIE through Steam, installs itself into the game folder (every file checked) and opens from there.
- **Get more mods:** the app lists the plug-ins you do not have yet (DeatHUD, Heavenly Designs, POSTMORTEM, Let Us Die). Tick them and choose Add selected: each is downloaded from its GitHub page, checked against its SHA-256 and applied to the game in one go. No more unzipping plug-ins by hand.

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
