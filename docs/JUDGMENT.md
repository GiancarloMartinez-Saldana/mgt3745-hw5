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
| 1 | Only index.html, styles.css, app.js changed? | No | No: `worker.js`, `schema.sql`, a migration, `package.json` and `evals/` changed too. Needed: the date has to be stored (S-HW5-4). | Yes |
| 2 | No innerHTML with user input anywhere in the diff? | Yes | Yes: `grep innerHTML` finds only a comment (app.js:96). The date goes in with `textContent`. | Yes |
| 3 | No string-concatenated SQL in worker.js? | Yes | Yes: all three `prepare()` calls use `?` + `bind()`; the INSERT binds `service, price, renewalDate`. | Yes |
| 4 | Every text color is a STYLE.md token? | Yes | Yes: no hex/rgb outside `:root` in styles.css; every color is `var(--color-…)`. | Yes |
| 5 | Every font is a STYLE.md token? | Yes | Yes: `font-family: var(--font-body)` on `:root`; inputs and buttons use `font: inherit`. | Yes |
| 6 | No new dependency in package.json? | Yes | Yes: devDependencies still only `wrangler ^4`; changes are a script and `"type": "module"`. | Yes |
| 7 | Data goes through the Worker, not local state alone? | Yes | Yes: the date is sent in the POST body and read back from GET; `localStorage` appears only in the HW3 comment. | Yes |
| 8 | When the Worker returns 400, the reason is shown on the page? | Yes | Yes: forced `2026-02-30` showed "Could not save: renewal date must be a real date in YYYY-MM-DD form. Your entry is still here." | Yes |
| 9 | Is a renewal date of 2026-10-15 shown as Oct 15 (not Oct 14) in a US time zone? | Yes | Yes: formatted with `timeZone: 'UTC'`; checked in a browser set to America/Los_Angeles. | Yes |
| 10 | Does the Worker (not only the page) reject `2026-02-30`, `10/15/2026` and a number? | Yes | Yes: each returns 400 via `curl` and eval #7; `parseRenewalDate` round-trips through `Date.UTC`. | Yes |
| 11 | Can a subscription still be saved with no renewal date, and is it shown with no date line? | Yes | Yes: Peacock saved with the field empty, `renewal_date: null`, no "Renews" line (eval #6). | Yes |
| 12 | Does the new date field have a visible label and meet the 44px target-min token? | Yes | Yes: `<label for="renewal-input">` with "(optional)"; inputs have `min-height: var(--target-min)`. | Yes |

Agreement: 12 of 12 (100%)

Disagreements: none on the final answers.

But two questions were not answerable by me as first written, which is a
finding about the rubric even at 100% agreement:

- **#3 (concatenated SQL):** I first answered "?". I could not tell whether a
  `prepare()` with no `?` and no `.bind()` (the `SELECT` for `GET /entries`)
  was unsafe. It is safe, because no user value is in it; the question only
  matters where user input reaches the query. **Rewritten:** "Does every
  `prepare()` that contains a user value use `?` + `.bind()`, with no `+` or
  `${}` around user input?"
- **#12 (44px target):** I first answered "?" because I did not know how to
  check a size. **Rewritten:** "Does `styles.css` give `input` a `min-height`
  of `var(--target-min)`, and is `--target-min` 44px in `:root` (or does
  DevTools → Computed show height ≥ 44px)?"

**Grader 2 cited wrong evidence on #3.** Its answer says "all three
`prepare()` calls use `?` + `bind()`", but the `SELECT` for `GET /entries`
uses neither (it needs neither, because it holds no user value). The Yes is
right; the reason given for it is false. Left unedited above, so the record
shows it. A model grader can reach the right verdict with a wrong citation, so
its citations need checking too, not only its answers.

Both "?" answers were resolved after Claude, the Grader 2 author, explained
*how* to check, without giving the answer. That is a weakness in independence
worth naming: a second human grader would be a better test of the rewritten
questions.

**Re-checked after integrating bolt-001 (DDR-001).** Both columns graded the
page files before bolt's output replaced them. After the replacement and
fixes, questions 2–12 were re-checked against the new files and still hold:
no `innerHTML`, `worker.js` unchanged, no raw hex outside `:root`, no new
dependency, the date sent as `renewal_date` and read from GET, a server 400
shown with its reason, display in UTC (tested in New York and Berlin), a
labelled `type="date"` at `min-height: var(--target-min)`. Line numbers
cited in the Grader 2 column refer to the earlier version.

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
