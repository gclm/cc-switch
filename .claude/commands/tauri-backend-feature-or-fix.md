---
name: tauri-backend-feature-or-fix
description: Workflow command scaffold for tauri-backend-feature-or-fix in cc-switch.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /tauri-backend-feature-or-fix

Use this workflow when working on **tauri-backend-feature-or-fix** in `cc-switch`.

## Goal

Implements new features or bug fixes in the Tauri backend, often involving Rust source files and configuration.

## Common Files

- `src-tauri/src/services/stream_check.rs`
- `src-tauri/src/proxy/gemini_url.rs`
- `src-tauri/Cargo.toml`
- `src-tauri/Cargo.lock`
- `src-tauri/src/commands/settings.rs`
- `src-tauri/src/lib.rs`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add Rust source files in src-tauri/src
- Update Cargo.toml and Cargo.lock if dependencies or plugins are added
- Update related logic in src-tauri/src/lib.rs or other core files

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.