---
title: "Tayda UV Artwork Processor"
description: "A Go TUI and CLI that validates guitar pedal enclosure artwork and produces print-ready PDFs for the Tayda UV printing service, one artboard per side."
summary: "From image file to prepared PDF for Tayda UV printing."
date: 2026-09-06T09:00:00-05:00
lastmod: 2026-09-06T09:00:00-05:00
draft: false
slug: "tayda-uv"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "tayda-uv-7ea5bf3f7f27aec0900c5d479a5f8ed8"
weight: 10
toc: true
seo:
  title: "Tayda UV Artwork Processor"
  description: "A Go TUI and CLI that validates guitar pedal enclosure artwork and writes print-ready PDFs for the Tayda UV printing service."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Source:** [github.com/drlholloway/tayda-uv-artwork-processor](https://github.com/drlholloway/tayda-uv-artwork-processor) (Go, MIT)

## Why

Tayda's UV printing service is a gift to small pedal builders. You can go from
a bare aluminium box to a professionally finished enclosure quickly and for
very little money. The hard part is getting the artwork into the exact shape
Tayda's Box Tool expects: the right artboard size for each side, the right
resolution, and the right spot colours for the white undercoat and optional
gloss varnish.

A community web tool exists for the front face, but web tools disappear. I
wanted something that runs locally, covers every side of the box, and can be
scripted.

## What it does

- **Interactive TUI.** Pick an enclosure (1590B, 125B, 1590XX, and friends),
  attach an image to each side you want printed, and convert them all in one
  pass. Each side is validated as you attach it, so problems show up before you
  spend anything.
- **Validation.** Checks image dimensions against the artboard for that side,
  with per-side tolerances, and reports effective DPI.
- **Print-ready output.** Writes a single-artboard CMYK PDF per side with the
  `RDG_WHITE` undercoat and optional `RDG_GLOSS` varnish layers in the order
  Tayda's process expects.
- **Inspection.** Reads a finished PDF back and reports its artboard, spot
  colours, and print order, so you can confirm what is actually in the file.
- **Scriptable.** Everything the TUI does is also a subcommand, so builds can
  be automated or driven by an agent.

## A taste

```sh
# what size does each side need to be?
tayda-uv sides 1590B

# check artwork without writing anything
tayda-uv validate -e 1590B -s A face.png

# write the print-ready PDF
tayda-uv convert -e 1590B -s A -o face.pdf face.png

# read it back and confirm what is in it
tayda-uv inspect -e 1590B -s A face.pdf
```
