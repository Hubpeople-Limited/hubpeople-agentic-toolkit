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

Three steps. The folder you open in the first one is the toolkit from then on.

1. **Make an empty folder called `hubpeople-toolkit`** and open it in your assistant
   — in the Claude desktop app, the Code tab.
2. **Connect your account**, once, ever — below.
3. **Let your assistant install the toolkit into that folder**, then start a new chat
   in the same place. Your assistant reads its instructions when a session starts,
   which is why the new chat matters.

### Get the toolkit

#### Let your AI assistant do it (recommended)

With the empty `hubpeople-toolkit` folder open, say:

> Set up the HubPeople toolkit in this folder.
>
> 1. Download https://github.com/Hubpeople-Limited/hubpeople-agentic-toolkit/releases/latest/download/hubpeople-toolkit.zip
>    and https://github.com/Hubpeople-Limited/hubpeople-agentic-toolkit/releases/latest/download/SHA256SUMS into this folder.
> 2. Check the zip's SHA256 against the line for hubpeople-toolkit.zip in SHA256SUMS. Stop and tell me if it does not match.
> 3. Extract it. The zip holds one top-level folder; put that folder's contents directly in this folder,
>    so AGENTS.md, VERSION and MANIFEST sit here at the top level.
> 4. Delete the zip, SHA256SUMS and any empty folder left behind, then list what is here.
> 5. Tell me the VERSION you installed and that I should start a new chat in this folder.
>
> Do not change anything on my HubPeople account; this is setup only.

Say yes to the cards that appear: they are the assistant asking to fetch and extract
the file. Then start a new chat in the same folder.

#### By hand

1. Download [`hubpeople-toolkit.zip`](../../releases/latest/download/hubpeople-toolkit.zip)
   — the newest release, always at that address.
2. Extract it where you want the workspace to live. It creates `hubpeople-toolkit/` —
   that folder is permanent: your brands, notes and history live inside it.
3. Open `hubpeople-toolkit/` itself in a new session, not the folder holding it.

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

### Start a new chat in `hubpeople-toolkit`

**A session that starts inside the folder that holds `AGENTS.md`.** Your assistant reads
the operating guide when a session starts, so the session that did the installing will
not pick it up — even after the files appear. Start a new one in the same folder. If
you extracted by hand, that folder is `hubpeople-toolkit` itself, not the one holding it.

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
- **Claude Desktop, the Cowork tab** — with `hubpeople-toolkit/` added as its working
  folder it reads the operating guide and the files in the workspace, but it does not
  load the skills. Use it for looking at a brand and for small copy changes, and the
  Code tab for building pages.
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

Your assistant checks once a session whether a newer release exists and tells you in
one line if so; it never upgrades unless you ask. Ask it to upgrade, or follow the
Upgrading section of the `README.md` inside your workspace. An upgrade replaces only
the toolkit's own files — everything of yours stays exactly as it is. Each release's
notes on the [Releases](../../releases) page say what changed, and the newest zip and
its hash are always at
[`hubpeople-toolkit.zip`](../../releases/latest/download/hubpeople-toolkit.zip) and
[`SHA256SUMS`](../../releases/latest/download/SHA256SUMS).

One step an upgrade cannot do for you: if your workspace still holds a `.mcp.json` from
an older version, replacing files will not remove it. Follow point 3 above — confirm
your account connection from outside the folder first, then delete it.

## Security

Please report suspected vulnerabilities as described in [SECURITY.md](SECURITY.md),
not through a public issue.

## Licence

See [LICENSE](LICENSE). The toolkit is for use with the HubPeople platform by
HubPeople partners and customers.
