# Vue 3 + TypeScript + Vite + Tailwind CSS Starter

A modern, fast, and feature-rich starter template for building Vue 3 applications with TypeScript, Vite, and Tailwind CSS.

## 🚀 Features

- ⚡️ **Vue 3** - The progressive JavaScript framework
- 🔷 **TypeScript** - Type safety and better development experience
- ⚡️ **Vite** - Lightning fast build tool
- 🎨 **Tailwind CSS v4** - Utility-first CSS framework
- 🔧 **Biome** - Fast linter and formatter (ESLint + Prettier alternative)
- 📦 **pnpm** - Fast, disk space efficient package manager
- 🎯 **Lucide Vue Next** - Beautiful & consistent icon pack
- 🏗️ **Script Setup** - Composition API syntax sugar

## 📋 Prerequisites

- Node.js 18+ 
- pnpm (recommended) or npm/yarn

## 🛠️ Setup

1. **Clone or use this template**
   ```bash
   git clone <your-repo-url>
   cd vite-vue-tailwind
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   ```

3. **Start development server**
   ```bash
   pnpm dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173`

## 📜 Available Scripts

| Script | Description |
|--------|-------------|
| `pnpm dev` | Start development server |
| `pnpm build` | Build for production |
| `pnpm preview` | Preview production build |
| `pnpm lint` | Lint and fix code with Biome |
| `pnpm format` | Format code with Biome |
| `pnpm check` | Run Biome checks (lint + format) |

## 🏗️ Project Structure

```
├── public/              # Static assets
├── src/
│   ├── assets/         # Asset files (images, fonts, etc.)
│   ├── components/     # Vue components
│   ├── App.vue         # Root component
│   ├── main.ts         # Application entry point
│   └── style.css       # Global styles with Tailwind imports
├── index.html          # HTML entry point
├── package.json        # Dependencies and scripts
├── vite.config.ts      # Vite configuration
├── tsconfig.json       # TypeScript configuration
├── biome.json          # Biome configuration
└── README.md           # This file
```

## 🎨 Styling

This template uses **Tailwind CSS v4** for styling. The main CSS file is located at [src/style.css](src/style.css) and includes Tailwind's base styles, components, and utilities.

Example usage:
```vue
<template>
  <div class="bg-blue-500 text-white p-4 rounded-lg">
    <h1 class="text-xl font-bold">Hello Tailwind!</h1>
  </div>
</template>
```

## 🔧 Code Quality

This project uses **Biome** for linting and formatting, which provides:

- ⚡️ Lightning fast performance
- 🔧 ESLint + Prettier functionality in one tool
- 📝 TypeScript-first approach
- 🎯 Zero configuration required

Configuration is available in [biome.json](biome.json).

## 🚀 Building for Production

```bash
pnpm build
```

This will:
1. Type-check your code with `vue-tsc`
2. Build optimized assets with Vite
3. Output to `dist/` directory

## 📚 Learn More

- [Vue 3 Documentation](https://vuejs.org/)
- [Vite Documentation](https://vitejs.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/)
- [Biome Documentation](https://biomejs.dev/)

## 📄 License

MIT License - feel free to use this template for your projects!
