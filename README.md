# RPGCore

RPGCore is a research-focused project aimed at identifying and documenting the common mechanical building blocks shared by tabletop role-playing game (RPG) systems.

The project treats each RPG system—and each of its editions—as distinct objects of study. Rather than attempting to implement rules or simulate gameplay, RPGCore records *which kinds of mechanics exist* in each system so they can later be compared, distilled, and abstracted into a generic, system-agnostic model.

This work is intentionally exploratory and descriptive.

---

## What RPGCore Is Trying To Do

- Build a structured research corpus of tabletop RPG systems and their editions
- Document *what mechanics exist*, not how they are implemented
- Classify mechanics into a small set of shared conceptual models
- Identify patterns and common ground across very different RPG systems
- Create a foundation for a future generic mechanics model

---

## What RPGCore Is Not

- Not a game engine
- Not an executable rules system
- Not a character builder
- Not a balance simulator
- Not a repository of copyrighted rules text
- Not defining a final schema or standard (yet)

---

## Research-First Philosophy

RPGCore deliberately separates **research** from **implementation**.

At this stage:

- Ambiguity is allowed and expected
- Over-modeling is avoided
- Features are recorded at a high level
- Details such as numbers, formulas, dice math, or exact rule text are out of scope

The guiding question is always:

> *Does this mechanic exist in the system at all?*

Not:

> *How exactly does it work?*

---

## Core Mechanics Models (Locked)

All observed mechanics are classified into one of four core conceptual models:

1. **Entities**
   Living or acting agents in the game (characters, creatures, etc.)
2. **Objects**
   Non-living items or resources that entities interact with
3. **Locations**
   Spatial or positional concepts that are mechanically relevant
4. **Resolution**
   How outcomes are determined (randomness, tables, comparisons, etc.)

If a mechanic does not clearly fit into one of these models, it is recorded under:

- **unknown**

These models are **conceptual buckets**, not schemas.

---

## How Mechanics Are Documented

Each *edition* of a game system has a single `mechanics.json` file.

That file always has the same top-level structure:

```json
{
  "entities": [],
  "objects": [],
  "locations": [],
  "resolution": [],
  "unknown": []
}
```

**Rules:**

- Values are arrays of strings only
- Strings indicate the *presence* of a mechanic
- No nesting, no booleans, no prose
- Synonyms and duplicates are allowed
- Normalization happens later

**Example features:**

- `attributes`
- `skills`
- `hit_points`
- `random_resolution`
- `tables`

---

## Repository Layout

```text
rpgcore/
├── LICENSE
├── README.md
└── research/
    ├── core_models/
    │   ├── entities.md
    │   ├── objects.md
    │   ├── locations.md
    │   └── resolution.md
    ├── notes/
    │   └── (historical lists and scratch data)
    └── rpg_systems/
        └── <system_id>/
            ├── metadata.json
            └── <edition_id>/
                ├── metadata.json
                └── mechanics.json
```

### Key principles

- One folder per **system lineage**
- One subfolder per **edition**
- Folder names are canonical IDs
- No decade-based organization in authoritative data
- All data under `research/` is provisional and research-oriented

---

## Metadata vs Mechanics

### System-level `metadata.json`

- Describes the overall system lineage
- Includes publishers, origin, genre, language, sources
- Does **not** list editions
- Does **not** include mechanics

### Edition-level `metadata.json`

- Describes a single mechanically distinct ruleset
- Includes edition label, publication year, availability, sources
- Does **not** include mechanics
- Does **not** duplicate system-level data

---

## Current Status

- Research structure established
- Core mechanics models defined and documented
- Mechanics classification approach locked
- Dungeons & Dragons set up as the reference system
- Edition metadata structure finalized
- Mechanics documentation beginning edition by edition

Current work is focused on **documenting mechanics features**, not expanding the system list aggressively.

---

## License

This repository contains original research structure and metadata only.
It does not include copyrighted game text or proprietary rule descriptions.
Please see the LICENSE file for details.
