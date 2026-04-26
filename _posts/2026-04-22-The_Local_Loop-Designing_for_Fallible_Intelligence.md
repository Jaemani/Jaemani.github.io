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

Logic errors, typos, and failed tests are not failures; they are **data points** for the next iteration. By decoupling the model's performance from the system's state, we create a machine that can churn through a hundred "wrong" attempts until it finds the one that passes the gate. This ensures that even an 80%-quality model can reach a 100% result through sheer persistence and a solid harness.

## The Problem Space: Why "Just Retry" Fails
If you've ever tried to build a simple coding agent, you've likely seen the "Instruction Drift." Without a harness, simply asking a model to "fix it" repeatedly is like a game of "telephone." Each retry moves further away from the original goal and closer to a hallucinated mess of compiler errors.

Coding isn't just about generation; it's about **context preservation**. Local models (like Qwen 3.5/3.6) have the raw intelligence to write code, but they lack the "reasoning density" to maintain a complex state over 50 turns. The harness exists to hold that state for them, preventing the loss of entropy that kills unconstrained agentic loops.

## The 80% Strategy
My goal with **OpenClaw** is to hit 80% of the performance of frontier cloud models (like GPT-4o or Claude 3.5) using local, cost-effective models.

When I say "80%," I mean reaching functional parity on standard software engineering tasks: identifying bugs, fixing regressions, and implementing v0.1 MVPs on known tech stacks. We bridge the remaining 20% gap through **disciplined engineering** (the harness) rather than more parameters (the model).

## The 5-Stage Architecture: A Cascade of Intent
To prevent "spaghetti prompts," I separated the system into five stages. This is a logical cascade designed to preserve intent by strictly separating concerns:

1.  **Planner (API):** Defines the **Strategy**. It chooses the stack and the "rules of the game."
2.  **Mid-Planner (Local):** Defines the **Context**. It translates the strategy into small, sandboxed tasks that won't overwhelm a local model.
3.  **Coder (Local):** Performs the **Action**. It makes scoped edits in a sandbox. It is forbidden from changing the strategy; it only executes the task.
4.  **Reviewer (Local):** Performs **Unit Verification**. It checks the Coder’s work against the specific task.
5.  **Final-Reviewer (API):** Performs **System Alignment**. It verifies that the final product still matches the original Strategy.

By strictly separating these roles, we ensure that the "Worker" (Coder) never pollutes the "Architect" (Planner), keeping the project's logic clean and the reasoning budget focused