```markdown
# rustdesk Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `rustdesk` Rust codebase. You'll learn about file naming, import/export styles, commit conventions, and how to write and organize tests. This guide also includes suggested commands for common workflows to streamline your development process.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `remoteControl.rs`, `fileTransfer.rs`

### Import Style
- Use **relative imports** within the codebase.
  - Example:
    ```rust
    use crate::utils::network;
    use super::config;
    ```

### Export Style
- Use **named exports** for modules and functions.
  - Example:
    ```rust
    pub fn start_server() { ... }
    pub mod network;
    ```

### Commit Patterns
- Follow **Conventional Commits** with the `feat` prefix for new features.
  - Example commit message:
    ```
    feat: add support for remote clipboard synchronization
    ```
- Commit messages should average around 80 characters.

## Workflows

### Feature Development
**Trigger:** When implementing a new feature  
**Command:** `/feature-dev`

1. Create a new branch for your feature.
2. Use camelCase for new file names.
3. Use relative imports for referencing other modules.
4. Export new functions or modules using named exports.
5. Write or update tests in files matching `*.test.*`.
6. Commit changes using the `feat` prefix and a descriptive message.
7. Open a pull request for review.

### Code Testing
**Trigger:** When adding or modifying code  
**Command:** `/run-tests`

1. Identify or create test files matching the pattern `*.test.*`.
2. Write tests for new or changed functionality.
3. Run tests using the project's preferred test runner (framework unknown; typically `cargo test` in Rust).
4. Ensure all tests pass before committing.

### Code Review Preparation
**Trigger:** Before submitting code for review  
**Command:** `/prepare-review`

1. Check that all files follow camelCase naming.
2. Verify all imports are relative.
3. Ensure all exports are named.
4. Confirm commit messages follow the conventional pattern.
5. Make sure tests are present and passing.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `network.test.rs`).
- The testing framework is not explicitly specified, but Rust projects typically use the built-in test framework.
- Example test:
  ```rust
  #[cfg(test)]
  mod tests {
      use super::*;

      #[test]
      fn test_connection() {
          assert!(connect_to_server().is_ok());
      }
  }
  ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /feature-dev    | Start a new feature development workflow      |
| /run-tests      | Run all tests in the codebase                |
| /prepare-review | Prepare your code for review and submission  |
```
