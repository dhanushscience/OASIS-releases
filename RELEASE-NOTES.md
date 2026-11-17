# What's new

## 0.1.5

**Public beta**
- The welcome screen now shows two short scenes: dictation that fixes a slip on its own, and a voice command that opens an app.
- Say "open a new window in <app>" to get a new window; plain "open" still reuses the last one.
- Calendar, Spotify and the browser extension are greyed out as "Coming soon" while they are still being tested.
- The update prompt now asks before upgrading.

## 0.1.3

**A better text-polish model**
- The text-polish helper now uses OASIS's own fine-tuned version of S1-mini, trained on dictated text. On a
  hand-checked test set it makes about a quarter fewer mistakes than the stock model (word error rate 0.15
  instead of 0.20) and gets about twice as many sentences exactly right, at a similar speed.
- PCs that use the polish helper download it once, the first time you start 0.1.3 (about 460 MB).
- It is still S1-mini by Superwhisper (a Qwen3-0.6B model, Apache-2.0). The licence and credits come with it.

**Strong PCs start on the best model**
- A PC that suits QUALITY (a graphics card with 4 GB or more of its own) now downloads QUALITY straight away instead
  of starting on the small set. First start takes longer, but dictation is accurate from the first word.

**Guides**
- New guide: how to remove an old version and keep your profiles.

## 0.1.2

**Faster, and much lighter on memory**
- Fixed a leak that made OASIS slow down your PC over time. Each time OASIS was closed by force, restarted by
  an update or crashed, its text-polish helper kept running in the background, holding about 1.2 GB of memory.
  On one PC fifteen of them had built up (20 GB). Helpers now always end with OASIS, and any left over from
  earlier versions are cleaned up when OASIS starts.
- With the memory free again, turning speech into text is about twice as fast on the test PC.

**Faster voice**
- The voice pop-up and the start sound now appear right when you press the talk button, not a moment later.
- OASIS waits less after you stop talking before it types or runs your words.
- Commands and typing are told apart better: with Notepad (or any text box) in front, "open Chrome" now opens Chrome
  instead of being typed.
- Spoken replies are gone; OASIS no longer talks back.

**Better cleanup of what you dictate**
- Names and the word "I" keep their capitals, and the cleanup no longer rewrites your sentence into something else.
- Repeated words and phrases, filler words, and corrections like "Tuesday, actually Wednesday" are handled better.
- Question marks are put where a question really is, and not on statements.
- KiCad and VS Code are written correctly, and VS Code is no longer treated as plain code text.
- Commands like "open Claude" or "close Claude" are heard correctly, and odd lookalike words only count when that
  app is installed.

**Editing by voice**
- Say "select all", "copy", "paste", "cut", "undo", "redo", "save this", "find", "bold", "italic" or "underline"
  and OASIS presses the matching keys. "Ctrl Z", "press enter", "go to end of line", "page down", "select line",
  "refresh", "go back" and "next tab" work too.
- They only count when they are the whole sentence: "copy" copies, "copy the file" is typed.
- New **Try voice commands** practice box with a short checklist: the last step of the first-run guide, and
  under Settings > Voice any time.
- Switch them off under Voice > Editing commands.

**Memory**
- The text-polish helper (S1-mini) now frees its memory after 10 idle minutes and starts again at your next press.
- The polish helper no longer keeps a copy of every sentence it has seen, which was making it grow over a long session.
- OASIS writes a small memory line to its log every 10 minutes, so growth is easy to spot.
- The tray menu has a separator before **Quit OASIS (pad and voice stop)**, so it is harder to hit by accident.

**Speech model**
- The small speech model is now called **Basic** (fastest, less accurate). More PCs get the accurate **Balanced** model
  (6 GB of memory is enough). If Basic is in use and your PC can run Balanced, Settings > Voice models offers
  **Better accuracy** in one click (about 660 MB).
- A PC that is too slow for Balanced now remembers that, instead of downloading it again at every start.

**Keys and Getting Started**
- New **Layout** choice in the first-run guide: horizontal (the overlay along the bottom, keys **F1 F2 F3**, now the
  default) or vertical (the overlay at the side, keys **`  Tab  Caps Lock**). The voice pop-up always sits at the
  bottom middle of the screen you are working on. Existing installs keep their keys.
- The overlay and the voice pop-up now follow you between screens.
- While keyboard input is on, these keys are taken in every program: Tab stops moving focus, Caps Lock stops
  toggling, ` types nothing outside OASIS, and F1 no longer opens an app's Help.
- When a new version is out, OASIS asks once a day: **Update now** or **Later**.

**Known limits**
- The first dictation after a break of more than 10 minutes is typed without polish while the helper starts.
- Very quiet speech may be cut off early.
- Caps Lock, Tab and F1 behave differently while keyboard input is on (see above).

**Getting Started**
- A short first-run guide with Mr. Science: which browser to use, which microphone, a first button press,
  and a first voice command. You can go **Back** to change an answer, or skip the guide at any time.

**Voice**
- While OASIS listens, a small pill appears at the bottom centre of your screen; its bars move with your voice.
  It and the close question follow the app's light or dark theme.
- The overlay's button labels have a light glass look, still easy to read on any background.
- **Hands-free dictation**: double-click the talk button. The pill shows a tick (button 1: finish and paste)
  and a cross (button 2: throw it away).
- One recording can now run for **30 minutes** (it used to stop at 4 min 59 s).
- A soft click when OASIS starts listening and another when your words are pasted. Turn them off under
  **Settings → Pad → Sound**. They also play on Bluetooth speakers that have gone to sleep.
- Closing an app by voice now asks at the bottom of the screen, where the pill shows: "Close **Notepad**?",
  with **01 Close** and **02 Keep**.

**Pad**
- On the OASIS window itself, the pad's buttons now run their actions like everywhere else, instead of
  moving around the window.
