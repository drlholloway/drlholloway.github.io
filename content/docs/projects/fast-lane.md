---
title: "Fast Lane"
description: "A Go TUI that watches your GitHub repositories and hands routine maintenance, like PR reviews, CI fixes, Dependabot bumps, review requests and mentions, to Claude Code sessions."
summary: "GitHub maintenance on autopilot, with you in the loop."
date: 2026-10-21T09:00:00-05:00
lastmod: 2026-10-21T09:00:00-05:00
draft: false
slug: "fast-lane"
menu:
  docs:
    parent: "projects-35a2864c314e4367eb1684bfe126a967"
    identifier: "fast-lane-8742714c622e4426800648c1d9eb240c"
weight: 50
toc: true
seo:
  title: "Fast Lane"
  description: "A Go TUI that watches your GitHub repositories and hands PR reviews, CI fixes, Dependabot bumps, review requests and mentions to Claude Code sessions."
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

**Source:** [github.com/drlholloway/fast-lane](https://github.com/drlholloway/fast-lane) (Go, PolyForm Shield) · **Docs:** [the wiki](https://github.com/drlholloway/fast-lane/wiki)

## Why

Every repo I own grows a little pile of chores: Dependabot bumps waiting for a
merge, a PR whose CI broke overnight, a reviewer's comments to work through, a
mention I missed. None of it is hard, and all of it interrupts whatever I was
actually doing.

Claude Code is very good at exactly this kind of work. What was missing was
something to notice the work as it shows up, hand it over with the right
instructions and the right permissions, and come get me only when a decision is
really mine.

## What it does

- **Watches your repos.** Pull requests, issues, Dependabot alerts and code
  scanning alerts on the repos you pick, using the GitHub CLI's login.
- **Reacts to what changes.** Triggers fire when a PR is opened, gets changes
  requested, fails CI, hits a merge conflict or gets a comment, and when your
  review is requested, you're mentioned, or you're assigned, on any repo.
- **Rules decide what runs on its own.** Auto rules filter by severity, labels,
  authors, drafts and bots, and set each session's prompt, model, effort, and
  the actions Claude may take without asking: edit, push, update a PR, comment,
  review, merge, and so on.
- **Asks when it should.** Anything not pre-approved opens a permission dialog
  in the TUI. Questions Claude asks show up there too.
- **Never touches your checkout.** Fast Lane finds your local clones and gives
  every session its own git worktree, so your working tree, branch and
  uncommitted changes are left alone.
- **Set up in the app.** A Rules tab edits the auto rules, and a Settings tab
  checks the prerequisites and edits every setting.

## A taste

```sh
go install github.com/drlholloway/fast-lane@latest
fast-lane
```

Two rules for your own PRs: fix CI when it breaks, and work through review
feedback, pushing to the PR branch and replying to each comment:

```json
"auto_rules": {
  "pull_request:checks_failed": { "authors": ["you"], "allow": ["edit", "update_pr"] },
  "pull_request:changes_requested": { "authors": ["you"], "allow": ["edit", "update_pr", "comment"] }
}
```

The [recipes](https://github.com/drlholloway/fast-lane/wiki/Recipes) page in
the wiki has more, from merging Dependabot PRs once they're green to patching
high-severity alerts.
