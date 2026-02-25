# Design System

A React component library built with TypeScript, developed and previewed via Storybook.

## Cursor Cloud specific instructions

### Services

| Service | Command | Port | Purpose |
|---------|---------|------|---------|
| Storybook | `pnpm dev` | 6006 | Component development & preview |

### Key commands

All commands are defined in `package.json` scripts:

- **Dev server**: `pnpm dev` (Storybook on port 6006)
- **Lint**: `pnpm lint`
- **Test**: `pnpm test` (Vitest) or `pnpm test:watch` for watch mode
- **Build library**: `pnpm build` (tsup, outputs to `dist/`)
- **Build Storybook**: `pnpm build:storybook`
- **Format**: `pnpm format` (Prettier)

### Gotchas

- The `pnpm.onlyBuiltDependencies` field in `package.json` allowlists `esbuild` for postinstall scripts. Without this, `pnpm install` will skip the esbuild native binary install and builds will fail.
- Storybook 8.6 peer-dependency warnings about Vite version mismatch (expects ^4/^5/^6, gets 7.x from vitest) are harmless and can be ignored.
- Components live in `src/components/<Name>/` with co-located `.tsx`, `.css`, `.test.tsx`, and `.stories.tsx` files. Re-export from the component's `index.ts` and from `src/index.ts`.
