# Prompt Audit Report Specification

## Universal scoring

Score each dimension from 0 to 5. Mark a dimension `N/A` when it genuinely does not apply; exclude it from the weighted total.

| Dimension | Weight | What to inspect |
| --- | ---: | --- |
| Goal clarity | 20 | Is the desired result unambiguous? |
| Context sufficiency | 15 | Is enough background supplied without irrelevant detail? |
| Input definition | 10 | Are source material, variables, and boundaries identifiable? |
| Constraints | 15 | Are important limits, permissions, and exclusions stated? |
| Output contract | 15 | Are format, audience, tone, length, and deliverable clear where needed? |
| Verifiability | 15 | Can the result be checked with criteria, evidence, or tests? |
| Robustness | 10 | Does the prompt handle ambiguity, missing data, conflicts, and failure appropriately? |

Calculate the total as the normalized weighted score out of 100. Scores are diagnostic, not scientific measurements; explain the evidence behind them.

Rating bands:

- 90–100: Excellent — ready to use; only optional refinements.
- 75–89: Good — usable with a few material improvements.
- 60–74: Fair — likely to work inconsistently.
- 40–59: Weak — important requirements are missing or conflicting.
- 0–39: Unreliable — the intended result cannot be produced consistently.

## Full report format

Use this order:

1. **Verdict** — one sentence naming the task type, score, and most important finding.
2. **Scorecard** — a compact table with dimension, score, and one evidence-based note.
3. **Priority findings** — up to five items, ordered by impact. Label each `Critical`, `Important`, or `Optional`.
4. **Improved prompt** — a complete copy-ready version in a fenced code block.
5. **Change log** — concise mapping from change to reason.
6. **Open questions** — only if answers would materially alter the prompt; maximum three.

Do not bury the improved prompt beneath long theory. Do not claim that a higher score guarantees better model output.

## Compact report format

Return:

- Score and one-line verdict
- Three highest-impact findings at most
- Improved prompt

## Batch format

Start with a table containing prompt identifier, detected type, score, top issue, and status. Then provide the compact report for each prompt. Use stable identifiers such as `P1`, `P2`, and `P3` when none are supplied.
