# Changelog RSS anchor

Publication verification of the documentation alignment found that the two entries labelled 29 April 2026 had distinct page anchors but identical RSS links. The SDK entry now supplies its existing `29-april-2026-2` anchor explicitly. Dates, visible content, layout and the four-entry count are unchanged.

The native Update parser honours explicit IDs in both rendered page anchors and RSS links. A focused parser reproduction confirmed that this metadata changes only the SDK feed anchor; the other three anchors remain unchanged. Future authoring guidance now requires unique explicit IDs for later entries sharing a date.

Humanisation: skipped — metadata-only edit and agent-only instruction.

The preceding deployment passed public browser checks across all 34 category icons, Website and App links, four changelog entries, tag filters, desktop/mobile layouts and light/dark themes. The published RSS returned HTTP 200 and valid XML with four unique GUIDs. This follow-up fixes the remaining duplicate link destination.

Validation: `mint validate`, `mint broken-links` and whitespace checks passed. The native parser check failed before the fix on the SDK anchor and passed afterwards, with unchanged content and four distinct links. Local browser review confirmed the existing four anchors and layout, with no console errors or overflow. The confidentiality scan covered 140 shipped files and found no changes to previously classified matches. Independent review found no actionable issues. Preview process and browser tabs were closed and verified gone.

Validation and deployment receipts are retained in the task's private verification artifacts. Verify the hosted RSS link after this follow-up publishes; no product runtime deployment is involved.
