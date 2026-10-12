<div align="center">

# DHA Exam Prep Hub

**Practice, review and build a more focused study routine.**

A browser-based exam-preparation app with timed practice, answer feedback and progress tracking.

[Open the application file](index.html) · [Getting started](#getting-started) · [Hosted build](#hosted-build) · [How it works](#how-it-works) · [For contributors](#for-contributors)

</div>

---

DHA Exam Prep Hub brings a practice-question interface, exam simulation, study notes and weak-area tracking into one static application. It is designed to run in a browser without a separate application server, database or package installation.

> **Independent study aid, not an official examination service.** The questions, scoring rules and study material in this repository must not be treated as current DHA requirements, an official question bank, clinical guidance or a guarantee of passing. Verify examination requirements with the relevant authority and review educational content independently.

## What is included

| Area | In the application |
| --- | --- |
| Exam practice | A timed exam flow, answer selection, scoring and a finish/results path. |
| Answer feedback | Correct/incorrect answer states and explanations in the practice logic. |
| Progress | Browser-local tracking of attempts and areas that need more work. |
| Study support | Guidelines and time-management notes alongside the practice experience. |
| Presentation | Responsive styling, light/dark theme rules and optional sound effects. |

These describe the checked-in application, not a claim that every browser and interaction has passed an independent acceptance test.

## Getting started

**No build step is required.** Download or clone the repository, then open `index.html` in a modern browser.

```sh
git clone https://github.com/bouncemonster/DHA-Exam-Prep-Hub.git
cd DHA-Exam-Prep-Hub
```

Open the `index.html` file from that directory. Use the same browser and browsing context to keep working with the same locally stored progress.

For development, a local HTTP server can provide a consistent origin. With Python 3 installed, run this from the repository directory:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Then visit `http://127.0.0.1:8000/`. Opening the file directly and serving it over HTTP are different browsing contexts; do not assume they share saved progress.

GitHub Pages or another static host can serve the application. A hosted build of this repository does exist — [dha-exam.moonsugar.space](https://dha-exam.moonsugar.space/) — and the next section states exactly what is published and what is not.

## Hosted build

[`https://dha-exam.moonsugar.space/`](https://dha-exam.moonsugar.space/) serves this repository's single `index.html`, pinned to revision `1ca3ca8`, as one of six project subdomains published on 2026-10-12. The build, the hosting and the DNS belong to the sibling **`moonsugar.space`** repository, not to this one.

What the published page adds to the file in this repository:

- a small back-link pill to the Moonsugar site and a disclosure bar stating that this is author-prepared practice, not an official DHA trainer. The bar is dismissible and collapses to a corner chip, so it never permanently covers the interface.
- a project favicon in the platform's own identity, and the standard security response headers.
- one content rewrite: the source declares its font through `https://r2cdn.perplexity.ai/fonts/FKGroteskNeue.woff2`, so the build copies that file from the other repository's `apps-assets/dha-exam/` store and rewrites the reference to `/assets/fonts/FKGroteskNeue.woff2` on the subdomain. The published page therefore **fetches nothing outside the subdomain** and keeps working offline once loaded. Text links that point outward (the DHA authority page, the Moonsugar site) are navigations, not requests made on load. The file in this repository is left as authored; the rewrite happens in the build.

What is **not** published: `index_dha_test_v1.2.html`, `index_dha_test_v1.3.html` and the instruction files are excluded from the artifact by name. Publishing a change here does not move the subdomain — the release lane rebuilds the revision pinned in that repository's `apps.lock.json`, and pulling the subdomain's ingress rule and DNS record is the rollback. Availability was checked over public HTTPS on 2026-10-12; no uptime or examination-outcome claim is made.

## How it works

```text
Open the app → Choose a study activity → Answer questions → Review results → Revisit weak areas
```

The repository has a deliberately small footprint:

| File | Responsibility |
| --- | --- |
| [`index.html`](index.html) | Application markup, styling, question content and browser-side logic; the only file the hosted build publishes. |
| [`index_dha_test_v1.2.html`](index_dha_test_v1.2.html), [`index_dha_test_v1.3.html`](index_dha_test_v1.3.html) | Archived earlier browser builds kept for comparison; not served anywhere. |
| [`.gitignore`](.gitignore) | Local files excluded from version control. |
| [`README.md`](README.md) | Project overview and contributor guidance. |
| [`AGENTS.md`](AGENTS.md), [`CLAUDE.md`](CLAUDE.md) | Working instructions for coding agents; `CLAUDE.md` imports `AGENTS.md`. |

There is no checked-in backend, package manifest or automated test suite in the current repository tree.

## Progress and limitations

Progress is stored locally in the browser; there is no documented account-based synchronization or server backup. Clearing browser data, using private browsing or changing devices can make saved progress unavailable. Do not use this app as the sole record of your preparation.

The simulator has its own question-selection and scoring logic, including an automatic stop when its configured error limit is reached. Those implementation choices are **practice rules**, not evidence of the official exam format.

## For contributors

Changes to the interface and question content currently live in the same file. Keep patches focused so educational changes can be reviewed separately from styling or behavior changes.

Before submitting a change, check the start-to-results flow, timer behavior, correct and incorrect answers, early termination, repeated attempts and progress persistence. Review both themes, keyboard interaction and a narrow mobile viewport. These are a manual review checklist, not automated checks supplied by this repository.

For question corrections, identify the affected question, explain the proposed correction and provide a reliable source and its date. Do not add copied examination material, personal data or unsupported claims about official requirements.

## Licensing

No standalone license file is present in the inspected repository. This README does not add a license or grant redistribution rights; clarify permitted use with the repository owner before redistribution.

---

**По-русски:** приложение для самостоятельной подготовки в браузере: тренировочные вопросы, симуляция экзамена и локальный прогресс. Для запуска откройте `index.html`; установка серверной части не нужна. Это независимый учебный инструмент, а не официальный сервис DHA и не подтверждение актуальных экзаменационных требований.
