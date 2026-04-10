# Project Overview

This repository is the Excalidraw monorepo. It contains the app shell, reusable editor packages, and shared tooling for building and testing.

## Tech Stack

- TypeScript
- React
- Vite
- Yarn workspaces (Yarn Classic)
- Vitest + ESLint + Prettier

## Project Structure

- `excalidraw-app/`: app shell and integration layer.
- `packages/excalidraw/`: reusable editor package.
- `packages/element/`, `packages/math/`, `packages/common/`, `packages/utils/`: shared domain and utility packages.
- `dev-docs/`: docs site and contributor documentation.

## Key Commands

- `yarn install`
- `yarn start`
- `yarn build`
- `yarn test:all`
- `yarn test:typecheck`
- `yarn test:code`
- `yarn fix`

## Architecture

- Keep package dependency direction stable: common -> math -> element -> excalidraw -> app.
- Place reusable editor logic in `packages/excalidraw`; keep app-only wiring in `excalidraw-app`.
- Prefer explicit module boundaries over cross-layer shortcuts.

## Conventions

- Prefer explicit typing and avoid `any` unless truly unavoidable.
- Use `import type` for type-only imports.
- Keep React components functional and focused.
- Add or update tests when behavior changes.

## Do-Not-Touch / Constraints

- Do not commit secrets or credentials.
- Avoid changing build/tooling configuration unless task requires it.
- Do not weaken lint/type/test gates to make changes pass.
- Keep changes scoped; avoid unrelated refactors in the same PR.
