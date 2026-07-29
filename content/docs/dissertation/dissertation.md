---
title: "Dissertation"
description: "Modeling and Formal Verification of Gaming Storylines — Lane Holloway's PhD dissertation, The University of Texas at Austin, 2016."
summary: "You like video games? You like formal verification? You'll love my PhD dissertation."
date: 2023-11-18T15:07:15-06:00
lastmod: 2026-07-29T00:00:00-06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "dissertation-175b303fe85575dc246f8612b94ea7ec"
weight: 999
toc: true
seo:
  title: "Modeling and Formal Verification of Gaming Storylines"
  description: "PhD dissertation applying formal verification techniques to video game storylines: SChar, SDL, and StoCk."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Modeling and Formal Verification of Gaming Storylines**
Ph.D. in Electrical and Computer Engineering, The University of Texas at
Austin, May 2016.

## The Problem

Video games have grown from linear stories into sprawling, interactive plots
with multiple parallel storylines that converge and diverge based on player
actions. That flexibility comes at a cost: it is easy to end up with plot
states that are inconsistent or outright impassable — a quest that can never
be completed, a character who is both dead and giving you directions.

At the time, the industry's tools for planning and testing game plots were
text documents, spreadsheets, and critical path testing. Academic research had
started to examine the design planning side, but testing and verification of
the possible plot lines went largely neglected. Hardware and protocol
designers had formal methods for exactly this class of problem; game writers
did not.

## The Approach

My dissertation brings formal verification to game storylines through three
pieces that build on each other:

### SChar — Storyline Characterization

A guided-questions tool that helps game developers characterize the category
of storyline they are working on (e.g., linear, branching, plot). Knowing what
kind of storyline you have determines how it can be modeled and what can go
wrong with it.

### SDL — Storyline Description Language

A description language that lets writers and designers express storylines in
a consistent format close to how they already reason about them — while being
precise enough to feed into formal verification tools.

### StoCk — Storyline Checker

The verification tool. StoCk accepts storylines described in SDL and formally
verifies them for errors using [SPIN](https://spinroot.com/), the model
checker. The dissertation examines StoCk in three use cases common in the
gaming industry: during storyline creation, during quality assurance, and
during storyline implementation.

Together, SChar, SDL, and StoCk give designers, writers, and developers a
methodology and tools to verify consistency in large and complex game plots —
before a player finds the hole for you.

## Abstract

> Video games are becoming more and more interactive with increasingly
> complex plots. These plots typically involve multiple parallel storylines
> that may converge and diverge based on player actions. This may lead to
> situations that are inconsistent or impassable. Current techniques for
> planning and testing game plots involve naive means such as text documents,
> spreadsheets, and critical path testing. Recent academic research examines
> the design planning problems, but neglect testing and verification of the
> possible plot lines. These complex plots have thus until now been handled
> inadequately due to a lack of a formal methodology and tools to support
> them. In this dissertation, we describe how we develop methods to 1)
> characterize storylines (SChar), 2) define a storyline description language
> (SDL), and 3) create a storyline verification tool based in formal
> verification techniques (StoCk) that use our SDL as input. SChar (Storyline
> Characterization) help game developers characterize the category of story
> line they are working on (e.g. linear, branching and plot) through a tool
> that give a set of guided questions. Our SDL allows its users to describe
> storylines in a consistent format similar to how they reason about
> storylines, but in such a way that it can be used for formal verification.
> StoCk accepts storylines, described in SDL, to be formally verified using
> SPIN for errors. StoCk is also examined in three common use cases found in
> the gaming industry used as a tool 1) during storyline creation 2) during
> quality assurance and 3) during storyline implementation. The combination
> of SChar, SDL, and StoCk provides designers, writers, and developers a
> novel methodology and tools to verify consistency in large and complex game
> plots.

## Read It

* [Full text (PDF, 3.2 MB)](https://repositories.lib.utexas.edu/bitstreams/3c4a8d61-e5dd-42a9-881b-a586e6dfcdef/download)
  from the University of Texas Libraries repository
* [Permanent record](http://hdl.handle.net/2152/41455) at the UT repository

### Citation

Holloway, Lane Thomas. *Modeling and Formal Verification of Gaming
Storylines.* Ph.D. dissertation, The University of Texas at Austin, 2016.
http://hdl.handle.net/2152/41455
