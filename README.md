# ASR Memory

[한국어](README.ko.md) · [日本語](README.ja.md)

ASR Memory is shared memory for your AI tools, run as a hosted remote MCP server. Save a decision in one tool and find it, word for word, from another.

This repository holds documentation, agent instructions and examples. The server source is not public.

- Website: https://asrmemory.com
- MCP endpoint: `https://asrmemory.com/mcp` (Streamable HTTP, OAuth 2.1)
- Official MCP Registry: `com.asrmemory/asr`

## Connect in three steps

1. Add `https://asrmemory.com/mcp` as a remote MCP server (custom connector) in your AI tool.
2. Sign in when the login page opens (email, Google, Kakao or GitHub). No key to copy.
3. Ask the tool: "Save to ASR: we chose Postgres for billing." Then, in another tool: "What did we decide about billing?"

Tools that cannot open a login page can connect with an API key issued in the dashboard (https://asrmemory.com/app/). Step-by-step guides for each client: https://asrmemory.com/en/docs.html

To see the project dashboard without signing up, open the demo: https://asrmemory.com/madang/?demo

## Tools (22)

| Tool | What it does |
|---|---|
| `memory_save` | Save a memory as written, with who saved it and when it happened |
| `memory_search` | Search by meaning and keywords |
| `memory_card` | Show one memory in full |
| `memory_recall_daily` | Recall what happened on a date |
| `wake_up` | Brief a new session on recent work |
| `memory_stats` | Counts by drawer and tool |
| `memory_retag` | Change a memory's drawer |
| `memory_delete` | Move a memory to the trash |
| `memory_trash` | List the trash |
| `memory_restore` | Restore from the trash |
| `memory_purge` | Permanently delete (asks first) |
| `memory_export` | Export your memories as JSON Lines |
| `secret_save` / `secret_get` | Store and read an encrypted value |
| `promise_start` / `promise_list` / `promise_resolve` | Track a goal day by day; only you mark the result |
| `asr_send` | Send a task to another tool |
| `asr_handoff` | Hand off unfinished work when a session ends |
| `asr_inbox` | See and take tasks sent to you |
| `asr_done` | Close a task with its result |
| `asr_tidy` | Save a project status summary |

## Agent instructions

[AGENTS.md](AGENTS.md) is a set of rules to paste into `CLAUDE.md`, `AGENTS.md` or `GEMINI.md` so long-running agents read memory at the start, save decisions as they go, and hand off work between tools. It also works without ASR. Korean: [AGENTS.ko.md](AGENTS.ko.md), Japanese: [AGENTS.ja.md](AGENTS.ja.md).

For chat apps (claude.ai project instructions, ChatGPT custom instructions), use the short 11-line version: https://asrmemory.com/en/docs.html#guide

## Your data

- Each account has its own memory space. Cross-account access tests run on every deployment, and the deployment stops if any fails.
- Deleted memories go to the trash first and can be restored. Permanent deletion is a separate, explicit step.
- You can export everything with `memory_export` and delete your account from the dashboard.
- Where data goes (database, server, embedding and classification providers): https://asrmemory.com/en/privacy.html
- Do not store passwords, keys or children's conversations as plain memories. Use `secret_save` for sensitive values.

## Price

Free during the beta, up to 1,000 memories per account. Searching, recall and export are not counted. Project summaries saved with `asr_tidy` do not count toward the limit.

## Feedback

Open an issue in this repository, or email idoweddings@naver.com.

## License

Documentation and agent instructions in this repository: CC BY 4.0. Example code in `examples/`: MIT. See [LICENSE](LICENSE).
