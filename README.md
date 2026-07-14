
# Junê — Downloads & Getting Started

**Junê** turns the files, notes, and documents you give it into a private, searchable **knowledge
graph** that lives on your own machine. Point it at a folder, a PDF, a spreadsheet, or a screenshot,
and Junê pulls out the people, places, organizations, and ideas inside — and connects them. Instead
of a pile of files, you get a map of what you know, that you can search and reason over.

And as of **v0.0.4**, that map is something your **AI agents can use too**: connect Claude Desktop
(or any MCP agent) to your graph with one click, and it gains a memory — cited answers from your
data, and the ability to remember new things into it.

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
5. **Connect your AI agent.** Give Claude Desktop (or any MCP agent) a memory backed by your graph —
   see the next section.
6. **(Pro) Enrich what you already built.** Added Pro later? Hit **Enrich** on a canvas and Junê
   re-processes it with the richer extraction — no need to re-upload.

---

## Give your AI agent a memory (MCP) — new in v0.0.4

Junê's engine runs privately on your machine — and it speaks **MCP** (the Model Context Protocol,
the open standard AI apps use to reach outside tools). That means Claude Desktop, Claude Code, and
a growing list of agents can plug straight into your graph.

**To connect Claude Desktop:**

1. Install the free connector once: `pipx install june-mcp` (or `pip install june-mcp`) in a
   terminal. It's a thin, open-source bridge —
   [PyPI](https://pypi.org/project/june-mcp/) · [source](https://github.com/Junemind/june-mcp).
2. In Junê, open **Settings → Connect an agent (MCP)**, pick (or create) a **memory canvas** for
   the agent, and click **Install into Claude Desktop**. Junê merges the entry into Claude's config
   without touching anything else, and saves a backup of your previous config next to it.
3. Fully quit Claude Desktop and reopen it — the **june** server appears with its tools.

**What the agent can do with it:** ask questions and get **answers cited from your graph** (with
an honest "not found" when your graph doesn't know, instead of a guess), search passages, browse
entities and their connections, **remember** new facts straight into the canvas you chose (watch
them appear in the Explorer), file longer text in as documents, and merge duplicate entities.

**Other MCP hosts:** the pane's **Copy config snippet** button gives you the same server entry —
one command, three plain values — for Claude Code, Cursor, or anything else that speaks MCP.

**Safety valves:**

- **Local-only:** the connector talks to the engine on `127.0.0.1` — nothing about your graph
  leaves your machine through this feature.
- **No secrets in the agent's config:** if you use your own LLM key for answers, it stays inside
  the app and is never written into any agent's configuration.
- **Read-only mode:** add `JUNE_READONLY=1` to the entry and the agent can look but never write.
- **File access is opt-in:** agents can only send text unless you explicitly grant a folder.
- **Health check:** `june-mcp --doctor` verifies the connection end-to-end and shows the engine's
  edition (Pro connections carry a `june-pro` tag).

---

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

As of v0.0.4 the richer extraction covers **text you write in** too — notes, pasted facts, and
everything your connected agent *remembers* — not just uploaded files. Free users keep Junê's fast,
fully-local built-in extraction; Pro adds the richer hosted step and one-click **Enrich** for graphs
you've already built.

> **On-device is available for *media*, not entities.** Reading text out of images and audio (OCR /
> transcription) *does* offer a fully on-device mode that sends nothing — see **Media extraction**
> above. The Pro entity step is the part that runs hosted on desktop.

---

## Pro

Junê is free to use. **Pro** adds:

- **Richer entities** — more precise people, organizations, and places, for a cleaner, better-connected graph — across uploads *and* written/remembered text. The heavy step runs hosted; your graph stays on your machine (see above).
- **Enrich existing graphs** — one click to re-process a canvas you already built (agents can trigger it too).
- **A usage meter** — **Settings → Account** shows hosted extractions used against your monthly allowance.
- **Visible everywhere** — connected tools see your edition (`june-mcp --doctor` shows `june-pro`).

**To turn on Pro:** subscribe on the website, and you'll be emailed an **activation code**. In the
app, open **Settings → Account**, paste the code, and Pro switches on (and stays on while your
subscription is active). Signing in with the same email restores Pro on any device.

## Privacy

Your knowledge graph is stored **locally** on your device — always, on Free and Pro alike. Pro's
hosted entity step sends **only the text being analyzed**, never the graph. On-device media
extraction sends **nothing** at all. The agent connection is **local-only** (`127.0.0.1`) and puts
no secrets in any agent's config.

## Supported platforms

- ✅ macOS on Apple Silicon (M-series), macOS 12+
- ✅ Windows 10 / 11, 64-bit
- ⏳ Intel Macs and Linux — planned, not packaged yet

## What's new

Each [release](https://github.com/Junemind/June_releases/releases) has its own notes. The current
release is **v0.0.4 — with MCP**: connect Claude Desktop and any AI agent to your graph in one
click, Pro's richer extraction now covers remembered text, and your plan is visible to connected
tools.

---

## Where's the source code?

Junê's engine is closed-source by design. The public artifacts are
[`june-bench`](https://github.com/Junemind/june-bench) — a pip-installable suite that
reproduces Junê's published head-to-head results (matching accuracy at 20–25× lower
cost) on public datasets, end to end, on your own machine — and
[`june-mcp`](https://github.com/Junemind/june-mcp), the open connector that plugs Junê
into any MCP-capable agent.

Questions or a bug? [Open an issue](https://github.com/Junemind/June_releases/issues). Thanks for
using Junê. 🌒
