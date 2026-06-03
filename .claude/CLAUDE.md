# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

This project uses `pnpm` (lockfile: `pnpm-lock.yaml`).

- **Start dev server:** `pnpm dev`
- **Type-check and build:** `pnpm build` (runs `vue-tsc -b && vite build`)
- **Preview production build:** `pnpm preview`

There is no test runner or linter currently configured.

## Architecture

This is a standard Vue 3 + TypeScript + Vite application using `<script setup>` single-file components.

- **Entry point:** `src/main.ts` creates the app and mounts it to `#app` in `index.html`.
- **Root component:** `src/App.vue` renders `src/components/HelloWorld.vue`.
- **Static assets:** Files in `public/` (e.g., `icons.svg`) are served at the root path. Files in `src/assets/` are imported as modules and processed by the build.
- **SVG sprites:** The project uses an SVG sprite in `public/icons.svg`, referenced via `<use href="/icons.svg#id">`.

## TypeScript Configuration

`tsconfig.app.json` extends `@vue/tsconfig/tsconfig.dom.json` and enables strict checks that will fail the build if violated:

- `noUnusedLocals: true`
- `noUnusedParameters: true`
- `erasableSyntaxOnly: true`
- `noFallthroughCasesInSwitch: true`

## Editor Setup

The workspace recommends the `Vue.volar` extension (see `.vscode/extensions.json`).
