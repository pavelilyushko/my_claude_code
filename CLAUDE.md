# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository layout

This repo contains a single project, `hookhub/`, a Next.js application bootstrapped with `create-next-app`. There is no root-level build tooling — all commands run from inside `hookhub/`.

## Critical: Next.js version mismatch

`hookhub` uses **Next.js 16.2.9**, a version newer than your training data. APIs, conventions, and file structure may differ from what you expect from older Next.js. Before writing or modifying any Next.js code, read the relevant guide under `hookhub/node_modules/next/dist/docs/` (organized as `01-app/`, `02-pages/`, `03-architecture/`, `04-community/`) and heed any deprecation notices found there.

## Commands

Run from the `hookhub/` directory:

```bash
npm run dev      # start dev server (http://localhost:3000)
npm run build    # production build
npm run start    # serve production build
npm run lint     # eslint
```

There is no test runner configured in this project.

## Architecture

- App Router structure under `hookhub/app/` (`layout.tsx`, `page.tsx`, `globals.css`).
- Path alias `@/*` resolves to the `hookhub/` root (see `tsconfig.json`).
- Styling via Tailwind CSS v4 (`@tailwindcss/postcss`).
- ESLint config (`eslint.config.mjs`) composes `eslint-config-next`'s `core-web-vitals` and `typescript` rule sets.
