# Humanisation workflow correction

Operator confirmed28October2026 that the installed `humanize` skill is the prose workflow. The authoring workflow now points to the skill and its checks. Removed the unsupported provider transport, scoring/retry, per-unit ledger and ineligible dispositions. Preserved the existing confidentiality, source verification, technical-token preservation, placement and site validation requirements.

Humanisation: skipped for this change because it edits agent-only instructions. `automation/` and `evidence/` are excluded from the documentation site by `.mintignore`; no reader-facing MDX, navigation, API contract or product availability claim changes.

Validation: `git diff --check`, stale-reference scan, `mint validate` and `mint broken-links` each exited0. No new test or harness required for a reversible prose correction. Rendered preview is inapplicable: both edited files are excluded by `.mintignore` and no shipped page changed. Source/meaning review confirms the humanize skill defines the referenced checks, while the removed requirements are absent from its required protocol.
