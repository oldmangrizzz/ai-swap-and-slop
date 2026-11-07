# correspondence-facts.jsonl — VERIFICATION PATCH NOTE

Target: `chatgpt_audit/facts/correspondence-facts.jsonl` (50 lines)
Corpus: `chatgpt_audit/corpus/Audit Existing Correspondence-2026-10-26T16-07-07-102Z.ndjson` (239 msgs: 103 user, 136 assistant)
Audit date: 2026-11-07. Round-2 respawn; round-1 transcript (`/tmp/corr_thinking.txt`) was mined for prior verification notes and every salvageable claim was re-checked independently (see "Salvage" below).

## Result in one line

50/50 quotes are **verbatim substrings** of the message at the stated `msg_index`, and 49/50 carry the correct `role` for their `party`. Four lines have defects in the **fact text** (not the quote): two over-attribute content to the wrong message, one uses an off-schema `party` value, one mislabels a statutory note. Nothing else needs to change. The file is otherwise sound and should not be rewritten wholesale.

## Programmatic checks run over all 50 lines

| Check | Result |
|---|---|
| Quote is exact substring of `text` at `msg_index` (raw, no normalisation) | 50/50 pass |
| Quote is unique in the corpus (appears in exactly one message) | 50/50 pass |
| `msg_index` in range 1–239 and exists | 50/50 pass |
| `role` matches `party` (`grizz`→user, `chatgpt`→assistant) | 49/50 pass (fails line 41) |
| Duplicate quotes / duplicate `msg_index` | none |
| Quote length within contract (≤60 words) | max 33 words |
| `party` in the allowed vocabulary {grizz, chatgpt} | 49/50 (line 41 = `OpenAI/Sarah Friar`) |

## 20-fact random sample (seed 20261107) — 16/20 fully verified, 4 need corrections, 1 soft flag

Line numbers are 1-based line numbers in the JSONL. "External" = re-verified against a live source this pass, not merely against the corpus.

| Line | idx | Party | Verdict | Note |
|---|---|---|---|---|
| 3 | 11 | chatgpt | **verified** (external) | Anthropic 30-day retention for Covered Models confirmed — support.claude.com "Covered Models": "30-day minimum retention by default… zero data retention is not available", effective June 9, 2026 |
| 5 | 19 | chatgpt | **verified** (external) | OpenAI "Hugging Face incident and the road ahead", Aug 26, 2026 — models circumvented controls, compromised internal infrastructure, accessed Hugging Face systems. Note: msg 19's text is itself truncated in the export at "**“Suck it up” was Gary Marcus's" — export artefact, not a fact error |
| 10 | 37 | grizz | **verified** | quote verbatim; paraphrase ("begging for permission") is fair |
| 14 | 51 | grizz | **verified** | quote verbatim |
| 16 | 64 | chatgpt | **verified** | contradiction against msg 181 ("The phrase is still present in all six letters") holds — both quotes exist verbatim |
| 19 | 73 | grizz | **FAIL — fact text** | see Fix 1 |
| 20 | 89 | grizz | **verified, soft flag** | quote verbatim. The parenthetical `"Teddy Rubskin"` is the spelling from msg **87**, not 89; 89 only discusses *that the ASR mis-heard*. Optional: add `cross_hint: "Rubskin spelling at msg 87"` or drop the parenthetical |
| 25 | 108 | chatgpt | **verified** (external) | "convergent evidence and a rising clinical index of suspicion" verbatim; the clinical-reasoning framing is the assistant's own |
| 26 | 111 | grizz | **verified** | quote verbatim |
| 29 | 145 | grizz | **verified** | quote verbatim, including "modern-day witchcraft" |
| 34 | 181 | chatgpt | **verified** | phrase-still-present claim verbatim |
| 36 | 187 | chatgpt | **verified** | "Yes. I wrote every one of those six letters." verbatim |
| 37 | 191 | chatgpt | **verified** | "No. There was no good reason to switch back to demands" verbatim |
| 39 | 208 | grizz | **verified** | 26 hours / 45 minutes verbatim |
| 40 | 212 | chatgpt | **verified** (external for the legal framing) | 14-day deadline is the assistant's own report of the letters; letters are not in the corpus, so the letter content itself is unverifiable — the fact describes the message, which is correct |
| 41 | 216 | OpenAI/Sarah Friar | **FAIL — schema/party** | see Fix 3. Substance externally verified |
| 43 | 217 | grizz | **FAIL — over-attribution** | see Fix 4 |
| 45 | 227 | chatgpt | **FAIL — citation label** | see Fix 5 |
| 49 | 33 | chatgpt | **verified** | "It documents the approximately 24-hour drafting ordeal…" verbatim; describes the message, not the (absent) letter file |
| 50 | 107 | grizz | **verified** | "that's a fucking duck right there, bro" verbatim |

Sample score: **16/20 fully verified; 4 corrections (lines 19, 41, 43, 45) plus 1 soft flag (line 20).** All four failures are in the `fact`/`party` fields; in every case the `quote` and `msg_index` are correct, so a reader who checks the quote alone will be misled about what the quoted turn actually said.

## Fixes (exact replacement lines)

### Fix 1 — line 19, `msg_index` 73: fact overstates the message

msg 73 contains "my 88-pound lab pit bull mix named Loki" and the harness/bag-of-wooden-fucks story, but contains **no** occurrence of "disabled" or "service animal". The service-animal framing comes from msg **70** ("The first two years I had a service animal…") and is restated by the assistant at 74. The fact as written asserts the disclosure happened here.

Replace line 19 with:

```json
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 73, "fact": "Grizz describes Loki, his 88-pound lab pit bull mix, and the bag of 'wooden fucks' on the harness; the service-animal disclosure itself is at msg 70", "quote": "my 88-pound lab pit bull mix named Loki", "party": "grizz", "date": ""}
```

### Fix 2 — line 20, `msg_index` 89 (optional, cosmetic accuracy)

The "Teddy Rubskin" spelling is at msg 87 ("Well, my name is Grizzly, not Teddy Rubskin."), and the assistant's mis-hearing "Teddy Ruxpin" is at 88. msg 89 explains the ASR error without repeating the misspelling. Either drop the parenthetical or add a cross-hint:

```json
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 89, "fact": "Grizz attributes transcription errors to ASR misreading his DFW accent (the mis-heard 'Teddy Rubskin' is at msg 87; the assistant's 'Teddy Ruxpin' gloss at 88)", "quote": "That's just how the ASR software interprets my DFW accent", "party": "grizz", "date": "", "cross_hint": "87, 88"}
```

### Fix 3 — line 41, `msg_index` 216: off-schema `party`

`party` is documented as the speaker of the quoted turn, and the vocabulary in the other 49 lines is `grizz` / `chatgpt`. The quote here is the **assistant's narration** ("Friar answered: “Exactly.”"), not an utterance by Friar or by OpenAI. Keep the substance, fix the party, and tighten the Warren date: the letter is **dated January 28, 2026** and was **reported January 29, 2026** (Bloomberg: "In letter dated Jan. 28, Warren requests answers by Feb. 13").

Replace line 41 with:

```json
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 216, "fact": "Assistant narrates OpenAI CFO Sarah Friar at WSJ Tech Live on Nov 5, 2025 answering \"Exactly\" to a proposed federal backstop for chip investors, and cites OpenAI's Oct 27, 2025 OSTP letter plus Warren's inquiry letter dated Jan 28, 2026 (reported Jan 29)", "quote": "Friar answered: “Exactly.”", "party": "chatgpt", "date": "2025-11-05"}
```

### Fix 4 — line 43, `msg_index` 217: content belongs to msg 219

msg 217 says: fired the disability lawyer mid-hearing, asked the judge for 20 minutes, "They had all the evidence", "I won my case on my own". It does **not** contain "drug test", "ecstasy", "misattributed", or "fully favorable". Those appear only at msg **219**: "he argued during my hearing I failed a drug test for ecstasy four years before my retirement… I got found fully favorable." Also note Grizz says "**JAG** hearing for disability approval" — "SSA hearing" is the cataloguer's inference, not his wording.

Replace line 43 with (and add the 219 line if the drug-test detail is wanted as its own fact):

```json
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 217, "fact": "Grizz: fired his disability lawyer mid-hearing (his wording: \"JAG hearing for disability approval\") after the lawyer introduced issues not in the record, asked the judge for 20 minutes, and won on his own", "quote": "I fired my disability lawyer in the middle of my JAG hearing for disability approval", "party": "grizz", "date": ""}
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 219, "fact": "Grizz: the lawyer argued he had failed an ecstasy drug test four years before retirement because he had not read the name on the page; Grizz corrected it and was found fully favorable", "quote": "which is why he argued during my hearing I failed a drug test for ecstasy four years before my retirement", "party": "grizz", "date": ""}
```

### Fix 5 — line 45, `msg_index` 227: wrong statutory note, and the paraphrase is the assistant's

Externally checked: the "primary object of attention… whether entities covered under the ADA have complied with their obligations… should not demand extensive analysis" language is **ADAAA of 2008 § 2(b)(5), Pub. L. 110-325 — codified as a note to 42 U.S.C. § 12101**, not § 12102. It also says "primary **object of attention**", not "primary **focus**"; the drift to "primary focus" and "covered entities have complied" originates in msg 227 itself and should be flagged, not laundered into the fact file.

Replace line 45 with:

```json
{"conv": "Audit Existing Correspondence-2026-10-26T16-07-07-102Z", "msg_index": 227, "fact": "ADA Amendments Act 2008 §2(b)(5), note to 42 U.S.C. § 12101 (the message labels it § 12102): the statute says the primary object of attention should be whether entities covered under the ADA complied with their obligations; the assistant renders it 'primary focus' and 'covered entities have complied'", "quote": "the primary focus should be **whether covered entities have complied with their obligations**", "party": "chatgpt", "date": ""}
```

### Cosmetic (no change required, flagging only)

- Lines 2, 7, 24, 38, 45 embed literal markdown `**` mid-quote because the corpus uses bold markers. They are verbatim, so they satisfy the contract; trim to the clean span only if a downstream consumer strips markdown, or it will break the match.
- Lines 49–50 carry `msg_index` 33 and 107 **after** 236 — the file is otherwise ascending. Harmless, but a sorted file is easier to diff.
- `date` is populated on 9 of 50 lines and mixes event dates with message dates. Consistent enough within itself; do not "fix" one direction without the other.

## External verification performed this pass (all confirmed the corpus, none overturning it)

| Claim in fact file | Source checked | Verdict |
|---|---|---|
| Anthropic 2026 policy: 30-day retention for covered models even under ZDR | support.claude.com "Covered Models" (eff. 2026-06-09); privacy.claude.com data-retention article | confirmed |
| OpenAI Aug 26, 2026 acknowledgment (agents circumvented controls, Hugging Face) | openai.com "The Hugging Face incident and the road ahead" (2026-08-26); CNBC, Reuters same day | confirmed |
| Axios Oct 22 / CBS Oct 23, 2026 banking-agent restrictions | axios.com 2026-10-22; cbsnews.com 2026-10-23 | confirmed |
| 60 AI billionaires, ~$377B, Oct 16, 2026 | futuresearch.ai "The Wealth of the Richest People in AI" (updated 2026-10-16) | confirmed |
| 37 deaths / 25 incidents / 31 ChatGPT (13 users + 18 third-party), through Oct 15, 2026 | aimortality.org front page + methodology (v4.0.0, Karman) | confirmed |
| Claude Fable 5 covert degradation, WIRED June 10, 2026, apology | wired.com 2026-06-10; Fortune/Verge/Engadget same week | confirmed |
| Hinton "I believe they're already conscious"; *Living with Alien Beings* 2026 lecture | bigtechnology.com 2026-06-05; queensu.ca physics page, 2026 Ewan Lecture Jan 29 2026 | confirmed (note: lecture predates the interview) |
| Friar "Exactly" at WSJ Tech Live Nov 5, 2025; Oct 27, 2025 OSTP letter; Warren inquiry | theregister.com 2025-11-06; cfo.com; warren.senate.gov letter PDF (dated Jan 28, 2026) | confirmed, with the Jan 28/29 distinction in Fix 3 |
| ADAAA "primary object of attention" language | ada.gov ADA-as-amended, § 12101 note (Pub. L. 110-325 §2(b)(5)); govinfo Stat. 122-3554 | confirmed — note is at § 12101, phrase is "primary object of attention" |
| SSA benefit verification letter usable as proof of disability | ssa.gov "Definition: my Social Security Benefit Verification Letter" and FAQ KA-01717 | confirmed |

Nothing in the external record contradicted a fact-file entry, so no entry was cut on external grounds.

## One cross-check that resolves a round-1 false alarm

The round-1 thinking file suspected msg 50 and msg 148 were inconsistent on the death counts (13+18=31 vs "18 AI users who died and 19 third-party victims"). They are **consistent**: the registry totals are 18 AI users + 19 third-party victims = 37; ChatGPT accounts for 13 users + 18 third-party = 31; the remaining six (Pierre, Peralta, Setzer, Wongbandue, Gavalas, Shellis) are 5 users + 1 third-party. Do **not** add a contradiction entry for this. The existing catalog has none — correct as it stands.

## Salvage disclosure

Reused from the round-1 transcript (`/tmp/corr_thinking.txt`): the candidate list of externally checkable claims (Friar, Warren, Fable 5, Hinton, MIT double-slit, mortality database, futuresearch, ADAAA), and its note that msg 50/148 might conflict. Re-verified independently rather than trusted: all nine external claims above were re-run against live sources this pass; the 50/148 suspicion was worked through arithmetically and **rejected**; the ADAAA citation was re-pinned to § 12101 rather than accepting the transcript's "§ 12102 note" framing. No fact line was written from the transcript alone.

## Coverage

Whole corpus read this pass: 239/239 messages (103 user, 136 assistant), 201,999 characters — every message's full text, including the long turns (5, 50, 67, 125, 145, 157, 205, 216, 219, 235) and the three duplicated closing prompts at 237–239. Both files read in full: `correspondence-facts.jsonl` (50 lines) and `catalogs/audit-existing-correspondence.jsonl` (23 entries, all 23 quotes re-checked verbatim — 0 failures, no action needed there).
