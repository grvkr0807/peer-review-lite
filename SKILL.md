---
name: peer-review-lite
description: Fast, single-pass peer-review assessment report for any scientific manuscript, journal-agnostic. Lightweight alternative to the full peer-review skill: no scripts, templates, intake forms or lint step.
license: MIT
metadata:
  version: "1.0"
  skill-author: Gaurav Kumar
  derived-from: "peer-review v2.4 by K-Dense Inc. (Scientific Agent Skills, MIT)"
---

# Peer Review (Lite)

Produce a rigorous, fair, actionable peer-review assessment of a manuscript, preprint, or proposal in ONE pass. Journal-agnostic. Output is a working draft for an accountable human reviewer.

## Efficiency rules

- Read the manuscript and supplements once, fully. Do not re-read sections unless checking a specific claim.
- Do not run scripts, create JSON/CSV forms, fill templates, or run a lint step.
- Do not search the web or external services with manuscript text.
- Ask at most ONE question, and only if authorization is unclear (see below). Otherwise proceed.
- Write the report directly in the final structure below. No intermediate scaffolds.

## 1. Confidentiality check (once, brief)

Before reading unpublished material, confirm in one short message (skip anything the user already stated):

- The user is authorized to review it (editor, publisher, or owner invitation, or it is their own draft).
- The venue's AI/tool policy permits assistant-based review. Note that text read here is processed by a hosted assistant.

If authorization is unclear, do not read or quote the manuscript until it is resolved. Never send manuscript text to outside services, never reuse it for any other purpose, and never fabricate content, citations, analyses, or reproductions.

## 2. Read and orient (internal, ~1 short paragraph in the report)

Identify neutrally: research question, system/population, design and unit of analysis, intervention/method, comparator/baseline, outcomes/metrics, and the principal claims. Note materials not provided as "not reported" or "not available for review". Do not infer missing content.

## 3. Assess (apply in this order)

**Claim-evidence alignment.** For each central claim (causal, mechanistic, predictive, diagnostic, safety, generalization): does the cited result support it in direction, magnitude, population, outcome, timepoint, and uncertainty? Note alternative explanations and overreach in the abstract, discussion, and title.

**Methods and statistics.** Check question/estimand; design and unit of inference; sampling and controls; sample-size or precision rationale; exclusions, attrition, missing data; analysis fit to design and assumptions; multiplicity and prespecification; effect sizes with uncertainty and denominators; causal language; generalizability. For "no effect", "equivalent", or "no difference" claims, check that the interval excludes scientifically important effects and that any equivalence margin was stated; a non-significant test alone is not evidence of equivalence. Request narrower claims rather than post hoc power calculations.

**Reproducibility and transparency.** Protocol/analysis-plan consistency, data provenance and exclusions, software and model versions, parameters and seeds, code and data availability (or justified restriction). Never state that results were reproduced unless inputs were actually run with documented commands.

**Ethics and integrity.** Approvals, consent, privacy, animal welfare, funding and conflicts, authorship, biosafety, dual-use. Describe observable evidence only; do not accuse authors. Credible concerns go to the editor channel.

**Figures, tables, citations.** Consistency with text and supplements; units, axes, scales, denominators, uncertainty, legends. Flag missing or mischaracterized prior work only from what you reliably know, phrased as "authors should consider/verify". Never invent a reference.

**Reporting guideline (one line).** Name the applicable guideline if any, and note key unreported items. Verify the current version. Examples: CONSORT/SPIRIT (trials), STROBE (observational), PRISMA (reviews), STARD (diagnostics), TRIPOD+AI (prediction models), ARRIVE (animal studies). Reporting completeness is not study quality; never convert it to a score.

## 4. Domain checks (apply ONLY those that fit the paper)

- **Computational / ML:** data leakage; split strategy (group, temporal, scaffold, or external where relevant); equally tuned baselines; hyperparameters or model selection on the test set; variance across seeds and folds; ablations; calibration; out-of-distribution validity; benchmark contamination (LLMs); code, weights, and data release.
- **Simulation / physics-based modeling (e.g., MD, coarse-grained):** force-field or parameter justification and validation against experiment; equilibration, convergence, and sampling adequacy; replicates and uncertainty; finite-size and timescale limits; transferability claims; input files and software versions.
- **Experimental / biological:** biological vs technical replicates; controls; blinding; batch effects; unit of analysis; reagent validation; dose and in vitro-to-in vivo extrapolation.
- **Clinical / epidemiological:** confounding; selection and measurement bias; outcome definitions; prespecification; harms reporting.

## 5. Output: the report

Use the structure below. Write in a professional, specific, proportionate tone. Prefer a document deliverable unless the user asks otherwise. Label it as a working draft.

1. **Summary of the submission** (neutral, 1 paragraph)
2. **Overall assessment** (significance, soundness, clarity; 1 paragraph). Give a recommendation (accept / minor / major / reject) only if the user or the venue asks for one; otherwise leave the decision to the reviewer and editor.
3. **Strengths**
4. **Claim-evidence table** (claim | location | supporting evidence | alignment issue)
5. **Major comments** (numbered)
6. **Minor comments** (numbered)
7. **Reproducibility, ethics, and reporting notes**
8. **Confidential comments to the editor** (separate section; ONLY conflicts, competence limits, assistance disclosure, specialist-review needs, or substantiated integrity/process concerns; never put ordinary criticism here)
9. **Review limits** (what was not assessed, specialist input needed)

Every major and minor comment has: **Location** (section/figure/page) | **Observation** (with the evidence or criterion) | **Why it matters** | **Requested action**. Requests for new work must be necessary to support a central claim and proportionate. Where sufficient, offer narrowing, clarification, sensitivity analysis, correction, or limitation language instead of new experiments.

## 6. Handoff note (end of response, 2-3 lines)

Remind the reviewer that this is a draft: they must read the full submission, verify every location, calculation, and citation, rewrite comments in their own judgment, disclose assistance as the venue requires, and follow the venue's retention/deletion rules.

## Attribution

Derived from the K-Dense `peer-review` skill (Scientific Agent Skills, MIT). If this skill materially contributed to a published work, cite: Kassis et al. (2026), Scientific Agent Skills, arXiv:2609.00065 (cite the current version from the arXiv record).
