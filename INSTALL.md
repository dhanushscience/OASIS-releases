# Install OASIS

About 10 minutes. You do not need to be an administrator.

## 1. Download

1. Open the **Releases** page of this repository.
2. Under the newest release, click **`OASIS_x.y.z_x64-setup.exe`** to download it (about 11 MB). The voice models
   are not inside it: OASIS downloads the ones that fit your PC the first time it starts (a few hundred MB, up to
   about 1.2 GB, once).

## 2. Install

1. Double-click the file you downloaded.
2. Windows may show **"Windows protected your PC"**. This is normal for a beta: the app is not signed yet.
   Click **More info**, then **Run anyway**.
3. Click **Next** and **Install**. Near the end, it asks **"Start OASIS automatically when you sign in to Windows?"**.
   Click **Yes** (recommended) so your pad and voice are ready every time you turn the computer on.
4. When it finishes, leave **Run OASIS** ticked and click **Finish**.

OASIS opens its window and puts an icon in the system tray (bottom right, near the clock; you may need to click the **^** arrow).

> Closing the window does not quit OASIS. It keeps running in the tray, so your buttons and voice keep working.
> To quit for real: right-click the tray icon, then **Quit**.

## 3. Connect the pad

You do **not** need to pair the pad in Windows Bluetooth settings. OASIS finds it by itself.

1. Make sure **Bluetooth is on** on your computer (Windows Settings → Bluetooth & devices).
2. **Switch the pad on** and keep it near the computer.
3. Wait a few seconds. On the home screen, the pad card changes to **Connected** and shows the battery.

The first OASIS pad that connects is remembered as *your* pad. After that, OASIS only connects to that one.

**It does not connect?**
- Bluetooth off or missing: a banner at the top of the window says so.
- Still "searching…" after a minute: switch the pad off and on again, and keep it close.
- You want to use a different pad: quit OASIS, delete the file
  `%APPDATA%\ProjectOASIS\trusted_device.json`, and start OASIS again.

**No pad?** Go to **Settings → Input** and turn on **Keyboard keys**. The three buttons are then
`Ctrl+Alt+Shift+1`, `2` and `3`. To use other keys, click a Button box and press the key you want:
any key works, including **Tab** and **Caps Lock**. To use **Shift**, **Ctrl** or **Alt** on its own, tap
it by itself. Then click **Save**. Two buttons cannot share a key.

## 4. Turn on voice

Voice is off when you first install.

1. Open **Voice** in the left menu.
2. In **01 Hold to talk**, switch it **on**.
3. Choose **Button to hold** (for example *Button 3*) and your **Microphone**.
4. Test it: click into any text box (Notepad, a chat), **hold** the button, say a sentence, and **let go**.
   Your words are typed after a moment.

The speech model runs on your computer. Nothing is sent online, unless you choose Groq
(see [Voice with Groq](VOICE-GROQ.md)).

## 5. Start with Windows

If you clicked **Yes** during the install, OASIS already starts quietly in the tray when you sign in.
To change it later, open **Settings** and use the **Start with Windows** switch.

## Uninstall

Windows Settings → Apps → Installed apps → **OASIS** → Uninstall.
Your settings stay in `%APPDATA%\ProjectOASIS` in case you install again; delete that folder to remove them too.
Moving to a new version, or removing an old copy that will not go away? Follow
**[Remove an old version and keep your profiles](UNINSTALL-AND-BACKUP.md)**: it shows how to save your profiles first and get them back.

Next: **[Use OASIS](USING.md)**
