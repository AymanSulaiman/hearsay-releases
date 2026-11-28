# Hearsay

Private meeting transcripts for your Mac. Hearsay records both sides of a call
— your microphone and the other people — and transcribes them **on your Mac**.
No bot joins the meeting, no account, no cloud.

**[⬇ Download Hearsay for Mac (.dmg)](https://usehearsay.app/latest/Hearsay-arm64.dmg)**
(Apple Silicon, macOS 14.4 or later)

## What it does

- **Records calls from any app** — Zoom, Meet, Teams, FaceTime, a browser tab.
  Your voice and theirs are saved as separate tracks.
- **Knows who said what.** Because the two sides are recorded separately, the
  transcript is labelled *Me* and *Them* exactly, with no guessing.
- **Transcribes locally** with Whisper large-v3, tuned against the repetition
  loops ("the architecture of the architecture of…") that make default Whisper
  drop real speech.
- **Small files.** Audio is stored as Opus at about 11 MB per hour, next to
  plain-text transcripts, in ordinary folders you can back up or search.
- Folders, search across every transcript (⌘O), click any line to hear it,
  export to Markdown, and import existing audio or video.

## What leaves your Mac

**Nothing you record.** The only thing Hearsay downloads is the speech model
itself (about 3.1 GB, once, from Hugging Face) on your first transcription.
Recordings and transcripts never leave your Mac. There's no analytics, no
account, and no server.

**Updates, only if you say yes.** On first launch Hearsay asks whether it may
check for new versions. If you agree, once a day it asks GitHub whether a newer
release exists; nothing about you or your recordings is sent. A new version is
never installed silently: you're asked, and Download opens the new `.dmg`.
Change it any time under Hearsay > Check for Updates Automatically.

Your library lives in `~/Documents/Hearsay` (you can move it from inside the
app).

## Install

This early version isn't signed with an Apple Developer certificate yet, so
macOS will block it the first time. That's expected:

1. Open the `.dmg` and drag **Hearsay** to **Applications**.
2. Open Hearsay. macOS says it can't verify the developer — click **Done**.
3. Go to **System Settings → Privacy & Security**, scroll down, and click
   **Open Anyway** next to Hearsay. Confirm with your password.
4. When you first record, allow **Microphone** and **Screen & System Audio
   Recording**. (Hearsay needs the second one to hear the other side of the
   call; it saves audio only, never your screen.)

To check your download wasn't tampered with, compare its checksum with the
`.sha256` file on the release page:

```sh
shasum -a 256 ~/Downloads/Hearsay-*.dmg
```

## Good to know

- **Use headphones.** On speakers your microphone also picks up the other
  side, so their words appear twice.
- **Ask before you record.** Several US states (and many countries) require
  everyone on a call to consent. Hearsay shows a red dot and timer in the menu
  bar while recording, but the other people can't see that — tell them.
- The first transcription waits for the model download (progress shows in the
  bottom-right corner).

## Feedback

Found a bug or want something? [Open an issue](https://github.com/AymanSulaiman/hearsay-releases/issues).
