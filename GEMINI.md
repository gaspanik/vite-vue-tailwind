# Project Context: Vite + Vue + Tailwind Starter

## Overview
This is a starter template for **Vue 3** applications using **TypeScript**, **Vite**, and **Tailwind CSS v4**. It emphasizes a modern, fast development experience with strict type safety and unified tooling.

### Key Technologies
- **Framework**: Vue 3 (Composition API with `<script setup>`)
- **Language**: TypeScript (Strict mode enabled)
- **Build Tool**: Vite
- **Styling**: Tailwind CSS v4 (via `@tailwindcss/vite`)
- **Linting/Formatting**: Biome (replaces ESLint/Prettier)
- **Icons**: `lucide-vue-next`
- **Package Manager**: `pnpm`

## Build & Run Commands

| Command | Description |
| :--- | :--- |
| `pnpm dev` | Start the development server (default port 5173). |
| `pnpm build` | Build for production (runs `vue-tsc` type check first). |
| `pnpm preview` | Preview the production build locally. |
| `pnpm check` | Run Biome to lint and format code (includes fixable errors). |
| `pnpm format` | Run Biome formatter only. |

## Development Conventions

### Component Structure
- Use **`<script setup lang="ts">`** for all components.
- Use generic `defineProps<{ msg: string }>()` syntax for props.
- Import components directly; explicit registration is not needed.

### Styling (Tailwind v4)
- **Entry Point**: `src/style.css` contains `@import "tailwindcss";`.
- **Usage**: Prefer utility classes over scoped styles.
- **Class Attribute**: The codebase contains a mix of `class` (standard Vue) and `className` (React-style, recommended by project instructions).
  - **Rule**: Check the specific file context. If editing existing `className` usage, maintain it. For new standard HTML elements, `class` is typically preferred in Vue, but be aware of the project's existing patterns.

### Icons
- Use **Lucide Vue Next** icons.
- Import pattern: `import { IconName } from 'lucide-vue-next'`.
- Apply classes for sizing and color: `<IconName class="w-6 h-6 text-blue-500" />` (or `className` if consistent with file).

### Quality Control
- **Biome** is the single source of truth for code style.
- Run `pnpm check` before committing to ensure linting and formatting pass.
- Configuration is in `biome.json`.

## Directory Structure
- `src/main.ts`: Application entry point.
- `src/App.vue`: Root component.
- `src/style.css`: Global styles and Tailwind imports.
- `vite.config.ts`: Vite configuration (minimal, uses plugins).
- `.github/copilot-instructions.md`: Detailed architectural guidelines and patterns.
