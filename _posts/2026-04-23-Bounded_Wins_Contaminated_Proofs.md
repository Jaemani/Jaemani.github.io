---
title: "Bounded Wins, Contaminated Proofs: What My Local Agent Harness Actually Proved"
subtitle: An interim engineering report on local repair loops, bounded product gaps, and why fresh autonomous product-making remains unproven.
author: jaeman
date: 2026-04-23 18:04:00 +0900
categories: [AI Agent Engineering, LLM Systems]
tags: [Chirpy, Jekyll, Github Page, Github Actions, workflows]
toc: true
---
## Opening

For several weeks, I worked on a harness that would let a local model participate in software delivery without pretending that the model was perfect. The target was not a one-off app generator. The target was a reusable control system: a planner and reviewer define bounded work, a local model writes code, deterministic gates verify the result, and stronger models or deterministic scripts intervene only at clearly defined boundaries.

The early hope was larger than the current evidence. I wanted the system to demonstrate fresh autonomous product creation from a basic prompt. The current system does not prove that yet.

What it does prove is narrower and still useful. Small local repair loops can pass repeatedly. Bounded product-gap loops can pass on the current fixture family. The harness can record route provenance, distinguish deterministic fallback from model-loop execution, and classify several infrastructure failures instead of silently treating them as model failures.

The strongest current negative result is also useful, but it is contaminated. The latest strict product-creation proof exposed harness/runtime faults before it could cleanly evaluate product-building capability. That means the result should not be read as “local models cannot do this.” It should be read as “this current harness is not yet clean enough to support that stronger claim.”

## Current Conclusion

The strongest conclusion I can justify today is narrower than what I initially hoped:

- Small local repair loops are proven on the current benchmark fixtures.
- Bounded product-gap loops have meaningful positive evidence on the current fixture family.
- Fresh autonomous product creation from a basic user prompt remains unproven.
- The current negative evidence does not support a general impossibility claim about local-model product loops.

This distinction matters. A failing strict proof can still be highly diagnostic while being too contaminated to support a clean capability claim. I was not strict enough about separating those two roles early in the project.

## What I Tried to Build

The system under test is a local-model harness wrapped around OpenClaw. The intended architecture is:

- API or stronger-model stages may be used for bounded planning, final review, or escalation.
- The repeated implementation loop must remain local-only.
- Middle-planner and reviewer stages should produce structured repair plans and judgment, not informal prose.
- The coder stage should make scoped edits against a workspace, not narrate changes.
- Deterministic gates should own linting, typechecking, build checks, health checks, design checks, and final verdicts.
- Every run should preserve enough evidence to distinguish model failure, harness failure, runtime failure, and evaluation contamination.

That distinction is the central idea. The harness is not supposed to replace model intelligence with hardcoded product logic. It is supposed to convert unreliable model behavior into bounded, observable, recoverable engineering steps.

## Evidence Standard

I now separate evidence into four categories:

| Evidence Type | Purpose | What It Can Support | What It Cannot Support |
| --- | --- | --- | --- |
| Contract benchmark | Verifies schemas, validators, route labels, and adapter surfaces | Harness contract correctness | Model capability claims |
| Fixture benchmark | Tests small repair loops | Bounded local repair capability | Product-scale autonomy |
| Product-gap benchmark | Tests bounded product-shaped gaps | Current fixture-family repair evidence | Fresh product creation from a basic prompt |
| Strict certification proof | Tests basic-prompt product creation with contamination controls | Stronger autonomous product claim | Any claim if the run is contaminated |

This taxonomy is not cosmetic. It prevents a useful Level 5 product-gap result from being inflated into a fresh product-maker claim. It also prevents a contaminated strict proof from being misread as a clean model-limit result.

## What Actually Worked

### Small Local Repair Loops

The strongest small-loop evidence is positive.

- `bench-model-loop-repeat-1776686015-44876` completed `10/10` runs with `pass_rate: 1.0`.
- `bench-model-loop-matrix-1776689812-87379` completed `10/10` runs across five fixture classes:
  - `docs-provenance-gap`
  - `lint-global`
  - `missing-export`
  - `route-health-mismatch`
  - `ts-prop-mismatch`

This supports the narrower claim that the current harness can drive repeated small local repair loops under controlled fixture conditions.

It does not support the stronger claim that the harness can generate complete fresh products from a basic prompt.

### Bounded Product-Gap Loops

The product-gap evidence is also meaningful, but bounded.

- `bench-model-loop-product-matrix-1776778129-73357` passed `6/6` on the direct-local route across the current two-gap product family, with `deterministic_fallback_histogram: {"false": 6}`.
- `bench-model-loop-product-matrix-1776843987-79157` passed `8/9` on the OpenClaw-agent route across the three-gap fixture family, with no deterministic fallback. One row failed as `child_verdict_missing`, which made the route evidence stronger than a single pass but still not clean.
- Later evidence in the internal evidence index records a stronger bounded local-agent baseline on the current three-gap family after terminalization hardening, but the public interpretation should remain bounded to this environment, fixture family, and adapter stack.

This supports the narrower claim that bounded product-shaped repair can work in the current harness.

It does not support the stronger claim that the system has proven general autonomous product-making.

### Provenance Improved

One of the most useful improvements was not a product feature. It was evidence quality.

The harness began recording:

- requested coder route,
- effective coder route,
- route fallback,
- deterministic fallback,
- harness adapter,
- final writer,
- blocker class.

This matters because an old “PASS” without provenance is easy to overread. A newer “PASS” that says it used `direct-local`, `openclaw-agent`, or deterministic fallback is much more useful. It tells me what actually passed.

## What Did Not Yet Work

### Fresh Product Creation Is Still Unproven

The strict zero-shot path is the important unresolved proof.

The relevant current evidence is:

- outer strict-proof wrapper: `bench-zero-shot-product-1776920746-56130`
- deepest recent inner run: `20260423-140816-task`
- key artifacts:
  - `shared/runs/20260423-140816-task/11-stage-events.jsonl`
  - `shared/runs/20260423-140816-task/resume_pipeline.log`
  - `shared/runs/20260423-140816-task/18-gate.log`
  - `shared/design/local_model_loop_limitations_2026-04-23.md`

That path reached meaningful stages: prompt-charter synthesis, planner artifacts, middle-planner handoff, deterministic scaffold, scaffold pre-gate, repair-plan preparation, and coder readiness checks.

But it did not produce a clean certification-quality product PASS. The failure was still entangled with harness and runtime issues.

### The Strict Proof Was Contaminated

The latest strict path exposed several upstream problems:

- Prompt-charter synthesis remained unstable.
- Middle-planner session-store behavior was not trustworthy.
- Stage handoff and runtime behavior showed contamination risk.
- The scaffold/gate contract was mismatched for a frontend-only web-game product.
- The gate attempted a backend-style `/api/health` check against a Vite frontend.
- ESLint failed to parse TypeScript scaffold code because the generated scaffold and lint contract were not aligned.

These are not product-quality failures. They are harness-quality failures.

That distinction changes the interpretation. The current negative result is meaningful, but it is not clean evidence that local model product loops are impossible.

## What I Misread or Underestimated

Several internal documents were directionally useful but no longer sufficient as current claim-setting sources. The corpus evolved, and later evidence narrowed earlier interpretations.

### I Underestimated Document Drift

One thing I initially underestimated was how easily a large internal corpus can preserve outdated interpretations. Some planning notes and changelog entries were useful historically, but later strict-proof runs and evidence-index updates narrowed what could honestly be claimed.

The fix is not to delete history. The fix is to separate current truth from archive.

### I Mixed Diagnostic Runs and Certification Proofs

Diagnostic runs are allowed to recover, synthesize artifacts, and continue in order to expose more failures.

Certification proofs are different. They need stricter stopping rules. A proof contaminated by automatic continuation can still teach something, but it cannot support the strongest public claim.

I was not strict enough about this early on.

### I Treated Current Scripts and Old Runs Too Closely

Another miss was treating current script inspection and older run artifacts as if they described the same system state. Once the harness changes daily, causal claims need stronger run-to-code freezing.

A run should be tied to:

- harness commit or snapshot,
- script manifest,
- config snapshot,
- adapter capability snapshot,
- environment fingerprint,
- protocol version.

Without that, a later reviewer can easily confuse “what the harness does now” with “what the harness did during that run.”

### I Overweighted Product PASS Before Route Provenance

A PASS is not enough. I need to know how the PASS happened.

For this system, a useful PASS must say whether it used:

- direct local model calls,
- OpenClaw agent dispatch,
- deterministic fallback,
- API fallback,
- manual escalation,
- rescue finalization.

Without that route information, the result is not useless, but it is weaker than it looks.

### I Underestimated Template/Gate Contract Risk

Some of the strongest negative evidence turned out to be upstream of product logic itself. Template/gate mismatches, scaffold assumptions, frontend/backend health assumptions, and session-store inconsistencies can all masquerade as model failures.

That changed how I now interpret failure. Before evaluating model capability, the harness must prove that the task contract, scaffold, gate, and validation target agree.

## Current Position

My current position is narrower than my earlier implicit hope:

The harness has real bounded successes. It can drive small local repair loops. It can close bounded product-shaped gaps under current fixture conditions. It has improved at recording route and fallback provenance.

The stronger fresh-product claim remains unproven in the current system.

The current strict negative result should be treated as a current-system result, not a universal impossibility result. It says the harness is still too contaminated to make the stronger capability claim. It does not say local loops can never work.

## Engineering Decision

The next work should not be louder capability claims. It should be decontamination and protocol hardening.

The immediate priorities are:

1. Separate diagnostic and certification modes.
2. Freeze run-to-code evidence for every new proof run.
3. Certify template/gate pairs before any strict proof.
4. Move outdated claim-setting documents into archive or mark them as superseded.
5. Maintain one current claim ledger as the public source of truth.
6. Expand fixture families only after the existing protocol is clean.
7. Add UI/design validation only as a defined evidence layer, not as a vague “looks good” claim.

## Next Proof Gates

Before I should claim fresh autonomous product creation, the system needs a clean strict proof with the following properties:

- basic user prompt only,
- no pre-authored project charter,
- no product-specific manual intervention,
- no fail-open diagnostic continuation,
- no hidden API coder loop,
- local-only repeated implementation loop,
- certified template/gate compatibility before coder dispatch,
- route provenance in final verdict,
- screenshot or DOM evidence for UI products,
- terminal verdict written by the deterministic verdict path,
- run manifest tying artifacts to code, config, adapter, and environment snapshots.

If that run fails, the failure must be classified as `BLOCKED` or `INVALIDATED`, not blended into a vague failure narrative.

## Appendix A. Claim Ledger

| Claim | Current Status | Evidence | Limit |
| --- | --- | --- | --- |
| Small local repair loops can pass repeatedly | Proven on current fixtures | `bench-model-loop-repeat-1776686015-44876`, `bench-model-loop-matrix-1776689812-87379` | Small fixtures only |
| Bounded product-gap loops can pass on current fixture family | Supported with bounded positive evidence | `bench-model-loop-product-matrix-1776778129-73357`, `bench-model-loop-product-matrix-1776843987-79157`, later evidence-index entries | Fixture-family and environment bounded |
| Route and fallback provenance can be captured | Proven going forward | `technical_report_evidence_index.md`, product matrix summaries, verdict metadata | Older runs may lack fields |
| Deterministic HarnessChanger path can produce a known-stack v0.1 | Proven | `20260420-130853-task/final_verdict.json` | Known stack and deterministic scaffold only |
| Fresh autonomous project creation from a basic prompt is proven | Unproven | Strict path `bench-zero-shot-product-1776920746-56130` and inner `20260423-140816-task` did not produce clean PASS | Current failures are harness/runtime contaminated |
| Local model loops are impossible in principle | Not supported | Current failures are entangled with harness faults | Requires cleaner negative evidence before such a claim |
| OpenClaw adapter portability is solved | Not supported | Adapter probe exists; Hermes registered but not implemented | Selector/probe layer only |

## Appendix B. Evidence Anchors

The public post should cite only a compact subset of artifacts. The full internal corpus can remain available for deeper review.

Primary current documents:

- `shared/design/technical_report_evidence_index.md`
- `shared/design/local_model_loop_limitations_2026-04-23.md`
- `shared/design/current_handoff.md`
- `shared/design/technical_debt_plan.md`

Small-loop evidence:

- `shared/runs/bench-model-loop-repeat-1776686015-44876/summary.json`
- `shared/runs/bench-model-loop-matrix-1776689812-87379/summary.json`

Product-gap evidence:

- `shared/runs/bench-model-loop-product-matrix-1776778129-73357/summary.json`
- `shared/runs/bench-model-loop-product-matrix-1776843987-79157/summary.json`

Strict-proof evidence:

- `shared/runs/bench-zero-shot-product-1776920746-56130/`
- `shared/runs/20260423-140816-task/11-stage-events.jsonl`
- `shared/runs/20260423-140816-task/18-gate.log`
- `shared/runs/20260423-140816-task/resume_pipeline.log`

Protocol and adapter evidence:

- `shared/contracts/zero-shot-product-proof.md`
- `shared/contracts/product-gap-benchmarks.json`
- `shared/contracts/harness-adapter-registry.json`
- `shared/design/openclaw_adapter_capability_probe.latest.json`

## Appendix C. Sentences I Should Not Write

These sentences would overclaim the current evidence:

- “The architecture is proven.”
- “Local models can now build complete products autonomously.”
- “The strict proof shows local loops are impossible.”
- “OpenClaw routing is generally stable.”
- “The HarnessChanger PASS proves the general harness.”
- “Bounded product-gap success proves fresh product-making.”
- “The latest failure was a product-quality failure.”

Safer replacements:

- “The architecture has bounded positive evidence, but the strongest claim remains unproven.”
- “The current harness can complete repeated small repair loops and bounded product-gap loops under current fixture conditions.”
- “The strict proof produced a meaningful current-system negative result, but it was contaminated by harness/runtime faults.”
- “Route provenance has improved, but portability and repeated cross-environment stability remain open.”

## Appendix D. Blog Title Options

1. Bounded Wins, Contaminated Proofs: What My Local Agent Harness Actually Proved
2. What My Local-Model Harness Proved, and What It Did Not
3. From Overclaim to Evidence: Revisiting My Local Agent Harness
4. Small Loops Passed. Fresh Product-Making Did Not.
5. Evidence, Contamination, and Local Agent Loops

## Closing

Some of the most useful results in this project were not wins. They were corrections.

The current evidence is enough to justify continued work. It is not enough to justify a victory claim. The next milestone is a clean proof environment: current-truth documents, frozen run manifests, certified template/gate pairs, and strict separation between diagnostic recovery and certification.

Only after that should I rerun the fresh product proof and decide what the model loop can really do.
