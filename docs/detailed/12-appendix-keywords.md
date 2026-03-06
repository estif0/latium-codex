# Latium Codex – Appendix: Latin Keyword & Function Reference

**Document ID:** `12-appendix-keywords.md`
**Part of:** Detailed Documentation Series
**Audience:** Developers, contributors, language implementers
**Last Updated:** 2026-03-06

---

## Overview

This appendix is the single authoritative reference for every Latin name in Latium Codex — language keywords, operators, module names, and all stdlib functions. Use it during implementation (lexer keyword list, parser, transpiler mappings) and during language design to check for collisions and consistency.

**Conventions:**
- Function keywords use the **imperative mood** (verbs as commands).
- Noun keywords use the **nominative case**.
- Standard operator symbols (`+`, `-`, etc.) are reused as-is.
- **Tier 1** = available in v1.0 (procedural). **Tier 2** = post-v1.0 OOP API.
- Parameters named `iter` mean a file path string. `terminus` means an end index/boundary (not `finis`, which is reserved as a block-closing keyword).
- OOP keywords are marked **future** and subject to change during the Week 1 design phase.

---

## 1. Core Language Keywords

| Category         | English      | Latin (Tentative)      | Notes                           |
| ---------------- | ------------ | ---------------------- | ------------------------------- |
| **Core**         | variable     | `res`                  |                                 |
|                  | function     | `munus`                |                                 |
|                  | if           | `si`                   |                                 |
|                  | else         | `aliter`               |                                 |
|                  | else if      | `aliter si`            |                                 |
|                  | while        | `dum`                  |                                 |
|                  | for          | `per`                  |                                 |
|                  | return       | `redde`                | imperative of reddere           |
|                  | print        | `scribe`               | console output only             |
|                  | write        | `inscribe`             | file write only                 |
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
|                  | end block    | `finis`                | optional closing keyword; **reserved — do not use as identifier** |
| **Import**       | import       | `importa`              |                                 |
|                  | from         | `ex`                   |                                 |
|                  | as           | `ut`                   | alias                           |
| **OOP (future)** | class        | `classis`              |                                 |
|                  | new          | `novus` / `crea`       | object creation                 |
|                  | is           | `est`                  | type check / instanceof         |
|                  | extends      | `ortus`                | inheritance; "born from"        |
|                  | super        | `superus`              | parent class call               |
|                  | self         | `se`                   | reflexive pronoun               |
|                  | override     | `supercede` / `obtege` | method override marker (optional) |
|                  | public       | `publicus`             | access modifier                 |
|                  | private      | `privatus`             | access modifier                 |

---

## 2. Operators

All operators use standard symbols. Latin names are not used for operators.

| Operator     | Symbol(s)            | Description                  |
| ------------ | -------------------- | ---------------------------- |
| Add          | `+`                  | Arithmetic addition          |
| Subtract     | `-`                  | Arithmetic subtraction       |
| Multiply     | `*`                  | Arithmetic multiplication    |
| Divide       | `/`                  | Float division               |
| Floor divide | `//`                 | Integer (floor) division     |
| Modulo       | `%`                  | Remainder                    |
| Power        | `**`                 | Exponentiation               |
| Equal        | `==`                 | Equality check               |
| Not equal    | `!=`                 | Inequality check             |
| Comparison   | `<`, `>`, `<=`, `>=` | Relational comparisons       |

---

## 3. Module Names

| English    | Module Name  |
| ---------- | ------------ |
| file I/O   | `fasciculus` |
| system     | `systema`    |
| path       | `via`        |
| math       | `numerus`    |
| string     | `filum`      |
| list       | `collectio`  |
| dictionary | `dictio`     |
| datetime   | `tempus`     |

---

## 4. Standard Library Functions

### 4.1. `fasciculus` – File I/O

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

### 4.2. `systema` – System

| Tier | Function                 | Latin Name                   | Description                             | Python Equivalent                          |
| ---- | ------------------------ | ---------------------------- | --------------------------------------- | ------------------------------------------ |
| 1    | Execute command          | `curre(commando)`            | Runs command, returns stdout as string. | `subprocess.run(..., capture_output=True)` |
| 1    | Exit program             | `exi(code)`                  | Exits with given code.                  | `sys.exit(code)`                           |
| 1    | Get environment variable | `cape_ambitum(nomen)`        | Returns value or null.                  | `os.environ.get(nomen)`                    |
| 1    | Set environment variable | `pone_ambitum(nomen, valor)` | Sets variable.                          | `os.environ[nomen] = valor`                |
| 2    | Process object           | `Process` class              | More detailed process control.          | `subprocess.Popen`                         |

*`ambitum` (surroundings/environment) is the canonical Latin term for "env". Use it consistently in any new environment-related names.*

### 4.3. `via` – Path

| Tier | Function        | Latin Name                  | Description                        | Python Equivalent        |
| ---- | --------------- | --------------------------- | ---------------------------------- | ------------------------ |
| 1    | Absolute path   | `via_absoluta(iter)`        | Returns absolute path.             | `os.path.abspath(iter)`  |
| 1    | Base name       | `via_basename(iter)`        | Returns final component of path.   | `os.path.basename(iter)` |
| 1    | Directory name  | `via_dirname(iter)`         | Returns parent directory.          | `os.path.dirname(iter)`  |
| 1    | Check existence | `via_existit(iter)`         | Returns boolean.                   | `os.path.exists(iter)`   |
| 1    | Is file?        | `via_est_archivum(iter)`    | Returns boolean.                   | `os.path.isfile(iter)`   |
| 1    | Is directory?   | `via_est_directorium(iter)` | Returns boolean.                   | `os.path.isdir(iter)`    |
| 2    | Path object     | `Via` class                 | Object-oriented path manipulation. | `pathlib.Path`           |

### 4.4. `numerus` – Math

*Basic arithmetic (`+`, `-`, `*`, `/`, `//`, `%`, `**`) uses standard operators. This module covers operations not expressible as operators.*

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

### 4.5. `filum` – String

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

### 4.6. `collectio` – List

| Tier | Function          | Latin Name                         | Description                     | Python Equivalent                       |
| ---- | ----------------- | ---------------------------------- | ------------------------------- | --------------------------------------- |
| 1    | Concatenate lists | `coniungere(l1, l2)`               | Returns new list.               | `l1 + l2`                               |
| 1    | Slice             | `secare(lista, initium, terminus)` | Returns slice.                  | `lista[initium:terminus]`               |
| 1    | Sort              | `ordinare(lista)`                  | Returns sorted list.            | `sorted(lista)`                         |
| 1    | Append element    | `addere(lista, elementum)`         | Returns new list with appended. | `lista + [elementum]`                   |
| 1    | Remove element    | `removere(lista, elementum)`       | Returns new list without.       | `[x for x in lista if x != elementum]` |
| 1    | Length            | `longitudo(lista)`                 | Returns integer.                | `len(lista)`                            |
| 2    | List object       | `Collectio` class                  | Mutable list with methods.      | –                                       |

### 4.7. `dictio` – Dictionary

| Tier | Function          | Latin Name                      | Description                | Python Equivalent                                |
| ---- | ----------------- | ------------------------------- | -------------------------- | ------------------------------------------------ |
| 1    | Add/Set           | `addere(dictio, clavis, valor)` | Returns updated dict.      | `{**dictio, clavis: valor}`                      |
| 1    | Remove            | `removere(dictio, clavis)`      | Returns updated dict.      | `{k:v for k,v in dictio.items() if k != clavis}` |
| 1    | Has key           | `habere(dictio, clavis)`        | Returns boolean.           | `clavis in dictio`                               |
| 1    | Get keys          | `claves(dictio)`                | Returns list of keys.      | `list(dictio.keys())`                            |
| 1    | Get values        | `valores(dictio)`               | Returns list of values.    | `list(dictio.values())`                          |
| 2    | Dictionary object | `Dictio` class                  | Mutable dict with methods. | –                                                |

### 4.8. `tempus` – DateTime

| Tier | Function          | Latin Name                      | Description                    | Python Equivalent    |
| ---- | ----------------- | ------------------------------- | ------------------------------ | -------------------- |
| 1    | Current datetime  | `nunc()`                        | Returns string representation. | `datetime.now()`     |
| 1    | Format datetime   | `formare_tempus(tempus, forma)` | Returns formatted string.      | `dt.strftime(forma)` |
| 1    | Difference (days) | `differre(t1, t2)`              | Returns number of days.        | `(t2 - t1).days`     |
| 2    | DateTime object   | `Tempus` class                  | Objects with methods.          | `datetime.datetime`  |

*Note: `formare_tempus` uses a `_tempus` suffix to avoid collision with `filum.formare`. Both functions exist in global scope after import; the suffix distinguishes them.*

---

## 5. Design Notes

| Topic | Note |
| ----- | ---- |
| `finis` | Reserved block-closing keyword (e.g., `finis munus`). Never use as a parameter or variable name. Use `terminus` for end-of-range values. |
| `se` (self) | Latin reflexive pronoun — semantically accurate and intentional. |
| `ortus` (extends) | Past participle of `oriri` — "having risen/been born from." Chosen for thematic richness. |
| `file.claude()` | `claude` is the Latin imperative of `claudere` (to close/shut). Correct Latin; intentional. |
| `ambitum` | Canonical Latin for "environment" (surroundings). Used in `cape_ambitum` / `pone_ambitum`; apply consistently to any new env-related names. |
| `coniungere` | Used in both `filum` (string concat) and `collectio` (list concat). No collision — module-qualified at global scope (`filum.coniungere` vs `collectio.coniungere`). |
| `addere` / `removere` | Used in both `collectio` and `dictio`. Module-qualified at global scope; no collision. |
| `longitudo` | Used in both `filum` (string length) and `collectio` (list length). Module-qualified; no collision. |
| `formare` vs `formare_tempus` | `filum.formare` = string format; `tempus.formare_tempus` = datetime format. Suffix kept to prevent global scope collision when both modules are imported. |

---

*Note: Final keyword selection will be confirmed during the Week 1 design phase, with input from Latin language resources and prototype code examples.*
