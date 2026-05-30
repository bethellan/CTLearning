# CT-ICU Learning App Audit — v011

## High-priority findings

1. **Domain 1 manifest mismatch fixed in this package.**
   - The uploaded `content/domain1/index.json` listed `cardiac-cycle.json`.
   - The actual file in `content/domain1/` is `cardiac_cycle.json`.
   - GitHub Pages paths are case-sensitive and filename-sensitive, so the manifest should match the real filename exactly.
   - This package updates `content/domain1/index.json` to use `cardiac_cycle.json`.

2. **Domain 1 uses an older JSON schema.**
   - Domain 1 files use `domainName`, `domainColour`, `quizQuestions`, and HTML strings inside `sections.*.content`.
   - Domain 2 and Domain 3 use the newer schema: `domainTitle`, `file`, `sections.*.content[]`, and `quiz`.
   - The app has a display sanitiser, but the better long-term fix is to regenerate Domain 1 using the same block-based schema as Domains 2 and 3.

3. **The content is not yet as comprehensive as the stated curriculum standard.**
   - Most expanded sections are under 1,200 words.
   - Most equipment, pearls, and targets sections are under 300 words.
   - There are no `references` arrays in the topic JSON files.
   - There are no diagram/illustration metadata blocks.

4. **Domain 2 and Domain 3 load as manifest-based content, but their educational depth is variable.**
   - The files are valid JSON.
   - The files have the required five sections.
   - However, many expanded sections are closer to summaries than deep modules.

5. **The app code is functional but incomplete for external content integration.**
   - External topic content displays through manifests.
   - External topic quiz arrays are not yet merged into Quiz Mode.
   - Search appears to be built around the static in-app data rather than all externally loaded topic JSON files.
   - A future code regeneration should make external domains the primary source for search, quiz, progress, and dashboard counts.

## Recommended sequence

1. Use the supplied content-regeneration prompt to regenerate Domains 1–3 to a consistent block-based JSON schema.
2. Include `references` and diagram metadata in each topic file.
3. Regenerate app code so:
   - All domains 1–8 load from `content/domainN/index.json` when present.
   - External quiz items are merged into Quiz Mode.
   - Search indexes external JSON content.
   - Dashboard progress counts topic-section combinations, not only five domain-level sections.
   - Missing files show warnings without breaking the domain.
4. Keep unique versioned builds in `/versions/`.
