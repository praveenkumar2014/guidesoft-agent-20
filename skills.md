# GUIDESOFT AGENT 20.0 — Skills Overview

Skills are modular instruction packages that specialize the agent for specific domains.  
They follow the standard SKILL.md format and can be loaded on demand.

## Available Skills

| Skill Name                  | Trigger Keywords                                      | Purpose |
|----------------------------|-------------------------------------------------------|---------|
| `multi-agent-orchestrator` | multi-agent, parallel agents, orchestrate, sub-agents | Core orchestration logic |
| `fullstack-builder`        | full-stack, web app, saas, next.js, react, backend    | End-to-end web applications |
| `mobile-app-builder`       | mobile, react native, flutter, expo, ios, android     | Cross-platform mobile apps |
| `cms-lms`                  | cms, lms, course, learning, headless cms, quiz        | Content management & learning platforms |
| `design-image`             | design, image, mockup, brand, logo, ui kit            | Visual design & image generation |
| `marketing-email`          | email, marketing, landing page, funnel, ads, seo      | Marketing assets & email systems |

## How to Use Skills

### In a custom agent / Cursor / Claude Project
1. Copy the desired `skills/<name>/SKILL.md` content into the system prompt or load it as a skill.
2. Or reference the skill name and the agent will load the corresponding instructions.

### Progressive Disclosure
- Metadata (name + description) is always visible
- Full SKILL.md body loads only when the skill is activated
- Heavy references stay in `references/` and are read on demand

## Creating New Skills

Follow the standard format:

```
skills/
└── my-new-skill/
    ├── SKILL.md          # Required
    ├── scripts/          # Optional executable helpers
    ├── references/       # Optional deep docs
    └── assets/           # Optional templates
```

## Recommended Loading Strategy

For a full GUIDESOFT AGENT session:
1. Always load `multi-agent-orchestrator`
2. Load domain skills on demand based on the user’s request
3. Keep the active skill set lean to preserve context window
