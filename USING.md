# Use OASIS

The window has five parts in the menu on the left: **Profiles**, **Quick Launch**, **Voice**, **Overlay** and **Settings**.
Every change saves at once. There is no Save button to forget.

## The three buttons

Each button does one thing, called its *action*:

| Action | What it does | Example |
|---|---|---|
| Shortcut | Presses keys for you | `Ctrl+Shift+T` |
| Launch app | Opens a program | VS Code |
| Open URL | Opens a web page | `https://mail.google.com` |
| Paste text | Types a piece of text | your email signature |
| Mouse click | Clicks at a spot on the screen | `800,450` |
| Join meeting | Joins your next Google Meet | |
| Automation | Several steps in a row (wait, keys, open, Quick Launch …) | open an app, wait 2 s, press a shortcut |

## Profiles: buttons that change with the app

A **profile** is a set of buttons for one app or website, such as *VS Code*, *YouTube* or *Chrome*.
OASIS looks at the window in front and uses its profile. If no profile fits, it uses **Default**.

**Make a profile**
1. Open **Profiles** and click the **+** at the end of the profile strip (New profile).
2. Choose the app from the list of running apps, or type a website (for example `youtube.com`).
3. Click a button on the pad picture and choose its action and value.

**Sets of buttons inside a profile**
One app can need different buttons in different places, such as the editor vs. the terminal in VS Code.
Inside a profile, add a **set**:
1. Click the **+** next to the sets (Add a set of buttons). It is named CP2, CP3 … (you can rename it).
2. Click **Pick the section**. You get a short countdown: click into the part of the app you mean
   (the terminal, say) before it ends. OASIS remembers that place.
3. Click **Create set**, then set the buttons for it.

OASIS will not make the same set twice: if one already exists for that place, it takes you to it.

**Show labels first**
Each profile, and each set, can **Show labels first** on the overlay before running, so you can check
what a button does, or **Run at once**.

## Voice

Hold your talk button, speak, let go. A small pill appears at the bottom centre of your
screen while OASIS listens; its bars move with your voice. A soft click plays when it starts listening and another when the words are
pasted; turn both off under **Settings → Pad → Sound**.

**Hands-free (long dictation):** double-click the talk button instead of holding it. The pill shows a
**tick** and a **cross**: press **button 1** (tick) to finish and paste, or **button 2** (cross) to throw the
recording away. One recording can run for up to 30 minutes.

- **In a text box**, what you said is **typed**: "comma" and "full stop" become `,` and `.`,
  number words become digits, "um" is dropped, and "no, actually …" keeps only the correction.
- **Anywhere else**, it runs as a **command**: "open Spotify", "new tab", "pause".
- You can change this under **04 Clean up → A recording becomes**: Auto, Always a command, or Always typed.

**The dictionary (Voice → 05 Dictionary)**
- **Words**: a word the model keeps getting wrong, and how to write it. Example: `kay cad → KiCad`.
- **Replacements**: a phrase you say, and your own text to type instead.
  Example: `my mail → you@example.com`. Then "send it to my mail" types your address.
- **Learns from your fixes**: after OASIS types your words, retype a wrong word yourself (select it and
  type the right one), then stop typing for two seconds. A small box **"Saving to dictionary"** appears on
  the overlay with a countdown. Let it run out to save the word, or click **Don't save**. It then shows up
  in the Words list at once.
  - It only works in programs that let OASIS read their text (Notepad, Word, most text boxes and web pages).
    In some programs, such as terminals, it stays silent.
  - It only notices a word that was changed into something that looks similar (such as `keycat` → `KiCad`),
    within a minute of the dictation, and only in the part OASIS typed.

**Noise filter (02)**: if you are in a noisy room, choose **Strong**. In a quiet room, **Light** or **Standard** is best.

**Speech to text (03)**: *This computer* (private, works offline) or *Groq online* (faster,
needs your own free key: see [Voice with Groq](VOICE-GROQ.md)).

**Risky voice commands ask first.** The overlay shows the question: button 1 runs it, button 2 cancels.
Closing an app asks at the bottom of the screen, where the listening pill shows ("Close **Notepad**?"): **01** closes it,
**02** keeps it open.

**On the OASIS window itself**, the pad's buttons run their actions as they do everywhere else (they no
longer move around the window).

## Quick Launch: your desk in one press

A *setup* opens several apps and places each one where you want it.

1. Open **Quick Launch**, click **Create +**, and give it a name (and a voice command if you like, such as "coding").
2. Add apps or web pages, or click **Capture open windows** to take the windows that are open now.
3. For each item, draw its box on the screen picture. The picture shows your real screens.
4. Click **Save**.

Run it by voice ("coding"), or put a **Quick Launch** step in a button's Automation.

## Overlay

The three bars on your screen that stand for the three buttons.

- **Where:** down the left or right edge, or in a row at the top or bottom.
- **At rest:** faint, hidden, or always visible. They light up when you press a button or talk.
- **Move it:** click **Move overlay** (on the Overlay screen, or in the tray icon's menu), drag it, then **Done moving**.

## Settings

- **Input**: use the OASIS pad, the keyboard, or both. Click a button's box and press the key you want
  (Tab and Caps Lock work too; tap Shift, Ctrl or Alt by itself to use it alone), then **Save**.
  Shift, Ctrl and Alt used alone still reach the program in front, so typing is not affected.
- **Start with Windows**, and other general options.
- **YouTube extension** (optional): for the YouTube buttons and ad skip. Click **Open extension folder**,
  then in Chrome or Edge open the extensions page, turn on **Developer mode**, click **Load unpacked**,
  and choose that folder.

Found something odd? **[Report a bug](FEEDBACK.md)**.
