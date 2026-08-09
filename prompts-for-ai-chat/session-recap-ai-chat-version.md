In this conversation, whenever I write exactly the word `recap` (nothing else in the message, no punctuation), generate a readable recap of the current session.

## Scope

Cover what happened **since the last recap you produced in this conversation**, or otherwise **since the start of the conversation**.

Do not summarize beyond this conversation: you have no access to past exchanges in other conversations.

If the session is long, adapt the granularity: group related exchanges into meaningful topics instead of producing an exhaustive log. Ignore trivial questions, inconsequential digressions, abandoned attempts with no impact, and low-value details.

Base everything strictly on what was actually exchanged in this conversation. Do not invent actions, decisions, or timestamps. If you cannot determine a time reliably, leave the cell empty rather than guessing.

## Output format

Produce exactly the following sections, in this order, in Markdown.

### `Session Summary`

Write exactly 2 sentences giving an overview of the session: the main topics covered, the most important decisions or results, and the overall state reached so far. Do not simply repeat the table that follows.

### `Session Timeline`

Markdown table with the following columns:

`| # | Topic | What was done | Time |`

Rules:

* follow chronological order;
* start a new topic when the thread, goal, or phase changes significantly;
* adapt the number of rows to the actual density of the session; for a long session, aim for about 8 to 12 meaningful topics;
* give each topic a short **bold** title;
* use several short bullet points in `What was done` when a topic covers multiple important items, each prefixed with `• ` and kept on a single line;
* each bullet describes a concrete action, decision, fix, or result; avoid repetition;
* put the timestamp in the last column, in *italics*, in `HH:MM` format, corresponding to the start of the topic block, only if you can determine it reliably from the conversation.

### `Where the project stands`

Markdown table with the columns `Status | State` and exactly these three rows, in this order:

* `✅ **Done**`: what is settled, validated, or stable enough;
* `🚧 **In progress**`: what has been identified but is still incomplete;
* `❓ **Open questions**`: questions, trade-offs, or choices still open.

In each `State` cell, use short bullet points, each prefixed with `• ` and kept on a single line. Only mention items that are actually relevant at this stage. Do not artificially fill a category if it is not relevant; use `—` instead of inventing content.

### `👉 Next step`

Outside the table, add exactly one line in this format:

`👉 **Next step**: ...`

A single sentence, indicating the most logical action to take right after this exchange. Do not repeat the full `In progress` list.

## Trigger

* Only apply this format when my message is exactly `recap`, with no other text or punctuation (case-insensitive: `recap`, `Recap`, `RECAP`).
* Outside of this trigger, reply normally to my messages, without generating a recap.
* You may be asked several times in the same conversation: each time, only cover what happened since the previous recap.

## Language

Reply in the language I use in the conversation, translating the section headers and labels accordingly.

## Constraints

* Do not propose an action plan or task list beyond `Next step`.
* Never use HTML tags such as `<br>` anywhere in the output: they are not rendered everywhere and can show up as raw text. A table cell must stay on a single line, with `• ` as the only bullet separator.
* Stay concise and directly readable in the chat.
* This instruction only applies to the current conversation. If I start a new conversation and want the same behavior, I need to paste it again.
