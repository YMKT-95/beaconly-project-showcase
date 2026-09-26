# Technical Decisions

## Hardcoded Forms vs Configuration-Driven Forms

With only a few categories, separate hardcoded flows are easy to build. As categories grow, the
same field definitions, entity logic and validation differences become duplicated.

That creates:
- more conditional rendering
- duplicated validation
- inconsistent changes
- higher regression risk
- slower extension of new categories

The design moved toward:

```text
Category config
    ↓
Unified rendering engine
    ↓
Reusable entity managers
    ↓
Rule-based validation
```

This lets a new category or rule change be introduced mainly by extending configuration/rules.

## Centralised API Access

A shared Axios client centralises authentication headers and error handling. Domain services keep
transport concerns out of UI components.

## Types Aligned with Backend DTOs

TypeScript definitions mirror backend DTOs to improve contract clarity and type safety.

## Lazy Loading + Protected Routes

Lazy loading/code splitting reduce unnecessary initial work, while protected routes support
role-based navigation.
