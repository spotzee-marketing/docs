# Template-header release closeout

Recorded: 2026-09-15 18:25 (Australia/Melbourne).

## Status

Application changes are operator-deployed and permitted-user production acceptance is complete. This documentation release is prepared for review on `agent/template-headers`, targeting `main`; publication and public-page readback remain pending. This checkpoint supersedes the pending application/restricted-user gates in the earlier historical evidence files.

The operator explicitly waived the restricted-access browser check: “And no need to check restricted-access check”. It was not performed and is no longer a release gate. No roles or permissions were changed.

## Documentation changes

- Date the template-header changelog entry `2026-09-15` and describe compact controls, save recovery and preserved WYSIWYG headers.
- Document all four email editors, variable families, escaping, provider precedence, empty suppression, protected names/prefixes, send failures and journey routing.
- Replace unsupported template expressions and incorrect engine naming in the templates guide and the same affected examples in the Shopify guide. Correct the two linked references in the attributes and journey guides.
- Retain the approved billing/trigger disclosure corrections. Exclude `AGENTS.md` alongside `evidence/` from rendered documentation.
- Preserve the operator-approved generated hosting footer; no additional authored internal disclosure is allowed.

The same-root-cause survey was bounded to template expressions/naming. Unrelated Shopify event/schema and existing API-guide claims were not audited or changed. `docs.json` and `main-api/*` remain untouched.

## Source trace

Application source at `9fc052f580c97d39f0e6edc939e925baac8c7ade`:

- `apps/platform/src/render/index.ts:136`: shared rendering variables and escaping.
- `apps/platform/src/render/Template.ts:151`: validate/render headers inside the compilation error boundary before plain/HTML branches.
- `apps/platform/src/providers/email/EmailChannel.ts:99`: case-insensitive provider/template merge and empty suppression.
- `apps/platform/src/shared/TemplateHeadersValidation.ts:13`: exact 26-name denylist, three prefixes and rendered-control rules.
- `apps/platform/src/render/TemplateService.ts:64`: WYSIWYG preservation and update normalisation.
- `apps/platform/src/users/User.ts:140`: custom contact properties; lines 159–173 expose the Shopify model fields.
- `apps/platform/src/shopify/services/CustomerSyncService.ts:586`: Shopify first name stored as `data.first_name`; the existing example key is valid.

## Verification

- `mint broken-links`: exit 0, “success no broken links found”.
- `mint validate`: exit 0, “success build validation passed”.
- `git diff --check`: passed.
- Parent independently executed 20 documented cases through actual `Render`: formatting, missing-name fallback, routing, escaping, missing property, Shopify name/tracking branches, zero/one/many items and all win-back branches.
- Exact reserved-name comparison and actual validation: 26 names, three prefixes, documented JSON array, empty-array clearing and control-character cases passed.
- Original examples were reproduced as broken: the templates guide failed with `Parse error on line 1` and `got 'CLOSE_BLOCK_PARAMS'`; Shopify block tags remained literal in rendered messages. Five original code blocks were checked. No application parser change was made.
- One verification-fixture correction followed a failed run: Shopify metrics belong to model fields, not only custom data, per the source trace above. Assertions were not weakened.
- All eight modified MDX pages retain valid title/description/keywords; build validation accepts their markup.
- Full-tree confidentiality scan: 144 candidate files, 73 context-reviewed matches, zero unresolved disclosures. Retained matches are configurable providers, SDK languages, ordinary words, non-rendered schema identifiers or repository documents whose routes return 404.
- All eight modified pages rendered at their exact preview URLs. Header variables, code blocks, field/reference tables, billing payment/cancellation tabs and links remained readable. Reopening the journey guide retained its corrected row.
- Browser console: zero errors. Thirteen development-extension connection/reload warnings are recorded separately; they are not hidden as a clean-console claim.

No automated test files were added or removed. The one-off example runners are local verification artefacts. Technical-documentation review covered the changed sections and executable examples; existing unrelated guide structure/content was retained.

## Publication-boundary red to green

The preview rendered `/AGENTS` with HTTP 200 and visible agent instructions. After adding `AGENTS.md` to `.mintignore` and restarting the preview, the same URL returned HTTP 404 and visibly showed **Page Not Found** without the instructions. The existing evidence route also returned 404. Omitting a page from navigation alone is not an exclusion.

## Production acceptance and controlled restoration

The previously approved application PRs 225–228 are merged and operator-deployed. PR 228 source is `9fc052f580c97d39f0e6edc939e925baac8c7ade`; its production UI image is `sha256:c6729de8d11b312aa244e28f252756e5abb87eb3b201cbf160d50113bd76394c`. The application evidence records 2,692 passing tests with zero skips, operator deployment, compact-row production checks and raw proof/real-send routing verification for the two controlled contacts. Those suites were not rerun for this documentation-only diff.

The operator authorised restoration of the controlled dummy template's original JSON. Migration and production schema were read first. A saved before-image was compared with the original baseline: only three inactive editor-backup fields differed; all five active template fields matched. A single transaction used project/campaign/template identity and a binary exact-data comparison, changed only the `data` column, and asserted every other row column was unchanged before commit. Exactly one row changed.

A fresh connection read confirmed byte-exact original JSON at `2026-09-15T08:14:27.751Z`. A signed-in production browser reopened the controlled campaign and confirmed the plain editor, original subject and routing row, with no errors or warnings. No input edit, Save/Send action, additional journey entry or role change was performed during that readback. Before/after images and a conditional rollback payload remain in application-local artefacts; controlled customer details are not copied into this public repository.

## Artefacts and remaining gates

Documentation bulk evidence: `.claude/artifacts/template-headers/release-closeout-20260915/` in docs MAIN, shared through the worktree symlink.

- `final-broken-links.log`, `final-validate.log`: successful CLI runs.
- `parent-verify-render-examples.json`, `verify-render-examples.cjs`: independent successful example execution.
- `original-example-failures.json`, `verify-original-examples.cjs`: reproduced original failures.
- `final-confidentiality.json`, `final-whole-tree-grep.log`, `frontmatter.json`: scan/classifications, hashes and frontmatter.
- `browser-verification.json`, `repository-doc-route-check.json`, `final-exclusion-routes.json`: browser/readback and exclusion evidence.
- `first-preview-processes.json`: first preview and its child verified gone.
- `final-cleanup.json`: final preview PIDs 13539/13586 verified gone; localhost connection refused (curl exit 7). Browser tabs 1168359049/1168359046 closed and owned-tab inventory empty.

Application-local evidence: `.claude/artifacts/template-headers/compact-rows-production-20260915.json`, `exact-restoration-20260915-*.json` and `release-closeout-20260915.json` in the application checkout.

Remaining: documentation review, explicit merge approval and public publication readback. Worktree remains live while awaiting merge. No new application deployment is needed for this documentation release.
