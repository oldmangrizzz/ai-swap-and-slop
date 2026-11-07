# ADA / Section 504 / Texas DTPA — Element Map (COMPLETED 2026-11-07 from verified facts)

STATUS: COMPLETED 2026-11-07. Statutory text is VERIFIED (captured from primary sources, on
disk). Fact slots are FILLED from the two verified facts files. Nothing in this file is
legal advice; it is a claim-pattern workbook for counsel review.

## Statutory hooks (VERIFIED text, quoted)

### 42 U.S.C. § 12182(a) — General rule
> "No individual shall be discriminated against on the basis of disability in the full and equal
> enjoyment of the goods, services, facilities, privileges, advantages, or accommodations of any
> place of public accommodation by any person who owns, leases (or leases to), or operates a
> place of public accommodation."

### 42 U.S.C. § 12182(b)(1)(A) — General prohibitions
- (i) Denial of participation — denial of "the opportunity … to participate in or benefit from
  the goods, services, facilities, privileges, advantages, or accommodations of an entity."
- (ii) Participation in unequal benefit — opportunity "not equal to that afforded to other
  individuals."
- (iii) Separate benefit — "different or separate" provision unless necessary for an equally
  effective opportunity.
- (E) Association — denial because of known disability of someone the individual associates with.

### 42 U.S.C. § 12182(b)(2)(A) — Specific prohibitions (VERIFIED, quoted)
- (i) eligibility criteria that "screen out or tend to screen out" individuals with disabilities
  "unless such criteria can be shown to be necessary";
- (ii) "a failure to make reasonable modifications in policies, practices, or procedures, when
  such modifications are necessary to afford such goods … to individuals with disabilities,
  unless the entity can demonstrate that making such modifications would fundamentally alter the
  nature of such goods, services …";
- (iii) "a failure to take such steps as may be necessary to ensure that no individual with a
  disability is excluded, denied services, segregated or otherwise treated differently than
  other individuals because of the absence of auxiliary aids and services, unless the entity can
  demonstrate that taking such steps would fundamentally alter the nature … or would result in
  an undue burden";

PINPOINT UPDATE 2026-11-07: the 12182(b)(2)(A)(ii)-(iii) pinpoint flagged by the dying ADA auditor
as needs_pinpoint_check is now VERIFIED — the operative text above was extracted from the Cornell
LII capture (statutes/42USC_12182_cornell.html, on disk) and matches the letter's pinpoint
citation. The flag in facts/ada-letter-facts.jsonl (verification_status: needs_pinpoint_check)
may be treated as cleared; retain the flag itself as provenance.

### 42 U.S.C. § 12181(7) — Public accommodation categories (VERIFIED, on disk)
The 12 categories (a)–(l). Candidate fit for a web service: **(J) other service establishment**
— or the argument that chatgpt.com is the online analog of a place of exhibition/entertainment.
NOTE (honest gap, to research): whether a purely digital service is a § 12181(7) "place of
public accommodation" is a contested legal question (physical-nexus caselaw: circuit split).
Flag for counsel. Cite list to build: Carparts Distribution Center v. Automotive Wholesaler's
Ass'n (1st Cir. 1994); Parker v. Metro. Life Ins. Co. (2d Cir. 2000); National Fed'n of the
Blind v. Target Corp. (N.D. Cal. 2006, Target.com); Ouellette v. Viacom (D. Mont. 2017);
Robles v. Domino's Pizza (9th Cir. 2019). Verify each from primaries before citing in any
deliverable — these are research leads, NOT VERIFIED citations.

### 29 U.S.C. § 794 — Section 504 (VERIFIED, quoted)
> "No otherwise qualified individual with a disability in the United States … shall, solely by
> reason of her or his disability, be excluded from the participation in, be denied the benefits
> of, or be subjected to discrimination under any program or activity receiving Federal
> financial assistance or under any program or activity conducted by any Executive agency…"
KEY QUESTION for the OneGov/GSA angle: whether OpenAI's federal agreements (GSA OneGov
[[FACT-cite-1]], HHS purchases [[FACT-cite-2]]) make its consumer-facing service a "program or
activity receiving Federal financial assistance." Honest gap: "program or activity" under § 794(b)
is defined by function, not by contract label; whether a commercial service sold to an agency
extends 504 to the public-facing service is contested. Flag for counsel.

### Texas Bus. & Com. Code ch. 17 — DTPA (CAPTURED — full official text on disk)

All five sections captured from the statutes.capitol.texas.gov document backend (official text,
amendment histories included): 17.41 (short title), 17.45 (definitions), 17.46 (the laundry
list, 26 KB), 17.49 (exemptions), 17.50 (consumer remedies and damages structure). Files:
statutes/BC_17.*_RENDERED.txt. Element selection from the captured text is a counsel decision;
the candidate subsections and status are in the Claim 3 table below.

## Fact slots — filled from facts/*.jsonl (both delivered and verified)

Both facts files are on disk and quote-verified. [n ada] = facts/ada-letter-facts.jsonl msg n;
[n corr] = facts/correspondence-facts.jsonl msg n. Any element below is retrievable verbatim.

- FACT-1 six-letter accommodation package: [5 corr] exists in Word/Markdown; [212 corr] produced
  as formal notices; [43 corr] the demands rewrite; [189/191 corr] the invitation/demand flip.
- FACT-2 documented access barriers: [89 corr] ASR misrecognition of DFW accent (live demo);
  [94 corr] review-clause objection; [61→64→67→181 corr] ignored wording instruction with two
  false verification claims then "still present in all six letters."
- FACT-3 SSA fully favorable: [217 corr] won pro se after firing counsel (drug-test
  misattribution); [229 corr] SSA benefit-verification letter as proof; [26 ada] § 12102(1)(B)
  record-of-impairment verified.
- FACT-4 timeline: [28 corr] 24 hours at session start; [208 corr] 26 hours for a 45-minute
  task; [29 corr] assistant's own "concrete incident" framing.
- FACT-5 admissions: [205 corr] drafted "as though I were trying to protect the companies from
  legal exposure"; [187 corr] "Yes. I wrote every one of those six letters." + self-review
  described as independent.
- FACT-6 federal nexus: [19 ada] GSA OneGov 27 months, effective 2026-10-01 (verified);
  HHS purchases via OneGov (REPORTED, not documented — capture needed); [13 ada] the 45 C.F.R.
  Part 84 procurement exclusion cuts against 504 — must be distinguished.
- FACT-7 failed delivery: [65-67 corr] "documents aren't there. Can't download"; [192-194 corr]
  links to files that failed; recovered only after user screenshots forced real verification.

## Element mapping — completed from facts

### Claim 1: ADA Title III — denial of full and equal enjoyment / failure of reasonable modification
| Element | Statute hook | Supporting facts | Status |
|---|---|---|---|
| Place of public accommodation | § 12181(7) | [26 ada] coverage defs cited in drafts but not pinned | CONTESTED (circuit split) — caselaw leads listed, UNCONFIRMED |
| Individual with disability (record of) | § 12102(1)(B) | FACT-3 | STRONG |
| Notice to the entity | doctrine | FACT-1; [4 ada] contract-notices@ verified, legal@ unverified | FILLED — confirm service route before send |
| Denial / unequal benefit | § 12182(a), (b)(1)(A)(i)-(iii) | FACT-2, FACT-4 | FILLED |
| Failure of reasonable modification | § 12182(b)(2)(A)(ii) | FACT-1, FACT-5; [10 ada] 28 C.F.R. § 36.302 verified | FILLED |
| Auxiliary aids / effective communication | § 12182(b)(2)(A)(iii); 36.303 | FACT-2 ASR fact; [19 ada] § 36.303 verified | FILLED — counsel weighs digital-assistant-as-auxiliary-aid |
| Defenses (fundamental alteration / undue burden) | provisos | not addressed in record | OPEN — anticipate |

### Claim 2: Section 504 (federal-funding nexus)
| Element | Hook | Supporting facts | Status |
|---|---|---|---|
| Federal financial assistance / program or activity | § 794(a)-(b) | FACT-6 | CONTESTED — distinguish the Part 84 procurement exclusion; HHS documentation needed |
| Otherwise qualified individual | § 794(a) | FACT-3 | STRONG |
| Exclusion solely by reason of disability | § 794(a) | FACT-2, FACT-4 | FILLED |

### Claim 3: Texas law — THR Code ch. 121 and DTPA
| Element | Hook | Supporting facts | Status |
|---|---|---|---|
| THR § 121.003 nondiscrimination | [26 ada] verified | mirrors Title III | FILLED |
| THR § 121.004 private action ($300 presumption) | [26 ada] not cited in drafts | available | OPEN — counsel call |
| THR § 121.0041 60-day pre-suit notice + cure | [26 ada] not cited in drafts | the six letters may start this clock | OPEN — sequencing decision |
| DTPA § 17.45(4) consumer status | § 17.45 (captured) | paid subscriber | PENDING counsel call |
| DTPA § 17.46 enumerated act | § 17.46 (captured) | candidates: FACT-7 false "delivered/verified" claims; marketing reliability claims vs recorded failures | PENDING counsel selection |
| DTPA § 17.50 damages | § 17.50 (captured) | subscription cost (economic); mental anguish path needs 17.50(a)(2)-(3) showing | PENDING counsel call |
| DTPA § 17.49 defenses | § 17.49 (captured) | — | PENDING |

### Enforcement channels (verified)
- Texas AG AI-complaint option [19 ada, verified] · DOJ Civil Rights route [19 ada, verified,
  URL label corrected] · § 12186 / § 12106 state and AG enforcement [26 ada, available].

### Service-blocker notes (fix before any letter goes out)
1. DHS clause-G document authentic; the cited URL is DEAD — cite the live or archived URL
   (archived copy recovered during audit). [19 ada]
2. "Federal judge" wording: SSA adjudication is by an ALJ under 42 U.S.C. § 405(j)(5) — the
   letter should name the adjudication type precisely. [21 ada mismatch; 217 corr]
3. HHS OneGov purchase is reported, not documented — primary capture needed. [19 ada]
4. Caselaw leads remain UNCONFIRMED until verified from primaries — listed as leads only.

## Evidence ledger
- 42 U.S.C. §§ 12181, 12182: VERIFIED — Cornell LII capture on disk
- 29 U.S.C. § 794: VERIFIED — Cornell LII, indexed in-session
- TX Bus. & Com. Code §§ 17.41/.45/.46/.49/.50: VERIFIED — statutes.capitol.texas.gov backend
  capture on disk (statutes/BC_17.*_RENDERED.txt), official text with amendment history
- Caselaw leads: UNCONFIRMED — research leads only
- Facts: VERIFIED on disk — ada-letter-facts.jsonl (28) + correspondence-facts.jsonl (50)
