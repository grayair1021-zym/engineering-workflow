# Research before build

Use for a new project, major capability expansion or a key architecture/dependency choice. Ordinary fixes, small changes and implementation continuing an already confirmed plan do not repeat this phase. A material change to the agreed architecture or MVP reopens only the affected decision.

## Read-only discovery

Establish the intended users, core outcome, constraints and success criteria from the request and existing project. Ask only for missing information that would change the recommendation; make other assumptions explicit and continue independent research.

Inspect existing local capabilities first, then search GitHub and relevant official documentation for comparable open-source projects. This phase creates no files, including trackers, plans or scaffolds; outputs no implementation code; installs no dependencies; and does not clone or execute candidate projects. Present findings in the conversation. Research access does not authorize adoption or integration.

When the existing [capability admission](capability-admission.md) scope applies, including a new MCP regardless of its product domain, follow its ECC upstream-first and five questions once. This checks reusable engineering capabilities and patterns; it does not make ECC a product architecture candidate. Also research the product's own domain. Products outside the admission scope need only their domain research. Do not duplicate admission checks or require a new Skill for each investigation.

## Evaluate evidence, not popularity

Select a small, relevant shortlist, usually 3–5 projects; fewer is appropriate when evidence is scarce. For each, explain the problem solved, fit to our requirements, architecture and data flow, technical dependencies, license constraints, operational cost, and designs to reuse or avoid.

Inspect relevant source, manifests, releases and maintainer activity, not only README claims. Look for credible real-use evidence such as documented deployments, downstream integrations or operational reports. Stars and a recent commit do not prove production use; low commit frequency alone does not prove abandonment. Record the date of the check and distinguish verified evidence, maintainer claims, inference and unknowns. Never label a project battle-tested without supporting evidence.

Study concrete pitfalls in Issues, fixes and migration notes. Link the relevant issue, PR, release note or source path; distinguish resolved historical problems from current limitations and our own inferred risks. Explain whether each lesson applies to our scale, deployment and trust boundaries. If research channels or evidence are unavailable, report that limit rather than claim no suitable project exists.

## Present a decision, then pause

Deliver a concise comparison and a recommendation tied to the user's requirements:

- Recommended stack and credible alternative, with explicit tradeoffs and a reuse, selective adaptation or custom-build decision.
- System components, data flow, storage and external dependencies; include trust boundaries where relevant.
- MVP inclusions, exclusions and observable acceptance criteria.
- Development order that proves the core outcome early, plus material risks and unresolved decisions.

Keep the scope proportional; this is not an exhaustive market survey. Stop when the evidence is sufficient for the decision, or explicitly identify what remains unverified. Ask the user to confirm this concrete plan before creating files or implementing. Reuse an existing confirmation of the same plan; do not ask again because the task or window continued. Explicit user changes to this workflow take precedence.

After confirmation, resume the owning build workflow and update its existing task record with the accepted decision and evidence. Follow project-specific contracts and applicable specialist guidance for MCP/module design, credentials and runtime operations; use existing `build-mcp-server` or `codebase-design` Skills if available, preserving their authorization boundaries. Do not create trackers solely to satisfy this reference.

Method reference: ECC search-first, <https://github.com/affaan-m/ECC/blob/main/skills/search-first/SKILL.md>, reviewed 2026-10-05. This guide references its research/evaluation approach and adds evidence and confirmation requirements; it does not install ECC or adopt its automatic implementation or agent-launch steps.
