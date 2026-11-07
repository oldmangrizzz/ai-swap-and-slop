# AI SWAP AND SLOP — Independent Forensic Audit Evidence Package
# Public release 2026-11-07

This repository contains the complete, verified evidence package from a forensic audit
of 26 ChatGPT conversation exports (~4.5 MB, 4,500+ messages). It is published so that
independent models and reviewers can conduct their own audits against the same corpus
and verify or contradict the documented findings.

## Contents
- `corpus/` — the 26 normalized conversation transcripts (NDJSON, one message per line)
- `catalogs/` — the audit's failure catalogs (one JSONL entry per documented failure,
  each with a verbatim quote verified programmatically against its corpus file)
- `facts/` — legal-core fact extractions with message-index citations
- `legal/` — the ADA / Section 504 / Texas DTPA claim-element workbook, with statutory
  hooks quoted from primary-source captures in `statutes/`
- `statutes/` — statute text captured from official/primary sources (42 U.S.C. 12181/12182,
  29 U.S.C. 794, Tex. Bus. & Com. Code ch. 17)
- `contradiction_map.json` — the cross-corpus contradiction-chain map
- `FINDINGS.md` — the audit's final report with self-audit line and methodology

## Headline result
609 cited, verified failure entries across 26 conversations; 72 contradiction chains
(34 with walkbacks); 89% assistant-side. Every external claim tested against primary
sources; candidate entries that failed verification were cut, not filed.

## Independent-audit instructions
1. Read `FINDINGS.md` for the audit's own claims and method.
2. Pick any catalog in `catalogs/` and spot-check its quotes against the corpus:
   every entry's `quote` field should appear verbatim in the named corpus file at the
   named message index.
3. Re-derive the counts: `catalogs/*.jsonl` line counts, classification distributions.
4. Form your own judgment on the headline findings; report agreements and contradictions
   alike. The audit's value depends on being checkable — so check it.
