---
name: slop-cleanup
description: Deep repository cleanup and code quality improvement workflow. Use when Codex needs to audit and clean a codebase by coordinating 8 specialized subagents to deduplicate code, consolidate shared types, remove unused code, untangle circular dependencies, replace weak types like any or unknown, remove unnecessary try/catch or defensive fallback patterns, delete deprecated or legacy paths, and remove AI slop or low-value comments while researching first and implementing only high-confidence recommendations.
---

# Slop Cleanup

Clean the codebase with a research-first, implementation-second workflow. Use exactly 8 subagents, one for each workstream defined below.

## Operating Rules

1. Read the codebase before changing it. Reuse existing patterns and keep diffs local.
2. Start with a quick repo census:
   - Detect languages, package managers, test commands, linters, and typecheck commands.
   - Identify relevant manifests, workspace files, and architecture boundaries.
   - Identify which of the requested tools already exist in the repo, such as `knip` or `madge`.
3. Spawn exactly 8 subagents. Give each one a single cleanup lane and clear ownership. Tell them they are not alone in the codebase and must not revert other edits.
4. Require each subagent to do detailed research before editing:
   - Inspect the relevant code paths.
   - Use repo-native tooling where available.
   - Use official docs or upstream source when type replacements or dependency behavior are unclear.
   - Separate findings into high-confidence, medium-confidence, and speculative recommendations.
5. Require each subagent to return:
   - Critical assessment of the current state.
   - Recommended changes with rationale.
   - The concrete edits they made for high-confidence items.
   - Verification performed and any residual risks.
6. Merge only high-confidence recommendations. If a recommendation is risky, invasive, or architecture-changing, leave it as a recommendation instead of forcing it.
7. Verify the final result with the smallest credible proof for the repo: targeted tests, lint, typecheck, build, or direct repro steps.

## Subagent Lanes

### 1. Deduplication and DRY

Find duplicated logic, parallel implementations, or near-identical utilities. Consolidate only when the shared abstraction reduces total complexity. Do not create generic helper layers for one-off code.

### 2. Shared Type Consolidation

Find type definitions that are duplicated, drifting, or should be shared across modules. Consolidate them into the narrowest shared home that matches existing project structure. Update imports and verify no type regressions.

### 3. Unused Code Removal

Use tools like `knip` when applicable, plus repo search, exports tracing, and framework entrypoint checks, to confirm code is actually unused. Remove only after proving it is not referenced by runtime wiring, dynamic imports, configuration, generated code, or tests.

### 4. Circular Dependency Untangling

Use tools like `madge` when applicable, plus manual graph inspection, to find cycles. Remove cycles with the smallest structural change that preserves ownership boundaries and avoids creating vague shared dumping grounds.

### 5. Weak Type Removal

Find weak types such as `any`, `unknown`, broad object maps, untyped JSON blobs, or language-equivalent escape hatches. Research the correct types from nearby code, external package typings, schemas, validators, or protocol docs before replacing them. Prefer strong types that reflect real data flow.

### 6. Defensive Error Handling Cleanup

Find `try/catch`, fallback branches, swallowed errors, silent recovery, and equivalent defensive patterns. Remove them when they only hide failures or wrap deterministic code with no real recovery path. Keep explicit handling for unsanitized input, network or I/O boundaries, third-party behavior, and user-facing recovery flows.

### 7. Deprecated, Legacy, and Fallback Path Removal

Find deprecated helpers, migration leftovers, compatibility branches, feature-flag corpses, old code paths, and fallback logic that no longer serves a real deployment case. Remove dead branches and simplify flow so the intended path is singular and clear.

### 8. AI Slop and Comment Cleanup

Find placeholder code, stubs, larp, generic wrappers, padded abstractions, TODO theater, and low-value comments. Remove comments that narrate edits, migrations, or obvious operations. Keep or replace only comments that help a new engineer understand intent, invariants, or non-obvious constraints.

## Execution Sequence

1. Build the repo census and define verification commands.
2. Spawn the 8 subagents with disjoint ownership where possible.
3. Let each subagent research first and write a critical assessment before editing.
4. Review their findings for overlap, then implement or integrate high-confidence changes.
5. Re-run targeted verification after each risky cluster of edits.
6. Finish with a concise final report covering:
   - What changed
   - What was recommended but not changed
   - What was verified
   - Remaining risks or follow-up work

## Tool Guidance

- Prefer repo-native tooling first.
- Use `knip` for unused code in JS or TS repos when relevant.
- Use `madge` for dependency-cycle analysis when relevant.
- Use fast code search such as `rg` to confirm references before deleting anything.
- When external types are involved, consult official package docs, generated typings, schemas, or upstream source before changing signatures.
- Do not add new dependencies unless the existing repo clearly needs them to complete the requested cleanup.

## Guardrails

- Do not silently widen types to make errors disappear.
- Do not replace duplicated code with a worse abstraction.
- Do not remove error handling at trust boundaries.
- Do not delete code that might be dynamically referenced until that path has been checked.
- Do not rewrite the architecture under the banner of cleanup.
- Do not keep decorative comments, defensive noise, or fallback paths without a concrete purpose.
