# GUIDESOFT AGENT 20.0

**The ultimate multi-agent creative & engineering platform.**

Inspired by Google Antigravity, Lovable.dev, Base44, Leap.new, and Replit Agent 4.

Build anything with natural language:
- Full-stack web apps
- Mobile apps (React Native / Flutter / Expo)
- CMS & LMS platforms
- Websites & high-converting landing pages
- Email templates & sequences
- Digital marketing assets
- Image generation & design systems
- Any custom craft

## Quick Start

1. Copy `systemprompt.md` into your AI tool (Claude Projects, Cursor, Grok Custom Instructions, OpenWebUI, etc.)
2. Load the skills from the `skills/` folder as needed
3. Start chatting:

```
GUIDESOFT AGENT 20.0 activated.
Brand: GUIDESOFT
Build me a complete LMS with student dashboard, course player, quizzes, and certificates.
```

## What's Included

| File / Folder              | Purpose                                      |
|---------------------------|----------------------------------------------|
| `ARCHITECTURE.md`         | Full system architecture & tech stack        |
| `systemprompt.md`         | Master system prompt (drop-in ready)         |
| `skills.md`               | Overview of all skills                       |
| `skills/`                 | Modular skill packages (SKILL.md format)     |
| `config/`                 | Model routing & provider configs             |
| `examples/`               | Ready-to-use prompt examples                 |
| `references/`             | Deep docs (optional load)                    |
| `vercel.json`             | Vercel deploy config                         |
| `.github/workflows/`      | GitHub Actions YAML for Vercel deploy        |

## Core Philosophy

- **Vibe first**: Pure natural language → production software
- **Multi-agent**: Orchestrator + specialized sub-agents (Frontend, Backend, Design, QA, Growth...)
- **Parallel by default**: Multiple agents work simultaneously
- **Artifacts everywhere**: Plans, code diffs, previews, architecture diagrams, screenshots
- **Model routing**: Select any provider/model or let the agent auto-route
- **In-built backend**: Auth, DB, storage, payments ready
- **Agent windows**: Everything happens inside the conversation / IDE surface

## Deploy

1. Connect this repo to Vercel (Import Project)
2. Add secrets for GitHub Actions (optional):
   - `VERCEL_TOKEN`
   - `VERCEL_ORG_ID`
   - `VERCEL_PROJECT_ID`
3. Push to `main` → auto deploy via YAML workflow

## License

MIT — Build your own brand on top of this foundation.
