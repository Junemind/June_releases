
# Junê — Downloads & Getting Started

**Junê** turns the files, notes, and documents you give it into a private, searchable **knowledge
graph** that lives on your own machine. Point it at a folder, a PDF, a spreadsheet, or a screenshot,
and Junê pulls out the people, places, organizations, and ideas inside — and connects them. Instead
of a pile of files, you get a map of what you know, that you can search and reason over.

This repository hosts the **installers**. Grab the latest below.

## Download the latest

| Platform | Download |
|----------|----------|
| **macOS** — Apple Silicon (macOS 12+) | [**June-mac-arm64.dmg**](https://github.com/Junemind/June_releases/releases/latest/download/June-mac-arm64.dmg) |
| **Windows** — 10 / 11 (64-bit) | [**June-Setup.exe**](https://github.com/Junemind/June_releases/releases/latest/download/June-Setup.exe) |

These links always point to the newest release. For a specific version, see
[**Releases**](https://github.com/Junemind/June_releases/releases).

---

## Install

- **macOS** — open the `.dmg` and drag **June** into your **Applications** folder, then launch it.
  The app is **signed and notarized by Apple**, so it opens normally with no warning.
- **Windows** — run `June-Setup.exe` and follow the installer. It isn't code-signed yet, so
  **SmartScreen** may warn on first run: click **More info → Run anyway**. After that it opens
  normally every time.

## How to use Junê

1. **Add your stuff.** Open the **Console** and drop in files — text, Markdown, HTML, PDFs, Word
   docs, spreadsheets, even images and audio (see *Media extraction* below). Junê reads each one,
   pulls out the entities, and merges them into your graph. You can keep adding over time; the graph
   grows with you.
2. **Search.** Type a question or a keyword. Junê searches across everything you've ingested and
   returns the passages that matter — not just exact-word matches, but related ideas too.
3. **Explore the graph.** Open the **Explorer** to see how people, places, and topics connect. Click
   a node to see what it's linked to and where it came from.
4. **Organize with canvases.** A **canvas** is an isolated workspace with its own graph. Keep work
   and personal separate, or spin up one per project — nothing leaks between them.
5. **(Pro) Enrich what you already built.** Added Pro later? Hit **Enrich** on a canvas and Junê
   re-processes it with the richer extraction — no need to re-upload.

### Media extraction (images & audio)

Under **Settings → Media extraction** you can let Junê read text out of the images and audio you
add — a screenshot's text, or a voice note's words — so they land in your graph too. Each type can be
set to **On-device**, **Use my LLM** (with a key you provide), or **Off** (the default).

---

## How Pro entity extraction works

Pro sharpens the entities in your graph — more precise people, organizations, and places. On the
desktop app this richer step runs **hosted**: the heavy work is done on June's servers, so the app
stays lightweight (no large model to download). Crucially, **only the text being analyzed leaves your
machine — your knowledge graph is built and stored locally, exactly like Free.** The graph itself
never leaves your device.

- **Needs:** an internet connection and an active Pro subscription.
- **What's sent:** just the text of the chunk being processed, for that one step. Nothing else.
- **What stays local:** everything — the graph, your files, your search.

Free users keep Junê's fast, fully-local built-in extraction; Pro adds the richer hosted step and
one-click **Enrich** for graphs you've already built.

> **On-device is available for *media*, not entities.** Reading text out of images and audio (OCR /
> transcription) *does* offer a fully on-device mode that sends nothing — see **Media extraction**
> above. The Pro entity step is the part that runs hosted on desktop.

---

## Pro

Junê is free to use. **Pro** adds:

- **Richer entities** — more precise people, organizations, and places, for a cleaner, better-connected graph. The heavy step runs hosted; your graph stays on your machine (see above).
- **Enrich existing graphs** — one click to re-process a canvas you already built.
- **A usage meter** — **Settings → Account** shows hosted extractions used against your monthly allowance.

**To turn on Pro:** subscribe on the website, and you'll be emailed an **activation code**. In the
app, open **Settings → Account**, paste the code, and Pro switches on (and stays on while your
subscription is active). Signing in with the same email restores Pro on any device.

## Privacy

Your knowledge graph is stored **locally** on your device — always, on Free and Pro alike. Pro's
hosted entity step sends **only the text being analyzed**, never the graph. On-device media
extraction sends **nothing** at all.

## Supported platforms

- ✅ macOS on Apple Silicon (M-series), macOS 12+
- ✅ Windows 10 / 11, 64-bit
- ⏳ Intel Macs and Linux — planned, not packaged yet

## What's new

Each [release](https://github.com/Junemind/June_releases/releases) has its own notes. The current
release is **v0.0.3** — richer Pro entities, enrich-existing-graph, a usage meter, and reliability
fixes.

---

Questions or a bug? [Open an issue](https://github.com/Junemind/June_releases/issues). Thanks for
using Junê. 🌒
