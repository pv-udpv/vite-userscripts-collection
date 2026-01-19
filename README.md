# Vite Userscripts Collection

A monorepo for managing multiple TypeScript userscripts using [Vite](https://vitejs.dev/) and [vite-plugin-monkey](https://github.com/lisonge/vite-plugin-monkey).

## Architecture

This project uses **pnpm workspaces** to manage multiple independent userscripts in the `packages/` directory.

### Structure

```
├── packages/
│   ├── shared-utils/       # Shared reverse-engineering utilities (logger, proxy, etc.)
│   ├── eruda-loader/       # Script to inject Eruda into SPA apps
│   └── template-script/    # Template for new scripts
├── pnpm-workspace.yaml     # Workspace configuration
└── package.json           # Root scripts
```

## Getting Started

1. **Install Dependencies**
   ```bash
   pnpm install
   ```

2. **Create a New Script**
   ```bash
   cd packages
   pnpm create monkey my-new-script
   ```
   
3. **Development**
   Each package works independently.
   ```bash
   cd packages/eruda-loader
   pnpm run dev
   ```

## Reverse Engineering Tools (Roadmap)

The goal is to build a toolkit for analyzing SPA applications (React, Vue, Angular):
- **Eruda Injection**: Mobile-first console for mobile web views.
- **Network Interceptor**: XHR/Fetch proxying to log/modify traffic.
- **Component Inspector**: Access internal React/Vue instance state from DOM elements.
- **Anti-Debugger Bypass**: Tools to break infinite debugger loops.

## Tech Stack

- **Build Tool**: Vite
- **Userscript Plugin**: vite-plugin-monkey
- **Language**: TypeScript
- **Package Manager**: pnpm
