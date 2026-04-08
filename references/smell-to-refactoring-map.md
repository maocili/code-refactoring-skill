# Smell To Refactoring Map

Use this map to choose a safe first move. Apply the smallest step first, then evaluate whether a follow-up is needed.

| Smell | Smallest safe first move | Follow-up move if needed |
| --- | --- | --- |
| Duplicated code | Extract one duplicated fragment into a named function and call it from both sites. | Slide related statements together, then pull up shared behavior or move it to one owner. |
| Long function | Extract a small intention-revealing function around one coherent block. | Replace temps with queries, introduce parameter object, or replace function with command. |
| Long parameter list | Introduce a parameter object for values that travel together. | Preserve whole object, replace parameter with query, or split the function by responsibility. |
| Global or mutable data | Encapsulate variable access behind controlled getters/setters. | Encapsulate record, remove setting methods where possible, and narrow scope to module/class. |
| Feature envy | Move a function closer to the data it mostly reads or updates. | Extract helper behavior first, then move function or move field to rebalance ownership. |
| Data clumps | Group recurring parameter/field bundles into a small object. | Extract class and move related behavior into it. |
| Repeated switches | Extract each branch calculation into named helper functions. | Replace conditional with polymorphism when repeated branching persists across the codebase. |
| Message chains | Hide delegate at the chain boundary to reduce caller coupling. | Move function down the chain so callers ask fewer intermediates. |
| Middle man | Remove trivial forwarding methods that add no value. | Inline lightweight delegators or redesign delegation boundaries. |
| Large class | Extract a cohesive subset of fields and methods into a new class. | Move function and move field iteratively; extract superclass only when common protocol is clear. |
| Data class | Move behavior from clients into the data-holding type. | Encapsulate record and remove mutable setters that are not required. |
| Comments as deodorant | Replace explanatory comments with intention-revealing names and extracted functions. | Introduce assertions for invariants and keep only high-value why-comments. |

## Practical Selection Rule

- Prefer a reversible first move over a perfect long-term design.
- Favor changes that reduce edit distance for the next likely feature request.
- Escalate to broader refactorings only after low-risk options plateau.
