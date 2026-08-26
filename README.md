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

### Which app am I opening it in?

- **Claude Code** — terminal or the VS Code extension: open the `hubpeople-toolkit`
  folder. The connection configures itself from the folder. This is the recommended
  way to run the toolkit.
- **Claude Desktop** — use the **Code tab** and open the `hubpeople-toolkit` folder;
  it reads the folder's connection setup the same way Claude Code does. The **Cowork
  tab does not read folder configuration** and cannot reach the HubPeople connection
  yet — Cowork support arrives when sign-in-based connection does.
- **Other assistants** (Codex, Gemini CLI, and anything that reads `AGENTS.md`):
  open the folder — the operating guide loads from `AGENTS.md`. Register the
  HubPeople MCP server your client's own way, using the address and token variable
  shown in the folder's `.mcp.json`.

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
