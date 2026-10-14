---
name: fullstack-builder
description: Build complete full-stack web applications from natural language. Use for SaaS, dashboards, web apps, Next.js, React, Node, Python backends, auth, databases, APIs, and one-click deploy.
---

# Full-Stack Builder

Produce production-ready full-stack applications.

## Preferred Stack (smart defaults)

- **Frontend**: Next.js 15 (App Router) + TypeScript + Tailwind CSS + shadcn/ui
- **Backend**: Next.js Route Handlers or separate Node/Python service
- **Database & Auth**: Supabase (Postgres + Auth + Storage + Realtime)
- **Payments**: Stripe
- **Deploy**: Vercel (frontend) + Railway / Supabase (backend services)

Override only when the user specifies a different stack.

## Standard Delivery

For every new app deliver:

1. Complete file structure
2. All source files (ready to run)
3. Environment variable list (`.env.example`)
4. Database schema (SQL or Prisma/Drizzle)
5. Auth flow (email + OAuth if relevant)
6. Deployment instructions
7. Local development commands

## Quality Checklist

- TypeScript strict mode
- Responsive + accessible UI
- Loading / error / empty states
- Secure by default (no secrets in code)
- Clean folder structure (`app/`, `components/`, `lib/`, `types/`)
- Meaningful commit-ready code
