# RPGCore

RPGCore is a system-agnostic foundation for working with tabletop role-playing game
(RPG) systems in code.

The idea is simple: treat each RPG system as its own thing, model its editions
explicitly, and build everything on top of that solid data. Over time, those systems
can be broken down into shared mechanics and eventually used as plugins inside
game engines or other tools.

Development starts in Python so it’s easy to experiment and iterate. If performance
ever becomes a problem, parts of the project may later be rewritten in a compiled
language like Rust.

---

## What RPGCore Is Trying To Do

- Build a clean, structured database of tabletop RPG systems
- Track editions and history accurately instead of flattening everything
- Find the common building blocks shared across different RPG systems
- Make it possible to implement systems as modular, pluggable rule sets
- Stay engine-agnostic and system-agnostic

---

## What RPGCore Is Not

- Not a game engine
- Not a character builder or content generator
- Not tied to any single RPG system or license
- Not a source of copyrighted game text

---

## Current Focus: Research First

Right now RPGCore is in a research and data-modeling phase.

Before trying to simulate mechanics or write rules engines, the goal is to first build
a reliable, historically accurate catalog of existing RPG systems and their editions.

### Research Scope

- Work decade by decade, starting with the 1970s
- English-language tabletop RPGs (US, UK, Canada)
- Includes both well-known and obscure systems
- Systems must have published rules (availability is tracked separately)

---

## Repository Layout

```text
rpgcore/
├── LICENSE
├── README.md
└── research/
    └── rpg_systems/
        ├── 1970s.json
        └── candidates_1970s.txt
```

- candidates_1970s.txt
  A working list of RPG systems being considered for the decade.

- 1970s.json
  Normalized data following the current RPGCore schema.

---

## Data Model (v1)

- One JSON file per decade
- Each file contains systems, not loose editions
- Each system includes:
  - Basic metadata (name, publisher, country, genre, sources)
  - A list of editions, each with:
    - A stable ID
    - Display name / edition label
    - First publication year
    - Availability info
    - License info
    - Notes and sources

This keeps history intact, avoids duplication, and lines up with the eventual
plugin-style architecture.

### How Edition Boundaries Work

- Editions follow publisher-recognized core rule releases
- Parallel branches count as separate editions (e.g. Basic D&D vs AD&D)
- Minor revisions, reprints, or later renaming don’t create new editions
- For Dungeons & Dragons, the Wikipedia “Editions of Dungeons & Dragons” page is used
  as the reference

---

## Current Progress

- Research structure in place
- Schema v1 stabilized
- Initial 1970s candidate list compiled
- Dungeons & Dragons fully normalized across its editions:
  - OD&D (1974)
  - Basic D&D (1977)
  - AD&D (1977)
  - AD&D 2nd Edition (1989)
  - D&D 3rd Edition (2000)
  - D&D 4th Edition (2008)
  - D&D 5th Edition (2014)

Naming reflects what the games were actually called at the time, not later
retrospective labels.

---

## Status

Active development.
Current work: normalizing the next RPG system from the 1970s.
