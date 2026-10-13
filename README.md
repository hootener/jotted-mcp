# jotted-mcp

An [MCP](https://modelcontextprotocol.io) server that lets Claude Code look at
your [Jotted](https://jotted.ink) jots as images. Capture a screen area in
Jotted, circle the problem, then tell Claude "look at my latest jot".

## Setup

Needs Node 22+ and the Jotted desktop app.

```sh
git clone https://github.com/hootener/jotted-mcp.git
cd jotted-mcp && npm install
claude mcp add jotted -- node "$PWD/server.mjs"
```

Open a new Claude Code session and try "look at my latest jot" or
"show me brave-gullible-snail".

## Tools

- `list_jots` — recent jots: name, id, time, stroke and image counts
- `get_jot` — render one jot to PNG, by name, part of a name, or ULID
- `get_latest_jot` — render the most recently updated jot

It reads the desktop app's jots folder directly (override with
`JOTTED_JOTS_DIR`) and never writes. Browser-version jots live in IndexedDB
and are not visible to it.

Published automatically from the Jotted release pipeline (Jotted 2026.10.13.014).
Issues: https://github.com/hootener/jotted/issues
