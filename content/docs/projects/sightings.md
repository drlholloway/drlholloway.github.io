---
title: "Sightings"
description: "Sightings is a Flutter workbench for the Peak Atlas DCA75 semiconductor analyser: identify tests, curve sweeps, and a local database for comparing and binning parts."
summary: "A DCA75 workbench for macOS, Linux, and Android."
date: 2026-09-06T09:00:00-05:00
lastmod: 2026-09-06T09:00:00-05:00
draft: false
slug: "sightings"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "sightings-7c05a476597576e257b79524b1c1936f"
weight: 20
toc: true
seo:
  title: "Sightings, a DCA75 Workbench"
  description: "Companion app for the Peak Atlas DCA75 semiconductor analyser with curve tracing, part binning, and a local readings database."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Platforms:** macOS, Linux, Android (USB host / OTG). Built with Flutter and Dart.

## Why

The [Peak Atlas DCA75](https://www.peakelec.co.uk/acatalog/dca75-dca-pro-semiconductor-analyser.html)
is a wonderful little semiconductor analyser, but the official companion
software is Windows only. I wanted to use it from the Mac on my bench, from a
Linux box, and from a phone with an OTG cable, and I wanted every reading kept
somewhere I could search later.

## What it does

- **Identify.** Press *Test* in the app or the button on the unit. Readings
  are decoded and saved immediately, or held as a draft you can tag with a
  part number and bin before saving.
- **Curves.** Ic/Vce families, hFE vs Ic, Id/Vds, Id/Vgs, and PN I-V sweeps
  with live plotting, cancel, CSV and PNG export, and overlays of saved sweeps.
- **History.** Filter, tag in bulk, export CSV, delete.
- **Parts.** Per-part and per-bin statistics, histograms, and closest-match
  search for transistor matching.

## How it is built

The protocol was ported from a reference WebUSB client and split into small
packages: a pure Dart protocol layer for frames, opcodes, and decoders; a
transport layer over libusb via `dart:ffi` with fake and replay transports
for testing; a typed device client with a connection controller and sweep
engine; and a SQLite store built on drift. A small CLI can decode, probe,
identify, and bench from the terminal without the app.

## Safety

The app never writes to the unit's firmware, calibration, or serial number.
Those opcodes cannot be constructed in the protocol library, and the EEPROM
write-arm status byte is rejected at the transport. Every error path returns
the unit to its leads-safe state.
