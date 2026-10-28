---
name: claude-code-vscode-handoff
description: Use when this user asks to send Markdown, notes, or a task to Claude Code, especially for Notion publication or continuing a visible VS Code conversation.
---

# Claude Code in VS Code: user-specific handoff

## User preference

For this user, “傳給 Claude Code” means the visible Claude Code conversation inside VS Code, unless they explicitly select another route. Codex prepares the material and task; Claude Code performs the requested downstream work, such as Notion publication.

Do not substitute `mcp__claude__claude_query`, a headless CLI, a new background session, or direct Notion writes merely because those tools are convenient. Those sessions can have different permissions, history, and destinations. Do not ask this user to repeat their established VS Code preference.

## Workflow

1. Save the deliverable and a concise task Markdown in the current workspace. Include absolute paths, the requested outcome, relevant sources, known destination, scope boundaries, and acceptance criteria. Treat a previously chosen destination as specific to its topic; do not automatically send unrelated notes there.
2. Use the supported computer-use interface to inspect VS Code and its Claude Code sessions. On this Mac, prefer `/Applications/Visual Studio Code.app` when the bundle ID is ambiguous. Read current UI state before choosing a conversation or input field.
3. Open the source Markdown in VS Code. Select a relevant existing Claude conversation using its visible title and context. If there is no relevant conversation, start a new visible Claude Code session in the appropriate workspace. Do not append an unrelated task to the currently selected chat just because it is open; do not interrupt an active task.
4. Send a concise instruction referencing the task file. Preserve the user's authorization without broadening it. For Notion, require destination verification, checking for an existing same-topic page, preserving other content, and reading back the result. Do not change permissions or retrieve credentials to bypass a blocked connection.
5. Verify the message appears in the intended conversation and execution begins. If following through to publication, obtain the returned Notion URL and read-back result. Report “已交接” separately from “已建立並驗證”. A file opened or text pasted without submission is not a completed handoff.

## If blocked

If VS Code, Claude Code, the correct conversation, or its input cannot be accessed, retain the files and report the exact blocker. Do not silently switch execution channels or claim that background-session permission errors apply to the user's VS Code session. Ask only for information necessary to identify the destination or resolve the observed blocker.

## Decision checks

| Situation | Expected action |
|---|---|
| “把這份 Markdown 傳給 Claude Code 建立 Notion” | Visible VS Code handoff; no headless substitute |
| An unrelated EIS chat is selected | Find a relevant chat or start a visible session |
| VS Code is inaccessible | Save task and report blocker; no route substitution |
| User explicitly requests the Claude MCP connector | Follow that explicit route for this request |
| A prior topic had a Notion destination | Reuse only when current context supports it |
