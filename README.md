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
    B --> C

    subgraph C[8 cleanup lanes]
        direction LR
        C1[dedupe]
        C2[shared types]
        C3[unused code]
        C4[circular deps]
        C5[weak types]
        C6[try catch cleanup]
        C7[legacy removal]
        C8[AI slop cleanup]
    end

    C --> D[Research each lane]
    D --> E[Write assessment and recommendations]
    E --> F[Apply high-confidence fixes]
```
