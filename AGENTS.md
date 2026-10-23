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

- **Document:** every user-facing feature and command, the optional AI layer, and the **public Percy API** (economy, items, inventories, leveling) under the API tab. The API facts come from `percy-dashboard/static/api/openapi.yaml` and `percy-dashboard/src/api/`; its live reference is `https://percy.klappstuhl.me/api`.
- The **Percy internal API** is **not documented here** — it's private infrastructure (localhost, shared bearer token). Contributors use the bot's self-hosted Scalar reference at `http://127.0.0.1:8090/docs`.
- **Never document secrets:** tokens, `.env` values, internal hostnames/ports, or anything that would help bypass auth.
- Don't invent commands or endpoints — mirror what the code actually exposes.

## Structure

The guide follows a task-based layout: each section has an **overview** page plus short how-to articles, and a **Common questions** section holds troubleshooting. Keep pages short, lead with the steps and the exact command, and link onward.

- Sections: Getting started, Dashboard and setup, Earning money, Items and shop, Playing games, Leveling and community, Moderation, Music, Utility, AI, Common questions. API and Legal are separate tabs.
- When you move or delete a page, add a `redirects` entry in `docs.json`.

## Slash or prefix

Not every command is a slash command. A command is a slash command only if it is declared with `hybrid=True` in the bot (and Discord caps a bot at 100 slash commands). Write prefix-only commands as `?command` (for example `?fish`, `?ban`, `?config`) and hybrid commands as `/command`. Check the declaration in `Percy-v2/app/cogs/**/cog.py` before writing a command.
