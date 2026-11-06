# Quality rules & conflict handling

## Source of truth priority (default)

When generating or updating docs, enforce this order in **AI Agent Instructions** and follow it yourself:

1. Explicit user instructions for the current task  
2. Approved PRD  
3. Approved architecture / ADRs  
4. System design / UI doc + **live CSS/theme tokens**  
5. Existing codebase conventions  
6. General AI assumptions (lowest)

## Design token conflicts

If both exist:

- Live theme/CSS variables (e.g. `frontend/src/styles.css`)
- A generated design-system master (e.g. `design-system/**/MASTER.md`)

**and** names/roles disagree (e.g. “Primary” = sidebar vs CTA):

1. **Do not silently pick.**
2. Record as Critical in the consistency review.
3. After owner approval, either:
   - Stub/redirect the master to CSS + UIUX doc, **or**
   - Regenerate the master to match CSS.

Declare the chosen SoT in UIUX + Agent docs.

## MCP / dual API surfaces

If the product exposes more than one agent surface (e.g. HTTP `/mcp` vs local stdio client):

- Document **each surface’s tool subset** in PRD, Architecture, and Agent instructions.
- Never imply vault (or other sensitive tools) exist on a surface that excludes them.

## Commands & environments

| Rule | Detail |
| --- | --- |
| Verify | README, package.json, Compose, pytest.ini |
| Unknown | `[TBD]` — never invent |
| Destructive | Explain + require human approval |
| Production | Never deploy/mutate live hosts without explicit ask |

## Backup / security wording

Do not write “encrypted dump” unless the script actually client-encrypts. Prefer precise language:

- Bucket/KMS **at rest**, and/or
- Application-level ciphertext columns (e.g. vault) inside a plain SQL dump

Separate **recommended** host practices (EBS snapshots) from **in-repo** automation.

## Acceptance criteria

- Prefer testable AC for every Must Have FR.
- UAT rows may stay `[TBD]` until executed — do not fake results.
- NFRs that need metrics: either define a measurement path or mark non-mandatory until observability exists.

## Consistency review severities

| Level | Meaning |
| --- | --- |
| Critical | Wrong SoT / agents will implement incorrectly |
| High | Contradictory requirements or missing must-have ops clarity |
| Medium | Incomplete AC, naming drift, under-specified surfaces |
| Low | Polish, optional tooling, deferred a11y claims |

## After approval

Patch all affected docs in one change set; update review “resolution status”; set **Last updated** (user’s timezone label).

