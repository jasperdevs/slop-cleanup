<h1 align="center">🧹 slop-cleanup</h1>

<p align="center">clean up your slop code with this simple skill, 8 subants cleaning it up</p>

<p align="center">Credit: <a href="https://x.com/shawmakesmagic">shawmakesmagic</a></p>

## Install

```bash
npx skills add jasperdevs/slop-cleanup
```

```mermaid
flowchart TD
    A[Start cleanup] --> B[Spawn 8 subagents]
    B --> L
    B --> R

    subgraph L[lanes 1-4]
        direction TB
        L1[1. dedupe and DRY]
        L2[2. shared types]
        L3[3. unused code]
        L4[4. circular deps]
    end

    subgraph R[lanes 5-8]
        direction TB
        R1[5. weak types]
        R2[6. try catch cleanup]
        R3[7. legacy removal]
        R4[8. AI slop cleanup]
    end

    L --> C[Research, assess, recommend]
    R --> C
    C --> D[Apply high-confidence fixes]
```
