# Template header documentation publication clearance

Recorded: 2026-09-15 14:47 (Australia/Melbourne).

## Status

Prepared locally on `agent/template-headers`; not pushed, reviewed, merged or published. This supplement preserves the earlier evidence as historical and supersedes its unresolved generated-footer gate. The release entry remains **Unreleased** while the application parent completes the remaining production editor and restricted-user acceptance.

## Approved exception

The operator explicitly approved retaining the existing generated **Powered by mintlify** footer, after its bottom-right location on the public changelog was shown. The approval is a narrow exception to the repository's confidentiality rule for this existing hosting attribution only; additional authored vendor disclosures remain prohibited. No general rules, hosting configuration or footer content were changed.

The eight approved authored disclosure removals and `.mintignore` exclusion of `evidence/` remain intact. Their implementation and observed public-route red → green check are recorded in [the disclosure follow-up](template-headers-disclosures-20260915.md).

## Application deployment checkpoint

The application parent reports the operator-deployed UI correction from PR 226 at source `425e866c0f16ee04e2a137730b181325dfc4d221`, running image digest `sha256:e8ae78693a40e78a98b8441670ebb113f6313672624c06dd40737483e43d41fc`. The parent verified the repaired wizard save barrier in production and restored CFC template 390 exactly. The operator's deployment record is in the application checkout at `.claude/artifacts/template-headers/deploy-ui-20260915-141603/`.

These application checks belong to the parent acceptance run, not this documentation pass. Full editor and restricted-user acceptance remain pending at this checkpoint. This pass performed no production interaction, email send, build or deployment.

## Fresh validation

- `mint broken-links`: exit 0, no broken links.
- `mint validate`: exit 0, build validation passed.
- `git diff --check`: passed.
- Expanded confidentiality scan: 142 shipped-candidate MDX, JSON, CSS and SVG files; zero unresolved internal disclosure candidates. The 63 retained matches comprise 36 customer-provider references or diagnostic examples, 22 public SDK language labels, four ordinary verbs and one non-rendered schema identifier.
- All four edited MDX pages still have title, description and keywords. Their bytes match the previously rendered and validated commit `f464829`; no shipped page changed during this clearance pass, so no new browser run was needed. Prior rendered-page checks and their recorded development warnings remain in the disclosure evidence.
- The `evidence/` exclusion remains present in `.mintignore`. Prior actual-route verification showed the evidence route changing from a rendered 200 response to a 404 after exclusion.

No automated tests were added or removed. No documentation defect beyond the approved scope was changed.

## Remaining release steps

The generated-footer confidentiality blocker is resolved by explicit operator approval. Before publication, the parent must finish the remaining application acceptance, replace **Unreleased** with the verified release date, review and commit the final documentation diff, then complete PR review and authorised merge. A successful public-page readback is still required after publication; local preparation is not deployment.

## Evidence and cleanup

Fresh artefacts: `.claude/artifacts/template-headers/footer-clearance-20260915/` in docs MAIN, shared through the worktree symlink.

- `broken-links.log`, `validate.log`: successful CLI validation output.
- `confidentiality.json`, `whole-tree-grep.log`: whole-tree candidates, contextual classifications and source hashes.
- `source-review.json`: frontmatter, byte equality with previously rendered pages and evidence-exclusion check.
- `pr-body.md`: draft PR description for parent review; not submitted.

Torn down: validation sessions `40986` and `9145` both exited 0. No preview process, container or browser tab was created. Worktree retained for parent review. No push, PR, merge or publication was performed.
