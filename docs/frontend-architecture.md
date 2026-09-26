# Frontend Architecture

The frontend was organised into seven main layers.

## 1. UI Layer
Pages and components are responsible for rendering and user interaction.

## 2. Routes Layer
React Router handles navigation, lazy loading, protected routes and role-based access.

## 3. Contexts Layer
Shared application state includes Clerk authentication and current-user/session information.

## 4. Hooks Layer
Custom hooks such as `useReports` and reusable form handlers encapsulate data fetching and
state-management logic, reducing duplication in components.

## 5. API Layer
A central Axios instance provides shared authentication and error handling. Domain-specific
services cover reports, cases, announcements, auth and users.

## 6. Types Layer
TypeScript definitions match backend DTOs, making data structures explicit and helping catch
mismatches earlier.

## 7. Validation Layer
Business rules are separated from rendering through form-level validation, entity-level validators
and a rule-based validation engine.

## Design Goals
- separation of concerns
- type safety
- code reuse
- maintainability
- easier testing
- lazy loading and code splitting
