---
title: "The Local Loop: Designing for Fallible Intelligence"
author: jaeman
date: 2026-04-22 20:00:00 +0900
categories: [AI Agent Engineering, LLM Systems]
tags: [workflows, Openclaw, LLM, LocalLLM, Architecture]
toc: true
---

## Why I'm doing this
Most autonomous agent frameworks nowadays are built on a "magic" promise: that the model is smart enough to handle everything. But LLMs—especially local ones—are probabilistic and fallible. When left to their own devices, they drift and eventually collapse into a "spaghetti prompt" mess.

I didn't want a "magic" box. I wanted a **machine**. 

### The 80% Strategy
My goal with the **OpenClaw** harness is to hit 80% of the performance of frontier cloud models using local, cost-effective models (like Qwen 3.5/3.6). To bridge that 20% gap in reliability, I’m investing in **disciplined engineering** rather than more parameters.

The strategy is simple: **Assume the model will fail.** Build a system that makes those failures observable, bounded, and recoverable.

## The 5-Stage Architecture
To prevent logic drift, I separated the system into five distinct stages. Each stage has a specific "contract"—a defined input and output that must be verified before moving to the next.

1.  **Planner (API):** High-level strategy. It defines the technical stack and the project "charter." It doesn't write code; it writes the rules of the game.
2.  **Mid-Planner (Local):** The translator. It takes the grand plan and breaks it into sandboxed, executable tasks that a local model can actually handle.
3.  **Coder (Local):** The worker. It performs scoped edits within a sandbox. It is forbidden from making architectural decisions; it only executes the mid-plan.
4.  **Reviewer (Local):** The immediate gate. It checks the Coder’s output against the specific mid-plan. If it fails, the loop restarts.
5.  **Final-Reviewer (API):** The end-of-line judge. It verifies the final product against the original project charter for total consistency.

> By separating these roles, I prevent the "spaghetti code" problem and keep the system's logic clean.
{: .prompt-info }

## The "Never Stop" Philosophy
A common failure in agents is "stopping on error." In this harness, the machine only stops for two reasons:
1.  **The job is done:** All deterministic gates (lint, build, health) pass.
2.  **The system breaks:** A critical infrastructure failure occurs.

Everything else—logic errors, typos, failed tests—is just another iteration in the loop. By decoupling the model's performance from the system's state, we create a machine that can churn through failures until it finds a path to success.
