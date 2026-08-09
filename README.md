# Session Recap

> **Recap your Claude Code session at a glance.**

Session Recap is a minimal slash command for Claude Code that generates a readable recap of the current work session: what was done, in what order, where the project stands, and what to pick up next time.

## Why?

A Claude Code session can quickly spread across several threads, fixes, and decisions. Without a recap, it is easy to lose track: what was done, in what order, what is still open.

Session Recap reads back the current conversation and produces a structured summary, so you can pick the work back up quickly, in the current session or the next one.

## Good for

Session Recap is useful when you want to:

* Quickly review what was done during a session.
* Understand the chronological flow of a long session.
* Know clearly where the project stands right now.
* Identify what to pick up in the next session.

## How to use it

In a Claude Code session, type:

```txt
/session-recap
```

## What the command does

The command covers the work done since the last recap generated in the conversation, or otherwise since the start of the conversation. It does not summarize the full project history, and it does not invent actions, decisions, or timestamps.

It produces four sections:

* **Session Summary**: two sentences giving an overview.
* **Session Timeline**: a chronological table by topic, with timestamps.
* **Where the project stands**: a `✅ Done` / `🚧 In progress` / `❓ Open questions` table.
* **👉 Next step**: a single sentence on the most logical action to take next.

For a long session, the recap groups related actions into meaningful topics instead of logging everything: trivial commands, inconsequential exploration, and abandoned attempts with no impact are ignored.

## How is this different from `/recap`?

Claude Code's built-in `/recap` gives a brief summary when you return to a session.

Session Recap goes deeper: a full chronological breakdown, a project status table, and a next step, always in the same four sections.

## Limitations

Session Recap does not modify any project file: it only produces recap text.

The recap is based solely on the context actually available in the current Claude Code conversation. It has no knowledge of past sessions that are not part of the current context, and it never invents a timestamp it cannot determine reliably.

## Install in Claude Code

### Method 1: copy the command file

Copy [session-recap.md](.claude/commands/session-recap.md) into your project's `.claude/commands/` folder.

### Method 2: install using Claude Code

You can ask Claude Code to handle the installation for you. Paste this prompt in a Claude Code session:

[install-session-recap-for-claude-code.md](prompts-for-installation/install-session-recap-for-claude-code.md)

## Use in a regular AI chat (ChatGPT, Claude, Gemini...)

If you just want to use Session Recap in a regular chat, without installing it in a project or a coding tool, paste this version into a conversation:

[session-recap-ai-chat-version.md](prompts-for-ai-chat/session-recap-ai-chat-version.md)

Once pasted, write exactly `recap` at any point in the conversation to get a recap of the current session. You can ask for it several times: each recap only covers what happened since the previous one.

This instruction only applies to the current conversation. If you open a new conversation, paste it again.

## Repository structure

```txt
session-recap/
├── README.md
├── LICENSE
├── .gitignore
├── .claude/
│   └── commands/
│       └── session-recap.md
├── prompts-for-installation/
│   └── install-session-recap-for-claude-code.md
└── prompts-for-ai-chat/
    └── session-recap-ai-chat-version.md
```
