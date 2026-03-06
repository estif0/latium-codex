# Latium Codex – Development Roadmap

**Document ID:** `07-development-roadmap.md`  
**Part of:** Detailed Documentation Series  
**Audience:** Project lead  
**Last Updated:** 2026-03-03

---

## Table of Contents

- [Latium Codex – Development Roadmap](#latium-codex--development-roadmap)
  - [Table of Contents](#table-of-contents)
  - [1. Roadmap Overview](#1-roadmap-overview)
  - [2. Pre‑Week: Minimal Prototype (Practice Project)](#2-preweek-minimal-prototype-practice-project)
  - [3. Week 1: Identity \& Foundations](#3-week-1-identity--foundations)
  - [4. Week 2: Lexer \& Parser Core](#4-week-2-lexer--parser-core)
  - [5. Week 3: Complete Parser \& AST](#5-week-3-complete-parser--ast)
  - [6. Week 4: Semantic Analysis \& Transpiler](#6-week-4-semantic-analysis--transpiler)
  - [7. Week 5: Standard Library (Tier 1), REPL, CLI](#7-week-5-standard-library-tier-1-repl-cli)
  - [8. Week 6: Ecosystem Polish](#8-week-6-ecosystem-polish)
  - [9. Versioning and Release Stages](#9-versioning-and-release-stages)
  - [10. Using This Roadmap](#10-using-this-roadmap)

---

## 1. Roadmap Overview

This roadmap breaks the development of Latium Codex into **six focused weeks** plus a preliminary “Week 0” practice project. Each week includes:

- **Concepts** to learn (with references to the detailed documentation and external resources).
- **Tasks** to complete.
- **Deliverables** that should be produced.
- **Version increment** (following Semantic Versioning).

The total estimated effort is **18–20 hours per week**. Adjust as needed, but try to keep the weekly goals achievable.

---

## 2. Pre‑Week: Minimal Prototype (Practice Project)

**Goal**: Build a minimal language (v0.1.0) to validate the pipeline before the full project. This ensures you understand the core components and can iterate quickly.

**Features**:
- Variables (dynamic typing)
- Basic arithmetic expressions (`+`, `-`, `*`, `/`, parentheses)
- Print statement (`scribe`)
- Assignment
- Integer and string literals

**Implementation Approach**:
- Create a new branch `feature/minimal-prototype`.
- Implement a simple lexer, parser, AST, and transpiler that outputs Python.
- Keep the code clean and modular so it can be reused in the full language.
- Write a few test programs to verify correctness.

**Resources**:
- Crafting Interpreters, Chapters 4–6 (lexing, parsing).
- Your own `detailed/` docs as they become available.

**Deliverables**:
- Working prototype, tagged as `v0.1.0`.
- Basic tests.
- Initial notes in `kb/` about the experience and any design decisions.

**Time Estimate**: 4–6 hours (spread over a few days).

---

## 3. Week 1: Identity & Foundations

**Concepts**:
- Language design, grammar, AST basics.
- Compiler pipeline overview.

**Tasks**:
- Finalize language name, keywords, file extension (`.lcdx`).
- Validate Latin keywords using Latin resources (see `kb/latin/`).
- Draft BNF/EBNF grammar.
- Define AST node structure (base classes, core node types).
- Set up GitHub repository with the modular structure (see `04-technical-architecture.md`).
- Begin lexer implementation.
- Create `ErrorReporter` skeleton.

**Resources**:
- "Build Your Own Programming Language" Ch 1‑2.
- "Crafting Interpreters" – Introduction & Lexing.
- IITK Systems Guide – expression parser exercise.

**Deliverables**:
- GitHub repo with README, project vision.
- Grammar specification document (in `docs/proposals/` or `kb/`).
- Project structure scaffolded.
- Version: **v0.2.0** (alpha)

---

## 4. Week 2: Lexer & Parser Core

**Concepts**:
- Finite state machines, regular expressions, error reporting.
- Context‑free grammars.

**Tasks**:
- Complete lexer with full token set, using `ErrorReporter`.
- Handle edge cases (invalid characters, unterminated strings, comments).
- Begin recursive descent parser for expressions.
- Unit tests for lexer.

**Resources**:
- "Build Your Own Programming Language" Ch 3 (Scanning).
- Dragon Book Ch 3.
- Ruslan's Blog – Writing a Lexer.

**Deliverables**:
- Working lexer with token output.
- Basic expression parser.
- Test suite.
- Version: **v0.3.0** (alpha)

---

## 5. Week 3: Complete Parser & AST

**Concepts**:
- Top‑down parsing, precedence, parse vs. syntax trees.
- AST node construction.

**Tasks**:
- Parse all language constructs (functions, conditionals, loops).
- Build AST nodes from parsed input.
- Implement error reporting with line numbers (via `ErrorReporter`).
- Output AST visualization (GraphViz format).

**Resources**:
- "Build Your Own Programming Language" Ch 4‑5 (Parsing, Syntax Trees).
- "Crafting Interpreters" – Parsing chapters.
- Jack Crenshaw's series parts 4‑6.

**Deliverables**:
- Complete parser for all language features.
- AST node hierarchy.
- GraphViz visualization.
- Version: **v0.4.0** (alpha)

---

## 6. Week 4: Semantic Analysis & Transpiler

**Concepts**:
- Symbol tables, scope management.
- Type checking, code generation.

**Tasks**:
- Implement symbol tables for each scope.
- Add type checking for optional annotations.
- Begin transpiler: convert AST to Python.
- Handle variable declarations and scope correctly.
- Unit tests for semantic errors.
- Integration tests for small programs.

**Resources**:
- "Build Your Own Programming Language" Ch 6‑8 (Symbol Tables, Type Checking, Intermediate Representations).
- "Crafting Interpreters" – Resolving and Binding.
- Dragon Book Ch 6.

**Deliverables**:
- Symbol tables.
- Type checker.
- Basic transpiler generating Python.
- Version: **v0.5.0** (alpha)

---

## 7. Week 5: Standard Library (Tier 1), REPL, CLI

**Concepts**:
- Runtime systems, interactive interpreters.
- CLI design.
- Import system.

**Tasks**:
- Implement **Tier 1** functions for must‑have modules:  
  `fasciculus` (file), `numerus` (math), `filum` (string), `systema` (system), `via` (path).  
  (See `03-language-features.md` for detailed function lists.)
- Optionally add minimal `collectio`, `dictio`, `tempus` if time permits.
- Implement import mechanism (`importa`).
- Implement REPL with line accumulation and persistent globals.
- Create CLI tool with flags using `argparse`.
- Test standard library and imports.

**Resources**:
- "Build Your Own Programming Language" Ch 12 (Bytecode Interpreters for REPL ideas).
- Study Celeratas REPL and help system.
- Python `argparse` and `code` modules.

**Deliverables**:
- Standard library modules (Tier 1 must‑haves).
- Working REPL.
- CLI tool with subcommands: `run`, `repl`, `ast`, `debug`.
- Version: **v0.6.0** (alpha)

---

## 8. Week 6: Ecosystem Polish

**Concepts**:
- IDE integration, documentation generation.
- Packaging, distribution.

**Tasks**:
- Build VS Code extension with syntax highlighting and “run” command.
- Create Next.js website with Fumadocs (English only for v1.0).
- Write 5+ example programs (Roman‑themed).
- Package CLI tool for PyPI.
- Final testing and documentation (user manual, developer manual, language reference).
- Create `CHANGELOG.md` with initial release notes.
- Add `LICENSE` (MIT).
- Add `.github/copilot-instructions.md` with project context.

**Resources**:
- "Build Your Own Programming Language" Ch 10 (Syntax Coloring in an IDE).
- VS Code TextMate grammar documentation.
- Study fzy's VS Code extension.
- Next.js docs, Fumadocs docs.
- PyPI packaging tutorial.

**Deliverables**:
- VS Code extension (core features).
- Documentation website on Vercel.
- 5+ example programs.
- PyPI package (`latium-codex`).
- User and developer manuals.
- Changelog.
- Version: **v0.7.0** (beta) – feature‑complete, ready for wider testing.

---

## 9. Versioning and Release Stages

The project follows [Semantic Versioning](https://semver.org/) from the start.

| Version         | Stage  | Description                                               |
| --------------- | ------ | --------------------------------------------------------- |
| v0.1.0          | Alpha  | Minimal prototype (practice project)                      |
| v0.2.0 – v0.6.0 | Alpha  | Incremental feature additions; not stable for general use |
| v0.7.0 – v0.9.0 | Beta   | Feature‑complete, polishing, bug fixes                    |
| v1.0.0          | Stable | First production release                                  |

**Alpha** (0.1.0 to 0.6.0): Features still being added; not recommended for production.  
**Beta** (0.7.0 to 0.9.0): Feature‑complete, but may have bugs; ready for wider testing.  
**Release Candidate** (0.9.0): Final testing before 1.0.0.

**Implementation**:
- Use Git tags: `git tag v0.1.0`
- Update `__version__` in Python package and `version` in `package.json` for VS Code extension.
- Maintain `CHANGELOG.md` with entries for each version.

---

## 10. Using This Roadmap

- This roadmap is a **guide**, not a strict contract. If a week takes a little longer, adjust.
- Document your progress in `journal.md` and update `kb/` with insights.
- After each week, consider writing a brief reflection in `kb/weekly-reflections/`.
- At the end of Week 6, you’ll have a solid v0.7.0 to share and build upon.

---

*Back to [detailed index](index.md) or [LATIUM_REFERENCE.md](../LATIUM_REFERENCE.md).*