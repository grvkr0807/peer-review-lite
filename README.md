# peer-review-lite

A lightweight, journal-agnostic Agent Skill for Claude that produces a structured
peer-review assessment report of a scientific manuscript in a single pass.

## What it does

- Reads the manuscript once and writes a draft referee report: summary, overall
  assessment, strengths, claim–evidence table, numbered major/minor comments
  (location, observation, why it matters, requested action), reproducibility/ethics/
  reporting notes, separate confidential comments to the editor, and review limits.
- Applies domain checks only where relevant: computational/ML, simulation
  (MD, coarse-grained), experimental/biological, clinical/epidemiological.
- Keeps core safeguards: a one-time authorization and venue AI-policy check, no
  fabricated citations or reproductions, and a reminder that the output is a draft
  for an accountable human reviewer.

## How it differs from the original

This is a **lite version** of the `peer-review` skill (v2.4) by **K-Dense Inc.**
from [Scientific Agent Skills](https://github.com/K-Dense-AI/scientific-agent-skills).
It keeps the original's review workflow and criteria in condensed form and removes the
bundled Python scripts, JSON/CSV templates, intake validator, lint step, and long
reference files. Skill overhead drops from roughly 23–25k tokens per run to about
3–4k (author's estimate), with far fewer tool calls.

For formal, confidentiality-critical reviews that need the full audit trail, use the
original skill.

## Install

- **Claude app (claude.ai / Cowork):** zip the `peer-review-lite` folder (so the zip
  contains `peer-review-lite/SKILL.md`) and upload it under Settings → Skills.
- **Claude Code:** copy the `peer-review-lite` folder into `~/.claude/skills/`.

Then attach a manuscript and ask: "Use peer-review-lite to review this manuscript."

## Responsible use

Only review manuscripts you are authorized to review, and check the journal's policy
on AI-assisted peer review first. Content read by a hosted assistant is processed
externally. The output is a draft: verify every statement, rewrite comments in your
own judgment, and disclose assistance as the venue requires.

## Acknowledgment and citation

This skill is derived from the `peer-review` skill by K-Dense Inc., part of
Scientific Agent Skills, licensed under the MIT License. Thanks to the K-Dense authors
for making their work openly available. If this skill contributes to published work,
please cite the original:

> Kassis, T., Agarwal, V., He, Y., Patel, D., & Brueckner, A. M. (2026). Scientific
> Agent Skills: A Library of Procedural Knowledge for Research Agents.
> arXiv:2609.00065. https://doi.org/10.48550/arXiv.2609.00065

## License

MIT. See [LICENSE](LICENSE), which retains the original K-Dense copyright notice
as required by the MIT License.
