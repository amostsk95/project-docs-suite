# Deliverables — section outlines & diagrams

Use these outlines when generating the suite. Omit sections only if truly N/A (note why). Mark unknowns `[TBD]`.

## `docs/PRD.md`

| Section | Content |
| --- | --- |
| Meta table | Doc ID, product, repo, status, owner, last updated (user TZ) |
| A Overview | Name, description, background, problem, solution, objectives, value |
| B Goals | Primary/secondary goals, KPIs, success criteria |
| C Users | Personas, permissions matrix |
| D Scope | In / out / assumptions |
| E Functional | FR catalog + AC for each Must/Should feature |
| F Non-functional | Performance, security, reliability, scale, compatibility |
| G Journeys | Primary flows + Mermaid |
| H (optional) | Data / integrations summary or link to architecture |
| I Risks | Risk register |
| J Release | Phases, deploy flowchart |
| K Acceptance | DoD, UAT checklist, sign-off |
| Appendix | Glossary, diagram index, changelog |

## `docs/SYSTEM_DESIGN_UIUX.md`

| Section | Content |
| --- | --- |
| A Design overview | Philosophy, objectives, audience, principles, visual direction, references |
| B Design system | Color tokens (name, HEX, RGB, usage, a11y), typography, spacing, radius, shadow, icons, grid, breakpoints |
| C Components | Buttons, inputs, nav, cards, modals, tables, empty/loading, etc. — purpose, variants, states, guidelines |
| D Screens | Screen ID, route, purpose, layout, components, desktop/tablet/mobile |
| E Interactions | Click/hover/focus/keyboard, validation, loading, errors, motion |
| F IA | Sitemap, hierarchy, menu, breadcrumbs |
| G Accessibility | WCAG target, contrast, keyboard, SR, forms |
| H Responsive | Breakpoints, adaptations |
| I Validation | Review / usability / a11y / consistency checklists |

**Token rule:** Prefer live CSS variables from the codebase as SoT. Declare SoT explicitly if a parallel design-system file exists.

## `docs/SYSTEM_ARCHITECTURE.md`

| Section | Content |
| --- | --- |
| A Overview | Description, objectives, principles, patterns, key decisions |
| B Stack | Category / tech / version / purpose; why / alternatives |
| C Components | Name, responsibility, tech, I/O, deps, comms, failure handling |
| D High-level diagram | Mermaid |
| E Flows | Request, auth, data, errors — sequence/flow Mermaid |
| F Database | ERD, tables, keys, indexes, migrations, backup |
| G API | Style, endpoint map, authz, errors, integrations; MCP surfaces if any |
| H Project structure | Tree + folder responsibilities |
| I Security | Authn/z, encryption, secrets, network, OWASP notes |
| J Infra & deploy | Hosting, envs, containers, CI/CD, rollback |
| K Scalability | What is / isn’t designed |
| L Observability | Logs, metrics, health, gaps |
| M ADRs | One record per important decision |
| N Testing | Layers and locations |
| O Future | Limitations, debt, proposals |

## `docs/AI_AGENT_INSTRUCTIONS.md` + `AGENTS.md`

| Section | Content |
| --- | --- |
| A Role | Identity, scope, limits, human approval |
| B Context | Overview + links to PRD / Arch / UI |
| C Doc priority | Explicit precedence list |
| D Coding standards | Naming, organization, errors, comments |
| E Structure rules | Where new files go |
| F Workflow | Understand → docs → code → plan → implement → test → review → docs → summarize |
| G Commands | Verified only; destructive gated |
| H Security | MUST / MUST NOT |
| I Database | Conventions; no destructive ops without approval |
| J Testing | Honesty about execution |
| K Debugging | RCA before speculative fixes |
| L Git | Branch/commit/PR rules for the environment |
| M Dependencies | Package managers, pinning |
| N Deploy | Env rules; no prod without ask |
| O Reporting | Change summary format |
| P Escalation | When to ask |

`AGENTS.md` at repo root: ≤20 lines pointing at the agent doc + reading order + critical SoT/MCP caveats.

## `docs/DOCUMENTATION_CONSISTENCY_REVIEW.md`

- Executive summary (quality, critical, gaps, actions)
- Consistency matrix
- Issue register (Critical / High / Medium / Low)
- Recommended changes by document
- Final validation checklist
- Conflicts awaiting human approval (until resolved)

## Recommended Mermaid sources (`docs/diagrams/`)

| File | Use |
| --- | --- |
| `architecture.mmd` | High-level components |
| `components.mmd` | Richer component/network view |
| `login-flow.mmd` / `nav-flow.mmd` | Auth / session |
| `request-flow.mmd` / `data-flow.mmd` / `interaction-form.mmd` | Runtime flows |
| `erd.mmd` | Data model |
| `deploy-flow.mmd` / `deployment.mmd` / `cicd.mmd` | Ops |
| `sitemap.mmd` / `responsive-shell.mmd` | IA / responsive |
| `expense-journey.mmd` (or domain journeys) | Key product flows |
| `agent-workflow.mmd` | Agent development loop |

Split large diagrams; keep labels meaningful; sync embedded Mermaid in `.md` with `.mmd` sources.

