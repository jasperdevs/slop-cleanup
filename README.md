<h1 align="center">🧹 slop-cleanup</h1>

<p align="center">clean up your slop code with this simple skill, 8 subants cleaning it up</p>

<p align="center">Credit: <a href="https://x.com/shawmakesmagic">shawmakesmagic</a></p>

## Install

```bash
npx skills add jasperdevs/slop-cleanup
```

```mermaid
flowchart TD
    A[Clean up the codebase]
    A --> B[Spawn 8 subagents]

    B --> C[1. Deduplicate code<br/>and apply DRY]
    B --> D[2. Consolidate shared<br/>type definitions]
    B --> E[3. Find and remove<br/>unused code]
    B --> F[4. Untangle circular<br/>dependencies]
    B --> G[5. Replace weak types<br/>with strong types]
    B --> H[6. Remove unnecessary<br/>try catch and fallbacks]
    B --> I[7. Remove deprecated<br/>legacy and fallback code]
    B --> J[8. Remove AI slop<br/>stubs and bad comments]

    C --> K[Research current state<br/>write assessment<br/>implement high-confidence fixes]
    D --> K
    E --> K
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K
```
