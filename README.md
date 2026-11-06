# Mod Drive 9000

A mod manager, plug-in host, installer and updater for **LET IT DIE** (Steam, PC).

Mod Drive 9000 loads plug-ins (DLLs) into the game and lists them on a **Mod Drive 9000** tab in the game's own options screen. There you can see each plug-in's details and switch it on or off. Plug-ins that need changes inside the game files (the title menu, the database, textures) bring a **pack**. The installer applies the packs to *your own* copy of the game files, so no game file is ever distributed.

| Plug-in | What it is |
|---|---|
| [DeatHUD](https://github.com/kevinsnagy-del/DeatHUD) | HUD and minimap overhaul |
| [Heavenly Designs](https://github.com/kevinsnagy-del/HeavenlyDesigns) | Visuals and performance |
| [POSTMORTEM](https://github.com/kevinsnagy-del/Postmortem) *(beta)* | A roguelike mode with its own save |
| [Let Us Die](https://github.com/kevinsnagy-del/LetUsDie) *(beta)* | Online co-op through Steam |

## Features

- **The Mod Drive 9000 tab** in the game's options screen: every installed plug-in with its details (X) and an on / off switch (Y), and each plug-in's own options page.
- **A plug-in host** with a stable plug-in API: plug-ins are DLLs dropped into `Binaries\Win64\ModDrive`.
- **The installer** applies every mod's pack to your own copy of the game files, after checking they are an unmodified, supported version, and backs them up first.
- **Updates** for Mod Drive 9000 and every plug-in, from their GitHub releases, checked and verified before anything is replaced.
- **Health check and repair** of every file Mod Drive manages.
- **Save backups**, automatic and on demand, for the normal save and the POSTMORTEM save, restorable together or one at a time.
- **Quick start:** the splash screens, title movies, the Death Drive logo and the press-any-key screen are skipped (straight to the title menu), and the title's two fixed 1.25 s pauses when a game starts are gone.
- **Game updates handled:** when LET IT DIE updates, the game asks once whether to quit and open Mod Drive 9000, which then looks for support for the new version.
- **Open Mod Drive 9000 from inside the game**, and a desktop shortcut.
- **Report a bug or send feedback** from the app, with the logs it needs attached (it shows exactly what is sent before you send it).

## Install

1. Download `ModDrive9000-<version>.zip` from [Releases](../../releases) and close the game.
2. Unzip it anywhere (right-click, *Extract All*) and open **`ModDriveInstaller\ModDrive9000.exe`**. It finds LET IT DIE through Steam: choose **Install Mod Drive 9000 here** and it moves into the game folder and opens from there. (Unzipping straight into the LET IT DIE folder works too.)
3. In Mod Drive 9000: Under **Get more mods**, tick the plug-ins you want and choose **Add selected**: each is downloaded from its GitHub page, checked, and applied to the game. (Or choose **Apply mods to the game** to apply Mod Drive 9000 on its own.) Applying checks that your game files are an unmodified, supported version, backs them up and your saves, then applies every mod. It takes a few minutes and needs about 3.5 GB of free space in your temp folder while it runs.
4. Plug-ins can also be installed by hand: unzip them into the same folder, then choose **Apply mods to the game**.
5. Start the game. The options screen has a **Mod Drive 9000** tab.

## The Mod Drive 9000 app

Everything is in one window, `ModDriveInstaller\ModDrive9000.exe`:

| Section | What it does |
|---|---|
| **Mods** | What is installed and whether updates are out. Tick the mods you want to update, apply them to the game, or remove one (its files and its game-file changes). |
| **Health check** | Checks every file Mod Drive manages (game files, packages, plug-in files, backups, saves) and repairs what it can, re-downloading damaged plug-in files. |
| **Backups** | Your save backups, the normal save **and** the POSTMORTEM save. Back up now, or restore both or just one. Saves are backed up automatically before every install, update and uninstall; the newest 10 are kept. |
| **Settings** | A GitHub token (only while a mod's page is private), folders, and uninstalling everything. |

The window needs Microsoft Edge, which is part of Windows 10 and 11; without it the app opens in your default browser. Command-line versions of every action are in `ModDriveInstaller\cmd`.

## When LET IT DIE updates

Steam replaces the patched game files, so the mods switch off. If the new game version is one Mod Drive 9000 does not know yet, the game asks once: **"Do you want to quit the game and open Mod Drive 9000?"** Choose Yes, and the app opens as soon as the game has closed and checks for an update. Choose No to keep playing unmodded.

When support for the new version is out, update and apply in the app. Nothing large is downloaded again, because the mods are rebuilt from your own files.

**Supported game version:** Steam build 25923506 (the 2026-10-20 update).

## Notes

- The installer only ever starts from the original files it backed up. Running it twice is safe.
- Backups and logs are in `Binaries\Win64\ModDrive\installer\`.
- If Steam reports a cloud-save conflict after you restore a save, choose the **local** files.
- `node.exe` (Node.js, MIT licence) runs the installer. The bytecode assembler is a self-contained .NET build.

LET IT DIE belongs to GungHo Online Entertainment / Supertrick Games. This is an unofficial fan project.
