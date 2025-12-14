========================
core_models/resolution.md
========================

# Resolution

Resolution describes how the game determines outcomes when uncertainty or conflict exists.

This model is intentionally separate from Entities, Objects, and Locations because it governs
*how decisions are resolved*, not what exists in the game world.

## Research questions

- Are outcomes deterministic or random?
- Are outcomes binary or graded?
- Is resolution centralized or context-specific?

## Common observable features

Examples of features that may appear under this model:

- random_resolution
- deterministic_resolution
- dice
- tables
- comparisons
- success_levels
- failure_levels
- modifiers
- target_numbers

Resolution mechanics often interact with other models, but should be categorized here
when their primary role is determining outcomes.

If a resolution mechanism cannot be cleanly classified, record it under `unknown`.

---