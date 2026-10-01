# FAILURES.md

The most honest file in any repository and the rarest. What went wrong,
what the agent got wrong, what you almost shipped.

- **HW4 → HW5: the focus ring sat on top of the labels.** It passed every HW4 check, because none of them looked at a focused input. It only showed up in the first HW5 screenshot, when a third field made it obvious. Lesson: a screenshot is an eval too.
- **Almost shipped: dates one day early.** `new Date("2026-10-15").toLocaleDateString()` reads the date as midnight UTC, which is still October 14 in Atlanta. It was caught in review, before it was committed, and is now tested in a Los Angeles browser.
- **The template's own test script ran zero tests on Node 22.** "npm test" printed `not ok 1 - evals`, which looks like my Worker failing. It was the script.
