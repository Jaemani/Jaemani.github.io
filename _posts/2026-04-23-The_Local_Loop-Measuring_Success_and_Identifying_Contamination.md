---
title: "The Local Loop: Measuring Success and Identifying Contamination"
author: jaeman
date: 2026-04-23 18:04:00 +0900
categories: [AI Agent Engineering, LLM Systems]
tags: [workflows, Openclaw, LLM, LocalLLM, Architecture]
toc: true
---

## Reality Check
For several weeks, I’ve been grinding on a harness to let local models handle software delivery. I didn't want a one-off app generator; I wanted a reusable control system.

The early hope was definitely larger than the evidence I have right now. While I wanted to prove fresh autonomous product creation, the current results are narrower. What I *can* prove is that small local repair loops work, but my attempts at "big" product creation were **contaminated** by harness faults.

## My Evidence Standard
I’ve realized that a "PASS" is useless if it's vague. I now categorize evidence into four levels to stop myself from overclaiming:

| Evidence Type | Purpose | What It Supports |
| --- | --- | --- |
| **Contract benchmark** | Verify schemas/adapters | Harness correctness |
| **Fixture benchmark** | Test small repair loops | Bounded repair capability |
| **Product-gap benchmark** | Test specific gaps | Current fixture-family repair |
| **Strict certification** | Zero-shot product creation | **Strong autonomous claim** |

## What Actually Worked

### 1. Small Local Repair Loops
This is the strongest part of the system. Local models are ready for "healing" code under controlled conditions.
- `bench-model-loop-repeat-1776686015-44876`: Completed **10/10** runs.
- `bench-model-loop-matrix-1776689812-87379`: Completed **10/10** across fixture classes like `lint-global`, `missing-export`, and `ts-prop-mismatch`.

### 2. Bounded Product-Gap Loops
I tried fixing product-shaped gaps, and it’s promising but bounded.
- `bench-model-loop-product-matrix-1776778129-73357`: Passed **6/6** on the direct-local route.
- `bench-model-loop-product-matrix-1776843987-79157`: Passed **8/9**. One failure (`child_verdict_missing`) actually helped me harden the terminalization logic.

## What Did Not Work (The "Contamination" Problem)
The "Strict Zero-Shot" path—building an app from a basic prompt—is still unproven. 
- **Key Run:** `bench-zero-shot-product-1776920746-56130`
- **Inner Run:** `20260423-140816-task`

This run failed, but the failure was entangled with harness issues:
- The gate attempted a backend-style `/api/health` check against a **Vite frontend**.
- ESLint failed because the generated scaffold and the lint contract weren't aligned.
- Middle-planner session-store behavior wasn't trustworthy.

> This is a harness-quality failure, not necessarily a model-capability failure. It means the system isn't clean enough yet to make a final judgment on local models.
{: .prompt-warning }

## Next Steps: Why Protocol Hardening Matters
I need to stop making capability claims and start "decontaminating."

1. **Separate Modes (Diagnostic vs. Certification):** We need a clear line. Diagnostic mode allows for "fail-open" recovery to see how far the model can go. Certification mode requires strict, one-shot stopping rules. This prevents us from citing a "lucky" recovery as a "reliable" capability.
2. **Freeze Evidence (Run-to-Code Freeze):** Every run must be tied to a specific harness commit. If the harness changes daily, we can't tell if a success was due to a better model or just a change in a script.
3. **Certify Contracts (Template/Gate Parity):** We must prove the template (scaffold) and the gate (validator) match *before* the coder starts. This ensures the model isn't set up to fail by a system-level mismatch.

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