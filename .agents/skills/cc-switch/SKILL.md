```markdown
# cc-switch Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the `cc-switch` repository, a Rust-based project (with some TypeScript/JavaScript components) focused on provider management and Tauri backend features. You'll learn the project's coding conventions, commit patterns, and the main development workflows for both provider features and backend updates.

---

## Coding Conventions

### File Naming

- **PascalCase** is used for file names.
  - Example: `CommonConfigEditor.tsx`, `GeminiUrl.rs`

### Import Style

- **Alias imports** are preferred.
  - Example (TypeScript):
    ```typescript
    import { CommonConfigEditor as ConfigEditor } from './CommonConfigEditor';
    ```
  - Example (Rust):
    ```rust
    use crate::services::stream_check as stream_checker;
    ```

### Export Style

- **Named exports** are used.
  - Example (TypeScript):
    ```typescript
    export { CommonConfigEditor };
    ```

### Commit Messages

- **Conventional Commits** are used, with prefixes:
  - `feat`: For new features
  - `fix`: For bug fixes
- **Average commit message length:** 51 characters
  - Example:
    ```
    feat: add support for new provider configuration
    fix: resolve stream check timeout issue
    ```

---

## Workflows

### Provider Feature Update

**Trigger:** When you want to add or update a provider, preset, or configuration option, including localization and documentation.  
**Command:** `/update-provider`

1. **Modify or add provider preset/configuration files:**
   - Edit or create files in `src/config` or `src/components/providers`.
     ```typescript
     // src/config/claudeProviderPresets.ts
     export const newProviderPreset = { ... };
     ```
2. **Update localization files:**
   - Edit `src/i18n/locales/en.json`, `ja.json`, or `zh.json` to add new strings.
     ```json
     // src/i18n/locales/en.json
     {
       "provider.new": "New Provider"
     }
     ```
3. **Update or add documentation:**
   - Add or update docs in `docs/user-manual/[lang]/2-providers/2.1-add.md`.
4. **Update or add related tests:**
   - Add or update test files in `tests/components`, following the `*.test.*` pattern.
     ```typescript
     // tests/components/CommonConfigEditor.test.tsx
     test('renders new provider config', () => { ... });
     ```

---

### Tauri Backend Feature or Fix

**Trigger:** When you want to implement a new feature or fix a bug in the Tauri (Rust) backend.  
**Command:** `/tauri-backend-update`

1. **Modify or add Rust source files:**
   - Edit or create files in `src-tauri/src`.
     ```rust
     // src-tauri/src/services/stream_check.rs
     pub fn check_stream() -> bool { ... }
     ```
2. **Update dependencies if needed:**
   - Edit `Cargo.toml` and run `cargo update` to update `Cargo.lock`.
     ```toml
     # src-tauri/Cargo.toml
     [dependencies]
     tauri = "1.2"
     ```
3. **Update core logic:**
   - Edit `src-tauri/src/lib.rs` or other core files to integrate new features or fixes.
     ```rust
     // src-tauri/src/lib.rs
     mod services;
     ```

---

## Testing Patterns

- **Test Framework:** Unknown, but tests use the `*.test.*` file pattern.
- **Test Location:** Typically in `tests/components/`.
- **Example:**
  ```typescript
  // tests/components/CommonConfigEditor.test.tsx
  test('should render correctly', () => {
    // test implementation
  });
  ```

---

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /update-provider       | Add or update a provider, preset, or configuration option    |
| /tauri-backend-update  | Add a new feature or fix a bug in the Tauri (Rust) backend   |
```
