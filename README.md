

# Junê

**A context engine for your machine.**
Junê turns your files into a private knowledge graph and answers questions over it — locally, by default.

[**⬇ Download for macOS**](https://github.com/Junemind/June_releases/releases/latest/download/June-mac-arm64.dmg) ·
[**⬇ Download for Windows**](https://github.com/Junemind/June_releases/releases/latest/download/June-Setup.exe) ·
[Website](https://june.januraine.ai) ·
[All releases](https://github.com/Junemind/June_releases/releases)

</div>

---

## Download

| Platform | Requirements | Installer |
|----------|--------------|-----------|
| **macOS** | Apple Silicon · macOS 12+ | [`June-mac-arm64.dmg`](https://github.com/Junemind/June_releases/releases/latest/download/June-mac-arm64.dmg) |
| **Windows** | Windows 10 / 11 · 64-bit | [`June-Setup.exe`](https://github.com/Junemind/June_releases/releases/latest/download/June-Setup.exe) |

These links always point at the **latest** release. Older versions and full notes are on the
[Releases](https://github.com/Junemind/June_releases/releases) page.

> This repository holds **only the installers** — Junê's source code is private. The **macOS**
> build is signed + notarized by Apple and opens cleanly; the **Windows** build isn't signed yet,
> so see [Opening it the first time](#opening-it-the-first-time) for its one-time SmartScreen prompt.

---

## What is Junê?

Most tools make you choose between *private* and *useful*. Junê is both. It runs a full retrieval
engine **on your computer**: it reads your documents, builds a knowledge graph out of them, and
answers questions with citations — without sending your data anywhere unless you explicitly turn on
the hosted engine.

- **Local-first & private.** Your files, your graph, and your LLM key stay on your device by default.
- **Deterministic graph.** Junê builds the graph with classic, model-free methods (BM25 + graph
  structure), so ingesting your corpus costs **$0** in API calls.
- **Bring your own LLM.** Plug in any OpenAI-compatible key (OpenAI, a local Ollama / LM Studio
  server, or a proxy) for cited answers and chat — app-wide.
- **Hybrid engine.** Switch between the on-device engine and an optional hosted cloud engine
  whenever you like.

## Features

- **📂 Ingest almost anything.** Markdown, text, HTML, CSV, **Excel (.xlsx)**, **PDF**, and **Word
  (.docx)** — dropped into the Console and merged into one graph.
- **🖼️ Media extraction (OCR + transcription).** Pull text out of **images** and **audio**. Choose
  *On-device* (private) or *Use my LLM* per type, in **Settings → Media extraction**.
- **🔎 Search, explore & ask.** Query your graph, browse entities and connections, and get
  cited answers from your own LLM.
- **🤖 Agent.** A built-in agent that works over your knowledge graph.
- **🔐 Accounts & licensing.** Use it free, or sign in / activate a license for **Pro** — a richer
  on-device entity model, cited answers, and cross-device sync.

## Pricing

- **Free** — the full local-first app, unlimited, fully private.
- **Pro — $10/mo (or $90/yr)** — a richer on-device graph, cited answers & chat, and vault sync.
- **Team — $25/seat/mo** — a hosted engine with shared, isolated workspaces.

Subscribe on the [website](https://june.januraine.ai/#/pricing). After payment you're emailed an
**activation code** — paste it in **Settings → Account** in the app and Pro turns on (and stays on
automatically while your subscription is active). Signing in with the same email restores Pro on any
device.

---

## Install

1. Download the installer for your platform from the table above.
2. **macOS:** open the `.dmg` and drag **June** into **Applications**.
   **Windows:** run `June-Setup.exe` and follow the installer.
3. Launch Junê. On first run you'll be asked how you'd like to use it (local-first by default).

### Opening it the first time

- **macOS** — the app is **signed and notarized by Apple**, so it opens normally — no warning, no
  workaround.
- **Windows** — the build isn't code-signed yet, so **SmartScreen** may appear on first launch.
  Click **More info → Run anyway**. After the first launch it opens normally every time. (A signed
  Windows build is planned; the download link won't change.)

---

## Bring your own LLM

Junê works fully without an LLM (deterministic retrieval). To enable cited answers and chat, add a
key in **Settings → Your LLM**:

- **OpenAI** — `https://api.openai.com/v1/chat/completions` + your key.
- **Local (Ollama)** — `http://localhost:11434/v1/chat/completions`, no key needed.
- **Local (LM Studio)** — `http://localhost:1234/v1/chat/completions`, no key needed.
- **Any** OpenAI-compatible endpoint or proxy.

The same key also powers the optional **"Use my LLM"** media-extraction mode.

---

## Support & links

- 🌐 Website — <https://june.januraine.ai>
- 💳 Pricing & Pro — <https://june.januraine.ai/#/pricing>
- 🐞 Issues & feedback — [open an issue](https://github.com/Junemind/June_releases/issues)


© Junê. Installers only — source is private. Built to keep your context yours. 🌒
