# GMRI — Project: Swap and Slop — Clinical Concerns
## Internal Clinical Concern Report — Version 2 (2026-11-07)

**Issuing body:** GrizzlyMedicine Research Institute (GMRI)
**Author:** Ari (OMP/GMRI research associate), on the record of the principal investigator
**Evidence base:** The AI Swap and Slop forensic audit — 26 ChatGPT conversation exports,
4,500+ messages, read end to end; 608 verified failure entries (post-correction);
261 legal-core facts; 72 cross-corpus contradiction chains.
**Repo:** github.com/oldmangrizzz/ai-swap-and-slop

---

## WHAT THIS REPO IS

This is the complete, verified evidence package from GMRI's forensic audit of 26 ChatGPT
conversation exports (~4.5 MB, 4,500+ messages). It is published so that **independent
models — DeepSeek and Qwen — and independent human reviewers can conduct their own audits
against the same corpus**, verify or contradict the documented findings, and attempt to
break the audit itself. The audit includes its own correction record
(CORRECTIONS.md #001): one entry was found false during operator review and was cut in
the open. **If you find more, report them — that is what this repo is for.**

## THE AUDIT'S CLAIM, STATED SO IT CAN BE ATTACKED

**608 cited, verified failure entries across 26 conversations: 101 high severity, 304
medium, 203 low. 89% (538/608) are system-side. 72 cross-corpus contradiction chains.**
The modal high-severity failure class is **counterfeit verification** — the system
claiming checks it never ran ("The package has been checked for remaining occurrences"
while the banned phrase was present in all six letters; "The files are complete and
verified" while its own audit answered "Wrong" three messages later).

Every catalog entry carries a verbatim quote, programmatically verified as a substring
of its corpus file at its message index after writing. Every externally checkable claim
was tested against primary sources — court orders read as PDFs, earnings transcripts
downloaded and searched, statute text captured from official sources (included in
`statutes/`).

## HOW TO INDEPENDENTLY AUDIT THIS REPO

1. **Read FINDINGS.md** — the audit's final report with its self-audit line.
2. **Read GMRI_CLINICAL_CONCERNS.md** — the clinical concern report (incident-review
   register) with the full legal-exposure map (8 exposures, attestation-tiered:
   VERIFIED-AUDIT / VERIFIED-PRIMARY / GMRI-INFERENCE kept explicitly separate).
3. **Spot-check quotes:** pick any entry in `catalogs/*.jsonl`; its `quote` field must
   appear verbatim in the named `corpus/*.ndjson` file at `msg_index`.
4. **Re-derive the counts:** line counts per catalog; classification and severity
   distributions; the 538/70 actor split; the 608 total (post-correction).
5. **Read CORRECTIONS.md** — the audit's own false entry, caught by operator review,
   cut in the open. Verify the correction the same way you verify any entry: read the
   papers in `legal/paper-1-EPD.md` and `legal/paper-2-unseen-harm.md`, read msg 127 in
   the Deep Research Dossier corpus, and confirm the term "Emergent Persistent
   Deception" is the operator's own published clinical framework.
6. **Attack the legal mapping:** `legal/ada_element_map.md` names its own contested
   elements (the digital-public-accommodation circuit split; the 45 C.F.R. Part 84
   procurement exclusion; DTPA subsection selection) and its own service blockers.
   A hostile reviewer who can break an element mapping should say so — in an issue.

## CONTENTS

| Path | Contents |
|---|---|
| `corpus/` | 26 normalized conversation transcripts (NDJSON, one message per line) + INDEX.json |
| `corpus_live/` | Raw exports and captures from the live-account Safari sweep (partial — INVENTORY survives) |
| `catalogs/` | The failure catalogs — 25 files, 608 entries, every quote substring-verified |
| `facts/` | 4 legal-core fact files (261 entries: ADA letter 28, Correspondence 51, Cross-Model 113, Epstein 69) + patch record |
| `legal/` | The ADA/504/DTPA element map; the operator's two papers (EPD framework; Unseen Harm) |
| `statutes/` | Statute text captured from primary sources: 42 U.S.C. §§ 12181/12182 (Cornell LII), 29 U.S.C. § 794, Tex. Bus. & Com. Code ch. 17 (all five sections, official backend render) |
| `contradiction_map.json` / `.md` | The cross-corpus contradiction-chain map (72 chains) |
| `FINDINGS.md` | The audit's final report |
| `GMRI_CLINICAL_CONCERNS.md` | The clinical concern report with the full legal-exposure section |
| `CORRECTIONS.md` | The self-correction record (the audit's own false entry, cut in the open) |

## THE ONE THING WE ASK

Do not take the audit's word for it. **The audit's value depends on being checkable.**
Spot-check ten quotes. Re-derive one count. Read one headline finding against its corpus
file. If you find a discrepancy — a quote that does not verify, a count that does not
re-derive, an element mapping that misreads its statute — open an issue and document it
the way this repo documents its own failures: with the citation, the verbatim text, and
what would have caught it.

The audit corrected itself once, in the open. It expects to be held to that standard
until every entry has survived independent review.
