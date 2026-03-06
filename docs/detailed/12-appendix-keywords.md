# Latium Codex – Appendix: Latin Keyword Candidates

**Document ID:** `12-appendix-keywords.md`
**Part of:** Detailed Documentation Series
**Audience:** Developers, contributors, language implementers
**Last Updated:** 2026-03-06

---

## Overview

This appendix lists all tentative Latin keyword mappings for the Latium Codex language. Keywords are organized by category. All selections are subject to revision during the Week 1 design phase, based on Latin language resources and thematic consistency review.

**Conventions:**
- Keywords use the **imperative mood** for verbs and **nominative case** for nouns.
- Standard operator symbols (`+`, `-`, etc.) are reused as-is — Latin does not add value over standard symbols for operators.
- OOP keywords are marked **future** — they will be finalized as part of the post-v1.0 OOP extension (see §8 of the main reference).

---

## Keyword Table

| Category         | English      | Latin (Tentative)      | Notes / Context                 |
| ---------------- | ------------ | ---------------------- | ------------------------------- |
| **Core**         | variable     | `res`                  |                                 |
|                  | function     | `munus`                |                                 |
|                  | if           | `si`                   |                                 |
|                  | else         | `aliter`               |                                 |
|                  | else if      | `aliter si`            |                                 |
|                  | while        | `dum`                  |                                 |
|                  | for          | `per`                  |                                 |
|                  | return       | `redde`                | imperative                      |
|                  | print        | `scribe`               | console output                  |
|                  | write        | `inscribe`             | file write                      |
|                  | read         | `lege`                 | file read                       |
|                  | run          | `curre`                | command execution               |
|                  | true         | `verum`                |                                 |
|                  | false        | `falsum`               |                                 |
|                  | and          | `et`                   |                                 |
|                  | or           | `aut`                  |                                 |
|                  | not          | `non`                  |                                 |
|                  | break        | `abrumpe`              | exit loop early                 |
|                  | continue     | `perge`                | skip to next iteration          |
|                  | null/None    | `nihil`                | absence of value                |
| **Import**       | import       | `importa`              |                                 |
|                  | from         | `ex`                   |                                 |
|                  | as           | `ut`                   | alias                           |
| **OOP (future)** | class        | `classis`              |                                 |
|                  | new          | `novus` / `crea`       | object creation                 |
|                  | is           | `est`                  | type check / instanceof         |
|                  | extends      | `ortus`                | inheritance (born from)         |
|                  | super        | `superus`              | parent call                     |
|                  | self         | `se`                   | reflexive pronoun               |
|                  | override     | `supercede` / `obtege` | method override marker          |
|                  | public       | `publicus`             | access modifier                 |
|                  | private      | `privatus`             | access modifier                 |
| **Modules**      | file I/O     | `fasciculus`           |                                 |
|                  | system       | `systema`              |                                 |
|                  | path         | `via`                  |                                 |
|                  | math         | `numerus`              |                                 |
|                  | string       | `filum`                |                                 |
|                  | list         | `collectio`            |                                 |
|                  | dictionary   | `dictio`               |                                 |
|                  | datetime     | `tempus`               |                                 |
| **Operators**    | +            | `+`                    | arithmetic; standard symbol     |
|                  | -            | `-`                    | arithmetic; standard symbol     |
|                  | *            | `*`                    | arithmetic; standard symbol     |
|                  | /            | `/`                    | float division; standard symbol |
|                  | //           | `//`                   | floor division; standard symbol |
|                  | %            | `%`                    | modulo; standard symbol         |
|                  | **           | `**`                   | power; standard symbol          |
|                  | ==           | `==`                   | equality; standard symbol       |
|                  | !=           | `!=`                   | inequality; standard symbol     |
|                  | <, >, <=, >= | `<`, `>`, `<=`, `>=`   | comparison; standard symbols    |

---

## Notes

- **`finis`** is reserved as the optional block-closing keyword (e.g., `finis munus`). Do not use it as a variable or parameter name. Use `terminus` for end-of-range parameters instead.
- **`se` (self)** is the Latin reflexive pronoun — semantically correct and intentional.
- **`ortus` (extends/inheritance)** is a past participle of `oriri` meaning "having risen/been born from" — chosen for thematic richness over a plain preposition.
- **`file.claude()` (close file)** uses `claude`, the Latin imperative of `claudere` (to close/shut) — this is correct Latin and intentional.
- **`ambitum`** is the canonical Latin term for "environment" (surroundings/circuit). Used consistently in `cape_ambitum` and `pone_ambitum`.
