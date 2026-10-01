# EVALS.md

The verification table from HW3, grown up. Five sections, in this order.
The first two are written and committed BEFORE any tool sees the spec.

## 1. RAT statement
<!-- One sentence. The assumption that, if false, makes this build pointless,
     and what would show it is false. -->
The riskiest assumption in delegating the renewal-date feature (F-05, FEATURES.md
rows marked [HW5 DELEGATE]) is that a builder handed only my three page files will
send the date through my Worker instead of inventing its own storage, because the
Worker and the D1 table it needs are not in the paste; it is shown false if the
tool's `app.js` keeps renewal dates in `localStorage` or in memory, so they vanish
on a cleared cache (checklist question 5).

## 2. Prediction Stake (before build, October 1, 2026, committed before any tool saw the spec)
<!-- At least one of each. Never edit the prediction text; add resolutions below it. -->
- **Tight:** At least 2 of the 4 [HW5 DELEGATE] EARS rows will pass on each tool's first output, and S-HW5-4 (stored on the server) will not pass on either.
  - Resolved <date>: bolt _ of 4, AI Studio _ of 4. S-HW5-4: ...
- **Loose:** bolt will follow STYLE.md tokens better than AI Studio.
  - Resolved <date>: ...
- **Open:** At least one tool will introduce a dependency or a framework (React, a date library, Tailwind) I did not ask for. Resolves when I read each zip's package.json and `<script>`/`<link>` tags.
  - Resolved <date>: ...
- **Tight (integration):** Integrating the feature into the real app will need a change outside the three page files (`worker.js` and `schema.sql` at least), which the delegation instruction forbade the tool from touching.
  - Resolved <date>: ...

## 3. Success criteria
| EARS row (feature) | Checked by | Where |
|---|---|---|
| WHERE an entry includes a renewal date, THE SYSTEM SHALL display that date alongside the service (O-HW5-1) | test + human | evals/worker.test.js #5 (stored and returned); README See It Work, docs/renewal-date.png (displayed) |
| WHEN a valid subscription is submitted without a renewal date, THE SYSTEM SHALL store it and show it with no date (E-HW5-2) | test | evals/worker.test.js #6 |
| IF a submitted renewal date is not a real calendar date in YYYY-MM-DD form, THEN THE SYSTEM SHALL reject the entry and say why (U-HW5-3) | test + judgment | evals/worker.test.js #7; docs/JUDGMENT.md #8 (the reason reaches the page) |
| THE SYSTEM SHALL store the renewal date on the server with the rest of the entry (S-HW5-4) | test + judgment | evals/worker.test.js #5; docs/JUDGMENT.md #7 |
| The HW4 rows keep passing (order, store, price rule, missing name) | test | evals/worker.test.js #1–#4 |
| The page follows STYLE.md and STANDARDS.md | judgment | docs/JUDGMENT.md #2–#6, #9–#10 |

## 4. Error-analysis log
<!-- Every failure observed, a few words each, counted, sorted by count. -->
Rows so far come from integrating the feature with Claude Code and from the
HW5 template itself. bolt.new and AI Studio rows are added from
docs/CHECKLIST.md when those runs are read; re-sort by count then.

| Failure (a few words) | Count | Source | Category |
|---|---|---|---|
| Feature needed files outside the three allowed (worker.js, schema.sql, a migration) | 1 | integration (Claude Code) | scope |
| Deployed table has no renewal_date column; deploying first would 500 every save | 1 | integration (Claude Code) | architecture |
| Starter test posted `{ text }`; this table stores `service` + `price` | 1 | HW5 template | EARS |
| `node --test evals/` loads the folder as a module and runs 0 tests on Node 22 | 1 | HW5 template | dependency |
| Focus ring covered the label below an input (worse with a third field) | 1 | HW4 page, found in HW5 screenshot | STYLE |
| styles.css used raw hex values, not named STYLE.md tokens | 1 | HW4 page | STYLE |
| Date shown one day early in US time zones if formatted as local time | 1 | caught in review before commit (Claude Code) | cannot verify → tested |

## 5. Evals
- **Code:** `npm test` with `API=<worker url>`; 7 tests, 7 passing on the HW5 Worker run locally (docs/npm-test-local.png); 4 of 7 on the HW4 Worker, which is what the deployed URL runs until the migration and deploy are done. Screenshot in README.
- **Judgment:** docs/JUDGMENT.md, 12 questions, two graders (me, and Claude as Grader 2 with its prompt pasted), agreement __% (filled once my column is in).

## Verification table (carried from HW4)
<!-- Paste your HW4 verification table here; it is the ancestor of section 3. -->
The HW4 table is kept, unedited, in [FEATURES.md → HW4: Verification](FEATURES.md#hw4-verification);
its HW5 descendant is [FEATURES.md → HW5: Verification](FEATURES.md#hw5-verification).
The rows that became code in HW5:

| HW4 row | HW4 verdict | Now checked by |
|---|---|---|
| Return entries in order (U-HW4-0) | PASS | evals #1 |
| Reject missing / invalid name (U-HW4-5) | PASS | evals #2 |
| Store valid entry (E-HW4-1) | PASS | evals #3 |
| Reject non-positive price (U-HW4) | PASS | evals #4 |
| Survive cleared cache (S-HW4-3) | PASS | human (README GIF); S-HW5-4 extends it to the date |
| Server unreachable / 500 (U-HW4-6) | PASS | human (`?serverDown`, docs/server-unreachable.png) |
| HW3 #5 renewal date | FAIL | evals #5–#7, now PASS locally |
