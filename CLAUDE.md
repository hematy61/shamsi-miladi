# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React application for converting dates between Shamsi (Solar Hijri/Persian) and Miladi (Gregorian) calendars. The project uses Vite as the build tool with TypeScript and React 19.

## Development Commands

```bash
# Start development server with HMR
npm run dev

# Build for production (runs TypeScript compiler then Vite build)
npm run build

# Run ESLint on all files
npm run lint

# Preview production build locally
npm run preview
```

## Build System

This project uses **rolldown-vite** (version 7.2.5) instead of standard Vite. This is configured via package.json overrides:

```json
"vite": "npm:rolldown-vite@7.2.5"
```

rolldown-vite uses oxc for Fast Refresh instead of Babel, providing better performance. Be aware of this when debugging build issues or looking up Vite documentation.

## TypeScript Configuration

The project uses a composite TypeScript setup with two separate configurations:
- `tsconfig.app.json` - for application code in src/
- `tsconfig.node.json` - for Vite configuration files

The build process runs `tsc -b` which compiles using both configurations.

## Code Structure

Currently minimal - the application is in early development:
- `src/App.tsx` - Main application component (currently just renders "test")
- `src/main.tsx` - Application entry point with React 19 StrictMode
- Standard Vite + React folder structure

## ESLint Configuration

Uses flat config format (eslint.config.js) with:
- TypeScript ESLint recommended rules
- React Hooks plugin
- React Refresh plugin for Vite
- Ignores dist/ directory

The README suggests optional stricter configurations (type-checked rules, react-x plugin) but they are not currently enabled.

## Key Dependencies

- React 19.2.0 (latest version)
- TypeScript 5.9.3
- Vite via rolldown-vite 7.2.5
- ESLint 9 with flat config