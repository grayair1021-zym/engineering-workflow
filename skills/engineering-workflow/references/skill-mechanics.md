# Skill invocation and context cost

The description is the discovery pointer. Keep it concise and specific to supported tasks, including indirect agent-facing documents; broad keyword triggers and competing ownership can select irrelevant Skills. Details hidden only in the body cannot reliably trigger discovery.

Codex Skills keep the required `name` and `description` frontmatter. Automatic selection is the default. Only an explicit user request for manual-only invocation justifies `policy.allow_implicit_invocation: false` in `agents/openai.yaml`; use current `skill-creator` rules for schema and packaging. Do not copy another host's `disable-model-invocation` field or assume that a router can never reach another Skill.

Choose the smallest useful ownership boundary:

- **Independent Skill:** a distinct task should discover it directly, or several workflows need it. Its extra name/description must earn their persistent context cost.
- **On-demand reference:** guidance belongs to one workflow or one escalation branch and needs no separate global trigger. Put a precise loading condition in its parent; the human should not have to memorize the reference's filename.
- **Router:** useful only when it reduces real selection burden. Reuse an existing router before adding another one. Keep detailed guidance at its owner rather than importing every body into the router.

Discovery descriptions consume context even when the Skill is unused; bodies load when selected; references load only for their declared branch. Packaging should reflect those three stages. Separate files remain useful only when agents can reach them predictably.

Prefer outcomes, domain constraints and conditional pointers over elaborate itineraries or old-model compensations. Consider the actual consuming models; do not turn simple tasks into mandatory document/test rituals. Preserve justified permissions, safety, integrity and compatibility requirements.

For new/substantially revised Skills, check applicable current official guidance for the consuming models; use `openai-docs` if available when evidence is missing or stale, otherwise consult the official provider documentation directly. Reuse current evidence within the task.

After a substantive primary-model change or observed instruction incompatibility, check current official guidance for that model and only affected Skills, AGENTS and long-lived prompts (`openai-docs` is optional). Change only requirements evidence shows are unsuitable; retain necessary boundaries. No scheduled whole-system audit or automatic rule deletion. Scope review to authorized files; suggest changes outside that scope.

For a substantive routing change, use a fresh task with a realistic request and inspect actual reads and behavior. Test an intended trigger and an adjacent non-trigger. Wording-only changes need proportionate local checks. Follow the host's actual loading/update mechanism; use the project's publication entrypoint when managed snapshots exist.

Reference: [OpenAI guidance](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra).
