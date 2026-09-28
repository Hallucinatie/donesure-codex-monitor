# DoneSure

DoneSure is a mobile and Apple Watch companion for developers who run long Codex tasks. When Codex finishes, encounters an error, or needs input, DoneSure sends a clear notification, summarizes the result, and lets the user continue the same task by voice.

**Public prototype:** https://hallucinatie.github.io/donesure-codex-monitor/

## The problem

Long-running Codex tasks do not always finish while the user is at the computer. Important updates can be missed, including successful completion, failures, and requests for additional input. Repeatedly checking the desktop interrupts focused work and reduces the value of running tasks asynchronously.

## The prototype

The prototype demonstrates three connected surfaces:

- **Landing page:** introduces the product and opens the main prototype flows.
- **Apple Watch Journey:** presents a six-step interaction from alert to voice follow-up and confirmed action.
- **Task Monitor:** shows long-running tasks, verified status, notification previews, and device settings.

The Apple Watch experience uses progressive disclosure for complex Codex replies:

1. Show the conclusion and the most important evidence on the watch.
2. Let the user ask a short clarifying question by voice.
3. Move code diffs, logs, and high-impact approvals to iPhone or Mac.

## Core user flow

1. Codex finishes, fails, or requests input.
2. DoneSure verifies the current task state.
3. iPhone and Apple Watch receive an actionable notification.
4. The user reviews a concise summary.
5. The user asks a follow-up or gives the next instruction by voice.
6. DoneSure continues the same Codex task and confirms the result.

## Run locally

This is a static HTML prototype with no build step.

```bash
python3 -m http.server 8000 --directory dist
```

Then open `http://localhost:8000`.

## Deployment

The contents of `dist/` are deployed automatically to GitHub Pages whenever the `main` branch is updated. The deployment workflow is defined in `.github/workflows/deploy-pages.yml`.

## Project structure

```text
dist/
  index.html      Product introduction
  journey.html    Apple Watch interaction journey
  monitor.html    Interactive Codex task monitor
  watch.html      Focused watch prototype
```

## Status

Classroom prototype. The interface is interactive, but it does not connect to a live Codex task or send real push notifications.
