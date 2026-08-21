# Nightjar Browser — downloads

A browser with a local AI that reads your pages without sending them anywhere.
The model runs on your machine; pages you visit and questions you ask are never
uploaded.

**[Download the latest release](https://github.com/goandude/jamunbrowser-releases/releases/latest)**

This repository holds builds only. It exists so downloads have a plain link
that needs no GitHub account. The source is developed separately.

## What you need

- **macOS 26 or newer.** Checked rather than assumed: the bundled inference
  engine is built with a minimum of macOS 26.0. On anything older the browser
  installs and browses normally, then fails the first time you ask it a
  question.
- **An Apple Silicon Mac** (M1 or later). Intel is not supported — there is no
  unified memory or Apple Silicon GPU, so the model would run on CPU at
  single-digit tokens per second.
- **Memory:** 8 GB minimum, 16 GB comfortable. The model is held in memory
  while you chat with it.
- **Disk:** about 4 GB — roughly 110 MB for the app, the rest for the model it
  downloads on first run.

## Installing

Builds are not yet signed with an Apple Developer ID, so macOS will refuse the
first launch and say the app is damaged or from an unidentified developer. It
is neither; it is unsigned. Removing the quarantine flag macOS attaches to
anything downloaded is what gets past it:

```
xattr -dr com.apple.quarantine /Applications/JamunBrowser.app
```

That command changes nothing else about the app or your Mac. If macOS still
blocks it, open **System Settings → Privacy & Security** and click **Open
Anyway** next to the message about JamunBrowser. Both steps go away once the
build is signed and notarized.

## Reporting something broken

Open an issue here. Please say which version you are on — it is in the ⋮ menu
under "Check for updates…" — and what you were doing.

Crash reports are collected inside the app under "View and send crash
report…". Nothing is uploaded on its own: sending one composes an email you
complete yourself, and the report excludes your history, page content and chat.
