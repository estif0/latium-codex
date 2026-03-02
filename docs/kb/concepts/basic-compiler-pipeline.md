# Latium Codex Compiler Pipeline Overview

This note summarizes the architecture of the Latium Codex transpiler. The pipeline converts `.lcdx` source code into equivalent Python code through a series of modular stages. The design is scalable, allowing incremental addition of language features.

```
.lcdx source → [Lexer] → tokens → [Parser] → AST → [Transpiler] → Python code
                      ↑           ↑         ↑
                      └───[ErrorReporter]───┘
```

## 1. Lexer (Tokenizer)
- **Purpose**: Transforms raw source text into a flat list of tokens – the smallest meaningful units (keywords, identifiers, operators, literals).
- **Input**: Source code string.
- **Output**: List of `Token` objects, each with `type`, `lexeme`, `line`, `column`.
- **Prototype features**: Handles `scribe`, identifiers, integers, strings, operators `+ - * / =`, parentheses. Discards whitespace (except indentation, deferred).
- **Error handling**: Reports invalid characters via `ErrorReporter`; can continue scanning.

## 2. Parser
- **Purpose**: Imposes grammatical structure on the token stream, producing an Abstract Syntax Tree (AST).
- **Input**: List of tokens.
- **Output**: AST root node (e.g., `Program` containing statements).
- **Approach**: Recursive‑descent parsing, with methods for each grammar rule.
- **Prototype grammar** (simplified):
  ```
  program   → statement*
  statement → printStmt | varDecl | exprStmt
  printStmt → "scribe" expression
  varDecl   → IDENTIFIER ":" expression
  exprStmt  → expression
  expression→ term (("+" | "-") term)*
  term      → factor (("*" | "/") factor)*
  factor    → INTEGER | STRING | IDENTIFIER | "(" expression ")"
  ```
- **Error handling**: On syntax error, reports via `ErrorReporter` and may attempt recovery (e.g., synchronize to next statement).

## 3. Abstract Syntax Tree (AST)
- **Purpose**: Represents the program structure in a tree form, hiding syntactic details (parentheses, etc.).
- **Node types (prototype)**:
  - `Program` (list of statements)
  - `PrintStmt` (expression)
  - `VarDecl` (name, initializer)
  - `BinaryOp` (left, operator, right)
  - `Literal` (value: int or string)
  - `Variable` (name)
- **Design**: Class hierarchy (or dataclasses) with optional Visitor pattern for traversal (useful for later stages like type checking).

## 4. Transpiler (Code Generator)
- **Purpose**: Walks the AST and outputs equivalent Python source code.
- **Input**: AST root.
- **Output**: Python code string.
- **Mapping (prototype)**:
  - `scribe expr` → `print(expr)`
  - `x: expr` → `x = expr`
  - Binary operations → same operators (relying on Python precedence)
  - Literals → unchanged
  - Variable references → same name
- **Implementation**: A `Transpiler` class with `visit` methods for each node type, accumulating output lines.

## 5. ErrorReporter
- **Purpose**: Collects errors and warnings from all stages, presenting them uniformly.
- **Design**: Shared instance passed to lexer, parser, etc. Accumulates error objects (message, location, severity). At end, prints formatted errors and determines compilation success.
- **Prototype**: Simple collector that prints all errors after parsing; later can support colored output, suggestions, etc.

## Modularity & Scalability
- Each stage is an independent module (`lexer/`, `parser/`, `ast/`, `transpiler/`, `utils/`) with clear interfaces.
- New features (functions, classes, indentation blocks, standard library) can be added by extending relevant modules:
  - Lexer: new token types (INDENT/DEDENT, new keywords)
  - Parser: new grammar rules
  - AST: new node types
  - Transpiler: new code generation patterns
- Intermediate stages (e.g., semantic analysis) can be inserted between parser and transpiler.

## Testing Strategy
- **Unit tests**: Each stage tested in isolation.
  - Lexer: input strings → expected token lists.
  - Parser: token lists → expected AST (snapshot testing).
  - Transpiler: AST → expected Python code.
- **Integration tests**: Full compilation of `.lcdx` files, optionally executing the generated Python to verify behavior.
- Use `pytest`; tests reside in `compiler/tests/`.

This pipeline forms the backbone of Latium Codex. The Week 0 prototype implements a minimal version, proving the end‑to‑end flow before adding complexity.