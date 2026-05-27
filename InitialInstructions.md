Based on an audit of your AI Studio histories and the codebase configurations across your repositories, here is the unified, high-performance configuration stack to anchor your AI agents (such as TRAE, Cursor, or Claude Code) inside the environment.

---

## Part 1: Comprehensive Stack of Agentic Dev Env Files

### 1. `AGENTS.md` (System Initialization & Orchestration Blueprint)

````markdown
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
````

````

---

### 2. `constraint.md` (Security, Scope & Guardrail Specifications)
```markdown
# AI Operational Guardrails & Security Policies

This document establishes the strict hard boundaries and testing constraints to prevent code slop, permission leakage, and build regressions.

## 1. Directory Governance & Core Symbiosis
- **Restricted Scopes**: You are strictly prohibited from writing or modifying any assets inside the `apps/mobile` or `apps/api` directories without permission.
- **Cross-Directory Constraints**: If a front-end modification to `apps/web` absolutely necessitates a backend update (e.g., GraphQL Schema resolvers or TypeORM entities inside `apps/api`), you MUST halt operations and prompt the developer for confirmation before writing.
- **Shared Brain First**: Prioritize business logic updates inside `packages/core` to enforce Zod-first validations across all consumer apps.

## 2. Security Protocols & Dependency Auditing
- **Open-Source Vigilance**: Before introducing or updating any external node module or package:
  - Invoke the **Semgrep MCP Server** via `security_check` or `semgrep_scan` to flag potential SAST vulnerabilities.
  - Scan package manifests using **Snyk Agent Scan MCP** or **SafeDep** (`vet-mcp`) to defend against malicious typosquatting, hidden supply chain exploits, or out-of-date licensing.
- **Credential Protection**: Secrets and API keys must remain strictly within local `.env` setups listed explicitly in `.gitignore`. Never inject raw tokens or keys directly into codebase strings.
- **Isolated Code Execution**: Complex, generated code spikes or runtime evaluations must be executed inside isolated sandboxes (e.g., E2B Sandboxes or Docker containers) away from live staging engines.

## 3. Grounding & Codebase Humanization
- **Senior Developer Aesthetic**: Strip out robotic AI tells. Remove structural markers such as "Step 1: Implementation", "Task Summary", or over-explained block comments (e.g., `// This triggers a click action`). Let clean, self-documenting code declare its intent.
- **Modern Language Features**: Utilize current web standards over manual hacks (e.g., leverage the native HTML `inert` attribute to handle modular focus trapping rather than heavy manual aria-hidden loops on `#root`).
- **Build Quality Law**: Do not declare any issue resolved without running full project verification steps. The codebase must successfully complete execution through `pnpm lint` and `pnpm build` across the workspace before a session can be concluded.

````

---

### 3. `mcp_config.json` (Model Context Protocol Tool Integration)

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "description": "Automates live framework discovery to ground the agent against official documentation for React 19, NestJS, GraphQL, and TanStack Query v5."
    },
    "semgrep-guardian": {
      "command": "uvx",
      "args": ["semgrep-mcp"],
      "description": "Runs localized static security audits, automated after-file-edit checks, and credential leak scans."
    },
    "nx-monorepo-docs": {
      "command": "npx",
      "args": ["-y", "nx-docs-mcp"],
      "description": "Provides the agent with structural monorepo awareness, preventing hallucinated project dependency commands."
    }
  }
}
```

---

## Part 2: Codebase & Repository Evaluation

### 1. Implemented Features Matrix

| Feature Domain              | [FarhanSabit-OITS/oits-webiz-gemdem](https://github.com/FarhanSabit-OITS/oits-webiz-gemdem) (Private Target)                                                                                                                                                      | [FarhanSabit-OITS/fts-oits-webgem](https://github.com/FarhanSabit-OITS/fts-oits-webgem) (Public Target)                                                            |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Portfolio Filtering**     | **Advanced Faceted Filter Logic**: Updates selection metrics across categories/chips instantly. Uses zero-matching reactive disabling states (`opacity-40 pointer-events-none`).                                                                                  | **Standard Grid Layout**: Basic categorization display with general structural mapping rules.                                                                      |
| **Asset Prefetching**       | **Adaptive Preloading**: Uses a custom `useEffect` inside `Portfolio.tsx` to pre-inject prefetch links into the document header. Queries `navigator.connection` to block video pre-downloads if network metrics indicate slow 2G/3G speeds or active data saving. | **Hover Preloading**: Implements a standard 150ms debounced hover link insertion pipeline without network link speed metrics checking.                             |
| **Media Engine**            | **Dual-Format Fallback Sourcing**: Custom player built to process explicit `.webm` compression paths with automatic `.mp4` fallbacks.                                                                                                                             | **Standard Sourcing**: Traditional video integration without systemic asset type configurations.                                                                   |
| **User Engagement Layouts** | **About Page Metrics & Footer Toasts**: Includes an animated business metrics module triggered by a scroll observer. Features real-time email format validation on input with an absolute-positioned toast box.                                                   | **Core Service Offerings Matrix**: Extends the capabilities layout array in `constants.ts` to support detailed feature descriptions and internal case study hooks. |
| **Aesthetic Cleanups**      | **Header Layout Isolation**: Simplifies desktop navigation layout rules and updates typing sequences on the landing page hero canvas.                                                                                                                             | **Icon-Only Navigation**: Replaces text links with symbolic SVG elements wrapped in customized tooltip nodes. Fixes text wrapping for CTA buttons.                 |

---

### 2. UI/UX Refinement & Interaction Comparison

- **The Reordering Layer**: `oits-webiz-gemdem` features an interactive filtering interface. Instead of standard visual grid pops, it wraps entries inside Framer Motion's `<AnimatePresence mode="popLayout">` and `<motion.div layout>`. Cards rearrange smoothly across the viewport, eliminating layout shifts.
- **Micro-Interaction Authenticity**: While `fts-oits-webgem` focuses on structural layout integrity (forcing clean single-line flexboxes for arrow-containing CTA buttons), `oits-webiz-gemdem` shifts focus toward interactive authenticity. Its typing sequence engine mimics real developer pauses around formatting syntax characters, elevating the overall premium engineering aesthetic.
- **Accessibility Integrity**: Both applications prioritize accessibility, but `oits-webiz-gemdem` integrates deeper background automation. It adds standard `role="status"` and `aria-live="polite"` tags to asynchronous newsletter feedback prompts and links focus listeners to the carousel to pause intervals immediately upon keyboard navigation.

---

### 3. Commit History & Evolution Summary

#### `oits-webiz-gemdem` (69 Total Commits)

- **Focus**: Performance, state management, and interaction optimization.
- **Key Milestones**: Early logs show general architecture migrations followed by rapid iteration cycles focusing on UX enhancements. Key entries highlight animating components via intersection observers (`pages/AboutPage.tsx`, `components/Metrics.tsx`) and finalizing performance tuning layers (`perf: implement adaptive connection preloading`). The terminal history concludes with deep asset-handling changes (`feat(portfolio): enhance media asset loading and navigation`) targeting loading speeds.

#### `fts-oits-webgem` (122 Total Commits)

- **Focus**: Layout architecture, capability definition, and automation scaffolding.
- **Key Milestones**: Reflects a broader development cycle spanning 5 months. Early work focuses on initializing Vite configurations and tailoring basic responsive styling rules (`index.css`, `tailwind.config.js`). Mid-stage progression centers around expanding business representation schemas within `constants.ts`. The final commit sequence features system cleanups (`feat: expand service offerings and refine navigation/CTA layouts`) alongside explicit configuration templates to streamline agent development workflows.

This comprehensive instruction blueprint and structured prompt stack is engineered for **Antigravity**. It provides clear guidelines for executing a deep code audit across both repositories, merging their capabilities, and assembling an enterprise-grade, Swiss-Modern digital ecosystem.

You can save this template directly into your workspace as `MERGE_WORKFLOW.md` or feed it to your Antigravity agent sequentially.

---

# Antigravity Orchestration Blueprint: Dual-Repository Architectural Fusion

## System Context & Objective

You are tasked with combining two codebases into a unified, high-performance platform:

1. **Primary Structural Site (Multi-Page Base):** [FarhanSabit-OITS/oits-webiz-gemdem](https://github.com/FarhanSabit-OITS/oits-webiz-gemdem) — Handles complex multi-page routing, advanced functional modules, and application pages.
2. **Aesthetic & Kinetic Enhancer (Single-Page Editorial Showcase):** [FarhanSabit-OITS/fts-oits-webgem](https://github.com/FarhanSabit-OITS/fts-oits-webgem) — Features a premium Swiss-Modern editorial layout, custom animations, asset prefetching, and high-density typography.

### Core Architecture Strategy

- **The Main Site:** Retain the React Router / multi-page layout of `oits-webiz-gemdem` as the primary user journey. Up-level its UI with the Swiss-Modern aesthetic rules, motion configurations, and interactive components from `fts-oits-webgem`.
- **The Single-Page Variant:** Maintain the original high-density landing page experience of `fts-oits-webgem` by placing it on an explicit fallback route (e.g., `/classic-editorial` or `/showcase`). Expose this alternative layout through an elegant link in the global footer.

---

## Phase 1: Contextual Discovery & Deep Audit

Execute these inspection commands to map the state configurations, dependencies, and component signatures of both source workspaces.

```markdown
# PROMPT STEP 1: COMPONENT & DATA SCHEMATIC AUDIT

Target: Analyze core configuration files and layout entry points across both repository trees.

Instructions:

1. Run `view_file` on both `App.tsx` file paths to contrast routing pipelines versus single-page block rendering.
2. Cross-examine both `constants.ts` and `types.ts` structures. Note any overlapping data models for Services, Case Studies, and Team portfolios.
3. Identify all UI modules in the single-page repo (`components/*`) that feature advanced interactive components missing from the multi-page app (e.g., connection-aware prefetchers, tab layout morphs).

Output Requirement:
Provide a unified schema draft for `constants.ts` that includes all extended parameters from both codebases without data truncation.
```

---

## Phase 2: Structural Synchronization & Dependency Consolidation

Before modifying the UI, unify the environment variables, packages, and style definitions.

```markdown
# PROMPT STEP 2: STACK HARMONIZATION

Target: Consolidate package manifests, Tailwind tokens, and global style layers.

Instructions:

1. Audit the `package.json` configurations. Merge all UI dependencies, ensuring compatible versions of Framer Motion (`motion`), Lucide React (`lucide-react`), and any core asset managers.
2. Combine the Tailwind configuration files. Specifically extract custom keyframes, text-glow animations, and micro-interactions from `fts-oits-webgem/index.css`.
3. Ensure strict TypeScript compilation rules remain intact. Define shared layout contracts explicitly within `/src/types.ts`.

Verification Guardrail:
Do not write code blocks using dynamic bindings until `compile_applet` confirms zero dependency mismatches.
```

---

## Phase 3: Architectural Layout Merging & Routing Setup

Integrate the multi-page engine with the alternative single-page presentation layout.

```markdown
# PROMPT STEP 3: ROUTING & SYSTEM ARCHITECTURE

Target: Formulate the hybrid router to serve both user experiences concurrently.

Instructions:

1. Preserve the structural routing system of `oits-webiz-gemdem` inside `/src/App.tsx`.
2. Encapsulate the single-page layout from `fts-oits-webgem` inside a standalone feature component: `/src/pages/EditorialShowcase.tsx`.
3. Configure an explicit route pointing to this new component: `<Route path="/editorial-showcase" element={<EditorialShowcase />} />`.
4. Inject a permanent, semantic link within the global `Footer` navigation block:
   - Label: "Switch to Single-Page Edition" / "Editorial Experience"
   - Destination: `/editorial-showcase`
```

---

## Phase 4: Component Polish & Aesthetic Enhancement

Refine the main site pages with the Swiss-Modern visual rules and performance enhancements found in the single-page design.

```markdown
# PROMPT STEP 4: INTERACTION & PERFORMANCE ENHANCEMENT

Target: Upgrade multi-page modules using the interactive elements from the single-page showcase.

Instructions:

1. Refactor the main site Hero and layout containers to reflect the Swiss-Modern theme: high contrast minimal dark/light nodes, Inter headings, and monospaced accents.
2. Implement the performance-focused, hover-triggered asset prefetching features from the showcase repo into the portfolio grids to reduce modal load times.
3. Port all physical motion configurations (500ms–700ms timing windows) into route variations and modal overlays using Framer Motion containers.
4. Verify text formatting across all devices: ensure call-to-action buttons maintain clean, single-line typography.
```

---

## Phase 5: Quality Assurance & Production Verification

Run comprehensive performance audits and ensure adherence to your structural engineering rules.

```markdown
# PROMPT STEP 5: COMPILATION & CONVENTIONAL AUDIT

Target: Validate type safety, layout performance, and complete the development cycle.

Instructions:

1. Trigger `lint_applet` followed directly by `compile_applet` to intercept potential compilation breaks or dead path configurations.
2. If any compilation errors arise, cease asset additions, locate the specific file context, and resolve the module mapping.
3. Upon validation, generate an automated conventional commit message matching the template in your `AGENTS.md` guidelines.

Commit Message Expectations:
feat(core): merge multi-page architecture with premium single-page visual assets

- System Integration: Linked single-page showcase onto an isolated route via the global footer layout.
- UI Enhancement: Ported Swiss-Modern typography configurations and hover-triggered asset prefetching.
- Performance: Standardized Framer Motion transition curves across all platform landing portals.
```

To install and activate **Antigravity Skills** and **Auto Skills** (automated lifecycle hooks) within your workspace, follow this step-by-step implementation guide. This setup configures the Model Context Protocol (MCP) layer alongside workspace-level markdown skill injectors to give your AI agent deep context and automated execution capabilities.

---

## Step 1: Configure the Global MCP Host Environment

Antigravity relies on an underlying configuration file to look up external tools and protocols. You need to register your required capability integrations (like `context7` for live documentation or `semgrep` for security scanning).

Locate your global configuration file (typically `mcp.json` or `antigravity.config.json` in your home directory or global app data) and add your server array:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "semgrep": {
      "command": "npx",
      "args": ["-y", "semgrep-mcp@latest"]
    }
  }
}
```

---

## Step 2: Inject Workspace-Level "Agent Skills"

Agent Skills are modular, `.md`-based packages of instructions, aesthetic rules, and workflows that Antigravity scans and loads when interacting with a specific repository.

1. Navigate to the root directory of your project.
2. Create a file named **`AGENTS.md`** (or place custom skill blocks inside a `.skills/` directory).
3. Populate it with your primary system contracts. Here is the operational skeleton for your architecture:

```markdown
# Repository Agent Skills & Constraints

## 1. Context Grounding

- Do not rely purely on internal knowledge boundaries for volatile syntaxes.
- Automatically trigger the `context7` server to fetch updated documentation whenever editing framework-level logic.

## 2. Code Quality & Verification

- Prioritize atomic components and separate state configuration data into `/src/constants.ts`.
- **The Iron Law:** You must trigger `lint_applet` followed by `compile_applet` to verify compilation before declaring a task finished.
```

---

## Step 3: Initialize "Auto Skills" (Automated Lifecycle Hooks)

Auto Skills allow the agent to automatically perform operations—like validating your code layout, formatting components, or writing structured git trails—without requiring explicit manual prompts.

### 1. Enable Automated Conventional Commits

To automate structured output workflows, add an explicit compliance layout rule at the bottom of your workspace `AGENTS.md` file:

```markdown
## 3. Auto-Skill: Automated Commit Generation

Upon completing any task involving verified code changes, you must automatically formulate a commit proposal in the following strict format:

type(scope): summary

- Technical change 1
- Technical change 2
```

### 2. Configure IDE File Watchers / Hooks

If you are using tools like **Semgrep Guardian** to automatically audit generated code right as the agent drops a block:

- Ensure Python 3.10+ and the Semgrep CLI are accessible on your system path (`pipx install semgrep`).
- In your IDE or workspace properties, activate the `afterFileEdit` or `post_write_code` triggers to pass altered code lines straight to the validation array.

---

## Step 4: Verification Run

To ensure Antigravity has properly ingested the configuration layer and the workspace skills:

1. Open your chat interface or terminal inside the workspace.
2. Issue a lightweight validation command to test alignment:

   > _"Scan this workspace and verify the active constraints inside AGENTS.md."_

3. The agent should return a summary of your custom layout conventions, proving that the skill stack has successfully mounted.

This **`constraint.md`** file establishes the operational boundaries, security protocols, and stylistic requirements for the AI tool within the codebase.

---

# 📜 Fundamental AI Constraints & Operational Rules

## 1. Directory & Scope Governance

- **Restricted Access:** You are strictly prohibited from modifying any files within the `apps/mobile` and `apps/api` directories [User Prompt].
- **Cross-Directory Dependency:** If a change to `apps/web` absolutely necessitates a corresponding modification in `apps/api` (e.g., a GraphQL schema update), you **must** pause and request explicit feedback from the lead developer before applying the change [User Prompt, 1052].
- **The Nerve Center:** Always prioritize logic and schema changes in **`packages/core`** first. This package acts as the "shared brain," ensuring that Zod-first validations and deterministic calculations remain consistent across all platforms.

## 2. Documentation & Knowledge Grounding

- **Official Tech Stack:** Before proposing architectural changes, use **MCP Servers** (like `Context7` or `nx_docs`) or web browsing to gather official documentation for the primary technologies:
  - **Frontend:** React 19, TanStack Router (File-based), TanStack Query v5 (Object-based syntax).
  - **Backend:** NestJS, GraphQL (Apollo), PostgreSQL, TypeORM.
  - **Validation:** Zod (for shared schemas) and TypeScript (Strict mode).
- **Context Discovery:** Use tools like `nx_docs` to retrieve up-to-date documentation sections relevant to the Nx monorepo structure to avoid hallucinating commands.

## 3. Security & Safety Protocols

- **Open-Source Vigilance:** When integrating open-source resources or MCP servers, follow strict security guidelines:
  - **Explicit Approvals:** Always prompt for manual user confirmation before triggering file system changes, write operations, or external API calls.
  - **Workspace Isolation:** Never attempt to connect directly to production databases; use staging or obfuscated data clones.
  - **Dependency Scanning:** Use specialized tools like **Semgrep** or **Snyk** to audit dependencies for vulnerabilities or malware before introducing them into the codebase.
- **Auth Integrity:** Do not alter the **Silent JWT Refresh** logic or the **Tab-Level Session Bridge** unless specifically tasked to resolve a verified bug in `auth-context.tsx`.
- **Secret Management:** Never hardcode credentials. Use `.env` files and ensure they are listed in `.gitignore`.

## 4. Codebase Humanization

- **Senior Dev Aesthetic:** All code must be "humanized." Remove robotic markers, formal section headers (e.g., "Step 1: Implementation"), and AI-generated filler comments.
- **Clean History:** Present code changes as logical, human-like iterations (e.g., "refactor: modernize api-client with centralized fetcher") to maintain a professional audit trail.
- **Readability:** Favor clear, expressive naming conventions and modular logic over over-engineered or repetitive "AI slop" patterns.

## 5. Verification & Completion

- **The Iron Law:** Do not claim a task is "complete" without performing verification.
- **Build Checks:** Ensure the project compiles by running `pnpm build` across the relevant workspace before finishing a session.
- **Schema Alignment:** After any API modification, re-run **GraphQL Codegen** to ensure the frontend remains in sync with the backend resolvers.

To implement **Semgrep** for enforcing security constraints within your project, you can integrate the **Semgrep MCP Server** and the **Semgrep Guardian** plugin. This setup allows your AI tool (like Antigravity, TRAE, Cursor, or Claude Code) to perform static analysis, audit open-source dependencies, and verify code against security policies in real-time.

### 1. Core Integration Methods

You can implement Semgrep through two primary paths depending on your workflow:

- **Semgrep MCP Server:** This provides the AI agent with specific tools to call on-demand, such as `security_check` (to scan for vulnerabilities) and `semgrep_scan_with_custom_rule` (to enforce project-specific logic).
- **Semgrep Guardian:** A more automated approach that bundles the MCP server with **IDE-level hooks**. It can be configured to scan every file an agent generates before the code is even committed.

### 2. Implementation Steps

To set up the environment for these security constraints, follow these steps:

1.  **Prerequisites:** Ensure you have **Python 3.10 or later** installed, as the Semgrep CLI requires it at runtime.
2.  **Install Semgrep CLI:** Use a package manager like `brew`, `pipx`, or `uv` to install the latest version:
    - `pipx install semgrep`.
3.  **Configure the MCP Server:** Add the Semgrep server to your tool's configuration (e.g., `mcp_config.json` or `mcp.json`). Use the following command for a local setup:
    - `npx -y semgrep-mcp@latest` or `uvx semgrep-mcp`.
4.  **Activate Guardian Hooks:** If your IDE supports it (like Cursor or Windsurf), enable the `afterFileEdit` or `post_write_code` hooks. This ensures that whenever the AI tool modifies a file, a security scan is triggered automatically.

### 3. Enforcing Specific Constraints

Drawing from your project's rules, you can use Semgrep to satisfy several security and operational requirements:

- **Open-Source Vigilance (SCA):** To follow your rule regarding **security concerns with opensource resources**, use Semgrep's **Supply Chain** scanning. This audits your `package.json` and lockfiles for known vulnerabilities in third-party libraries. You may also consider the **Snyk Agent Scan MCP** as a secondary layer for dependency auditing.
- **Enforcing Directory Governance:** While the AI tool is instructed to avoid `apps/api`, you can write **custom Semgrep rules** to flag any unauthorized patterns or imports that bypass your established `packages/core` logic.
- **Credential Protection:** Use Semgrep's **Secrets** scanning to ensure the AI does not accidentally hardcode credentials in `.env` files or source code, which aligns with your project's security protocols.

### 4. Operationalizing via AI Prompts

Once integrated, you can proactively command Antigravity, TRAE, Cursor, or Claude Code to use these security tools. Examples include:

- _"Scan the current file for security vulnerabilities using Semgrep."_
- _"Check if the new open-source package I just added has any reported vulnerabilities."_
- _"Run a security audit on the latest changes in apps/web before I review the PR."_

By combining the **Semgrep MCP Server** for on-demand checks and **Semgrep Guardian** for automated hooks, you create a "security-first" environment that prevents the AI from introducing "slop" or vulnerabilities into the codebase.

To enhance the security posture of the **Citadel NexGen** project, the following rules regarding **Semgrep** and **dependency auditing** have been added to your **`constraint.md`** file. These rules ensure that every AI-generated change is audited for vulnerabilities, secrets, and supply chain risks before being finalized.

---

# AI Constraints & Operational Rules (Updated)

## 1. Directory & Scope Governance

- **Restricted Access:** You are strictly prohibited from modifying any files within the `apps/mobile` and `apps/api` directories [User Prompt].
- **Cross-Directory Dependency:** If a change to `apps/web` absolutely necessitates a corresponding modification in `apps/api`, you **must** request explicit feedback from the developer first [User Prompt, 1052].
- **Shared Logic:** Prioritize logic in **`packages/core`** to maintain a "single source of truth" for Zod schemas and calculations.

## 2. Documentation & Knowledge Grounding

- **Official Tech Stack:** Use **MCP Servers** (e.g., `Context7`) or web browsing to fetch official documentation for technologies used in the codebase.
- **Context Discovery:** Use the **Nx MCP server** (`nx_docs`) to understand monorepo relationships and avoid hallucinating Nx commands.

## 3. Security & Operational Auditing

- **Semgrep Static Analysis:** Before submitting any code change, you must invoke the **Semgrep MCP Server** to perform a multi-layer scan:
  - **Vulnerability Check:** Use `security_check` or `semgrep_scan` on all modified files to identify SAST (Static Application Security Testing) issues.
  - **Secret Detection:** Run Semgrep **"Secrets"** scanning to ensure no hardcoded credentials or JWT keys are introduced into `.env` or source files.
  - **Custom Rules:** Enforce project-specific standards using `semgrep_scan_with_custom_rule` where necessary.
- **Dependency Auditing:** You must audit all open-source resources before they are added to the codebase [User Prompt]:
  - **Supply Chain Security:** Use **Semgrep Supply Chain** or the **Snyk Agent Scan MCP** to check `package.json` and lockfiles for vulnerabilities, malware, or typosquatting.
  - **Vetting:** Utilize **SafeDep (`vet-mcp`)** to vet new packages for security risks before recommending them for installation.
- **Real-time Validation:** If available in the IDE, ensure **Semgrep Guardian** hooks (like `afterFileEdit`) are active to catch issues as code is written.

## 4. Codebase Humanization

- **Senior Dev Aesthetic:** Code must be expressive and modular. Remove AI-generated filler comments and robotic section headers [User Prompt, 1082].
- **Clean History:** Present changes as logical, human-like iterations.
- **Accessibility:** Use the **modern `inert` attribute** instead of manual `aria-hidden` management on the `#root` element to prevent focus traps.

## 5. Verification & Completion

- **The Iron Law:** No task is complete without verification. **Evidence before claims**.
- **Pre-Commit Build:** Run `pnpm build` and `pnpm lint` across the workspace before concluding a session.
- **Auth Integrity:** Ensure the **Silent JWT Refresh** logic is not degraded during refactors.

To **humanize** OITS_WEB TypeScript codebase, you should move away from robotic, AI-generated structures and toward a **Senior Developer Aesthetic** that prioritizes intent, clean history, and expressive logic.

### 1. Eliminating Robotic Scaffolding

- **Remove AI Signatures:** Strip out formal section headers such as "Step 1: Implementation," "Task Summary," or "Plan Overview" that often characterize AI-generated outputs.
- **Clean Documentation:** Delete generic filler comments like `// This is a constant for the API URL` and focus on documentation that provides **high-level context** or explains **why** a complex architectural decision was made.
- **Senior Dev Tone:** Avoid repetitive "AI slop" patterns by favoring **modular logic** and clear, expressive naming conventions over over-engineered boilerplate.

### 2. Human-Centric Git Iterations

Instead of submitting massive, monolithic code dumps, present changes as **logical, human-like iterations** with clear rationales.

- **Expressive Commit Messages:** Use specific, descriptive titles like `refactor: modernize api-client with centralized fetcher logic` instead of generic descriptors like `update files`.
- **The "Rationale" Pattern:** Include personal-sounding justifications in commit descriptions to show the thought process, such as "I'm tired of manually typing responses; let's let the machine do the heavy lifting from the schema".
- **Incremental Progress:** Break large features into **human-sized phases**—for example, separate "Tooling & Infrastructure" from "Feature Integration"—to maintain a professional and readable audit trail.

### 3. Architecture as a Maturity Signal

A humanized codebase demonstrates **technical maturity** through sophisticated patterns rather than just functional code.

- **Single Source of Truth:** Enforce "Core Symbiosis" by sharing **Zod-first validations** and deterministic calculations in `@repo/core` so that backend and frontend stay perfectly in sync.
- **Modern Language Features:** Use current standards like the **`inert` attribute** for accessibility instead of manual `aria-hidden` management to solve complex problems simply and elegantly.
- **Strict Type Safety:** Implement high-fidelity tools like **TanStack Router** to achieve 100% type-safety, ensuring that non-existent route navigation is caught at build-time.

### 4. Advanced "Humanized" Features

- **Zero-Flicker UX:** Implement **Route Loaders** to pre-fetch data, ensuring that the UI only renders once the cache is hydrated, providing a premium feel.
- **Context-Aware UI:** Build responsive navigation using a **"Fitting Room"** approach—using `ResizeObserver` to calculate pixel-level width—rather than relying on rigid, robotic CSS breakpoints.
- **Atomic State Management:** Treat user profiles and tokens as **atomic pairs** to ensure consistency across multiple browser tabs, preventing "ghost sessions" or UI flashes.

```

```
