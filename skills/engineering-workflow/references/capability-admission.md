# Capability admission

Use before adding or introducing a coding agent, Skill, hook, MCP, adapter, engineering framework or general engineering workflow. Ordinary fixes, reviews and use of existing capabilities need no admission.

New or substantially revised Skills also require the Skill compatibility check below. Revisions introducing no new capability need only that check; wording-only edits skip it.

## Check upstream first

Check current [ECC upstream](https://github.com/affaan-m/ECC) for a mature, maintained implementation, pattern or component suited to the current harness. Verify maintenance and harness support from current upstream evidence; do not assume parity across harnesses. ECC is the default engineering upstream candidate, not a second framework or runtime dependency.

If ECC covers the need, compare what existing capabilities already cover and name its actual increment. Prefer upstream reuse, selective adoption or reference to a mature implementation. Do not adopt a whole profile for completeness, fork ECC, or copy large upstream trees into local maintenance. Before an authorized component integration, dry-run and audit conflicts; prefer removing the local duplicate it replaces, preserving needed behavior, over layering implementations. Evaluation does not authorize installation, configuration changes or deletion.

If ECC does not cover the need, is unsuitable, or costs more than its increment, record that finding and use the five questions below to decide on local implementation. Any proposed adoption must also justify a clear increment. Unavailable upstream evidence is an explicit unknown, not proof of noncoverage or a reason to block ordinary engineering.

## New capability admission

1. 它填补了哪个真实、反复出现的缺口？
2. 现有能力已覆盖多少，剩余增量是什么？
3. 增量需要独立 Skill，还是现有入口的按需 reference？
4. 常驻 context、重复规则和维护成本增加多少？
5. 不收编会具体失去什么，是否已有更小的解决办法？

没有清晰增量就不收，不为体系完整引入第二套 workflow。Keep canonical source → validation → the project's existing publication and recovery path; this Skill does not require creating a Registry or managed-release system.

## Skill compatibility

Read the bundled [Skill mechanics](skill-mechanics.md) for discovery, ownership, loading and model compatibility. Use `writing-for-agents` if installed for instruction wording. Reuse these checks, not a second checklist. For new capabilities, retain ECC and the five questions above; an existing Skill revision does not itself authorize a new capability or bypass the project's publication rules.

## Memory boundary

Do not replace the project's designated long-term memory or truth source with ECC Memory Vault / unified-memory, continuous-learning / continuous-learning-v2, Context Keeper, omega-memory or another semantic retrieval layer without explicit scoped authorization. Preserve the existing authority and permissions of formal data; retrieved or inferred candidates require original-source verification before factual use.

This upstream-first policy installs no ECC full / developer / core / minimal profile, runs no installer, changes no MCP / hook / credentials, and creates no automatic upstream sync or daemon. Any later component adoption is a separate scoped change.
