---
name: provider-feature-update
description: Workflow command scaffold for provider-feature-update in cc-switch.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /provider-feature-update

Use this workflow when working on **provider-feature-update** in `cc-switch`.

## Goal

Adds or updates provider-related features, presets, or configuration options, often including localization and documentation.

## Common Files

- `src/config/claudeProviderPresets.ts`
- `src/components/providers/forms/CommonConfigEditor.tsx`
- `src/i18n/locales/en.json`
- `src/i18n/locales/ja.json`
- `src/i18n/locales/zh.json`
- `docs/user-manual/en/2-providers/2.1-add.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add provider preset/configuration files in src/config or src/components/providers
- Update localization files in src/i18n/locales
- Update or add relevant documentation in docs/user-manual
- Update or add related tests in tests/components

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.