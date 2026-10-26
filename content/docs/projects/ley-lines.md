---
title: "Ley Lines"
description: "Ley Lines is a browsable map of guitar-pedal lineage: which circuits came from which, and the circuit blocks, like tone stacks and clipping stages, that they share."
summary: "A map of which guitar pedals came from which."
date: 2026-10-25T09:00:00-05:00
lastmod: 2026-10-25T09:00:00-05:00
draft: false
slug: "ley-lines"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "ley-lines-5d0c3b7e8a1f4c2b9e6d7a4f1b3c8e25"
weight: 60
toc: true
seo:
  title: "Ley Lines, Guitar Pedal Lineage Map"
  description: "A browsable graph of guitar-pedal lineage, from the originals through reissues, boutique takes, kits and layouts, with every link sourced."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Live:** [leylines.cryptideffects.com](https://leylines.cryptideffects.com)

**Platforms:** a static web app that runs in any modern browser.

## Why

Almost every pedal is based on another pedal. A boutique fuzz is a Big Muff
with a mids knob, a kit is a clone of a Rat, and that Rat owes something to
the circuits before it. The family trees are out there, scattered across
forum threads, maker interviews, kit build documents and a few devoted
reference sites, but there has never been one place to follow a circuit from
its original all the way down to the boards you can build today.

## What it does

- **A lineage graph.** Pick a family and follow its links: version of,
  reissue of, clone of, derived from, inspired by, rebrand of. Every link
  points from the newer pedal to the older one.
- **A timeline view.** The same pedals laid out by year, so you can see when
  each branch appeared.
- **Shared circuit blocks.** Tone stacks, clipping stages, buffers and gain
  stages are records of their own, so you can see every pedal that uses the
  Big Muff tone stack, wherever it sits in the tree.
- **Kits and layouts too.** DIY boards come in from
  [Akashic](../akashic/), linked to the originals their vendors say they are
  based on.
- **Search and filters.** Find a pedal or block by name, and narrow the graph
  by family and by kind: production, reissue, boutique, kit or DIY.
- **Over 4,000 pedals in 146 families.** It started with the Big Muff and has
  grown to fuzzes, drives, phasers, flangers, choruses, delays, tremolos,
  rotary simulators, ring modulators and more.

## Every link has a source

Each lineage link cites at least one source and says how sure it is: stated
by the maker, documented by an established reference, shown by a schematic
trace, community consensus, or unverified. Doubtful records are flagged for a
human check. The descriptions are facts written in my own words, never copied
from another site.

## How it is built

The data is hand-curated YAML, one file per pedal, family and circuit block.
A Python build step validates every reference and writes a single graph file,
and a static site draws it with Cytoscape.js. The same graph exports to
graphify, so I can ask it questions like how two pedals are connected.
