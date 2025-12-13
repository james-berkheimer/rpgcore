# RPGCore

RPGCore is a system-agnostic core framework for representing tabletop role-playing game
(RPG) systems in a structured, extensible, and historically accurate way.

The project treats each RPG system as a first-class entity, with explicit modeling of
editions and lineage. This data-first foundation is intended to support later
decomposition of mechanics and eventual use of RPG systems as modular plugins in
software engines.

Initial development is Python-first to prioritize clarity, correctness, and rapid
iteration.

---

## Project Goals

- Create a canonical, version-controlled database of tabletop RPG systems
- Model RPG systems and their editions explicitly and historically
- Establish common structural abstractions across disparate RPG systems
- Enable future implementation of systems as pluggable rule modules
- Remain engine-agnostic and system-agnostic

---

## Non-Goals

- RPGCore is not a game engine
- RPGCore is not a content or character generator
- RPGCore does not include copyrighted game text
- RPGCore does not attempt to simulate or balance gameplay at this stage

---

## Current Phase: Research & Data Modeling

RPGCore is currently in a **research and normalization phase**.
The focus is on compiling a reliable database of existing RPG systems and editions
before attempting to formalize mechanical abstractions.

### Research Scope

- Decade-by-decade approach, starting with the **1970s**
- English-language tabletop RPGs (US / UK / Canada)
- Includes both major and obscure systems
- Inclusion requires published rules (availability tracked separately)

### Repository Structure

```text
rpgcore/
├── LICENSE
├── README.md
└── research/
    └── rpg_systems/
        ├── 1970s.json
        └── candidates_1970s.txt
```

- `candidates_1970s.txt`
  A staging list of candidate systems identified for the decade.
- `1970s.json`
  Normalized, structured data following the RPGCore schema.

---

## Data Model (Schema v1)

- One JSON file per decade
- Each file contains **systems**, not flat editions
- Each system contains:
  - Metadata (name, publisher, country, genre, sources)
  - A list of **editions**, each with:
    - Stable ID
    - Display name and edition label
    - First publication year
    - Availability status
    - License status
    - Sources and notes

This structure avoids duplication, preserves historical lineage, and maps cleanly to
future plugin-based implementations.

### Edition Boundary Rules

- Edition boundaries follow **publisher-recognized, formally released core rulesets**
- Parallel branches are separate editions (e.g., Basic D&D vs AD&D)
- Minor revisions, reprints, or retrospective labels do not create new editions
- For *Dungeons & Dragons*, the Wikipedia “Editions of Dungeons & Dragons” page is used
  as the authoritative guide

---

## Current Progress

- Research framework established
- Schema v1 stabilized
- 1970s candidate list compiled
- **Dungeons & Dragons** fully normalized across its historical editions:
  - OD&D (1974)
  - Basic D&D (1977)
  - AD&D (1977)
  - AD&D 2nd Edition (1989)
  - D&D 3rd Edition (2000)
  - D&D 4th Edition (2008)
  - D&D 5th Edition (2014)

Naming reflects contemporaneous usage, not later retrospective terminology.

---

## Process Discipline

- One change at a time
- No inferred naming or assumptions
- Explicit confirmation before schema or naming changes
- Data validity verified via scripts

---

## Status

Active development — research and normalization ongoing.

Next step: normalize the next 1970s RPG system.
