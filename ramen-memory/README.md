# RAMen Memory for Claude

RAMen Memory gives Claude one memory that follows you across Claude's apps, your devices and your local AI (ChatGPT next).
While you chat, Claude saves the lasting things you tell it (your people, your work, your rules and how you like
things) and looks them up when they matter, so you stop explaining yourself again in every new chat. When something
changes, the newer note wins, and when the memory has nothing, Claude says so instead of guessing.

![RAMen](assets/ramen-256.png)

## Install

In Claude Code:

    /plugin install ramen-memory --marketplace MatthewLeibel/ramen-plugins

Then connect it once and sign in with your RAMen Pro license key (get one at https://getramenai.com/#pricing).

In claude.ai and the Claude desktop and phone apps, add it as a custom connector instead: Settings > Customize >
Connectors > Add > Add custom connector, with the address https://ramen-online.matthewsleibel.workers.dev/mcp. Then
add the one line from https://getramenai.com/#online-setup to Settings > Your Claude > Instructions: without it,
Claude uses its own memory unless you name RAMen; with it, Claude checks RAMen before answering anything about you
and saves what you tell it, in every chat (we tried both on claude.ai).

## What it does

- `recall`: looks up what you told Claude or your other AI apps before, with RAMen's own lookup, oldest first so the
  newest holds.
- `remember`: saves a lasting fact you tell Claude, in your words.
- `forget`: deletes what you ask Claude to forget.
- `memory_status`: says how much is kept and which computers are linked.
- In Claude Code, the skill tells Claude when to use them: before answering anything that depends on you, and when
  you share something it should keep. In claude.ai, the line in your instructions does that.

## What it sends and where

- The plugin connects Claude to RAMen Online (https://ramen-online.matthewsleibel.workers.dev/mcp), RAMen's MCP
  server on Cloudflare, over HTTPS with OAuth. You sign in with your RAMen Pro license key; RAMen keeps only a one-way
  hash of it.
- Claude sends RAMen Online only what it saves (`remember`) and what it looks up (`recall`), never your whole
  conversations. Your memory is kept encrypted at rest, never read, sold or used for training.
- With RAMen on a computer, `ramen online` links it to the same memory: what RAMen Sleep learns from your local
  conversations goes up, and what you told Claude comes down to your local models. To keep everything on your
  computer instead, use RAMen's local connector (`ramen connect claude-desktop`, or `claude mcp add ramen-memory --
  ramen mcp`).
- Delete it any time: ask Claude to forget something, or run `ramen online --forget`.

## Privacy and support

Privacy policy: https://getramenai.com/privacy.html. Terms: https://getramenai.com/terms.html. Questions:
support@getramenai.com.
