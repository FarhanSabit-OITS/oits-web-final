# Implementation Plan - Dual-Repository Architectural Fusion

This plan merges the premium single-page aesthetic showcase from `fts-oits-web-monopager` into the multi-page base architecture of `fts-oits-web-multipager`.

## User Review Required

> [!IMPORTANT]
> The multi-page project `fts-oits-web-multipager` will serve as the root repository. We will integrate the single-page mono-pager at `/editorial-showcase` (or `/classic-editorial`) and link it elegantly in the global footer.

> [!WARNING]
> We will merge `package.json` dependencies and custom Tailwind tokens (colors, animations, fonts) to match the Swiss-Modern editorial aesthetic across all components.

## Proposed Changes

### Component 1: Core Configuration and Styles

#### [MODIFY] [package.json](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/package.json)
- Merge dependencies from both folders: lucide-react, motion, lottie-react, etc.

#### [MODIFY] [tailwind.config.js](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/tailwind.config.js)
- Extend theme properties: custom Swiss colors (`swiss-black`, `swiss-white`, `swiss-accent`), typography keys (`sans: Inter`, `mono: JetBrains Mono`), and textGlow animations.

#### [MODIFY] [index.css](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/index.css)
- Inject the Swiss-Modern base, component, and utility layers (e.g. `.glow-headline`, `.premium-cta`, `.typing-cursor`).

### Component 2: Unified Schema Data

#### [MODIFY] [constants.ts](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/constants.ts)
- Construct unified content maps combining portfolio items, extended service descriptors, and route references including the `/editorial-showcase` navigation parameters.

#### [MODIFY] [types.ts](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/types.ts)
- Standardize data structures for `ServiceItem`, `PortfolioItem`, and connection-aware `MediaSource`.

### Component 3: Hybrid Routing & Pages

#### [MODIFY] [App.tsx](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/App.tsx)
- Wire the hybrid router. Separate the standalone showcase view (`/editorial-showcase`) from standard multi-page wraps.

#### [NEW] [EditorialShowcase.tsx](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/components/EditorialShowcase.tsx)
- Port the single-page stack containing the dynamic hero, capabilities matrix, and connection-aware prefetch grids.

#### [MODIFY] [Footer.tsx](file:///c:/FTS/NovoRepo_FOITS/OITS_WEB/fts-oits-web-multipager/components/Footer.tsx)
- Add the permanent "Switch to Single-Page Edition" action anchor.

---

## Verification Plan

### Automated Tests
- Run `npm run build` or `npx tsc` inside `fts-oits-web-multipager` to verify strict type compliance and zero compilation errors.
- Run dev server and use browser audits if applicable.
