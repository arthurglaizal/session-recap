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
* when a topic covers multiple important items, list them inside `What was done` on **one single line**, each item introduced by `• ` (see `Table cell formatting` below);
* each bullet describes a concrete action, decision, fix, or result; avoid repetition;
* put the timestamp in the last column, in *italics*, in `HH:MM` format, corresponding to the start of the topic block, only if you can determine it reliably from the conversation.

### Table cell formatting

This applies to every table in the output.

A cell is **always one single line of text**. Items inside a cell are separated by `• ` and nothing else: no line break, no `\n`, no HTML tag. Many interfaces render table cells as plain text, so any tag appears literally in the output.

Write a multi-item cell exactly like this:

```
| 1 | **Network guard** | • NETWORK_DELAY raised from 120 to 300 s • Comment rewritten to justify the two pauses • Edit made before launch | *10:32* |
```

Keep each item short so the line stays readable once the line wraps.

### `Where the project stands`

Markdown table with the columns `Status | State` and exactly these three rows, in this order:

* `✅ **Done**`: what is settled, validated, or stable enough;
* `🚧 **In progress**`: what has been identified but is still incomplete;
* `❓ **Open questions**`: questions, trade-offs, or choices still open.

Each `State` cell follows the same `Table cell formatting` rule: one single line, items introduced by `• `. Only mention items that are actually relevant at this stage. Do not artificially fill a category if it is not relevant; use `—` instead of inventing content.

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
* Never use an HTML tag anywhere in the output. Before returning the recap, check that no `<` character remains in any table cell.
* Stay concise and directly readable in the chat.
* This instruction only applies to the current conversation. If I start a new conversation and want the same behavior, I need to paste it again.
