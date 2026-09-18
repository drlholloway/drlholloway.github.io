---
title: "Fretman"
description: "Fretman is a Flutter app for learning the notes and chords on a guitar or bass fretboard through quick drills and a guided learning path. iOS, Android, macOS, and Linux."
summary: "Learn the fretboard through quick drills and a guided path."
date: 2026-09-18T00:00:00-05:00
lastmod: 2026-09-18T00:00:00-05:00
draft: false
slug: "fretman"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "fretman-2d54463b0dac41748b8c6bd16ad7ee2d"
weight: 30
toc: true
seo:
  title: "Fretman, a Fretboard Trainer"
  description: "A guitar and bass fretboard trainer with note and chord drills and a guided learning path, for iOS, Android, macOS, and Linux."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Source:** [github.com/drlholloway/fretboardtrainer](https://github.com/drlholloway/fretboardtrainer) (Flutter and Dart, PolyForm Shield)

**Platforms:** iOS, Android, macOS, Linux. Builds are on the
[Releases page](https://github.com/drlholloway/fretboardtrainer/releases), and
the [Wiki](https://github.com/drlholloway/fretboardtrainer/wiki) covers
installation, the learning path, drills, chords, and tunings.

## Why

Knowing where every note lives on the neck is the thing that makes the rest
of guitar and bass theory click, and it is mostly a matter of repetition. I
wanted a trainer that fits into five spare minutes, works on the phone and on
the desk, and knows about non-standard tunings and real chord shapes rather
than just the natural notes on the low E string.

Fretman is Mothman's musical cousin.

## What it does

- **Learn.** A guided path in the style of a language app. It starts with
  guitar in E standard and teaches the notes on the low E and A strings, then
  the octave shapes that map those notes onto every other string, then the
  remaining strings, with a test at the end of each unit. From there it moves
  on to the whole fretboard mixed, open chords, power chords, barre chords,
  and finally drop D. Bass follows the same path without open and barre
  chords.
- **Drill.** Free practice with five question types in any mix: fret to note,
  note to fret, octave shapes, chord to name, and name to chord. Options
  cover fret range, natural notes only, which strings, which chord families,
  and how many questions.
- **Instruments and tunings.** Guitar with six or seven strings, bass with
  four to six, tuning presets such as drop D and C standard, sharps or flats,
  and a left-handed fretboard. The drill uses the chosen tuning and names
  every chord from what it actually sounds.

## How it is built

The music theory lives in a pure Dart package: notes, tunings, instruments,
chord voicings and naming, drills, and the curriculum. The Flutter app sits on
top of it, and Linux packaging (AppImage, Flatpak, tarball) is kept alongside.
Keeping the theory free of UI means it can be tested exhaustively, which is
where most of the bug reports go.
