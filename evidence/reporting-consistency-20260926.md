# Documentation validation — 26 September 2026

Status: published and browser-verified on 27 September 2026. The audit and release-gate sections below record the pre-publication candidate.

## Coverage

The audit covers 137 existing pages, two new reporting guides and both generated API references. Existing-page dispositions are 116 correct, 12 rewrite and nine keep. The public coverage record is `automation/reporting-release-coverage.json`; detailed source evidence is retained privately.

The new Query events and Campaign bounce reporting guides cover the four existing reporting calls, all 12 category identifiers and display labels, classification availability, unknown evidence, severity and finality, historical data and freshness. Guides, Main API and Extended API remain separate tabs. No existing page URL moved.

## Checks

- Mintlify validation and internal-link checks passed.
- All 139 pages passed frontmatter, code-fence and navigation checks; all 15 JSON examples parsed.
- All 139 pages received rendered review. The final three SDK corrections returned HTTP 200, with no horizontal overflow or console errors in the desktop preview.
- External links: 95 of 96 succeeded. The animal-generator destination timed out and then returned HTTP 403, so its availability remains inconclusive.
- All 587 changed prose units are finalised: 410 retained after manual preservation review, 54 short manual units and 123 technical-reference units. No blocked or unmatched units remain. Retention follows explicit approval and does not claim that every detector score met its threshold.

The public hash and disposition record is `automation/reporting-humanisation-ledger.json`. Detailed source citations, provider output and review records remain private. These files are excluded from the website but remain public in this repository.

## Rate-limit correction verification — 27 September 2026

The Rate limits guide and Extended API introduction now document the current per-IP limits and block durations. The guide clarifies that `/api/client/*` requests count towards both overlapping rules and that a suggested 60-second backoff cap applies only when `Retry-After` is absent.

All 139 page hashes and seven rate-limit prose-unit hashes match the current files. Mintlify validation and internal-link checks passed using saved post-deployment API reference specifications. Both corrected pages rendered in the local preview with no console errors or document overflow; the guide was also checked at mobile width.

## Deployed contract verification — 27 September 2026

Both live API specifications match the reviewed contracts. Current rate-limit configuration and the configured error body were confirmed. Read-only reporting checks returned a classification with `category: unknown` and `reason: unmatched`, consistent with the documented fallback. Campaign recipient pagination returned non-overlapping first and second pages.

The sampled event day contained one result, so live event pagination was not exercised. Local pagination contract tests remain the evidence for that case. These release checks do not claim that every guide workflow was exercised in production, or that production query latency was measured.

## Release gate (pre-publication record)

The deployed contract and rate-limit gates are satisfied. After documentation review and publication, verify:

- <https://docs.spotzee.com/guides/query-events>
- <https://docs.spotzee.com/guides/campaign-bounce-reporting>
- <https://docs.spotzee.com/main-api/introduction>
- <https://docs.spotzee.com/extended-api/introduction>

## Publication closeout — 27 September 2026

Documentation merge `67d06c86` completed, and the Mintlify deployment check succeeded. Browser navigation from `docs.spotzee.com` reached the canonical `spotzee.com/docs` pages below; each rendered its title and expected release content:

| Canonical page | Browser result |
| --- | --- |
| <https://spotzee.com/docs/guides/query-events> | Query events and classification guidance rendered |
| <https://spotzee.com/docs/guides/campaign-bounce-reporting> | Bounce categories and unclassified guidance rendered |
| <https://spotzee.com/docs/main-api/introduction> | Main API and Events navigation rendered |
| <https://spotzee.com/docs/extended-api/introduction> | Extended API and the corrected limit rendered |
| <https://spotzee.com/docs/guides/api-rate-limits> | Corrected limits, block duration and retry guidance rendered |

Automated HTTP checks to the requested `docs.spotzee.com` URLs returned `403`; normal browser navigation rendered all five pages. Four earlier pages whose saved review lacked individual current-hash render rows—Authentication, Billing and credits, Core concepts, and CRM—were rechecked in a local preview. Each returned HTTP 200 and rendered with no console errors, broken images or document overflow.

The Billing and credits guide's user-limit and per-call wording was checked against the billing source, then rendered at its final file hash in a local preview. Mintlify validation and broken-link checks passed; the rendered page showed neither the superseded seat wording nor console errors, broken images or document overflow.

A later bounded event-pagination check returned two disjoint pages of two events each, with payloads omitted and classification not requested. It closes the earlier sampled-day pagination gap without claiming that every guide workflow was exercised live. Performance evidence is local only; no production p95 is claimed. A current migration-state check cannot establish the historical deployment-step log. The animal-generator external destination remains inconclusive after a timeout and a later `403`.
