---
title: "The Local Loop: Designing for Fallible Intelligence"
author: jaeman
date: 2026-04-22 20:00:00 +0900
categories: [AI Agent Engineering, LLM Systems]
tags: [workflows, Openclaw, LLM, LocalLLM, Architecture]
toc: true
---

## The Core Philosophy: "Never Stop"
Before we talk about architecture, we have to talk about the "Never Stop" rule. Most agents fail because they treat an error as a stop signal. In this harness, the machine only stops when the job is done or the infrastructure itself collapses.

Logic errors, typos, and failed tests are not failures; they are **data points** for the next iteration. By decoupling the model's performance from the system's state, we create a machine that can churn through a hundred "wrong" attempts until it finds the one that passes the gate. This ensures that a model starting with 80% accuracy can reach a 100% result through sheer persistence and a disciplined loop.

## The Problem Space: Why "Just Retry" Fails
If you've ever tried to build a simple coding agent, you've likely seen the "Instruction Drift." Without a harness, simply asking a model to "fix it" repeatedly is like a game of "telephone." Each retry moves further away from the original goal and closer to a hallucinated mess of compiler errors.

Coding isn't just about generation; it's about **context preservation**. Local models have the raw intelligence to write code, but they often lack the "reasoning density" to maintain a complex state over 50 turns. The harness exists to hold that state for them, preventing the loss of entropy that kills unconstrained agentic loops.

## The 80% Strategy: Leveraging the Local SOTA
My goal with **OpenClaw** is to leverage the fact that current local SOTA models (like Qwen 3.5/3.6) already hit roughly 80% of the functional performance of frontier cloud models on benchmarks.

The strategy isn't to settle for 80%. It’s to take that powerful 80% baseline and supplement it with an **Infinite Feedback Loop**. By placing a capable local model inside a disciplined harness, we can iterate until the final output is 100% correct, achieving frontier-level results at a fraction of the cost.

## The 5-Stage Architecture: A Cascade of Intent
To prevent "spaghetti prompts," I separated the system into five stages. This is a logical cascade designed to preserve intent and keep the loop focused:

1.  **Planner (API):** Defines the **Strategy**. It chooses the stack and the "rules of the game."
2.  **Mid-Planner (Local):** Defines the **Context**. It translates the strategy into small, sandboxed tasks.
3.  **Coder (Local):** Performs the **Action**. It executes edits in a sandbox without polluting the original strategy.
4.  **Reviewer (Local):** Performs **Unit Verification**. It checks the work against the local task.
5.  **Final-Reviewer (API):** Performs **System Alignment**. It ensures the final result still matches the initial goal.

By strictly separating these roles, we ensure the "Worker" (Coder) remains focused on implementation while the "Architect" (Planner) preserves the project's integrity across infinite iterations.