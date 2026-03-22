---
skills:
  - vercel-react-best-practices
always_apply: true
---

# Project Context

## Tech Stack

- Next.js 16 (App Router) + React 19
- TypeScript 5
- Tailwind CSS 4
- ESLint 9 + Prettier
- Lefthook + commitlint

## Project Structure

- `/app` - Next.js App Router
- `/components` - React components
- `/lib` - Utilities, helpers
- `/.vscode` - VS Code settings

## Code Standards

- Conventional Commits (feat:, fix:, chore:, docs:, style:, refactor:, test:)
- ESLint + Prettier auto-format on save
- Pre-commit hooks: lefthook (lint + format + knip)
- Pre-push hooks: type check

## Best Practices to Apply

- Server Components by default
- Client Components only when needed ('use client')
- Dynamic imports for heavy components
- Image optimization with next/image
- Route handlers for API endpoints
