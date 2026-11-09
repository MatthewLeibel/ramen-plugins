---
name: ramen-memory
description: Use the person's own RAMen Memory whenever an answer depends on them (their family, work, projects, rules, preferences, or anything they told an AI before), save lasting facts they share, and save or continue long work as a RAMen thread so it goes on in a fresh session or another app. One memory shared across Claude, ChatGPT and their other AI apps.
---

# RAMen Memory

RAMen Memory is the person's own memory, shared by their AI apps (Claude, ChatGPT, and RAMen's local models when they
run RAMen on a computer). It keeps the lasting things they said, with when they said them.

## recall

Call `recall` before you answer anything that depends on who the person is or on what they told you or another AI
before, for example:

- questions about themselves, their people, their work, their projects or their routines ("What's my usual order?",
  "Who is Ravi?", "Plan dinners for Jonah's night shifts")
- their rules and preferences ("in my usual format", "the way I like it", units, things to leave out)
- anything that refers back ("as I said", "like last time", "my starter")

Pass their question in their own words. Use what comes back as what you know about them. When it answers "You haven't
told me that", say you don't know rather than guess, and ask. When two things it returns disagree, the later one is
what holds now.

## remember

Call `remember` when the person asks you to remember something, or tells you a lasting fact about themselves that they
would expect you to know next time (a new address, a new routine, a name). Save one clear sentence in their words.
RAMen learns it during its next `ramen sleep`.

## save_thread, resume_thread, recall_thread (RAMen Endless)

A long session re-reads everything said so far on every turn. When the person wants to go on in a fresh session or in
another app (Claude, ChatGPT, Codex, any app with RAMen Memory), or the session has grown long, call `save_thread`
with where the work stands: the goal, the values that can change (with what they were before), the facts, the
decisions and why, what is still open, and the latest version of everything you wrote together, word for word. Then
tell them to start fresh and say "Continue my RAMen thread" with its name.

When a session starts with "continue my RAMen thread ..." or asks to pick up earlier work, call `resume_thread` and go
on from it as if it were this session. For a draft's full text or a detail it does not show, call `recall_thread`.
Saving again under the same name updates the thread: values change and keep what they were, the open list is replaced.

## forget

Call `forget` when the person asks you to forget something. Pass a few words the notes contain, and tell them what
was deleted. To delete a saved thread, pass `thread: ` and its name.

## memory_status

Call `memory_status` when they ask what RAMen knows or whether it is set up.

## When it is not there

If the tools are missing or ask the person to connect, tell them to connect RAMen Memory in their connectors and sign
in with their RAMen Pro license key (https://getramenai.com/#pricing).
