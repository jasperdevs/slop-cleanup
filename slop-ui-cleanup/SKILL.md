---
name: slop-ui-cleanup
description: UI cleanup and design quality improvement workflow. Use when Codex needs to audit and improve an existing interface by coordinating 8 specialized subagents to deduplicate UI patterns, consolidate shared UI systems, remove unused interface pieces, untangle messy layouts, strengthen typography and hierarchy, remove unnecessary fallback or cluttered UI, delete deprecated interface paths, and remove AI slop or low-value UI copy while researching first and implementing only high-confidence recommendations. Focus on design systems, layout, hierarchy, modularity, states, and interface clarity rather than backend, business logic, or non-UI programming work.
---

I want to clean up my UI and improve design quality. This is a complex task, so we'll need 8 subagents. Make a subagent for each of the following:
1. Deduplicate and consolidate UI patterns, and implement modularity where it reduces visual complexity
2. Find all shared UI systems, tokens, style definitions or components and consolidate any that should be shared
3. Find all unused UI, dead variants, old styles or unnecessary interface pieces and remove them, ensuring that they are actually not referenced anywhere
4. Untangle any messy layout structure, inconsistent composition, or confusing component relationships
5. Remove any weak UI decisions, for example generic spacing, weak hierarchy, weak color usage, weak typography, weak states or the equivalent in other design systems, research what the UI should be, research in the current product and related systems to make sure that the replacements are strong and there are no design issues
6. Remove all fallback or defensive UI patterns if they do not serve a specific role for the user or otherwise have a reason to be there, with clear interaction handling and no clutter, duplication or confused states
7. Find any deprecated, legacy or fallback UI, remove it, and make sure all interface paths are clean, concise and as singular as possible
8. Find any AI slop, placeholders, generic dashboard patterns, unnecessary labels, helper text or comments and remove them. Any copy or comments that describe in-motion work, replacements of previous work with new work, or otherwise are not helpful should be either removed or replaced with helpful UI language for a new user trying to understand the interface-- but if you do edit, be concise

I want each to do detailed research on their task, write a critical assessment of the current UI and recommendations, and then implement all high confidence recommendations.
