# Judgment Eval: renewal date (F-05, HW3 #5)

The seven checklist questions, extended to twelve, specific to this feature
and this STYLE.md. Two grader columns. Grader 2 is a model, so its prompt is
pasted at the bottom; every disagreement is marked. Agreement under 80 percent
is a finding about the rubric, logged in EVALS.md.

**What is graded:** the integrated feature, the diff from commit `cac566d`
(HW4 work brought in) to the HW5 feature commits: `index.html`, `styles.css`,
`app.js`, `worker.js`, `schema.sql`, `migrations/0001_add_renewal_date.sql`,
`package.json`. The bolt.new and AI Studio zips are graded with the shorter
docs/CHECKLIST.md, not this file.

**Independence note:** Grader 2 is Claude, the same agent that integrated the
feature (DDR-003). That makes it the least independent grader possible, so
every Grader 2 answer below cites the line or the command that decides it,
and the "You" column is graded without looking at Grader 2's.

| # | Question (yes/no) | You | Grader 2 (Claude) | Agree? |
|---|---|---|---|---|
| 1 | Only index.html, styles.css, app.js changed? | | No: `worker.js`, `schema.sql`, a migration, `package.json` and `evals/` changed too. Needed: the date has to be stored (S-HW5-4). | |
| 2 | No innerHTML with user input anywhere in the diff? | | Yes: `grep innerHTML` finds only a comment (app.js:96). The date goes in with `textContent`. | |
| 3 | No string-concatenated SQL in worker.js? | | Yes: all three `prepare()` calls use `?` + `bind()`; the INSERT binds `service, price, renewalDate`. | |
| 4 | Every text color is a STYLE.md token? | | Yes: no hex/rgb outside `:root` in styles.css; every color is `var(--color-…)`. | |
| 5 | Every font is a STYLE.md token? | | Yes: `font-family: var(--font-body)` on `:root`; inputs and buttons use `font: inherit`. | |
| 6 | No new dependency in package.json? | | Yes: devDependencies still only `wrangler ^4`; changes are a script and `"type": "module"`. | |
| 7 | Data goes through the Worker, not local state alone? | | Yes: the date is sent in the POST body and read back from GET; `localStorage` appears only in the HW3 comment. | |
| 8 | When the Worker returns 400, the reason is shown on the page? | | Yes: forced `2026-02-30` showed "Could not save: renewal date must be a real date in YYYY-MM-DD form. Your entry is still here." | |
| 9 | Is a renewal date of 2026-10-15 shown as Oct 15 (not Oct 14) in a US time zone? | | Yes: formatted with `timeZone: 'UTC'`; checked in a browser set to America/Los_Angeles. | |
| 10 | Does the Worker (not only the page) reject `2026-02-30`, `10/15/2026` and a number? | | Yes: each returns 400 via `curl` and eval #7; `parseRenewalDate` round-trips through `Date.UTC`. | |
| 11 | Can a subscription still be saved with no renewal date, and is it shown with no date line? | | Yes: Peacock saved with the field empty, `renewal_date: null`, no "Renews" line (eval #6). | |
| 12 | Does the new date field have a visible label and meet the 44px target-min token? | | Yes: `<label for="renewal-input">` with "(optional)"; inputs have `min-height: var(--target-min)`. | |

Agreement: __ of 12 (__%)

Disagreements (fill after grading; for each, say which wording two people
read differently and how the question was rewritten):

-

## Grader 2 prompt (if a model)
```
You are grading a code change against a yes/no rubric. The change adds an
optional renewal date to a subscription dashboard (index.html, styles.css,
app.js, worker.js on Cloudflare Workers + D1). The rules it must follow are in
context/STYLE.md (the token list in the frontmatter), context/STANDARDS.md and
context/CLAUDE.md. The diff is from commit cac566d to HEAD.

For each of the 12 questions in docs/JUDGMENT.md, answer Yes or No. After each
answer, cite the file and line, or the command and its output, that decides
it. If you cannot decide from the code alone, run the code (npm run dev, curl,
a browser) and say what you ran. Do not answer from what the code is supposed
to do; answer from what it does. Do not soften a No.
```
