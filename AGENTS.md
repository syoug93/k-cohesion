# k-cohesion Codex Instructions

This repository publishes a public GitHub Pages schedule board at:

https://syoug93.github.io/k-cohesion/

## Editing Rules

- Keep `index.html` and `국민통합위_3건_간트차트.html` identical unless the user explicitly asks otherwise.
- `index.html` is the GitHub Pages entry point.
- When changing schedule data, update both the overview chart and the gender WBS chart only when the request affects both.
- Preserve the two-tab structure:
  - `통합 일정`
  - `세대젠더 상세 WBS`
- Preserve the dynamic today line based on `new Date()`. Do not hard-code today's date.
- For Slack requests, use the Slack thread as context, but summarize the interpreted schedule changes in the final answer.

## Verification

Before finishing a schedule change:

- Run `git diff --check`.
- Confirm there are no stale hard-coded today labels such as `2026-06-09`.
- Confirm `index.html` and `국민통합위_3건_간트차트.html` have the same content.
- If possible, serve the page locally and verify that both tabs render.

## Calendar Sync Policy

Calendar-driven updates should be treated as proposals unless the user explicitly asks for fully automatic commits.

Recommended flow:

1. Read Google Calendar events from a dedicated project calendar or iCal feed.
2. Match only events with clear project markers such as `[세대젠더]`, `[경제양극화]`, or `[경청소통]`.
3. Convert matched events into schedule board updates.
4. Open a pull request or commit with a clear summary.
5. Never delete existing schedule items unless the calendar event is explicitly cancelled or the user asks for deletion.

If the request comes from Slack, prefer a concise final reply with:

- changed events
- files changed
- public link
- any assumptions
