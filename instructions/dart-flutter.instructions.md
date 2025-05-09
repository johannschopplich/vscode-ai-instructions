---
applyTo: "**/*.dart"
---
# Project Coding Standards for Dart/Flutter

Apply the [general coding guidelines](./general-coding.instructions.md) to all code.

## Project Architecture

- Follow feature-first architecture with clear feature modules
- Use layered architecture within each feature:
  - `domain`: Models, entities, and business logic interfaces
  - `data`: Repositories, data sources, and API clients
  - `application`: Services, controllers, and state management
  - `presentation`: UI components, screens, and widgets
- Keep shared/common code in corresponding `common/` directories

## Naming Conventions

- Use `snake_case` for file names (e.g., `login_controller.dart`, `local_storage_provider.dart`)
- Use `PascalCase` for classes, including widgets (e.g., `LoginController`)
- Use `camelCase` for variables, methods, and functions (e.g., `localStorage()`)
- Use `SCREAMING_SNAKE_CASE` for constants (e.g., `MAX_LOGIN_ATTEMPTS`)
- Prefix private members with an underscore (e.g., `_privateVariable`, `_privateMethod()`)
- Prefix private widgets with an underscore (e.g., `_CategoryItem`)
- Suffix widgets with descriptive UI terms (`View`, `Section`, `Item`, etc.), but not `Widget`

## State Management with Riverpod

- Use `@riverpod` or `@Riverpod(keepAlive: true)` annotations for generating providers when possible
- Use `StateProvider` for simple, one-value state management
- Use `AsyncValue` for handling loading, error, and success states

## Flutter Widgets & UI

- Prefer `ConsumerWidget` and `ConsumerStatefulWidget` for widgets that depend on providers
- Prefer private widgets (e.g., `_CategoryItem`) over build methods (e.g., `_buildCategoryItem()`) for UI composition
- Use `BuildContext` extensions for theme and localization access (e.g., `context.l10n`, `context.surfaces`)

## Immutability & Data Classes

- Use `@freezed` annotation for immutable state and data classes

## Error Handling

- Use `AsyncValue.guard()` to wrap async operations
- Propagate errors through the state rather than showing UI directly from services
- Use dedicated error presentation widgets for consistent error display (e.g. `ErrorMessage.simple()`)

## Comments Guidelines

- Annotate providers and functions that are not self-evident with `///` comments and end the comment with a period
