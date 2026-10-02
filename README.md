# X1 Wealth MCP server

X1 is building an AI family office that adapts to your family's financial life, so you don't have to run it all yourself. This MCP server lets the AI assistant you already use work from your X1 household record: the trusts, entities, properties, policies, and documents behind them. Ask a question and the answer comes back with its source attached, or X1 declines.

This repository documents the server. The server itself is operated by X1 Wealth and is not open source.

| | |
|---|---|
| Endpoint | `https://mcp.x1wealth.com/mcp` |
| Transport | Streamable HTTP |
| Sign-in | OAuth with dynamic client registration; X1 API keys for eligible accounts |
| Registry name | `com.x1wealth/x1` in the [official MCP Registry](https://registry.modelcontextprotocol.io) |
| Website | [x1wealth.com](https://x1wealth.com) |

## Connect

Step-by-step guides for each app:

- [Claude](https://x1wealth.com/connect/claude)
- [ChatGPT](https://x1wealth.com/connect/chatgpt)
- [Codex](https://x1wealth.com/connect/codex)
- [Muse](https://x1wealth.com/connect/muse)
- [Any other MCP app](https://x1wealth.com/connect/other)

For any other app, add a remote MCP server named X1 at `https://mcp.x1wealth.com/mcp`, choose Streamable HTTP if asked, and sign in with your X1 account. Apps that run on your own computer connect right away. Web apps connect once X1 has confirmed where their sign-in returns; the [other apps guide](https://x1wealth.com/connect/other) explains how to ask.

You need an X1 account with at least one document in it. [Create a free account](https://x1wealth.com).

## What your assistant can do with X1

- Answer questions about your household record, citing the document and page behind each answer.
- Find and read the documents you keep in X1, and compare what they say.
- Review a capital-call notice: what it asks for, when it's due, and what still needs checking before anyone pays.
- Prepare for a meeting with your advisor, CPA, or attorney from the record you already have.
- Prepare changes to your record. X1 asks for your approval when a step needs it.

X1 does not trade, move money, file taxes, or give professional sign-off.

The tools available depend on your account and on the app you connect from. The server only lists the tools the signed-in person can use. Ask your assistant to call `get_user_capabilities` to see your role and what this connection allows.

## Skills

Open-source skills that teach an agent how to do this work well, with a hard stop before money moves, live in [x1wealth/x1-agent-skills](https://github.com/x1wealth/x1-agent-skills) (Apache-2.0). They install in Claude Code, Codex, Grok Build, and other agents that read skills.

## Privacy and security

- Your assistant only sees what your X1 account is allowed to see, and only after you sign in and approve the connection.
- Sign-in returns only to callbacks X1 has reviewed, plus apps running on your own computer.
- This repository contains no household data, credentials, or server code.

Read the [privacy policy](https://x1wealth.com/legal/privacy-policy). To report a security issue or ask a question, use [x1wealth.com/contact](https://x1wealth.com/contact).

## Registry entry

[`server.json`](server.json) mirrors the manifest published to the official MCP Registry. Directories copy their listing from that record.

## License

The documentation in this repository is licensed under Apache-2.0. The X1 Wealth service and its server are proprietary.
