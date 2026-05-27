# AI Operational Guardrails & Security Policies

This document establishes the strict hard boundaries and testing constraints to prevent code slop, permission leakage, and build regressions.

## 1. Directory Governance & Core Symbiosis
- **Restricted Access**: You are strictly prohibited from writing or modifying any assets inside the `apps/mobile` or `apps/api` directories without permission.
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

## 4. Semgrep & Security Rules (Updated)
- **Vulnerability Check**: Use `security_check` or `semgrep_scan` on all modified files to identify SAST (Static Application Security Testing) issues.
- **Secret Detection**: Run Semgrep **"Secrets"** scanning to ensure no hardcoded credentials or JWT keys are introduced into `.env` or source files.
- **Custom Rules**: Enforce project-specific standards using `semgrep_scan_with_custom_rule` where necessary.
- **Dependency Auditing**: You must audit all open-source resources before they are added to the codebase:
  - **Supply Chain Security**: Use **Semgrep Supply Chain** or the **Snyk Agent Scan MCP** to check `package.json` and lockfiles for vulnerabilities, malware, or typosquatting.
  - **Vetting**: Utilize **SafeDep (`vet-mcp`)** to vet new packages for security risks before recommending them for installation.
