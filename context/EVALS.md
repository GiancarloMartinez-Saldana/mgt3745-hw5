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
| WHEN ..., THE SYSTEM SHALL ... | test | evals/worker.test.js, "..." |
| IF ..., THEN THE SYSTEM SHALL ... | judgment | docs/JUDGMENT.md #8 |
| THE SYSTEM SHALL ... | human | README, See It Work |

## 4. Error-analysis log
<!-- Every failure observed, a few words each, counted, sorted by count. -->
| Failure (a few words) | Count | Source | Category |
|---|---|---|---|
| Buttons used its own blue, not color-primary | 2 | bolt, AI Studio | STYLE |
| | | | |

## 5. Evals
- **Code:** `npm test` with `API=<worker url>`; _ tests, _ passing. Screenshot in README.
- **Judgment:** docs/JUDGMENT.md, _ questions, two graders, agreement _%.

## Verification table (carried from HW4)
<!-- Paste your HW4 verification table here; it is the ancestor of section 3. -->
