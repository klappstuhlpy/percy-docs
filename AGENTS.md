> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

This site documents **Percy**, a multipurpose Discord bot, and the **Klappstuhl.me** platform that hosts it. The source code lives in two sibling repos (`Percy-v2`, `klappstuhl_me`); this repo is docs-only. When a user-facing command, AI feature flag, or API endpoint changes there, update the matching page here.

## Terminology

- Say **server** (not "guild") in user-facing prose; "guild" is fine only in API paths where the code uses it.
- Say **member** for a user in a server, **moderator** for staff.
- Refer to commands in the slash form with code formatting: `/tag find`.
- The bot is **Percy**; the platform/API is **Klappstuhl.me**.

## Style preferences

- Use active voice and second person ("you").
- Keep sentences concise — one idea per sentence.
- Use sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Code formatting for command names, file names, paths, and code references.
- Prefer the Mintlify components already used here: `<Note>`, `<Warning>`, `<Tip>`, `<Steps>`, `<AccordionGroup>`, `<CardGroup>`, `<ParamField>`.
- For API endpoints, lead with method + path, then params (`<ParamField>`), then a `curl` example and a response/error table.

## Content boundaries

- **Document:** every user-facing feature and command, and the optional AI layer.
- The **Percy internal API** is **not documented here** — it's private infrastructure (localhost, shared bearer token). Contributors use the bot's self-hosted Scalar reference at `http://127.0.0.1:8090/docs`. The API Reference tab holds only the "Public API — coming soon" page (`api-reference/introduction.mdx`); the future public API reference will be served at `percy.klappstuhl.me/api/docs`, not from this repo.
- The **public Klappstuhl.me platform API** is **out of scope here for now** — it will get its own separate page later. Its live reference is the Scalar page at `klappstuhl.me/api/docs`.
- **Never document secrets:** tokens, `.env` values, internal hostnames/ports, or anything that would help bypass auth.
- Don't invent commands or endpoints — mirror what the code actually exposes.
