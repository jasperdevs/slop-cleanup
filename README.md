<h1 align="center">🧹 slop-cleanup</h1>

<p align="center">A research-first repository cleanup skill that coordinates 8 specialized subagents and implements only high-confidence fixes.</p>

<p align="center">Credit: <a href="https://github.com/shawmakesmagic">shawmakesmagic</a></p>

## Install

```bash
npx skills add jasperdevs/slop-cleanup
```

## Use

Use `slop-cleanup` when you want a full-repository cleanup pass instead of one-off linting or formatting. It researches the codebase first, splits work across 8 focused subagents, writes a critical assessment for each lane, and only applies high-confidence fixes.

```text
Use slop-cleanup on this codebase. Research the current state, have each cleanup lane
write a critical assessment and recommendations, then implement all high-confidence changes.
```
