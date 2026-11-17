# Remove an old version and keep your profiles

About 15 minutes. Do this when you move to a new version, or if an old copy of OASIS will not go away.
Your profiles live in plain files on your computer. Copy them first, remove the old version, install the new one,
and copy them back.

## Before you start

Quit OASIS completely. Closing the window is not enough, because OASIS keeps running in the tray.

1. Click the **^** arrow near the clock (bottom right) if you do not see the OASIS icon.
2. Right-click the OASIS icon, then click **Quit OASIS (pad and voice stop)**.

Why: while OASIS runs, it can write its files again and undo your copy or your clean-up.

## 1. Save your profiles and settings

Your profiles, your Dictionary and your voice settings are all in one file, `profiles.json`. Copy the files below.

**With PowerShell** (Start menu, type **PowerShell**, open it, paste, press Enter):

```powershell
$d = "$env:USERPROFILE\Documents\OASIS-backup\$(Get-Date -Format yyyy-MM-dd)"
$src = "$env:APPDATA\ProjectOASIS"
New-Item -ItemType Directory -Force "$d\Rust" | Out-Null
foreach ($f in "Rust\profiles.json","Rust\profiles.sig","Rust\profile_use.json","Rust\onboarding.json","profiles.json","profiles.sig","trusted_device.json") {
  if (Test-Path "$src\$f") { Copy-Item "$src\$f" "$d\$f" }
}
if (Test-Path "$src\profile_icons") { Copy-Item "$src\profile_icons" "$d\profile_icons" -Recurse -Force }
Get-ChildItem $d -Recurse -File | Select-Object FullName, Length
```

**With File Explorer:** press `Win+R`, type `%APPDATA%\ProjectOASIS`, press Enter. Make the folder
`Documents\OASIS-backup\<today's date>` and copy into it:

- the whole **Rust** folder (it holds `profiles.json`, `profiles.sig`, `profile_use.json`, `onboarding.json`)
- the **profile_icons** folder (the pictures on your buttons)
- `trusted_device.json` (it remembers your pad, so you do not have to connect it again)
- if you used the very old OASIS: `profiles.json` and `profiles.sig` from the top of this folder

**Check:** the last line of the PowerShell code lists your files. `Rust\profiles.json` must be there and not empty.
Or open the backup folder in File Explorer and look for it.

Your **Groq key** and other sign-ins (the `secrets` folder) are locked to your Windows account. Do not copy
them to another PC. On the same PC they stay where they are; you do not need to copy them.

Everything you dictated and the speech models are not part of the backup.

## 2. Remove the old version

Pick the one that matches what you have.

**A. An OASIS_0.x.x setup.exe version (0.1.0, 0.1.1 and later)**

1. Windows **Settings**, then **Apps**, then **Installed apps**.
2. Find **OASIS**, click the three dots, then **Uninstall**, and follow the prompts.
3. If it asks about deleting application data, you may tick it. That only clears the app's window cache, not your
   profiles.

This removes the program and its start-with-Windows entry. It does **not** remove your profiles, models or logs,
and it does not stop the text-polish helper if that is still running (see step C).
Not yet tried on a clean PC.

**B. The very old OASIS (the first one, not from a setup.exe)**

It was not installed with a setup file. It is a folder you copied or unzipped somewhere, and it has no uninstall
entry in Settings.

1. Quit it (see step C if it will not quit).
2. Delete its program folder, the one that holds its `.exe`.
3. Remove its start-with-Windows entry (see step C).

Your profiles for this old version are in `%APPDATA%\ProjectOASIS` (not in the `Rust` folder). The new OASIS does
not read them. Not yet tried on a clean PC.

**C. Stuck, portable or half-removed copies**

1. Press `Ctrl+Shift+Esc` to open Task Manager. On the **Details** tab, look for `oasis-desktop.exe`, `OASIS.exe`
   and `llama-server.exe`. For each: right-click, **End task**.
2. If you ran it as administrator and Windows says **Access is denied** when you delete the folder, open
   PowerShell with **Run as administrator** and run the delete there.
3. Stop it starting at sign-in: Settings, **Apps**, **Startup**, and switch **OASIS** off. Or press `Win+R`, type
   `regedit`, go to `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run` and delete the value
   **ProjectOASIS**. Both the old and the new OASIS use that name.
4. If you turned on "Run as administrator" in the old OASIS: open **Task Scheduler**, look in the folder
   **ProjectOASIS** and delete the task **RunAsAdministrator**.
5. If the install folder is left behind (usually `%LOCALAPPDATA%\OASIS`), delete it.

Not yet tried on a clean PC.

## 3. Clean leftovers (optional)

Press `Win+R`, type `%LOCALAPPDATA%\ProjectOASIS`, press Enter. Same for `%APPDATA%\ProjectOASIS`.

**Safe to delete**

- The `*.log` and `*.log.old` files in `%APPDATA%\ProjectOASIS`.
- `%LOCALAPPDATA%\ProjectOASIS\Models` if you want the space. It can be several GB. OASIS downloads again what it
  needs. This takes a while and needs internet.
- `%LOCALAPPDATA%\ProjectOASIS\DictationHistory` (your saved dictations, if you turned that on) and `bench`.
- `%LOCALAPPDATA%\dev.oasis.desktop` (the window cache).

**Keep**

- `%APPDATA%\ProjectOASIS\Rust` (your profiles, Dictionary and voice settings).
- `%APPDATA%\ProjectOASIS\profile_icons`, `trusted_device.json` and `secrets`.

To start completely fresh, delete the whole `%APPDATA%\ProjectOASIS` folder, but only after step 1 is done.

## 4. Install the new version

1. Open <https://github.com/dhanushscience/OASIS-releases/releases/latest>.
2. Download `OASIS_<version>_x64-setup.exe` and double-click it. Follow [Install OASIS](INSTALL.md)
   (Windows may say **Windows protected your PC**: click **More info**, then **Run anyway**).
3. When it asks about starting with Windows, answer **Yes** if you want it. If it says another copy of OASIS is
   already set to start, answer **Yes** to use the new one.
4. Let OASIS open once, then quit it again from the tray (see "Before you start"). This creates its folders.
   The first-run guide starts on a fresh install. It takes you through the pad and voice.

## 5. Get your profiles back

OASIS has no Export or Import button yet, so this is a copy.

1. OASIS must be quit (tray, **Quit OASIS**).
2. Press `Win+R`, type `%APPDATA%\ProjectOASIS`, press Enter.
3. Copy everything from your backup folder back into this folder, so that `Rust\profiles.json` ends up at
   `%APPDATA%\ProjectOASIS\Rust\profiles.json`. Click **Replace the files in the destination** if asked.
4. **If this is a different PC or a different Windows account**, also delete `%APPDATA%\ProjectOASIS\Rust\profiles.sig`.
   (Why: the file is signed with a key that belongs to one Windows account. Without that file, OASIS accepts the
   profiles and signs them again for you.)
5. Start OASIS from the Start menu.

**Check:** open **Profiles** in OASIS. Your profiles, their icons and your Dictionary are back, and there is no
black banner at the top. OASIS reads older profile files and brings them up to date by itself. A file from a
newer OASIS than the one you installed will not load: install the newest version.

Not yet tried on a clean PC.

## If something goes wrong

- **Profiles are not showing.** The file is in the wrong place or OASIS was still running. Quit OASIS from the
  tray, check that the file is exactly `%APPDATA%\ProjectOASIS\Rust\profiles.json` (not one folder deeper), start again.
- **A black banner says "Your profiles file was changed outside OASIS".** The signature does not match, usually
  because the file came from another PC or was edited. Buttons will not run and nothing saves. There is no button
  to accept it. Quit OASIS, delete `%APPDATA%\ProjectOASIS\Rust\profiles.sig`, start OASIS again.
- **OASIS still starts when I sign in.** Remove the startup entry (step 2C, item 3).
- **`llama-server.exe` is still in Task Manager and uses a lot of memory.** End it there (Details tab, **End task**).
  Current versions end it when OASIS quits, and clean up old ones at the next start.
- **"Access is denied" when deleting.** The old copy was run as administrator. End its tasks first (step 2C), then
  delete the folder from PowerShell opened with **Run as administrator**.

## What gets removed and what stays

| What | Where | Uninstall in Settings | Your clean-up |
|---|---|---|---|
| The program | `%LOCALAPPDATA%\OASIS` (setup.exe versions) | Removed | - |
| Start with Windows entry | `Run` value `ProjectOASIS` | Removed, if it points at this copy | Remove by hand if it points at an old copy |
| Profiles, Dictionary, voice settings | `%APPDATA%\ProjectOASIS\Rust` | **Stays** | Keep |
| Button pictures, pad pairing, sign-ins | `%APPDATA%\ProjectOASIS` | **Stays** | Keep |
| Logs | `%APPDATA%\ProjectOASIS` | Stays | Safe to delete |
| Speech and polish models | `%LOCALAPPDATA%\ProjectOASIS\Models` | Stays | Safe to delete (re-downloaded) |
| Saved dictations | `%LOCALAPPDATA%\ProjectOASIS\DictationHistory` | Stays | Safe to delete |
| Window cache | `%LOCALAPPDATA%\dev.oasis.desktop` | Removed if you tick the box | Safe to delete |
| Browser add-on copy | `%LOCALAPPDATA%\ProjectOASIS\Extensions` | Stays | Safe to delete |
