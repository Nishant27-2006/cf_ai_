# AI Prompts Used

This document lists all the prompts used to build this project with AI assistance.

## Initial Setup Prompt

```
can you help me build this project out: Build Agents on Cloudflare
The Agents SDK enables you to build and deploy AI-powered agents that can autonomously perform tasks, communicate with clients in real time, call AI models, persist state, schedule tasks, run asynchronous workflows, browse the web, query data from your database, support human-in-the-loop interactions, and a lot more.

Ship your first Agent
To use the Agent starter template and create your first Agent with the Agents SDK:

Terminal window
# install it
npm create cloudflare@latest agents-starter -- --template=cloudflare/agents-starter
# and deploy it
npx wrangler@latest deploy

[... full documentation from Cloudflare provided ...]
```

## Configuration Fix Prompt

```
i added the openai api key to .env so test it out and let me know how it goes
```

## Documentation Cleanup Prompt

```
can you remove any comments and make a readme, when writing the readme out Write with confidence and clarity as if you're talking to a sharp friend.

Skip the long dash and curly quotes. Plain punctuation only.

Buzzwords such as cutting edge, robust, and seamless are off-limits.

Use a short dash or a comma, never the long one.

Keep your language simple. No showy words or jargon.

Never use em dash "—" in anything.

Keep your language simple. No showy words or jargon.

If any word from the ban list slips in, you owe a thousand bucks—so check twice

Ban list (do not use)
Adventure, Architect, Beacon, Boast, Bustling, Dazzle, Delve, Demistify, Depicted, Discover, Dive, Eerie, Elegant, Elevate, Empower, Empowering, Embark, Enrich, Entanglement, Ever-evolving, Grappling, Harnessing, Hurdles, Insurmountable, Journey, Meticulously, Multifaced, Navigate, Navigation, New Era, Picture, Poised, Pride, Realm, Supercharge, Tailor, Tailored, Unleash, Unliving, Unlock, Unprecedented, Unravel, Unveiling the power, Weighing

also can you make sure you include this: Write with confidence and clarity as if you're talking to a sharp friend.

Skip the long dash and curly quotes. Plain punctuation only.

Buzzwords such as cutting edge, robust, and seamless are off-limits.

Use a short dash or a comma, never the long one.

Keep your language simple. No showy words or jargon.

Never use em dash "—" in anything.

Keep your language simple. No showy words or jargon.

If any word from the ban list slips in, you owe a thousand bucks—so check twice

Ban list (do not use)
Adventure, Architect, Beacon, Boast, Bustling, Dazzle, Delve, Demistify, Depicted, Discover, Dive, Eerie, Elegant, Elevate, Empower, Empowering, Embark, Enrich, Entanglement, Ever-evolving, Grappling, Harnessing, Hurdles, Insurmountable, Journey, Meticulously, Multifaced, Navigate, Navigation, New Era, Picture, Poised, Pride, Realm, Supercharge, Tailor, Tailored, Unleash, Unliving, Unlock, Unprecedented, Unravel, Unveiling the power, Weighing

and To be considered, your repository name must be prefixed with cf_ai_, must include a README.md file with project documentation and clear running instructions to try out components (either locally or via deployed link). AI-assisted coding is encouraged, but you must include AI prompts used in PROMPTS.md

All work must be original; copying from other submissions is strictly prohibited.
```

## Summary

All code in this project was generated with Claude Code (Anthropic's AI coding assistant) using the prompts above. The AI:

1. Created the project using Cloudflare's agents-starter template
2. Set up the development environment and fixed configuration issues
3. Removed code comments for cleaner files
4. Created documentation following specific style guidelines
5. Renamed the project to follow the cf_ai_ naming convention

No code was copied from other submissions. All implementation is based on Cloudflare's official starter template and documentation.
