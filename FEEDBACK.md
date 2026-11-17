# Report a bug

Every bug report helps. Short is fine.

## What to send

Send a message to the person who invited you (or open an **Issue** in this repository) with:

1. **What you did**: the steps, for example "held button 3 in Notepad and said hello".
2. **What you expected.**
3. **What happened instead.** A screenshot or a short screen recording helps a lot
   (`Win+Shift+S` for a screenshot, `Win+Alt+R` to record).
4. **Which version**: shown at the bottom of the left menu (`VERSION 0.1.0 · BETA`), or in the installer's file name.

## Log files (please attach)

Press `Win+R`, paste this, and press Enter:

```
%APPDATA%\ProjectOASIS
```

Attach these files if they are there:

| File | What it holds |
|---|---|
| `crash.log` | What happened if OASIS crashed |
| `ble_log.txt` | Pad connection problems |
| `security.log` | Actions OASIS refused to run |
| `fixes.log` | Why "Saving to dictionary" did or did not appear (program names only, never what you said) |

They hold no passwords and no recordings. Your Groq key is never in them.

## Common problems

| Problem | Try this |
|---|---|
| Pad stays "searching…" | Bluetooth on? Switch the pad off and on, keep it close. |
| Voice says *No speech model* | Reinstall OASIS. The model comes with the installer. |
| Voice types nothing | Check the microphone in **Voice → 01 Hold to talk**, and that you clicked into a text box first. |
| Buttons do nothing | Is the right profile in front? Check the home screen: it shows the active profile. |
| OASIS seems gone | It is in the tray (near the clock, maybe under the **^** arrow). |
