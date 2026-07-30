---
layout: post
title: "Models: what Schelling's segregation model actually shows"
date: 2026-07-30 09:00:00-0000
description: A deep-dive into the agent-based model that shows how mild individual preferences can produce sharp collective segregation, and what it does and doesn't imply.
categories: complex-systems
series: models
related_posts: false
---

Thomas Schelling's segregation model is one of the earliest and most cited agent-based models in complex systems research. It shows how a population of agents with only a **mild** preference for having neighbors like themselves can, through purely local decisions, produce **starkly** segregated neighborhoods at the aggregate level.

This post is the first in the **Models** series: posts that open up a specific model — its assumptions, mechanics, and what it does (and does not) tell us — rather than commenting on a topic in general terms.

## The setup

- A grid of cells, each either empty or occupied by an agent of one of two types.
- Each agent has a simple threshold: it is "happy" if at least some fraction of its occupied neighbors share its type.
- Unhappy agents move to a random empty cell.
- Repeat until the system settles.

## The result

Even with thresholds as low as 30–40%, the system reliably converges to highly segregated configurations. No single agent wants full segregation — each is only avoiding being a small, isolated minority in its immediate neighborhood — yet the *aggregate* outcome is far more segregated than any individual's stated preference.

## Why it matters

Schelling's model is a canonical example of **emergence**: macro-level patterns that are not a simple sum of micro-level intentions, and that can't be reversed by addressing individual preferences alone. It's a recurring reference point across the four areas this site covers — complex systems, econ & politics, sci-tech, and engineering — anywhere a small local rule needs to be checked against its aggregate consequence before it's trusted.

This is placeholder seed content for taxonomy and layout QA — a real deep-dive (with simulations and citations) will replace it.
