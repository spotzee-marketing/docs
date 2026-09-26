# Documentation validation — 26 September 2026

Status: validated locally; publication held until deployed API contracts and current rate limits are verified.

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

All 139 page hashes and seven rate-limit prose-unit hashes match the current files. Mintlify validation and internal-link checks passed using saved API reference specifications. Both corrected pages rendered in the local preview with no console errors or document overflow; the guide was also checked at mobile width. Publication remains held pending the release gate below.

## Release gate

Publish after deployed behaviour matches both API references and current rate limits are confirmed. Then verify:

- <https://docs.spotzee.com/guides/query-events>
- <https://docs.spotzee.com/guides/campaign-bounce-reporting>
- <https://docs.spotzee.com/main-api/introduction>
- <https://docs.spotzee.com/extended-api/introduction>
