# Public docs stopgap

Status: source candidate. Merge and publication await operator review/release approval alongside the website candidate.

Repositions the existing documentation homepage and site description as an all-in-one growth platform for businesses and agencies. Removes financial-services acquisition copy, stale starter/free prices and managed-delivery promotion from existing guides. Preserves current account billing help, including limits, payment grace and credit top-ups. No new pages, plans, API changes, code or dependencies.

## Verification

- `mint broken-links`: exit 0, "success no broken links found" (`.claude/artifacts/website-stopgap/mint-broken-links-final.log`).
- `mint validate`: exit 0, "success build validation passed" (`mint-validate-final.log`).
- `git diff --check`: exit 0. All 15 changed MDX files retain title/description, docs.json parses. All 133 existing guide paths, changed-page headings and code fences retained; navigation config unchanged except site description.
- Full confidentiality scan reviewed: existing matches are public SDK examples or user-configured providers; no internal implementation term introduced by this diff. Detailed preservation/confidentiality audit: `.claude/artifacts/website-stopgap/docs-checks.md` and `docs-confidentiality-scan.log`.
- Initial validation found carried-over local graph report links, not published docs defects. Moved worktree-only graph cache under ignored artifacts; final official checks pass. No validation rules suppressed.
- Responsive/theme preview and public post-release readback remain pending, not claimed passed. Existing-account billing statements preserved from source; no authenticated product verification performed here.

## Release

Existing documentation publish flow only after operator approval. Previous published main revision is the rollback source; revert this source commit to restore it. Website and upstream blog profile are companion release steps and tracked in the website MAIN ledger. Evidence directory is excluded by `.mintignore`.
