# Agent entry — DHA Exam Prep Hub

## Identity and scope

The source of truth is `bouncemonster/DHA-Exam-Prep-Hub` on its current GitHub default branch. This is a browser-based independent study application, not an official examination service, a backend platform or clinical software. Do not replace it with a local exam document or another project's source.

Read [README.md](README.md), inspect the current `index.html` and review the latest relevant Git history before changing behavior. The application currently combines markup, styles, question content and JavaScript in that file. There is no package manifest or declared automated app-test command; do not invent npm setup or a passing CI result.

## Start or resume

Confirm repository identity and branch before editing:

```sh
git remote get-url origin
git status --short --branch
git log -5 --oneline
```

Inspect origin locally; redact embedded credentials before sharing its output. Compare with current GitHub through an authorized read, without resetting or pulling over uncommitted work. Read the existing issue or handoff before starting a second implementation of the same task.

Record one outcome, affected file sections and intended checks. If another IDE/agent owns those sections, coordinate or serialize edits. A lost chat does not prove another worker stopped. Do not create branches, worktrees, deployments or new infrastructure merely to edit documentation.

## Local inspection

No build step is required. From the repository root, serve a disposable local preview:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Open `http://127.0.0.1:8000/` and stop only this task's server with `Ctrl+C` when finished. Check the port first. Use a fresh browser profile for demo/test progress; do not erase a user's existing local storage.

Opening `index.html` as a file and serving it over HTTP are different origins. Browser-local progress must not be described as account synchronization or a server backup.

## Review changes by risk

For UI or behavior changes, inspect the activity-to-results flow, timer, correct/incorrect answers, configured early termination, repeated attempts and persisted progress. Review keyboard use, narrow/mobile and desktop layouts and both themes. Identify the browser, viewport, source revision and exact flows actually checked.

For question/content changes, isolate the educational diff from visual changes. Identify the question and provide a reliable dated source. Do not copy protected exam banks, invent official requirements or treat the app's scoring rules as the official exam format. Do not remove the independent-study limitation from the README.

A screenshot proves only its captured state. Do not present illustrative art, a reconstructed UI, historical images or a missing browser run as fresh acceptance evidence. Use synthetic attempts without personal information for demonstrations.

## Handoff

Use the current issue or a concise existing task record; do not add a competing board or store private conversation history. Record the source revision, changed sections/files, test results, publication commit and readback, remaining local work, worker ownership and one next step.

Distinguish PASS, FAIL, NOT RUN and BLOCKED. An absent test suite is NOT RUN, not PASS. A created commit must be visible on the intended branch before publication is reported as complete.

Preserve the app's source, user data and existing rights. No dependency installs, hosting changes, new license, real account activity or outbound integrations are authorized by a documentation-only change. Read any nearer instruction file before editing its directory.
