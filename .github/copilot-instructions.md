# AI Agent Instructions

## Architecture Overview

This is a Vue 3 + TypeScript + Vite starter template with Tailwind CSS v4 and Biome tooling. The project uses a minimal, modern architecture focused on developer experience and performance.

**Key Stack:**
- **Vue 3** with `<script setup>` composition API syntax
- **TypeScript** with strict configuration and unused variable checking
- **Tailwind CSS v4** (latest version) integrated via Vite plugin
- **Biome** for unified linting/formatting (replaces ESLint + Prettier)
- **pnpm** as package manager with workspace configuration

## Critical Tooling Patterns

### Biome Configuration
- Uses single `biome.json` for linting AND formatting
- Configured for Vue/TypeScript: `trailingCommas: "all"`, `semicolons: "asNeeded"`
- CSS parser has `tailwindDirectives: false` - this is intentional
- Run quality checks: `pnpm check` (lint + format together)

### Development Workflow
- **Start dev server**: `pnpm dev` (not `npm run dev`)
- **Build**: `pnpm build` - runs `vue-tsc -b` first for type checking
- **mise tasks available**: Use `mise run vite:dev`, `mise run biome:format` etc.

### TypeScript Configuration
- Uses project references: `tsconfig.json` → `tsconfig.app.json` + `tsconfig.node.json`
- Strict mode enabled with `noUnusedLocals`, `noUnusedParameters`
- Uses `"types": ["vite/client"]` for Vite-specific types

## Vue 3 Specific Conventions

### Component Structure
```vue
<script setup lang="ts">
// Use defineProps<>() generic syntax, not defineProps()
defineProps<{ msg: string }>()
// Import components directly, no need for components: {} registration
import { ComponentName } from './path'
</script>

<template>
  <!-- Use className (React-style) for consistency with examples -->
  <div className="flex items-center gap-2">
</template>

<style scoped>
/* Prefer scoped styles or Tailwind classes */
</style>
```

### Icon Usage
- Uses `lucide-vue-next` for icons
- Import pattern: `import { IconName } from 'lucide-vue-next'`
- Standard props: `className="w-6 h-6"` for consistent sizing
- Example usage:
  ```vue
  <script setup lang="ts">
  import { SquareDashed, Github, ArrowRight } from 'lucide-vue-next'
  </script>
  
  <template>
    <div class="flex items-center gap-2">
      <SquareDashed className="w-6 h-6 text-blue-500" />
      <Github className="w-5 h-5" />
      <ArrowRight className="w-4 h-4 text-gray-400" />
    </div>
  </template>
  ```
- Available size patterns: `w-4 h-4`, `w-5 h-5`, `w-6 h-6`, `w-8 h-8`
- Color via Tailwind: `text-blue-500`, `text-gray-400`, etc.

## Styling Approach

### Tailwind CSS v4 Integration
- **Entry point**: `src/style.css` with single `@import "tailwindcss"`
- **Plugin integration**: Uses `@tailwindcss/vite` plugin (not PostCSS)
- **Class patterns**: Use utility-first approach, avoid custom CSS when possible

### Layout Patterns
```vue
<!-- Standard centered layout pattern used in HelloWorld.vue -->
<div class="flex flex-col justify-center items-center bg-gray-50 min-h-screen">
  <div class="flex flex-col items-start gap-1">
    <!-- content -->
  </div>
</div>
```

## File Organization

### Source Structure
```
src/
├── main.ts           # App entry with createApp()
├── App.vue           # Root component (minimal)
├── style.css         # Tailwind imports only
├── assets/           # Static assets
└── components/       # Vue components
```

### Configuration Files
- `vite.config.ts` - Simple config with Vue + Tailwind plugins only
- `biome.json` - All code quality configuration
- `mise.toml` - Task runner with confirmation prompts for build/format

## Development Commands

| Command | Purpose | Notes |
|---------|---------|-------|
| `pnpm dev` | Development server | Port 5173 default |
| `pnpm build` | Production build | Includes type checking |
| `pnpm preview` | Preview build | Use after build |
| `pnpm check` | Lint + format | Single command for quality |
| `mise run vite:dev` | Alternative dev server | Via mise task runner |

## Common Patterns to Follow

1. **Use `<script setup>` syntax** - this is the preferred Vue 3 composition API style
2. **Import types with defineProps<>()** - not runtime props validation
3. **Prefer Tailwind utilities** over custom CSS
4. **Use Biome formatting** - configured for consistent style
5. **Leverage TypeScript strict mode** - already configured properly
6. **Use pnpm workspace** - optimized for monorepo structure even as single project

## Key Integration Points

- **Vite + Tailwind**: Uses plugin integration, not PostCSS
- **Vue + TypeScript**: Full type safety with SFC support
- **Biome + Git**: VCS integration enabled for pre-commit formatting
- **pnpm + mise**: Alternative task running via mise for consistent environments