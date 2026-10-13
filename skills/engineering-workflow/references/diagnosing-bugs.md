# Diagnosing hard bugs

Use after quick inspection fails to explain a hard bug, flaky failure or performance regression, or for an explicitly requested deep diagnosis. Keep the investigation within the task's existing authority and stop at a verified outcome. This is a diagnostic reference, not a second engineering workflow.

## Protect the evidence

Before displaying or retaining commands, logs, traces, HARs or packet captures, redact secrets, cookies, authorization headers and private payloads. Capture only the signal needed for the current hypothesis. Use approved credential injection; never print environment dumps or put secrets in command arguments. Keep raw sensitive artifacts out of the repository, Vault and conversation. When redaction removes necessary evidence, identify the missing fact and request a safe alternative. Live instrumentation and production replay require their normal authorization.

## Establish a tight, red-capable loop

A **tight** loop is cheap enough to repeat during investigation. **Red-capable** means it drives the actual failing path and asserts the user's symptom, rather than merely finishing without an exception.

Inspect enough code and configuration to construct the loop. Prefer an existing targeted test; otherwise use a minimal CLI/HTTP fixture, browser check, sanitized replay or disposable harness. Run it and preserve the command, relevant conditions and red result. If a human step is unavoidable, record the action and observable verdict explicitly; do not mistake an unrun automation for reproduction.

Reduce inputs and steps one at a time while preserving the same failure. Stop shrinking when further reduction would not distinguish causes or improve regression coverage; proving mathematical minimality is unnecessary.

- **Flaky:** pin seeds, time and dependencies where useful; control interleavings or use bounded repetitions. Record failures/trials and conditions. A zero-failure run alone is not proof of a fix. Do not use uncontrolled stress against live systems.
- **Performance:** establish the same workload, warm-up and baseline; measure latency, throughput or resource use with a profiler/query plan as appropriate. Compare distributions or repeated measurements, not one noisy timing. Prefer deterministic work counts when they faithfully capture the regression.

If reproduction remains unavailable, report attempted probes and the missing environment or sanitized evidence. Hypotheses may guide further evidence gathering, but a speculative patch is not a verified fix. Do not turn missing access into indefinite looping or an automatic request for broader access.

## Falsify, then fix

Rank plausible hypotheses by evidence; use as many as materially differ, not a fixed quota. For each, name a prediction and an observation that would refute it: “If X causes the failure, varying Y should change Z.” Briefly expose consequential uncertainty to the user without creating routine approval gates.

Choose the smallest probe that discriminates between hypotheses. Change one variable at a time; use a debugger or targeted instrumentation at the relevant interface. Give temporary logs a unique tag so they can be found and removed. Prefer profiling over blanket logging for performance work. Keep an evidence trail of predictions, outcomes and eliminated causes; do not log everything.

Turn the repro into regression coverage at the actual caller/test interface, including multiple callers or timing when those cause the bug. Observe red before the fix, then green after the narrow fix. If that interface cannot reproduce the pattern, document the verification gap; do not add a hollow unit test or redesign unrelated architecture just to claim coverage.

## Finish

Re-run the original scenario as well as the minimized regression and nearby relevant checks. For flakes/performance, report the comparison conditions and remaining uncertainty. Remove temporary tagged instrumentation; retain only useful regression fixtures. Handle disposable artifacts through the project's cleanup rules, with recoverable Trash for existing user files. State the supported cause, fix and evidence in the task result; creating a commit or PR is not required.

Adapted from Matt Pocock's `diagnosing-bugs`; provenance and MIT notice are bundled in `ATTRIBUTION.md` and `LICENSE` at the Skill root.
