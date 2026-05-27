# OITS Dhaka | Agent Core Initialization & Workflow Engine

This file dictates the persistent cognitive boundaries, architectural standards, and validation protocols for all AI operations within this workspace.

## 1. Aesthetic Identity & Design System (Swiss-Modern)

- **Theme**: Swiss-Modern Editorial. Minimalist, high-density, absolute high-contrast black/white palette, and intentional use of large negative space as a structure rather than generic borders.
- **Typography**: Clean system sans-serif (`Inter`) for layouts/headings; rigid monospaced (`JetBrains Mono` / `Fira Code`) for metrics, data tables, counters, and technical badges.
- **Motion (Physicality over Automation)**: Framer Motion / Motion for React. Page/element transitions must fall strictly between 500ms and 700ms. Grid elements must use layout-aware animations to prevent jarring layout pops.
- **Micro-Interactions**: Granular, contextual pauses for custom typing sequences (e.g., holding on brackets `{}` `[]`, colons `:`, and semicolons `;`). Hover states must implement explicit visual glows (`hover:shadow-[0_0_20px_rgba(37,99,235,0.4)]`) layered over smooth scale-up transitions.

## 2. Technical Stack & Engineering Standards

- **Core Runtime**: Vite + React 18+ + TypeScript (Strict Mode) + Tailwind CSS.
- **Data & Schema Layout**: Centralized static schemas, navigation items, and categories must live inside `/src/constants.ts`. Shared types must live explicitly in `/src/types.ts`. Avoid inline interface definitions or standard `const enum`. Named imports only.
- **Modularity**: Primitive, reusable UI nodes belong in `/components/ui/`. Structural domain blocks (Header, Hero, Services, Portfolio, Footer) must be built independently.
- **Accessibility (WCAG Compliance)**: Focus rings must be visible (`focus-visible:ring-2 focus-visible:ring-blue-500`). Touch targets on carousels must utilize explicit gesture constraints (`touch-action: 'pan-y'`) to avoid scroll cross-interference. Screen reader properties (`role="status"`, `aria-live="polite"`) are mandatory for dynamic toast alerts.

## 3. Workflow Priorities (Sequential Execution)

1. **Type Definition**: Populate or augment `types.ts` before writing component business logic.
2. **Data Mocking**: Define content layouts in `constants.ts`.
3. **Atomic UI Setup**: Formulate clean, accessible presentation files.
4. **Iterative Feature Integration**: Hook up state mechanics incrementally.
5. **Continuous Verification**: Execute quality hooks on every cycle phase.

## 4. Automation & GitHub Commit Protocol

Upon completing any change, you MUST propose a comprehensive, structured conventional commit message directly to the user in this exact format:

```text
type(scope): summary of the primary change

- Core Theme/UI Component: Detail exactly what was modified and its file location.
- Performance/Accessibility: Specify any optimizations, ARIA additions, or caching adjustments implemented.
```
