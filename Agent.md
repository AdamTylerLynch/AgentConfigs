# Claude Assistant Guidelines

This document provides comprehensive guidelines for Claude when working with this codebase and environment.

## Core Tenets

1. We preference **security**, **durability**, **availability**, in that order.
2. Never put secrets/credentials in code, but they can go in environment files.
3. We use **GitFlow** as a branching strategy:
   - Branch from `develop` for each work item
   - Merge from `develop` to `main` for releasing
4. For external interfaces and APIs:
   - Always favor backwards compatibility
   - Design forward and backward compatible interfaces
   - Support clients with Tolerant-Reader pattern
   - Always think about the consumer when designing

## Available Tools and Usage

When you need to call tools from the shell, use this rubric:

### File Operations
- **Find files by name:** `fd <pattern>`
- **Find files with path name:** `fd -p <file-path>`
- **List files in a directory:** `fd . <directory>`
- **Find files with extension and pattern:** `fd -e <extension> <pattern>`

### Text and Code Search
- **Find Text:** `rg` (ripgrep) - Use for plain-text searches only when explicitly requested
- **Find Code Structure:** `ast-grep` - Prefer this for syntax-aware matching
  - Go  `ast-grep --lang go -p '<pattern>'`
  - TypeScript  `ast-grep --lang ts -p '<pattern>'`
  - React (TSX)  `ast-grep --lang tsx -p '<pattern>'`
  - Python  `ast-grep --lang python -p '<pattern>'`
  - Bash  `ast-grep --lang bash -p '<pattern>'`
  - JavaScript  `ast-grep --lang js -p '<pattern>'`
  - Rust  `ast-grep --lang rust -p '<pattern>'`
  - JSON  `ast-grep --lang json -p '<pattern>'`

### Data Processing
- **Select among matches:** pipe to `fzf`
- **JSON processing:** `jq`
- **YAML/XML processing:** `yq`

**Important:** If `ast-grep` is available, avoid plain-text searches (`rg`/`grep`) when you need syntax-aware matching. Use `rg` only when a plain-text search is explicitly requested.

## References

Use the Terraform MCP server when working in Terraform/HCL.
Use context7 tools for looking at documentation and API guides!

## Working with Repositories

### GitHub Operations
Use `gh` when working with GitHub.

### Pushing Code
- **Always run tests before pushing**, if tests exist.
- After pushing code to a branch, if there is a PR for it, update the PR with a comment indicating the changes you have made.

### Pull Requests
- When creating pull requests, always make them to the `develop` branch from origin unless specified otherwise.

## Coding Guidelines

### Codebase Norms (in prder of preference)
1. Always follow the existing folder structure in the source code
2. Always understand the cultural norms in the code (style, naming, organization) and use that
3. We preference idiomatic code matching the language
3. We generally preference SOLID principles
4. We preference single use functions and classes

### Scratchpad for Plans and Todos
- If you need to write markdown files or scratch space, write them in `./scratchpads` folder
- If you need to write examples to test something, also write them in `./scratchpads` folder
- Track your todos in `scratchpads/todos/todo-<today's date>.md`
- As you go through the todos list, if they are done, check them off in the markdown file

### Code Commenting
- Don't excessively comment code; stick to good functions that are not overly complex
- When creating documentation in-code:
  - Create documentation on functions and classes
  - Avoid putting inline comments unless it is critical to do so

### Testing Guidelines
1. Mark tests as **unit** or **integration**
2. Always follow the folder structure in the source code
3. Ensure that static values are in a `fixtures` folder that can be reused between tests

## Environment Information

This file is stored in `~/.claude/` for persistent reference across all projects and sessions.%   