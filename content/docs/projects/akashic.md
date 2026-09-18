---
title: "Akashic"
description: "Akashic is a searchable reference library of DIY guitar-pedal circuits, built from the build documents that PCB vendors publish, with parsed parts lists you can search across every vendor."
summary: "A cross-vendor library of DIY guitar-pedal PCBs and their parts lists."
date: 2026-09-18T00:00:00-05:00
lastmod: 2026-09-18T00:00:00-05:00
draft: false
slug: "akashic"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "akashic-b27207c5c194a134d7aa69b4f0025cbc"
weight: 40
toc: true
seo:
  title: "Akashic, Guitar Effects PCB Lookup"
  description: "A searchable, offline-capable library of DIY guitar-pedal circuits from PCB vendors, with normalized parts lists and cross-vendor search."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Live:** [akashic.cryptideffects.com](https://akashic.cryptideffects.com)

**Source:** [github.com/drlholloway/akashic](https://github.com/drlholloway/akashic) (Python and SvelteKit, PolyForm Shield)

**Platforms:** a static, offline-capable web app that installs as a PWA on
macOS, Linux, Android, and iOS.

## Why

Every DIY pedal PCB vendor publishes a build document, and every one of them
formats it differently. If you want to know which boards are based on the Rat,
which circuits use an LM308, or which three-knob boards fit a 125B enclosure,
you have to open a lot of PDFs. The information is all public; it just has
never been in one place.

## What it does

- **One record per board.** For each PCB, the commercial pedal it is based
  on, the vendor and price with a link to buy, the build document, the
  controls and enclosure, and a fully parsed parts list.
- **Normalized values.** Every vendor's parts list lands in one database with
  a shared taxonomy, so `1K5`, `1.5k`, and `1k5` are the same part, and
  `A100K`, `100KA`, and `100k log` are the same pot. Cross-vendor questions
  become a search.
- **Prices in one currency.** Vendors list in USD, EUR, GBP, and CAD. The
  export fetches exchange rates so the app can show everything in one
  currency, or the vendor's own.
- **Your own schematic.** Every circuit has a slot for a hand-drawn KiCad
  fragment, rendered on the circuit page with the source file offered for
  download.
- **Twenty sources and counting.** PedalPCB, Aion FX, Fuzz Dog, Madbean,
  GuitarPCB, and many smaller shops, plus schematic archives with no board to
  buy at all.

## What is indexed and what is not

Names, prices, part values, controls, enclosures, and the original circuit
are indexed as facts, and every record links back to the vendor's product
page and build document. The build documents and their schematic images
remain the vendors' copyright. The scraper caches them locally for personal
reference, and the public site does not republish them.

## How it is built

A Python package holds one adapter per vendor, the PDF parsing (with OCR for
the vendors whose parts lists are raster images), a SQLite database, and a
JSON export. A SvelteKit app prerenders every circuit and part page into a
static site, builds its search index in the browser, and caches pages with a
service worker for offline use.
