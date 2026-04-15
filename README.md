<h1 align="center">slop-cleanup</h1>

<p align="center">A research-first repository cleanup skill that coordinates 8 specialized subagents and implements only high-confidence fixes.</p>

## Install

```bash
npx skills add jasperdevs/slop-cleanup
```

## What It Does

This skill is for full-repo cleanup work, not one-off lint fixes. It coordinates eight focused lanes:

1. deduplicate code and reduce unnecessary repetition
2. consolidate shared type definitions
3. remove provably unused code with tool-assisted verification
4. untangle circular dependencies
5. replace weak types with strong, researched types
6. remove unnecessary try/catch and error-hiding fallback logic
7. delete deprecated, legacy, and dead fallback paths
8. remove AI slop, stubs, and low-value comments

Each lane is expected to inspect the codebase, produce a critical assessment, make high-confidence edits, and report residual risk.

## Use

Ask your agent to use `slop-cleanup` when you want a serious cleanup pass across an existing repository. A typical request looks like this:

```text
Use slop-cleanup on this codebase. Research the current state, have each cleanup lane
write a critical assessment and recommendations, then implement all high-confidence changes.
```

## Repository Shape

This repository intentionally contains one public skill at the root so it can be installed directly from GitHub and indexed by the `skills` ecosystem.
