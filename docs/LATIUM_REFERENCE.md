# Latium Codex Project Documentation (Final – With Actionable Roadmap)

## Comprehensive Reference for Building a Latin-Based Programming Language Ecosystem

---

# Table of Contents

- [Latium Codex Project Documentation (Final – With Actionable Roadmap)](#latium-codex-project-documentation-final--with-actionable-roadmap)
  - [Comprehensive Reference for Building a Latin-Based Programming Language Ecosystem](#comprehensive-reference-for-building-a-latin-based-programming-language-ecosystem)
- [Table of Contents](#table-of-contents)
- [1. Project Overview](#1-project-overview)
  - [1.1. Language Identity](#11-language-identity)
  - [1.2. Core Philosophy](#12-core-philosophy)
  - [1.3. Target Audience](#13-target-audience)
- [2. Design Decisions](#2-design-decisions)
  - [2.1. Syntax Style](#21-syntax-style)
  - [2.2. Transpilation Target](#22-transpilation-target)
  - [2.3. Typing System](#23-typing-system)
  - [2.4. Automation Focus](#24-automation-focus)
  - [2.5. Thematic Identity](#25-thematic-identity)
  - [2.6. Error Reporting \& Developer Experience](#26-error-reporting--developer-experience)
- [3. Language Features](#3-language-features)
  - [3.1. Core Language Constructs](#31-core-language-constructs)
  - [3.2. Standard Library (Modular, Built-in)](#32-standard-library-modular-built-in)
    - [3.2.1. File I/O Module – `fasciculus`](#321-file-io-module--fasciculus)
    - [3.2.2. System Module – `systema` \& Path Module – `via`](#322-system-module--systema--path-module--via)
      - [`systema` (process and environment)](#systema-process-and-environment)
      - [`via` (path manipulation)](#via-path-manipulation)
    - [3.2.3. Math Module – `numerus`](#323-math-module--numerus)
    - [3.2.4. String Module – `filum`](#324-string-module--filum)
    - [3.2.5. List Module – `collectio`](#325-list-module--collectio)
    - [3.2.6. Dictionary Module – `dictio`](#326-dictionary-module--dictio)
    - [3.2.7. DateTime Module – `tempus`](#327-datetime-module--tempus)
  - [3.3. Import System](#33-import-system)
  - [3.4. Advanced Error Reporting](#34-advanced-error-reporting)
  - [3.5. REPL \& CLI Modes](#35-repl--cli-modes)
- [4. Technical Architecture](#4-technical-architecture)
  - [4.1. Module Structure](#41-module-structure)
  - [4.2. AST Design Principles](#42-ast-design-principles)
  - [4.3. Transpiler Approach](#43-transpiler-approach)
  - [4.4. Error Handling Architecture](#44-error-handling-architecture)
  - [4.5. Development Infrastructure](#45-development-infrastructure)
    - [4.5.1. Python Dependency Management with `uv`](#451-python-dependency-management-with-uv)
    - [4.5.2. JavaScript/TypeScript Workspaces with `pnpm`](#452-javascripttypescript-workspaces-with-pnpm)
    - [4.5.3. CI/CD with GitHub Actions and Path-Based Triggers](#453-cicd-with-github-actions-and-path-based-triggers)
    - [4.5.4. Git Branching and Tagging Strategy](#454-git-branching-and-tagging-strategy)
- [5. Learning Resources](#5-learning-resources)
  - [5.1. Essential Books](#51-essential-books)
  - [5.2. Online Courses \& Tutorials](#52-online-courses--tutorials)
  - [5.3. Python-Specific Resources](#53-python-specific-resources)
  - [5.4. Latin Language Resources](#54-latin-language-resources)
  - [5.5. AI-Assisted Learning](#55-ai-assisted-learning)
- [6. Reference Projects](#6-reference-projects)
  - [6.1. Latin-Based Languages](#61-latin-based-languages)
  - [6.2. Transpiler Examples](#62-transpiler-examples)
  - [6.3. Project Structure References](#63-project-structure-references)
  - [6.4. OOP Reference Projects](#64-oop-reference-projects)
- [7. Development Roadmap (Actionable Week-by-Week)](#7-development-roadmap-actionable-week-by-week)
  - [7.0. Pre-Week: Minimal Prototype (Practice Project)](#70-pre-week-minimal-prototype-practice-project)
  - [7.1. Week 1: Identity \& Foundations](#71-week-1-identity--foundations)
  - [7.2. Week 2: Lexer \& Parser Core](#72-week-2-lexer--parser-core)
  - [7.3. Week 3: Complete Parser \& AST](#73-week-3-complete-parser--ast)
  - [7.4. Week 4: Semantic Analysis \& Transpiler](#74-week-4-semantic-analysis--transpiler)
  - [7.5. Week 5: Standard Library (Tier 1), REPL, CLI](#75-week-5-standard-library-tier-1-repl-cli)
  - [7.6. Week 6: Ecosystem Polish](#76-week-6-ecosystem-polish)
  - [7.7. Versioning and Release Stages](#77-versioning-and-release-stages)
- [8. Object-Oriented Programming Extension (Post-6 Weeks)](#8-object-oriented-programming-extension-post-6-weeks)
  - [8.1. Motivation](#81-motivation)
  - [8.2. Learning Path](#82-learning-path)
  - [8.3. Features to Implement](#83-features-to-implement)
  - [8.4. Implementation Phases](#84-implementation-phases)
  - [8.5. Reference Projects](#85-reference-projects)
- [9. Ecosystem Components](#9-ecosystem-components)
  - [9.1. VS Code Extension](#91-vs-code-extension)
  - [9.2. Website (Next.js + Fumadocs)](#92-website-nextjs--fumadocs)
  - [9.3. GitHub Strategy](#93-github-strategy)
  - [9.4. Documentation Deliverables](#94-documentation-deliverables)
- [10. Future Features (Post-v1.0)](#10-future-features-post-v10)
  - [10.1. Documentation \& Code Quality](#101-documentation--code-quality)
  - [10.2. Object-Oriented Programming (Detailed)](#102-object-oriented-programming-detailed)
  - [10.3. Functional Programming](#103-functional-programming)
  - [10.4. IDE \& Developer Tooling](#104-ide--developer-tooling)
  - [10.5. Online Playground](#105-online-playground)
- [11. Changelog](#11-changelog)
  - [11.1. Format and Maintenance](#111-format-and-maintenance)
- [12. Appendix: Latin Keyword Candidates](#12-appendix-latin-keyword-candidates)
- [14. Knowledge Management and Documentation for Future Reference](#14-knowledge-management-and-documentation-for-future-reference)
  - [14.1. Project Journal / Development Log](#141-project-journal--development-log)
  - [14.2. Personal Knowledge Base (KB)](#142-personal-knowledge-base-kb)
  - [14.3. AI Copilot Instructions](#143-ai-copilot-instructions)
  - [14.4. Resource List](#144-resource-list)
  - [14.5. Versioned Documentation](#145-versioned-documentation)
- [15. License](#15-license)
- [16. Security Considerations](#16-security-considerations)

---

# 1. Project Overview

## 1.1. Language Identity

| Attribute          | Value                                  |
| ------------------ | -------------------------------------- |
| **Name**           | Latium Codex (short: Latium)           |
| **File Extension** | `.lcdx`                                |
| **Tagline**        | "The Ancient Way to Modern Automation" |
| **Domain**         | latiumcodex.dev (or similar)           |
| **GitHub**         | latium-codex repository                |

## 1.2. Core Philosophy

- **Educational**: Beginner-friendly, clear syntax, comprehensive documentation.
- **Automation-focused**: Built-in file operations and command execution.
- **Thematic**: Latin/Roman identity throughout keywords, built-ins, and examples.
- **Transpiler-based**: Converts Latium Codex to clean, readable Python code.
- **Professional-grade**: Modular architecture, unit tests, error reporting, and ecosystem tooling.

## 1.3. Target Audience

- Students learning programming concepts.
- Developers seeking a scripting language with automation capabilities.
- Hobbyists interested in language design and Roman history.

---

# 2. Design Decisions

## 2.1. Syntax Style

- **Indentation-based blocks** like Python (familiar, clean).
- **Optional explicit closing keywords** (e.g., `finis`, `finis function`) for thematic flair and parser robustness.

## 2.2. Transpilation Target

- **Clean Python code** – readable output, easy debugging, educational.
- One-to-one mapping where possible, with comments preserved.

## 2.3. Typing System

- **Optional typing** using `:` syntax (like TypeScript).
- Dynamic typing by default; type annotations optional for static checks.

## 2.4. Automation Focus

- **File operations**: read, write, append, etc.
- **Command execution**: run system commands from within Latium scripts.
- Additional utilities in the standard library.

## 2.5. Thematic Identity

- **Roman/Latin** naming for all keywords and built-in functions.
- Consistent conjugation (verbs in imperative mood, nouns in nominative).
- Example programs themed around Roman life (legions, aqueducts, census).

## 2.6. Error Reporting & Developer Experience

- **Line numbers** and **caret indicators** pointing to error location.
- **Comprehensive error messages** with context.
- **REPL** for interactive exploration.
- **CLI tool** with subcommands: run, repl, ast, debug.

---

# 3. Language Features

## 3.1. Core Language Constructs

| Feature           | Description                                      | Example Keyword (tentative)       |
| ----------------- | ------------------------------------------------ | --------------------------------- |
| Variables         | Mutable variables with optional type annotations | `res` (thing)                     |
| Functions         | Reusable blocks of code                          | `munus` (task)                    |
| Conditionals      | `if`, `else if`, `else`                          | `si`, `aliter si`, `aliter`       |
| Loops             | `while` and `for`-each style loops               | `dum` (while), `per` (for)        |
| Scoping           | Lexical scoping with nested blocks               | –                                 |
| File I/O          | Read, write, append files                        | `lege` (read), `inscribe` (write) |
| Command Execution | Run system commands                              | `curre` (run)                     |
| Comments          | Single-line and multi-line                       | `#` and `/* */`                   |
| Return            | Return value from function                       | `redde` (give back)               |
| Print             | Output to console                                | `scribe` (write)                  |
| True/False        | Boolean literals                                 | `verum`, `falsum`                 |
| Logical Operators | and, or, not                                     | `et`, `aut`, `non`                |

## 3.2. Standard Library (Modular, Built-in)

All standard library modules are built into the language runtime and available via `importa`. No additional installation required.

To balance timeline and future extensibility, each module is split into:

- **Tier 1 (v1.0)**: Procedural functions that are sufficient for automation and educational use.
- **Tier 2 (post-v1.0)**: Object-oriented APIs that will be added as part of the OOP extension (Section 8).

### 3.2.1. File I/O Module – `fasciculus`

| Tier | Function                   | Latin Name                    | Description                         | Python Equivalent                |
| ---- | -------------------------- | ----------------------------- | ----------------------------------- | -------------------------------- |
| 1    | Read entire file           | `lege(iter)`                  | Returns file content as string.     | `open(iter).read()`              |
| 1    | Write string to file       | `inscribe(iter, scriptum)`    | Writes string to file (overwrites). | `open(iter,'w').write(scriptum)` |
| 1    | Append string to file      | `appone(iter, scriptum)`      | Appends string to file.             | `open(iter,'a').write(scriptum)` |
| 1    | Remove file                | `dele(iter)`                  | Deletes file.                       | `os.remove(iter)`                |
| 1    | Check if file exists       | `existit(iter)`               | Returns boolean.                    | `os.path.exists(iter)`           |
| 2    | Open file (returns object) | `aperi(iter, modus)`          | Returns a file object.              | `open(iter, modus)`              |
| 2    | Read from file object      | `file.lege([amplitudo])`      | Reads from open file.               | `file.read([size])`              |
| 2    | Read line                  | `file.lege_lineam()`          | Reads one line.                     | `file.readline()`                |
| 2    | Read all lines             | `file.lege_lineas()`          | Reads all lines into a list.        | `file.readlines()`               |
| 2    | Write to file object       | `file.inscribe(scriptum)`     | Writes to open file.                | `file.write(scriptum)`           |
| 2    | Write lines                | `file.inscribe_lineas(lista)` | Writes a list of lines.             | `file.writelines(lista)`         |
| 2    | Close file                 | `file.claude()`               | Closes the file.                    | `file.close()`                   |
| 2    | Flush buffer               | `file.consiste()`             | Flushes internal buffer.            | `file.flush()`                   |
| 2    | Seek                       | `file.quaere(offset, unde)`   | Changes file position.              | `file.seek(offset, whence)`      |
| 2    | Tell position              | `file.dic()`                  | Returns current file position.      | `file.tell()`                    |

### 3.2.2. System Module – `systema` & Path Module – `via`

#### `systema` (process and environment)

| Tier | Function                 | Latin Name                   | Description                             | Python Equivalent                          |
| ---- | ------------------------ | ---------------------------- | --------------------------------------- | ------------------------------------------ |
| 1    | Execute command          | `curre(commando)`            | Runs command, returns stdout as string. | `subprocess.run(..., capture_output=True)` |
| 1    | Exit program             | `exi(code)`                  | Exits with given code.                  | `sys.exit(code)`                           |
| 1    | Get environment variable | `cape_ambitum(nomen)`        | Returns value or null.                  | `os.environ.get(nomen)`                    |
| 1    | Set environment variable | `pone_ambitum(nomen, valor)` | Sets variable.                          | `os.environ[nomen] = valor`                |
| 2    | Process object           | `Process` class              | More detailed process control.          | `subprocess.Popen`                         |

*Note: `ambitum` (environment) is the canonical Latin term for the concept of an environment variable. Use it consistently wherever "env" would appear in function names or documentation.*

#### `via` (path manipulation)

| Tier | Function        | Latin Name                  | Description                        | Python Equivalent        |
| ---- | --------------- | --------------------------- | ---------------------------------- | ------------------------ |
| 1    | Absolute path   | `via_absoluta(iter)`        | Returns absolute path.             | `os.path.abspath(iter)`  |
| 1    | Base name       | `via_basename(iter)`        | Returns final component of path.   | `os.path.basename(iter)` |
| 1    | Directory name  | `via_dirname(iter)`         | Returns parent directory.          | `os.path.dirname(iter)`  |
| 1    | Check existence | `via_existit(iter)`         | Returns boolean.                   | `os.path.exists(iter)`   |
| 1    | Is file?        | `via_est_archivum(iter)`    | Returns boolean.                   | `os.path.isfile(iter)`   |
| 1    | Is directory?   | `via_est_directorium(iter)` | Returns boolean.                   | `os.path.isdir(iter)`    |
| 2    | Path object     | `Via` class                 | Object-oriented path manipulation. | `pathlib.Path`           |

### 3.2.3. Math Module – `numerus`

*Note: Basic arithmetic uses standard operators directly: `+`, `-`, `*`, `/`, `//` (floor divide), `%` (modulo), `**` (power). The `numerus` module provides functions for operations not covered by operators.*

| Tier | Function          | Latin Name             | Description                     | Python Equivalent   |
| ---- | ----------------- | ---------------------- | ------------------------------- | ------------------- |
| 1    | Absolute value    | `absolutus(a)`         | Returns absolute value.         | `abs(a)`            |
| 1    | Square root       | `radix(a)`             | Returns square root.            | `math.sqrt(a)`      |
| 1    | Floor             | `pavimentum(a)`        | Rounds down to nearest integer. | `math.floor(a)`     |
| 1    | Ceiling           | `tectum(a)`            | Rounds up to nearest integer.   | `math.ceil(a)`      |
| 1    | Round             | `rotunda(a, n)`        | Rounds to n decimal places.     | `round(a, n)`       |
| 1    | Sine              | `sinus(angulus)`       | Returns sine (radians).         | `math.sin(angulus)` |
| 1    | Cosine            | `cosinus(angulus)`     | Returns cosine (radians).       | `math.cos(angulus)` |
| 1    | Tangent           | `tangens(angulus)`     | Returns tangent (radians).      | `math.tan(angulus)` |
| 1    | Natural logarithm | `logarithmus(x)`       | Returns ln(x).                  | `math.log(x)`       |
| 1    | Log base 10       | `logarithmus_decem(x)` | Returns log₁₀(x).               | `math.log10(x)`     |
| 2    | Numerus object    | `Numerus` class        | Allows method chaining, etc.    | –                   |

### 3.2.4. String Module – `filum`

| Tier | Function      | Latin Name                        | Description                          | Python Equivalent         |
| ---- | ------------- | --------------------------------- | ------------------------------------ | ------------------------- |
| 1    | Concatenate   | `coniungere(s1, s2)`              | Returns concatenated string.         | `s1 + s2`                 |
| 1    | Substring     | `excerpere(s, initium, terminus)` | Returns substring.                   | `s[initium:terminus]`     |
| 1    | Length        | `longitudo(s)`                    | Returns integer length.              | `len(s)`                  |
| 1    | Split         | `findere(s, delimiter)`           | Returns list of strings.             | `s.split(delimiter)`      |
| 1    | Join          | `iungere(lista, separator)`       | Returns string.                      | `separator.join(lista)`   |
| 1    | Format        | `formare(formato, ...)`           | Basic string formatting.             | `formato.format(...)`     |
| 1    | Trim          | `tondere(s)`                      | Removes leading/trailing whitespace. | `s.strip()`               |
| 1    | Uppercase     | `ad_maius(s)`                     | Returns string in uppercase.         | `s.upper()`               |
| 1    | Lowercase     | `ad_minus(s)`                     | Returns string in lowercase.         | `s.lower()`               |
| 1    | Replace       | `mutare(s, vetus, novus)`         | Returns string with substitution.    | `s.replace(vetus, novus)` |
| 1    | Contains      | `continet(s, pars)`               | Returns boolean.                     | `pars in s`               |
| 1    | Starts with   | `a_capite(s, initium)`            | Returns boolean.                     | `s.startswith(initium)`   |
| 1    | Ends with     | `a_calce(s, terminus)`            | Returns boolean.                     | `s.endswith(terminus)`    |
| 2    | String object | `Filum` class                     | Methods like `s.coniungere()`, etc.  | –                         |

### 3.2.5. List Module – `collectio`

| Tier | Function          | Latin Name                         | Description                     | Python Equivalent                      |
| ---- | ----------------- | ---------------------------------- | ------------------------------- | -------------------------------------- |
| 1    | Concatenate lists | `coniungere(l1, l2)`               | Returns new list.               | `l1 + l2`                              |
| 1    | Slice             | `secare(lista, initium, terminus)` | Returns slice.                  | `lista[initium:terminus]`              |
| 1    | Sort              | `ordinare(lista)`                  | Returns sorted list.            | `sorted(lista)`                        |
| 1    | Append element    | `addere(lista, elementum)`         | Returns new list with appended. | `lista + [elementum]`                  |
| 1    | Remove element    | `removere(lista, elementum)`       | Returns new list without.       | `[x for x in lista if x != elementum]` |
| 1    | Length            | `longitudo(lista)`                 | Returns integer.                | `len(lista)`                           |
| 2    | List object       | `Collectio` class                  | Mutable list with methods.      | –                                      |

### 3.2.6. Dictionary Module – `dictio`

| Tier | Function          | Latin Name                      | Description                | Python Equivalent                                |
| ---- | ----------------- | ------------------------------- | -------------------------- | ------------------------------------------------ |
| 1    | Add/Set           | `addere(dictio, clavis, valor)` | Returns updated dict.      | `{**dictio, clavis: valor}`                      |
| 1    | Remove            | `removere(dictio, clavis)`      | Returns updated dict.      | `{k:v for k,v in dictio.items() if k != clavis}` |
| 1    | Has key           | `habere(dictio, clavis)`        | Returns boolean.           | `clavis in dictio`                               |
| 1    | Get keys          | `claves(dictio)`                | Returns list of keys.      | `list(dictio.keys())`                            |
| 1    | Get values        | `valores(dictio)`               | Returns list of values.    | `list(dictio.values())`                          |
| 2    | Dictionary object | `Dictio` class                  | Mutable dict with methods. | –                                                |

### 3.2.7. DateTime Module – `tempus`

| Tier | Function          | Latin Name                      | Description                    | Python Equivalent    |
| ---- | ----------------- | ------------------------------- | ------------------------------ | -------------------- |
| 1    | Current datetime  | `nunc()`                        | Returns string representation. | `datetime.now()`     |
| 1    | Format datetime   | `formare_tempus(tempus, forma)` | Returns formatted string.      | `dt.strftime(forma)` |
| 1    | Difference (days) | `differre(t1, t2)`              | Returns number of days.        | `(t2 - t1).days`     |
| 2    | DateTime object   | `Tempus` class                  | Objects with methods.          | `datetime.datetime`  |

## 3.3. Import System

- **Keyword**: `importa` (or alternative Latin verb).
- **Syntax**:
  ```
  importa numerus
  importa fasciculus ut fs
  ```
- All modules are built-in; import simply makes them available in the current namespace.

## 3.4. Advanced Error Reporting

- **Line numbers** in error messages.
- **Caret** (`^`) pointing to exact token in error.
- **Error categories**: syntax, semantic, runtime (when possible).
- **ErrorReporter** class collects multiple errors and prints them in a unified format.

## 3.5. REPL & CLI Modes

- **REPL**: Interactive shell with persistent state, multi-line input support (accumulates lines until a complete block is detected).
- **File execution**: `latium run script.lcdx`
- **AST visualization**: `latium ast script.lcdx` (outputs GraphViz format)
- **Debug mode**: `latium debug script.lcdx` (verbose output)

---

# 4. Technical Architecture

## 4.1. Module Structure

```
latium-codex/
├── src/                               # Source root (standard location)
│   └── latium/                        # Main package (importable as 'latium')
│       ├── __init__.py                 # Makes 'latium' a package
│       ├── lexer/                      # Lexical analysis
│       │   ├── __init__.py
│       │   └── ...                     # Lexer implementation files
│       ├── parser/                     # Syntax analysis
│       │   ├── __init__.py
│       │   └── ...
│       ├── ast/                        # Abstract Syntax Tree nodes
│       │   ├── __init__.py
│       │   └── ...
│       ├── transpiler/                  # Python code generation
│       │   ├── __init__.py
│       │   └── ...
│       ├── stdlib/                      # Standard library (Tier 1)
│       │   ├── __init__.py
│       │   └── ...                     # One file per module (fasciculus.py, etc.)
│       ├── repl/                        # Interactive REPL
│       │   ├── __init__.py
│       │   └── ...
│       ├── cli/                         # Command-line interface
│       │   ├── __init__.py
│       │   └── ...                     # CLI entry point and subcommands
│       └── utils/                       # Shared utilities
│           ├── __init__.py
│           └── ...                     # ErrorReporter, helpers, etc.
├── tests/                               # All tests
│   ├── __init__.py
│   ├── unit/                            # Unit tests (mirror src structure)
│   │   ├── test_lexer/
│   │   ├── test_parser/
│   │   └── ...
│   └── integration/                      # Integration tests
│       ├── test_programs/
│       └── ...
├── vscode-extension/                     # VS Code extension (TypeScript)
│   ├── package.json
│   ├── src/
│   └── syntaxes/
├── website/                              # Next.js site with Fumadocs
│   ├── package.json
│   ├── pages/
│   └── components/
├── docs/                                 # All documentation
│   ├── user/                             # End-user documentation
│   ├── dev/                              # Contributor documentation
│   ├── proposals/                        # Design docs, SRS
│   ├── kb/                               # Personal knowledge base
│   └── journal.md                        # Development log
├── examples/                             # Sample .lcdx programs
├── scripts/                              # Utility scripts
│   ├── build.sh
│   ├── test.sh
│   └── release.sh
├── pyproject.toml                        # Build configuration (Python)
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── .gitignore
├── .github/
│   ├── workflows/
│   │   ├── test.yml
│   │   └── release.yml
│   └── copilot-instructions.md           # AI context
└── CHANGELOG.md                           # Version history
```

## 4.2. AST Design Principles

- **Hierarchical nodes**: `Program`, `Statement`, `Expression`, etc.
- **Visitor pattern** for traversals (transpilation, analysis).
- **Rich node information**: line numbers, column offsets for error reporting.
- **Extensible** for future OOP features.

## 4.3. Transpiler Approach

- **AST walker** that emits Python code strings.
- **Symbol tables** for scope management.
- **Type checking** (optional) during transpilation.
- **Generated Python** should be human-readable with comments.

## 4.4. Error Handling Architecture

- **ErrorReporter** class (in `utils/errors.py`):
  - Collects errors with line, column, message, severity.
  - Can print all errors in a unified format with caret indicators.
- Used by lexer, parser, semantic analyzer.
- Lexer may stop after first error or collect multiple; parser may attempt recovery.

## 4.5. Development Infrastructure

### 4.5.1. Python Dependency Management with `uv`

- Use `uv` for fast dependency installation and virtual environment management.
- `compiler/pyproject.toml` defines dependencies.
- In CI, use `uv pip install` for speed.

### 4.5.2. JavaScript/TypeScript Workspaces with `pnpm`

- Use `pnpm` for `vscode-extension/` and `website/`.
- Each has its own `package.json`; no workspace linking needed initially.
- `pnpm` ensures efficient disk usage and fast installs.

### 4.5.3. CI/CD with GitHub Actions and Path-Based Triggers

- Separate workflows for compiler, VS Code extension, website.
- Use `paths` or `paths-ignore` to trigger only when relevant files change.
- Example: changes to `compiler/**` trigger compiler tests; changes to `docs/**` skip all tests.

**Example `test.yml` snippet**:

```yaml
name: Test
on:
  push:
    paths-ignore:
      - 'docs/**'
      - '**.md'
  pull_request:
    paths-ignore:
      - 'docs/**'
      - '**.md'
jobs:
  test-compiler:
    if: github.event_name == 'push' || github.event_name == 'pull_request'
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - name: Install uv
        run: pip install uv
      - name: Install dependencies
        run: cd compiler && uv pip install -e .
      - name: Run tests
        run: cd compiler && pytest
```

### 4.5.4. Git Branching and Tagging Strategy

- **Default branch**: `main` (always deployable).
- **Feature branches**: `feature/description` for each week's tasks.
- **Pull requests**: Merge via PRs (even if self-merged) to maintain history.
- **Tags**: Use semantic versioning tags (`v0.1.0`, `v0.2.0`, ...) after each milestone.
- **Changelog**: Update `CHANGELOG.md` with each release.

---

# 5. Learning Resources

## 5.1. Essential Books

| Title & Author                                                           | Why It's Valuable                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| **"Build Your Own Programming Language"** (Clinton L. Jeffery, 2024)     | Comprehensive guide covering the entire pipeline; includes transpiler chapter. |
| **"Crafting Interpreters"** (Robert Nystrom)                             | Step-by-step interpreter construction; excellent explanations; free online.    |
| **"Compilers: Principles, Techniques, and Tools"** (Dragon Book)         | The classic reference for deep dives.                                          |
| **"Engineering a Compiler"** (Cooper & Torczon, 2022)                    | Academic depth; used in university courses.                                    |
| **"Hands-On Object-Oriented Programming"** (Anil Kumar Rangisetti, 2024) | For OOP extension after core language; covers C++ and Python.                  |

## 5.2. Online Courses & Tutorials

| Resource                                                                         | Focus                                  |
| -------------------------------------------------------------------------------- | -------------------------------------- |
| [LLVM Kaleidoscope Tutorial](https://llvm.org/docs/tutorial/)                    | Complete compiler with LLVM backend    |
| [IITK Systems Guide](https://pclub.in/roadmap/2025/11/01/systems-roadmap/)       | Step-by-step roadmap with exercises    |
| [Jack Crenshaw's "Let's Build a Compiler"](https://compilers.iecc.com/crenshaw/) | Classic tutorial building from scratch |
| [Ruslan's Blog - Writing a Lexer](http://lisperator.net/pltut/)                  | Detailed Python implementation         |

## 5.3. Python-Specific Resources

| Resource                                                                     | Description                                                     |
| ---------------------------------------------------------------------------- | --------------------------------------------------------------- |
| PyCon US 2017 Talk: "How to write a Python transpiler" (Russell Keith-Magee) | Directly relevant to your transpiler-to-Python approach.        |
| [py2many](https://github.com/adsharma/py2many)                               | Python to multiple language transpiler; study its architecture. |
| Python `argparse` module documentation                                       | For building CLI.                                               |
| Python `code` module documentation                                           | For REPL basics.                                                |

## 5.4. Latin Language Resources

| Resource                                                                    | Purpose                                                 |
| --------------------------------------------------------------------------- | ------------------------------------------------------- |
| [Collatinus](https://github.com/biblissima/collatinus)                      | Latin lemmatizer and morphological analyzer.            |
| Lewis and Short Dictionary (CEX format)                                     | Standard Latin-English dictionary.                      |
| [Latin POS Tagger & Lemmatizer](https://pypi.org/project/latin-pos-tagger/) | Python package for Latin word analysis.                 |
| [awesome-latin](https://github.com/latin-language/awesome-latin)            | Curated list of Latin language resources.               |
| [velut](https://github.com/david1726/velut)                                 | Next.js website returning Latin vocabulary information. |
| [Latin Dictionary (Latdict)](https://latin-dictionary.net/)                 | Online lookup.                                          |
| [Whitaker's Words](http://archives.nd.edu/words.html)                       | Classic Latin word analyzer.                            |
| [Perseus Digital Library](https://www.perseus.tufts.edu/hopper/)            | Classical texts and dictionaries.                       |
| [Latin Stack Exchange](https://latin.stackexchange.com/)                    | For questions about usage.                              |

## 5.5. AI-Assisted Learning

- Use AI tools (like ChatGPT) to summarize course material chapters and extract key concepts relevant to each implementation phase.
- Cross-reference AI summaries with original texts to ensure accuracy and depth.

---

# 6. Reference Projects

## 6.1. Latin-Based Languages

| Project   | Description                                                                                   | GitHub                                                      | Key Takeaways                                                              |
| --------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------------- | -------------------------------------------------------------------------- |
| Celeratas | Latin-based language in Python with indent syntax, REPL, and help system (`auxilium`).        | [planto73/Celeratas](https://github.com/planto73/Celeratas) | Keyword translations, help system, Python-based architecture.              |
| Latinium  | Latin-based language with custom VM; uses PLY for lexing/parsing; features pointers, vectors. | [mcpeixoto/Latinium](https://github.com/mcpeixoto/Latinium) | Grammar definition, PLY usage, feature set (including pointer arithmetic). |

## 6.2. Transpiler Examples

| Project | Description                                                                            | GitHub                                                  | Why Study                              |
| ------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------- | -------------------------------------- |
| RRL     | Tiny language that compiles to Python; includes parser, transpiler, sandboxed runtime. | [RRL_OpenSource](https://github.com/RRL_OpenSource)     | Minimal transpiler architecture.       |
| py2many | Production-grade transpiler from Python to Rust, C++, etc.                             | [adsharma/py2many](https://github.com/adsharma/py2many) | Type inference, multi-language output. |
| Barn    | Simple language in C that compiles to C.                                               | [barn-lang/barn](https://github.com/barn-lang/barn)     | Basic transpiler patterns.             |

## 6.3. Project Structure References

| Project         | Description                                                                                | GitHub                                                | Highlights                                           |
| --------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------- | ---------------------------------------------------- |
| fzy (fozzylang) | Rust-based language with modular crates (parser, ast, hir, runtime) and VS Code extension. | [fzy-lang/fzy](https://github.com/fzy-lang/fzy)       | Professional modular structure, tooling integration. |
| Svastra         | 22-week language roadmap with detailed weekly concepts.                                    | [svastra/svastra](https://github.com/svastra/svastra) | Learning progression, curriculum structure.          |

## 6.4. OOP Reference Projects

| Project         | Description                                                        | GitHub                                                            | Notes                               |
| --------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------- | ----------------------------------- |
| iox-transpiler  | Based on Crafting Interpreters; OOP + inheritance on TODO list.    | [iox-io/iox-transpiler](https://github.com/iox-io/iox-transpiler) | Visitor pattern, AST design.        |
| POOL Language   | Persistent Object-Oriented Language; subclass-as-subtype approach. | [pool-lang](https://github.com/pool-lang)                         | Inheritance model.                  |
| Traits Research | Inria research on traits as alternatives to inheritance.           | [TraitTalk](https://github.com/traittalk/traittalk)               | Pure trait language implementation. |

---

# 7. Development Roadmap (Actionable Week-by-Week)

This roadmap provides a concrete, week-by-week plan with concepts to learn, tasks to complete, resources to use, and deliverables to produce. It is designed for 18–20 hours per week.

## 7.0. Pre-Week: Minimal Prototype (Practice Project)

**Goal**: Build a minimal language (v0.1.0) to validate the pipeline before the full project.

**Features**:
- Variables (dynamic typing)
- Basic arithmetic expressions (`+`, `-`, `*`, `/`, parentheses)
- Print statement (`scribe`)
- Assignment
- Integer and string literals

**Implementation**:
- Lexer, parser, AST, transpiler that outputs Python.
- Should take about 1 week (18-20 hours).

**Version**: v0.1.0 (alpha)

## 7.1. Week 1: Identity & Foundations

**Concepts**:
- Language design, grammar, AST basics.
- Compiler pipeline overview.

**Tasks**:
- Finalize language name, keywords, file extension (`.lcdx`).
- Validate Latin keywords using Latin resources.
- Draft BNF/EBNF grammar.
- Define AST node structure.
- Set up GitHub repository with modular structure.
- Begin lexer implementation.
- Create `ErrorReporter` skeleton.

**Resources**:
- "Build Your Own Programming Language" Ch 1-2.
- "Crafting Interpreters" - Introduction & Lexing.
- IITK Systems Guide - expression parser exercise.

**Deliverables**:
- GitHub repo with README, project vision.
- Grammar specification document.
- Project structure scaffolded.
- Version: v0.2.0 (alpha)

## 7.2. Week 2: Lexer & Parser Core

**Concepts**:
- Finite state machines, regular expressions, error reporting.
- Context-free grammars.

**Tasks**:
- Complete lexer with full token set, using `ErrorReporter`.
- Handle edge cases (invalid characters, unterminated strings).
- Begin recursive descent parser for expressions.
- Unit tests for lexer.

**Resources**:
- "Build Your Own Programming Language" Ch 3 (Scanning).
- Dragon Book Ch 3.
- Ruslan's Blog - Writing a Lexer.

**Deliverables**:
- Working lexer with token output.
- Basic expression parser.
- Test suite.
- Version: v0.3.0 (alpha)

## 7.3. Week 3: Complete Parser & AST

**Concepts**:
- Top-down parsing, precedence, parse vs. syntax trees.
- AST node construction.

**Tasks**:
- Parse all language constructs (functions, conditionals, loops).
- Build AST nodes from parsed input.
- Implement error reporting with line numbers (via `ErrorReporter`).
- Output AST visualization (GraphViz).

**Resources**:
- "Build Your Own Programming Language" Ch 4-5 (Parsing, Syntax Trees).
- "Crafting Interpreters" - Parsing chapters.
- Jack Crenshaw's series parts 4-6.

**Deliverables**:
- Complete parser.
- AST node hierarchy.
- GraphViz visualization.
- Version: v0.4.0 (alpha)

## 7.4. Week 4: Semantic Analysis & Transpiler

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
- "Build Your Own Programming Language" Ch 6-8 (Symbol Tables, Type Checking, Intermediate Representations).
- "Crafting Interpreters" - Resolving and Binding.
- Dragon Book Ch 6.

**Deliverables**:
- Symbol tables.
- Type checker.
- Basic transpiler generating Python.
- Version: v0.5.0 (alpha)

## 7.5. Week 5: Standard Library (Tier 1), REPL, CLI

**Concepts**:
- Runtime systems, interactive interpreters.
- CLI design.
- Import system.

**Tasks**:
- Implement **Tier 1** functions for modules: `fasciculus`, `numerus`, `filum`, `systema`, `via` (must-have set).
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
- Standard library modules (Tier 1 must-haves).
- Working REPL.
- CLI tool with run/repl/ast/debug commands.
- Version: v0.6.0 (alpha)

## 7.6. Week 6: Ecosystem Polish

**Concepts**:
- IDE integration, documentation generation.
- Packaging, distribution.

**Tasks**:
- Build VS Code extension with syntax highlighting and "run" command.
- Create Next.js website with Fumadocs (English only for v1.0).
- Write 5+ example programs (Roman-themed).
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
- PyPI package.
- User and developer manuals.
- Changelog.
- Version: v0.7.0 (beta) – feature complete, ready for wider testing.

## 7.7. Versioning and Release Stages

The project follows [Semantic Versioning](https://semver.org/) from the start.

| Version         | Stage  | Description                                               |
| --------------- | ------ | --------------------------------------------------------- |
| v0.1.0          | Alpha  | Minimal prototype (practice project)                      |
| v0.2.0 – v0.6.0 | Alpha  | Incremental feature additions; not stable for general use |
| v0.7.0 – v0.9.0 | Beta   | Feature-complete, polishing, bug fixes                    |
| v1.0.0          | Stable | First production release                                  |

**Alpha** (0.1.0 to 0.6.0): Features still being added; not recommended for production.
**Beta** (0.7.0 to 0.9.0): Feature-complete, but may have bugs; ready for wider testing.
**Release Candidate** (0.9.0): Final testing before 1.0.0.

**Implementation**:
- Use Git tags: `git tag v0.1.0`
- Update `__version__` in Python package and `version` in `package.json` for VS Code extension.
- Maintain `CHANGELOG.md` with entries for each version.

---

# 8. Object-Oriented Programming Extension (Post-6 Weeks)

## 8.1. Motivation

- Showcases language evolution (v1.0 → v2.0).
- Adds significant functionality for complex programs.
- Demonstrates extensible architecture.
- Enables Tier 2 module APIs (object-oriented versions).

## 8.2. Learning Path

1. **Read**: "Hands-On Object-Oriented Programming" (Rangisetti, 2024) - C++ chapters then Python adaptation.
2. **Study**: CMU Lecture Notes on adding objects to languages.
3. **Analyze**: iox-transpiler's OOP TODO and visitor pattern.
4. **Understand**: Orthogonal dimensions of object-based languages (Wegner, 1987).

## 8.3. Features to Implement

| Feature          | Latin Keyword (tentative)  | Description                          |
| ---------------- | -------------------------- | ------------------------------------ |
| Class            | `classis`                  | Defines a class.                     |
| Constructor      | `constructor`              | Special method for object creation.  |
| Method           | `munus` (same as function) | Method definition inside class.      |
| Self reference   | `se`                       | Reference to current instance.       |
| Inheritance      | `ortus` (born from)        | Single inheritance.                  |
| Super call       | `superus`                  | Call parent class method.            |
| Override         | `supercede` / `obtege`     | Explicit override marker (optional). |
| Dynamic dispatch | –                          | Virtual method calls.                |
| Public/Private   | `publicus` / `privatus`    | Access modifiers (future).           |

## 8.4. Implementation Phases

| Phase | Features                                                          | Key Challenges                    |
| ----- | ----------------------------------------------------------------- | --------------------------------- |
| 1     | Classes with fields and methods.                                  | Object layout, symbol tables.     |
| 2     | Constructors and instance creation (`novus` or `crea`).           | Constructor chaining.             |
| 3     | Single inheritance and method overriding.                         | Virtual tables, dynamic dispatch. |
| 4     | Polymorphism and dynamic dispatch.                                | Method lookup performance.        |
| 5     | (Optional) Traits/mixins as alternatives to multiple inheritance. | Conflict resolution, composition. |

## 8.5. Reference Projects

- **iox-transpiler**: OOP on TODO list; study its AST and visitor pattern.
- **POOL language**: Subclass-as-subtype approach.
- **Traits research**: Pure trait languages (e.g., TraitTalk).

---

# 9. Ecosystem Components

## 9.1. VS Code Extension

**Core Features (v1.0)**:
- Syntax highlighting (TextMate grammar for `.lcdx`).
- Command to run current file (using `latium run`).
- Output channel for results.
- Basic error linting (via problem matcher).

**Future Enhancements**:
- Code snippets for common constructs.
- Advanced linting (semantic errors).
- Debugger support.

**Resources**:
- "Build Your Own Programming Language" Ch 10.
- VS Code extension documentation.
- fzy's VS Code extension structure.

## 9.2. Website (Next.js + Fumadocs)

**v1.0 Scope**:
- Built with Next.js and Fumadocs.
- Single language (English).
- Pages: Landing, User Manual, Language Reference, Example Gallery, Installation, Download.
- Hosted on Vercel.

**Post-v1.0 Enhancements**:
- Internationalization (i18n) – Latin toggle, with modular JSON translation files.
- Online playground (using Pyodide or similar).
- Scalable architecture for future languages.

**i18n Strategy**:
- Use Next.js internationalized routing.
- Store translations in `locales/{lang}/common.json`.
- For documentation content, use locale-specific MDX files (`docs/en/`, `docs/la/`).
- Provide contribution guidelines for adding new languages.

## 9.3. GitHub Strategy

- **Public from day one**.
- **Weekly commits** showing progress.
- **GitHub Projects** board for roadmap tracking.
- **README** with project vision, setup instructions, and badges.
- **CONTRIBUTING.md** with guidelines (including Git workflow, coding standards).
- **LICENSE**: MIT.

## 9.4. Documentation Deliverables

| Deliverable            | Purpose                                                            | Example Content / Format                                                                                                                          |
| ---------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User Manual**        | For programmers writing Latium code.                               | Tutorials ("Your first Latium program"), language guide, standard library reference with examples. Include security note about command execution. |
| **Developer Manual**   | For contributors to the compiler and tooling.                      | Architecture overview, setup guide (uv, pnpm), how to add a feature, testing guidelines, release process.                                         |
| **Language Reference** | Formal specification of syntax and semantics.                      | BNF grammar, keyword list, type rules, operator precedence table.                                                                                 |
| **Reflection**         | Personal analysis of design decisions, tradeoffs, lessons learned. | Markdown document in `docs/reflection.md`, structured by topic.                                                                                   |

These are distinct from the website: the website presents a polished subset (user manual + reference), while developer manual and reflection stay in the repo.

---

# 10. Future Features (Post-v1.0)

## 10.1. Documentation & Code Quality

- Docstrings (support for documenting functions, classes, modules).
- Type hints (full static typing).

## 10.2. Object-Oriented Programming (Detailed)

(See Section 8.)

## 10.3. Functional Programming

- First-class functions.
- Higher-order functions (`transforma`, `elige`, `accumula`).
- Anonymous functions (lambdas) with `->` syntax.
- Closures.

## 10.4. IDE & Developer Tooling

- **Language Server Protocol (LSP)** implementation for advanced code completion, smart suggestions, auto-imports, hover documentation, go-to-definition.
- **Auto-imports**: Suggest and insert imports for modules based on what the user types.
- **Linting and formatting** tools.

## 10.5. Online Playground

- Web-based editor and runner for Latium Codex.
- Options: Pyodide (Python in WASM) to run transpiler in browser, or server-side execution with sandbox.
- Planned for post-v1.0.

---

# 11. Changelog

## 11.1. Format and Maintenance

A `CHANGELOG.md` file will be maintained in the repository, following [Keep a Changelog](https://keepachangelog.com/) format.

**Template**:

```markdown
# Changelog

All notable changes to Latium Codex will be documented in this file.

## [Unreleased]
### Added
- New standard library module: `tempus` for date/time operations.
- Support for `importa` keyword.

### Changed
- Improved error messages for lexer.

### Fixed
- Bug in function scope resolution.

## [1.0.0] - 2026-03-06
### Added
- Initial release of Latium Codex.
- Core language features: variables, functions, conditionals, loops.
- REPL and CLI.
- VS Code extension.
- ...
```

---

# 12. Appendix: Latin Keyword Candidates

> **Canonical version:** [`docs/detailed/12-appendix-keywords.md`](detailed/12-appendix-keywords.md) — keep that file as the authoritative reference. The table below is a summary copy.

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

*Note: Final keyword selection will occur during Week 1 design phase, with input from Latin resources and thematic consistency.*

---

# 14. Knowledge Management and Documentation for Future Reference

## 14.1. Project Journal / Development Log

Maintain a daily or weekly log in `docs/journal.md` recording:
- What you did each day
- Decisions made and why
- Problems encountered and solutions
- Links to resources found helpful
- Next steps

## 14.2. Personal Knowledge Base (KB)

Folder `docs/kb/` containing:
- Summaries of key concepts from course material.
- Notes on reference projects (Celeratas, Latinium).
- Latin vocabulary spreadsheet.
- Design notes and diagrams.
- Code snippets and patterns.

This is for internal use, not published on the website.

## 14.3. AI Copilot Instructions

File `.github/copilot-instructions.md` (or similar) with:
- Project overview and goals.
- Current development phase (e.g., Week 1).
- Coding conventions (Python style, Latin naming).
- Key design decisions (transpiler, optional typing, Tier 1 vs Tier 2).
- List of keywords and modules.
- Common tasks (e.g., "Add a new AST node").

Update this file as the project evolves.

## 14.4. Resource List

Maintain a curated list of resources (books, articles, videos) with annotations on why they are useful. (Already in Section 5.)

## 14.5. Versioned Documentation

All project documentation is versioned alongside code in the `docs/` folder. Use `docs/README.md` as an index.

---

# 15. License

The project is licensed under the [MIT License](https://opensource.org/licenses/MIT). A `LICENSE` file will be included in the root of the repository.

---

# 16. Security Considerations

- The `systema` module allows execution of arbitrary system commands via `curre()`. This is a powerful feature but can be dangerous if used with untrusted input. The user manual will include a warning:
  > "Be cautious when using `curre()` with user-provided strings, as it can execute arbitrary commands. Validate and sanitize any external input before passing it to this function."
- File I/O functions also operate on the file system; standard precautions apply.

---

**This document is a living reference.** Update it as design decisions evolve and new resources are discovered. Use it to stay organized and focused throughout the 6-week build and beyond.