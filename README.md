# HubPeople Agentic Toolkit

An AI teammate for your HubPeople brands. Connect once and work across your whole
portfolio — pages edited as ordinary files on your own machine, every change pushed
deliberately and proved after it lands.

## What it is

The toolkit is a workspace folder your AI assistant works in. It carries the operating
guide the assistant follows, the skills it works with — building pages, auditing a
site, starting a brand from nothing — and the folder structure your brands are checked
out into. It reaches the HubPeople platform through a connection you add once to your
Claude account; there is nothing to install and no key to keep.

## Install

Three steps, and the third is the one people miss.

1. **Get the toolkit** — below. It extracts to a folder called `hubpeople-toolkit/`.
2. **Connect your account**, once, ever — below.
3. **Open `hubpeople-toolkit/` itself in a new session.** Not the folder you extracted
   it into. Your assistant reads its instructions when a session starts, so it has to
   start in there.

### Get the toolkit

#### Let your AI assistant do it (recommended)

Open an assistant session wherever you keep your projects and say:

> Install the HubPeople agentic toolkit from
> https://github.com/Hubpeople-Limited/hubpeople-agentic-toolkit — download the
> latest release's `agentic-toolkit-*.zip` asset, verify it against the SHA256 in the
> release notes, and extract it here.

#### By hand

1. Download `agentic-toolkit-<version>.zip` from the
   [latest release](../../releases/latest) — the named asset, not "Source code".
2. Extract it where you want the workspace to live. It creates `hubpeople-toolkit/` —
   that folder is permanent: your brands, notes and history live inside it.

### Connect your account (once, ever)

Not per machine and not per folder. Do it once and every session you open afterwards,
on any computer you sign into, already has it.

1. In Claude, open **Settings → Connectors** and choose **Add custom connector**.
2. Give it the address `https://mcp.hubpeople.ai/mcp`.
3. Sign in with the HubPeople login you already use.

There is no token to copy, nothing to paste into your system, and nothing to set up
again on your second machine.

**Not sure whether you have already done it?** You do not have to find out first. Open
the workspace and your assistant tells you where you stand in its opening words — it
reports what it is connected to before it does anything else. Or check it yourself with
`claude mcp list` in a terminal: a HubPeople line beginning `claude.ai ` is your account
connection.

### Open `hubpeople-toolkit` itself, in a new session

**That exact folder, not the one holding it, and a session that starts inside it.** This
is the easiest thing to get wrong and the hardest to spot. Your assistant reads the
operating guide when a session starts, so a session already running in the folder above
will not pick it up — even after the files appear. Start a new one in
`hubpeople-toolkit`.

From anywhere else the assistant reads no guide, and nothing tells you so: it simply
behaves like an assistant that has never heard of any of this. If a first session seems
not to know what the toolkit is, check which folder is open before you check anything
else.

### Which app am I opening it in?

- **Claude Desktop, the Code tab** — where we would start. It opens the folder the same
  way the others do, and it can show you a page in a browser pane beside the work while
  you build it, reading the files on your machine so what you see is the change you have
  not pushed yet. On Windows it needs Git for Windows installed first, and the app
  restarted afterwards.
- **Claude Code** — terminal or the VS Code extension. Same behaviour, and the same
  account connection; there is no browser pane, so open a page file from disk when you
  want to look at one.
- **Claude Desktop, the Cowork tab** — not this one. Cowork does not open a folder on
  your machine, so it reaches neither the workspace nor the skills and scripts in it,
  even though your connection is there.
- **Other assistants** (Codex, Gemini CLI, and anything that reads `AGENTS.md`): the
  operating guide loads for them from `AGENTS.md`, but connecting them to the HubPeople
  platform is not supported yet — the sign-in these clients use is not one the platform
  accepts today. Claude is the supported route.

## When it does not connect

Work down this list. The first two cover almost everything.

1. **Are you in the right folder?** As above: the one containing `AGENTS.md`.
2. **Is the connector actually on your account?** In a terminal, run `claude mcp list`.
   A HubPeople line beginning `claude.ai ` is your account connection. No such line
   means it was never added, or it was added on a different Claude account from the one
   you are signed into here.
3. **Is there a connection file in the folder?** If your workspace contains a
   `.mcp.json` — older versions of this toolkit shipped one — it **overrides your
   account connection** for that folder, silently, and nothing looks wrong while it
   does. Run `claude mcp list` **from any folder outside the workspace**: inside it, the
   file is what answers, so the check there cannot tell you about your account. Once you
   can see the connector working from outside, the file can be deleted. Not before —
   until then that file is what is connecting you.
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

One step an upgrade cannot do for you: if your workspace still holds a `.mcp.json` from
an older version, replacing files will not remove it. Follow point 3 above — confirm
your account connection from outside the folder first, then delete it.

## Security

Please report suspected vulnerabilities as described in [SECURITY.md](SECURITY.md),
not through a public issue.

## Licence

See [LICENSE](LICENSE). The toolkit is for use with the HubPeople platform by
HubPeople partners and customers.
