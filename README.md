<h1 align="center">🧹 slop-cleanup</h1>

<p align="center">two cleanup skills: one for code, one for UI</p>

<p align="center">Credit: <a href="https://x.com/shawmakesmagic">shawmakesmagic</a></p>

## Install

```bash
npx skills add jasperdevs/slop-cleanup
```

<details>
<summary>Install Manually</summary>

```bash
npx skills add https://github.com/jasperdevs/slop-cleanup --skill slop-cleanup
npx skills add https://github.com/jasperdevs/slop-cleanup --skill slop-ui-cleanup
```

</details>

## `slop-cleanup`

<a href="https://skills.sh/jasperdevs/slop-cleanup/slop-cleanup">View `slop-cleanup` on skills.sh</a>

```mermaid
flowchart TD
    A[slop-cleanup] --> B[spawn 8 subagents]
    B --> L
    B --> R

    subgraph L[code lanes 1-4]
        direction TB
        L1[dedupe and DRY]
        L2[shared types]
        L3[unused code]
        L4[circular deps]
    end

    subgraph R[code lanes 5-8]
        direction TB
        R1[weak types]
        R2[try catch cleanup]
        R3[legacy removal]
        R4[AI slop cleanup]
    end

    L --> C[research and assess]
    R --> C
    C --> D[apply high-confidence fixes]
```

## `slop-ui-cleanup`

<a href="https://skills.sh/jasperdevs/slop-cleanup/slop-ui-cleanup">View `slop-ui-cleanup` on skills.sh</a>

```mermaid
flowchart TD
    A[slop-ui-cleanup] --> B[spawn 8 subagents]
    B --> L
    B --> R

    subgraph L[UI lanes 1-4]
        direction TB
        L1[UI pattern dedupe]
        L2[shared UI systems]
        L3[unused UI cleanup]
        L4[layout untangling]
    end

    subgraph R[UI lanes 5-8]
        direction TB
        R1[strong hierarchy]
        R2[remove UI fallbacks]
        R3[legacy UI removal]
        R4[AI slop UI cleanup]
    end

    L --> C[research and assess]
    R --> C
    C --> D[apply high-confidence fixes]
```
