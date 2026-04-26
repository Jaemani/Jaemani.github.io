---
title: "The Local Loop: Measuring Success and Identifying Contamination"
author: jaeman
date: 2026-04-23 18:04:00 +0900
categories: [AI Agent Engineering, LLM Systems]
tags: [workflows, Openclaw, LLM, LocalLLM, Architecture]
toc: true
---

## Reality Check
For several weeks, I’ve been grinding on a harness to let local models handle software delivery. I didn't want a one-off app generator; I wanted a reusable control system that empowers local models through iteration.

The early hope was larger than the evidence I have right now. While I wanted to prove fresh autonomous product creation, the current results are narrower. What I *can* prove is that small local repair loops work. The failures we saw in "big" product creation were not failures of model capability, but **contamination** of the harness itself.

## The "9-Second" Discovery: Why We Measure
Recently, a strict proof run failed with a `switch_timeout` error after 120 seconds. My first instinct was to blame the infrastructure—to assume the local proxy was too slow. I almost spent days refactoring the entire proxy system.

Instead, I measured.

A controlled dry-run revealed that the actual model switching time was only **9 seconds**. The infrastructure was healthy. The failure wasn't in the hardware; it was a "contamination" of the reasoning loop that caused the system to hang. This discovery was critical: it proved that our focus should be on protecting the **purity of the reasoning loop**, which is where the system's power actually resides.

## My Evidence Standard
I’ve realized that a "PASS" is useless if it's vague. I now categorize evidence into four levels:

| Evidence Type | Purpose | What It Supports |
| --- | --- | --- |
| **Contract benchmark** | Verify schemas/adapters | Harness correctness |
| **Fixture benchmark** | Test small repair loops | Bounded repair capability |
| **Product-gap benchmark** | Test specific gaps | Current fixture-family repair |
| **Strict certification** | Zero-shot product creation | **Strong autonomous claim** |

## What Did Not Work (The "Contamination" Problem)
The failure of our "Strict Zero-Shot" runs reached meaningful stages but failed because of harness issues: mismatched scaffolds, incorrect health gates, and untrustworthy session stores.

> This is a harness-quality failure, not a model-capability failure. Because the harness was contaminated, the **Infinite Feedback Loop** was never given a clean environment to succeed.
{: .prompt-warning }

## Next Steps: Why Protocol Hardening Matters
To unlock the true potential of the local model loop, we must "decontaminate" the environment:

1.  **Separate Modes (Diagnostic vs. Certification):** Clear lines to prevent "lucky" passes from being cited as reliable capability.
2.  **Freeze Evidence (Run-to-Code Freeze):** Every run tied to a specific harness commit so we can measure the loop's improvement over time.
3.  **Certify Contracts (Template/Gate Parity):** Ensuring the model is never set up to fail by a system-level mismatch.

---

## Appendix A. Claim Ledger

| Claim | Status | Evidence | Limit |
| --- | --- | --- | --- |
| Small local repair loops pass | **Proven** | `bench-model-loop-repeat-1776686015-44876` | Small fixtures only |
| Bounded product-gap loops pass | **Supported** | `bench-model-loop-product-matrix-1776778129-73357` | Fixture-family bounded |
| Route/fallback provenance captured | **Proven** | Verdict metadata in `technical_report_evidence_index.md` | Older runs may lack fields |
| Fresh project creation proven | **Unproven** | Run `20260423-140816-task` | Contaminated by harness faults |

## Appendix B. Evidence Anchors

Primary current documents:
- `shared/design/technical_report_evidence_index.md`
- `shared/design/local_model_loop_limitations_2026-04-23.md`
- `shared/design/current_handoff.md`

Small-loop evidence:
- `shared/runs/bench-model-loop-repeat-1776686015-44876/summary.json`
- `shared/runs/bench-model-loop-matrix-1776689812-87379/summary.json`

Strict-proof evidence:
- `shared/runs/bench-zero-shot-product-1776920746-56130/`
- `shared/runs/20260423-140816-task/11-stage-events.jsonl`