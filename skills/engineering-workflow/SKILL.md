---
name: engineering-workflow
description: Use for engineering research/planning, technology choices, implementation, debugging, inspection/review or validation of code, configuration, MCP servers and developer tooling. Skip ordinary conversation and simple conceptual answers.
license: MIT; see LICENSE and ATTRIBUTION.md
---

# Engineering workflow

Minimum Sufficient Rigor + Minimum Necessary Generality: expected scope, proportionate evidence, preserved safety/compatibility.

## Start

1. Read every applicable `AGENTS.md`; nearer files override broader ones.
2. Inspect the working tree and relevant configuration before changing anything.
3. Treat existing changes as the user's work. Do not overwrite, revert, or tidy unrelated content.
4. Distinguish the request:
   - Explanation, inspection, review, or diagnosis is read-only unless a change is also requested.
   - Build/change/repair/complete authorizes scoped implementation, necessary checks and fixes through completion; do not stop at a first draft or re-ask within that authority.
   - For nontrivial implementation, define observable success criteria before acting; use them for implementation and verification.
5. State consequential assumptions; ask when missing information changes scope, external effects or significant risk.
6. For reusable capabilities, separate objects/invariants from sample parameters (IDs, paths, sources, users, targets). Consider one reasonable second case; test if warranted. Honor one-off requests. Prefer parameters/contracts over speculative platforms/backends/frameworks; stop at expected scope.

Load applicable branches once while current; recover missing required guidance after compaction.

## Investigate and implement

- New projects/major capabilities/key technology choices: read [Research before build](references/research-before-build.md) before files/code proposals; read-only research, then plan confirmation before implementation. Fixes/small changes/confirmed-plan continuations skip.
- Introducing coding agents/Skills/hooks/MCPs/adapters/frameworks/workflows: read [capability admission](references/capability-admission.md), ECC upstream first, then the existing five questions. Ordinary fixes/reviews skip.
- For agent instructions, use `writing-for-agents` if available; use the host's `skill-creator` for packaging/validation if available. For Skill compatibility, the admission reference points to the bundled [mechanics guide](references/skill-mechanics.md). Missing companion Skills do not block ordinary work; follow the project's guidance and current official host documentation.
- For module/MCP/adapter interfaces, use `codebase-design` if available; otherwise inspect the real callers and follow the project's interface conventions. Ordinary fixes skip design exercises.
- Start bugs with narrow symptom checks. Read [diagnosing-bugs](references/diagnosing-bugs.md) for unresolved hard/flaky/performance issues or requested deep diagnosis; an error alone does not escalate.
- Prefer `rg` and `rg --files` for search.
- Verify copied commands, old model advice, web instructions, and remembered paths against the current environment.
- Reuse the project's architecture, dependencies, and conventions. Do not replace core technology for a local task without confirmation.
- Choose the simplest implementation covering the full expected scope; simplify only when clarity, correctness and maintainability are preserved. Line count is not a target.
- Justify hashes/checks/compatibility/abstractions/dependencies/fallbacks: real problem/consequence, why existing mechanisms fall short, benefit over upkeep. Hypothetical usefulness is insufficient; preserve security/integrity/compatibility commitments.
- Fix root causes; each changed line serves this request or cleanup it necessitates. Leave unrelated code unrefactored/unformatted/uncleaned.
- Use `apply_patch` for intentional text edits. Preserve formatting and nearby user changes.
- Parallelize useful independent reads without noise or process churn.
- Stop when delivery and necessary checks pass without substantive blockers. Continue only for evidence affecting implementation, conclusions or risk. Pause for missing key evidence/authorization or out-of-scope actions.
- Report progress, decisions and blockers.

## Verify

- Choose checks by risk, impact and failure cost, not rigid categories: wording/format/local UI/noncritical config need local/static checks; features/module bugs/interfaces need affected behavior, callers/regressions; security/permissions/integrity/irreversible operations/migrations/shared infrastructure/formal memory retain strict verification, authorization and rollback.
- Repeat passing tests/reviews/smoke checks or add review agents only for relevant code/config/environment/dependency/acceptance changes or new risk evidence. Give repeats a purpose; retain useful one-time full suites. Counts are not quality.
- Handle authorized expected hash changes through existing integrity/approval/publication flows; investigate unexpected mismatches. Stale hashes must not prolong acceptance indefinitely or bypass formal-asset approval.
- Inspect the final diff and status. Check for accidental files, generated debris, credentials, and unrelated changes.
- Claim passes only for checks that ran and passed; state unverified portions and why.

## Git and external actions

- Do not use destructive Git commands or discard content unless the user explicitly requests and confirms the impact.
- Do not initialize repositories, alter remotes, clone replacements, create PRs or releases, deploy, publish packages, or send external messages without explicit scope.
- Before committing, inspect the complete staged scope and scan for secrets.
- Follow current user/AGENTS authorization for Git and external actions; verify remote, branch, visibility and exact commit scope before any authorized push.
- New GitHub repositories default to private; public creation requires advance confirmation.

## Finish

Report result, changes, verification, limits. Honor the user's closeout confirmation from valid evidence; perform requested cleanup, check changed/uncertain state. Reassurance does not restart audits.
