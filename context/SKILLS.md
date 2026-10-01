# SKILLS.md

Reusable patterns and delegation guidance, written so an agent (or a
stranger) could apply them next time. Each entry under fifteen lines.
Load-on-demand: an agent reads the heading first and the body only when relevant.

## Pattern: fetch with the failure shown on the page
**When:** any call from app.js to the Worker.
**Do:** check `res.ok`; on failure, read `res.text()` and put it in the
status element with `textContent`; wrap the call in try/catch for network
errors; never throw to the console.
**Because:** localStorage never failed; the network does (ADR-002).

## Delegation guidance: what to paste, what to check first
**Paste, in order:** PROJECT, FEATURES (rows marked), STYLE, STANDARDS, TOOLS, then the current page files. One instruction line naming the files it may touch.
**Check first:** the diff's file list, then innerHTML / concatenated SQL, then whether it used the tokens.
**Also paste:** the instruction line, and say which rows *cannot* be met from the files allowed (S-HW5-4 needs the Worker), so the tool asks instead of inventing storage.
**Reliably wrong (this week, EVALS.md section 4):** changes that need the server (a new column, a migration) when the paste only allows page files; template code written for another schema (`{ text }` vs `{ service, price }`); style details no test looks at (focus ring overlap, raw hex instead of tokens). *Add the bolt / AI Studio rows once read.*

## Pattern: add a field end to end (page → Worker → D1)
**When:** a feature needs one more value stored per entry (HW5: renewal date).
**Do, in order:**
1. EARS rows first, including the unwanted one (what is a bad value?) and "no value" if it is optional.
2. `migrations/NNNN_*.sql` with `ALTER TABLE ... ADD COLUMN`; add the column to `schema.sql` for fresh databases.
3. Worker: validate (400 + reason), `bind()` the value, add it to the `SELECT`.
4. Page: labelled input, send it, render it with `textContent`; dates formatted with `timeZone: 'UTC'`.
5. One eval per EARS row; prove they fail on the old Worker.
6. Deploy order: `npm run db:migrate`, then `npm run deploy`, then `API=... npm test`.
**Because:** deploying the Worker before the column exists turns every save into a 500.
