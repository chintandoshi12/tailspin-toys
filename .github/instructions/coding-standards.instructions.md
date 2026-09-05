---
description: 'Shared TypeScript, documentation, and comment standards'
applyTo: '**/*.{ts,astro,css}'
---

# Coding Standards

## Comments and Documentation

- Comment intent, constraints, trade-offs, or other information that is not
  apparent from the code. Do not restate what the next line already says.
- Prefer a precise name or a small refactor over a comment that explains
  obvious mechanics.
- Keep comments close to the code they explain, and update or remove them when
  the related implementation changes. An outdated comment is a bug.
- Use TSDoc/JSDoc for every exported function in `db/` and `src/lib/`. Describe
  the function's purpose, every parameter with `@param`, and its return value
  with `@returns`. For data-access helpers, document the injectable `db`
  parameter and explain notable ordering, lookup, or nullability behavior.
- Reusable `.astro` components must document their `Props` interface,
  including what each prop controls and any important defaults or constraints.
  Page-only components do not need a separate API document.
- Use comments in GitHub Actions only to explain non-obvious workflow intent or
  security decisions; do not annotate every command.

## TypeScript Formatting and Types

- Use four spaces for TypeScript indentation, single quotes, and semicolons,
  matching the existing project style.
- Use explicit parameter and return types for functions, especially exported
  functions and all data-layer helpers. Prefer named interfaces or type aliases
  for reusable object shapes.
- Keep imports type-only when they are used only for types (`import type`).
- Prefer narrow unions, null checks, and inferred local types over `any` or
  unnecessary type assertions.
- ESLint enforces the project's recommended JavaScript and TypeScript rules,
  including explicit type annotations at exported module boundaries. TSDoc
  quality and comment relevance are reviewed by maintainers.
