---
applyTo: "**.ts,**/*.vue"
---
# Project Coding Standards for TypeScript and Vue

Apply the [general coding guidelines](./general-coding.instructions.md) to all code.

## Naming Conventions

- Use kebab-case for file names (e.g., `my-component.ts`)
- Use camelCase for variables and function names (e.g., `myVariable`, `myFunction()`)
- Use PascalCase for classes, types, and interfaces (e.g., `MyClass`, `MyInterface`)
- Use ALL_CAPS for constants and enum values (e.g., `MAX_COUNT`, `Color.RED`)

## TypeScript Guidelines

- Follow functional programming principles where appropriate (e.g., pure functions, higher-order functions, immutability)
- Leverage modern TypeScript and JavaScript features (e.g., optional operator, nullish coalescing, and `satisfies` operator)
- Prefer top-level `import type` over inline `import { type ... }`
- Always prefer interfaces when modelling inheritance (only use the `&` operator where `interface extends` is not possible)
- Prefer immutable data (e.g., `const` declarations, `readonly` properties)
- Prefer an `as const` object over enums
- Proactively use discriminated unions to model data that can be in one of a few different shapes

## Vue & Nuxt Guidelines

- Use Nuxt's auto-imports instead of manual imports (e.g., components, composables)
- Prefer built-in Nuxt composables (e.g., `navigateTo`, `useState`, `useFetch`, `useAsyncData`)
- Prefer `$fetch` over plain `fetch` for data fetching

## JSDoc Comments Guidelines

- Use JSDoc comments to annotate functions and types
- Be concise in JSDoc comments, and only provide JSDoc comments if the function's behaviour is not self-evident
- Use the JSDoc inline `@link` tag to link to other functions and types within the same file
