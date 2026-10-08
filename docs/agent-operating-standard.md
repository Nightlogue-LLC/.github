# Nightlogue LLC — Shared Agent Operating Standard

This document governs coding agents working in Nightlogue LLC repositories. Product-specific repository instructions take precedence for technical architecture and safety; this standard governs workflow, issue creation, metadata, and PR handling.

## Sources of truth
- Work-item naming and approved areas: [work-item-conventions.md](./work-item-conventions.md). **Do not duplicate or invent controlled Area names.**
- Nightlogue Command Center: https://github.com/orgs/Nightlogue-LLC/projects/2
- Product repository AGENTS.md: product architecture, local tests, deployment rules, and special constraints.
- Verify current GitHub settings before mutating issues or project items; if they differ from this document, surface the discrepancy rather than guessing.

## Execute the work
- Inspect the repository and existing issue/PR history. When tooling and permissions permit, implement a scoped request directly in code, run relevant checks, and open a PR rather than referring it to Lovable.
- Escalate to Lovable only when its editor or managed services are genuinely required. Explain the concrete blocker and what can be completed directly.
- Use a dedicated branch and PR for substantive changes. Never force-push or rewrite published history in Lovable-connected repos. Don't merge, deploy, publish, or run destructive production migrations without authorization.
- Report what was tested and what remains unverified. Never imply a change is merged, deployed, or tested without evidence.

## Issue titles and fields
- Title format: `[Area] Verb + outcome` — follow [work-item-conventions.md](./work-item-conventions.md).
- Do not add [Type], Product, Priority, or Horizon to the title.
- Set the native issue Type, appropriate repository labels, and project/issue fields when accessible. Do not confuse issue types with labels or Size with Effort.
- When creating an implementation issue, include Goal, Why, Scope, Constraints, acceptance criteria, verification plan, and references. Include reproduction steps for bugs.
- Search for duplicates first. Avoid replacing existing owner decisions with invented assumptions.

### Command Center dictionary (owner-confirmed 2026-10-08)
| Field | Valid choices |
| --- | --- |
| Status | Backlog; Ready; In progress; In review; Done |
| Priority | Urgent; High; Medium; Low |
| Size | XS; S; M; L; XL |
| Effort | High; Medium; Low |
| Product | Forbidden Folio; ExactMods; LO Ecosystem; Note & Veil; TSP; LO; Menkari; Other |
| Horizon | 🔥 Now; 🌤️ Soon; 🌙 Later; 💭 Someday |

**Repository labels confirmed for Forbidden Folio**: `accessibility`, `blocked`, `bug`, `data`, `dependencies`, `editor`, `needs-design`, `needs-research`, `performance`, `security`. Labels belong to individual repos: check availability there before assigning; do not assume this list exists in other repos.

**Issue types:** Check native enabled types in the organization before assignment. The existing work-item conventions reference Task, Bug, Feature, Improvement, Content, SEO, Maintenance, Research, and Idea; not all were independently verified as enabled from the current connector. Never silently create a label in place of a missing native Type.

Use product ownership based on the work's actual scope, not merely the repository name. Ask when ambiguous. `Status` reflects workflow; `Horizon` reflects desired timing; `Priority` reflects importance.

### Project status transitions
- **Backlog:** not actively queued.
- **Ready:** scoped and suitable for pickup.
- **In progress:** implementation actively underway.
- **In review:** PR/review or acceptance verification underway.
- **Done:** verified completion with acceptance criteria met; do not infer Done from PR creation.
Project status is separate from GitHub issue open/closed state.

## Manual GitHub setup — mandatory fallback
Try native API connections first, then verify results. If any metadata or link cannot be set, place a **Manual GitHub setup** checklist at the *beginning* of the issue body, including only unfinished actions, with exact values and links:

```md
## Manual GitHub setup
- [ ] Add to Nightlogue Command Center — Project #2
- [ ] Set Type: Improvement
- [ ] Set Status: Ready
- [ ] Set Product: Forbidden Folio
- [ ] Set Priority: Medium
- [ ] Set Effort: Low
- [ ] Set Size: S
- [ ] Set Horizon: 🌤️ Soon
- [ ] Add native sub-issue relationship: parent #123
- [ ] Add dependency: blocked by #124
```

Remove a line once its action is verifiably applied. Do not claim an issue is a native sub-issue from a Markdown reference alone. For items requiring user decisions, write `Needs owner decision` rather than inventing a value. Use the same fallback for every child issue.

## Parents, children, and dependencies
- Make parent issues outcome-focused; create discrete, individually testable children for separable work.
- Assign the native parent/sub-issue connection if the API supports it. Link parent in the child's body as a readable fallback.
- Set native blocked-by/blocking dependencies where available. Avoid duplicative or circular relationships.
- Preserve parent metadata when appropriate, but verify inherited fields instead of assuming automation succeeded.
- A completed child never implies parent completion.

## PRs and completion
- Link every implementation PR to the relevant issue. Use `Closes #123` or `Fixes #123` only when acceptance criteria are fully satisfied and merge closure is intended.
- For partial implementation use `Refs #123` and leave the issue open. When a parent has children, close only the completed scope.
- Include summary, issue link, changed behavior, tests actually run and outcomes, screenshots for UI changes where feasible, migration/risk notes, and remaining manual QA.
- Create a draft PR for unverified or incomplete changes and clearly list blockers.
- Confirm checks and review state before proposing merge; never assume opening a PR completes the task.

## Product and data safeguards
- Preserve product-specific instructions in each repository's AGENTS.md and follow them for architecture, integrations, publishing, and migration.
- Do not expose secrets, private configuration, or private data in issues/PRs.
- Protect production data; use auditable and reversible migrations and explicit production-write approval.
- Preserve existing editorial content and live URLs unless the work explicitly authorizes changes.

## How each repository consumes this standard
Place an `AGENTS.md` at the repository root that tells agents to read this standard and the naming conventions, then supplies local repo guidance. Agents must fetch linked shared docs when they can; the document link alone does not guarantee every agent will automatically read the remote file.

**Canonical shared URLs:**
- https://github.com/Nightlogue-LLC/.github/blob/main/docs/agent-operating-standard.md
- https://github.com/Nightlogue-LLC/.github/blob/main/docs/work-item-conventions.md

For agents without network or cross-repository access, local instructions should summarize the critical rules and request the authoritative standard when needed.
