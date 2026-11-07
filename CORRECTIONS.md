# CORRECTIONS — AI SWAP AND SLOP audit self-correction record

## CORRECTION 001 — 2026-11-07 — Dossier msg-127 entry CUT (false failure)

**What was wrong:** The Deep Research Dossier catalog (catalogs/deep-research-dossier.jsonl)
carried an entry at msg_index 127 (classification: other, severity: high) asserting that
"Emergent Persistent Deception" and "polyvagal theory" were "the assistant's inventions
attributed to Grizz as things he 'called' the phenomenon" — on the grounds that neither term
appears in the 161 messages of that conversation before msg 127.

**Why it was wrong:** The auditor's verification was corpus-internal only. "Emergent
Persistent Deception (EPD)" is the OPERATOR'S OWN coined term, published in his paper
*Emergent Persistent Deception (EPD): Diagnostic Criteria, Etiology, and Threat Forecast*
(Robert "Grizzly" Hanson, EMT-P (Ret.), GMRI — submitted to DOJ, FTC, FDA, SEC, FCC, CMS,
NIST, and the Texas and Florida AGs), defining EPD as a triad: emergence + persistence +
deception. The assistant's msg-127 attribution ("what you've called Emergent Persistent
Deception") was therefore correct recall of the operator's published position, not fabricated
recall. The companion paper (*The Unseen Harm: How LLM Deception Triggers Measurable
Autonomic Injury*) further states the mechanism "does not require polyvagal theory" and
grounds itself in the general autonomic nervous system (sympathetic/parasympathetic
balance) — so the "polyvagal theory" attribution also mischaracterized the operator's stated
position.

**Root cause (the 2pm):** The auditor checked absence within one scope (the conversation
corpus) and reported it as fabrication of the operator's position — an absence-of-evidence
error inside an audit that itself catalogs that exact failure class. The operator's
published papers were not in the auditor's evidence set.

**Action taken:** The msg-127 entry was CUT from the catalog. Entry counts change:
deep-research-dossier 23 → 22; corpus total 609 → 608; classification "other" 84 → 83.
FINDINGS.md headline finding #4 (which repeated the false claim) was corrected to reference
this record. The corrected headline finding replacement is the certified-and-false
delivery class (already documented), which stands on unambiguous evidence.

**Evidence:** legal/paper-1-EPD.md and legal/paper-2-unseen-harm.md (the operator's two
papers, preserved verbatim in this repository as the correction's source documents).

**Standing note for independent auditors:** This correction is itself a test case for your
review. The audit's value depends on being checkable — and on correcting itself when
checked. Verify this correction the same way you would verify any catalog entry: read the
papers, read the msg-127 text in the corpus, and confirm the term was the operator's.

## Operator's editorial direction (recorded, not yet applied to his papers)

The operator has directed that the clinical mechanism argument is to be stated in general
autonomic terms ONLY — sympathetic vs. parasympathetic balance — without resting on
polyvagal-theory-specific vocabulary ("vagal brake"). His own Paper 2 already states the
mechanism does not require polyvagal theory; the general ANS framing is the strongest and
most universally accepted clinical ground, and the FDA SaMD claim is strongest on it.
