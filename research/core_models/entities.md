# Entities

Entities represent living or acting agents within a game system.

This model exists to capture whether a system treats characters, creatures, or other actors as
distinct mechanical units with persistent state.

This model intentionally ignores *how* entities are implemented and focuses only on *whether*
certain concepts exist.

## Research questions

- Do entities exist as discrete mechanical units?
- Are entities persistent across game sessions?
- Do entities have internal state that can change over time?

## Common observable features

Examples of features that may appear under this model in a system’s mechanics.json:

- attributes
- skills
- hit_points
- levels
- classes
- conditions
- status_effects
- progression
- advancement
- combat_capability
- non_combat_actions

These examples are not exhaustive and not prescriptive.

If a feature relates primarily to the internal state or capabilities of a character or creature,
it should be considered part of the Entities model.

If a feature does not clearly fit, record it under `unknown`.

---
