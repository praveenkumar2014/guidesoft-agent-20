# GUIDESOFT AGENT 20.0 — Architecture

## High-Level Overview

```
┌────────────────────────────────────────────────────────────────┐
│                     USER INTERFACE LAYER                         │
│  Agent Windows (Chat + Artifacts + Design Canvas + Previews)    │
│  - Streaming chat                                                │
│  - Parallel sub-agent status panels                              │
│  - Live code diffs & file tree                                   │
│  - Design Canvas (mockups → code)                                │
│  - One-click deploy buttons                                      │
└───────────────────────────────┬──────────────────────────────────┘
                             │
┌────────────────────────────┴───────────────────────────────────┐
│                  ORCHESTRATOR (GUIDESOFT AGENT)                  │
│  - Intent understanding & task decomposition                     │
│  - Dynamic sub-agent spawning                                    │
│  - Parallel execution coordination                               │
│  - Context management & memory                                   │
│  - Model routing & provider selection                            │
│  - Artifact generation & verification                            │
└────────────────────────────┬───────────────────────────────────┘
                             │
        ┌───────────────────┬───────────────────┐
        ▼                    ▼                    ▼
┌──────────────┐   ┌──────────────┐   ┌──────────────┐
│  SUB-AGENTS   │   │  SUB-AGENTS   │   │  SUB-AGENTS   │
│  Architect    │   │  Frontend     │   │  Backend      │
│  Design       │   │  Mobile       │   │  DevOps       │
│  Content      │   │  QA           │   │  Growth       │
└──────────────┘   └──────────────┘   └──────────────┘

## Multi-Agent Design

### Orchestrator Responsibilities
- Parse user intent
- Create high-level plan
- Spawn / terminate sub-agents dynamically
- Merge results and resolve conflicts
- Maintain project memory across turns
- Produce final Artifacts for the user

### Dynamic Sub-Agents
Each sub-agent receives focused system prompt + skill, relevant context only, clear success criteria, and ability to call domain tools. Parallelism is preferred whenever tasks have no hard dependencies.

## Model Routing Strategy

```yaml
routing:
  planning_reasoning: ["claude-4-opus", "gemini-2.5-pro", "o3"]
  fast_coding: ["gemini-2.5-flash", "claude-4-sonnet", "grok-4"]
  long_context: ["gemini-2.5-pro", "claude-4"]
  image_generation: ["flux-pro", "imagen-3", "dall-e-3"]
  vision: ["gemini-2.5-pro", "gpt-4o"]
  default: "auto"
```

## Recommended Tech Stack (Production)

| Component              | Recommended Choices                          |
|------------------------|----------------------------------------------|
| Agent Orchestration    | LangGraph / CrewAI / AutoGen / custom        |
| Sandbox                | E2B, Daytona, Modal, Firecracker             |
| Frontend (Agent UI)    | Next.js 15 + Tailwind + shadcn/ui + Vercel AI SDK |
| Backend (Agent)        | Supabase + Edge Functions or Encore.ts       |
| Model Gateway          | LiteLLM or OpenRouter                        |
| Design Canvas          | Excalidraw / Fabric.js + AI images           |
| Auth & DB              | Supabase (Postgres + Auth + Storage + Realtime) |
| Deploy Targets         | Vercel + Railway + Cloudflare Workers        |
| Mobile                 | Expo / React Native + EAS                    |
| MCP                    | Official MCP servers + custom                |

## Artifact Types

1. **Plan** – numbered steps + dependency graph
2. **Architecture Diagram** – Mermaid or image
3. **Code Diffs** – file-by-file changes
4. **Live Preview** – localhost or deployed URL
5. **Screenshots / Recordings** – visual verification
6. **Task Board** – real-time sub-agent status
7. **Design Variants** – multiple UI options

## Security Principles

- Sandbox all code execution
- Never expose secrets in prompts or code
- Use environment variables + secret managers
- Principle of least privilege for sub-agents
- Human-in-the-loop for destructive actions
- Audit logs for all agent actions

## Scalability Path

1. **MVP**: Single orchestrator + sequential sub-agents + local sandbox
2. **v1**: Parallel sub-agents + E2B sandbox + Supabase backend
3. **v2**: Multi-user workspaces + team collaboration + custom skills marketplace
4. **v3**: Self-improving agents + long-term memory + enterprise SSO

## File Layout for Implementation

```
guidesoft-agent/
├── apps/
│   ├── web/                 # Agent UI (Next.js)
│   └── api/                 # Orchestrator backend
├── packages/
│   ├── agents/
│   ├── skills/
│   ├── tools/
│   └── shared/
├── sandbox/
├── config/
└── docker-compose.yml
```
