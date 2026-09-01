# HubPeople Agentic Toolkit

An AI teammate for your HubPeople brands. Connect once and work across your whole
portfolio — pages edited as ordinary files on your own machine, every change pushed
deliberately and proved after it lands.

## What it is

The toolkit is a workspace folder your AI assistant works in. It carries the operating
guide the assistant follows, the skills it works with — building pages, auditing a
site, starting a brand from nothing — and the folder structure your brands are checked
out into. It connects to the HubPeople platform through one connection and one token;
there is nothing else to install.

## Install

The toolkit is a folder. Installing means: get the zip, extract it **where you want
the folder to live** — it creates `hubpeople-toolkit/` itself, so there is no need to
make a folder for it first — set your token once, then open that folder.

### Let your AI assistant do it (recommended)

Open an assistant session wherever you keep your projects and say:

> Install the HubPeople agentic toolkit from
> https://github.com/Hubpeople-Limited/hubpeople-agentic-toolkit — download the
> latest release's `agentic-toolkit-*.zip` asset, verify it against the SHA256 in the
> release notes, and extract it here.

Then set your token (step 3 below) and open the new `hubpeople-toolkit/` folder in a
fresh session.

### By hand

1. Download `agentic-toolkit-<version>.zip` from the
   [latest release](../../releases/latest) — the named asset, not "Source code".
2. Extract it where you want the workspace to live. It creates `hubpeople-toolkit/` —
   that folder is permanent: your brands, notes and history live inside it.
3. Set your HubPeople token once per machine: the Connecting section of the
   `README.md` **inside the folder** has the two commands (the variable is
   `HUBPEOPLE_PAT`). Then restart your editor completely — a running program keeps
   its old environment.
4. Open the `hubpeople-toolkit/` folder in your assistant and approve the HubPeople
   connection when asked.

### Open the folder itself

**Open `hubpeople-toolkit` — that exact folder, not the one holding it.** This is the
easiest thing to get wrong and the hardest to spot. From a folder above it the assistant
reads no operating guide and gets no connection, and nothing tells you so: it simply
behaves like an assistant that has never heard of any of this. If a first session seems
not to know what the toolkit is, check which folder is open before you check anything
else.

### Which app am I opening it in?

- **Claude Desktop, the Code tab** — where we would start. It opens the folder the same
  way the others do, and it can show you a page in a browser pane beside the work while
  you build it, reading the files on your machine so what you see is the change you have
  not pushed yet. On Windows it needs Git for Windows installed first, and the app
  restarted afterwards.
- **Claude Code** — terminal or the VS Code extension. Same behaviour, and the
  connection configures itself from the folder; there is no browser pane, so open a page
  file from disk when you want to look at one.
- **Claude Desktop, the Cowork tab** — not this one. Cowork takes its connections from
  your claude.ai account rather than from the folder, so it reaches neither the
  workspace nor the skills and scripts in it.
- **Other assistants** (Codex, Gemini CLI, and anything that reads `AGENTS.md`):
  open the folder — the operating guide loads from `AGENTS.md`. Register the
  HubPeople MCP server your client's own way, using the address and token variable
  shown in the folder's `.mcp.json`.

## When it does not connect

Work down this list. The first two cover almost everything.

1. **Did you restart the editor, or only reload the window?** A program keeps the
   environment it started with, so a token set while the editor was already running is
   invisible to it. Close it completely and reopen.
2. **Are you in the right folder?** As above: the one containing `AGENTS.md`.
3. **Is the token reaching the editor?** In its own terminal, `echo $env:HUBPEOPLE_PAT`
   on Windows or `echo $HUBPEOPLE_PAT` on macOS and Linux. Empty means the editor cannot
   see it, which is nearly always cause 1.
4. **Did you decline the connection prompt?** Assistants generally ask once per folder
   and remember the answer. In Claude Code, `claude mcp reset-project-choices` clears it
   so you are asked again.

If the connection is up but a brand you expected is missing, that is account access
rather than setup: the assistant sees exactly the brands your HubPeople login does.

## Upgrading

Ask your assistant to upgrade, or follow the Upgrading section of the `README.md`
inside your workspace. An upgrade replaces only the toolkit's own files — everything
of yours stays exactly as it is. Each release's notes on the
[Releases](../../releases) page say what changed.

## Security

Please report suspected vulnerabilities as described in [SECURITY.md](SECURITY.md),
not through a public issue.

## Licence

See [LICENSE](LICENSE). The toolkit is for use with the HubPeople platform by
HubPeople partners and customers.
