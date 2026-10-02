# Comparison: bolt.new vs Google AI Studio (vs the integration that shipped)

| | bolt.new | AI Studio | Claude Code (DDR-003) |
|---|---|---|---|
| Stayed in the three files? | Almost: one empty lockfile | No: 10 extra files | No, by design: allowed to change the Worker |
| Used my Worker for the date? | Sent it, under a name nothing stores | Sent it under two guessed names | Yes |
| Used STYLE.md tokens? | No: raw hex, 14.4px text | Added no styles of its own | Yes |
| Added a dependency or framework? | No | Yes: 19 packages (React, Tailwind, Gemini SDK…) | No |
| [HW5 DELEGATE] rows passing | 1 / 4 | 2 / 4 (4 / 4 on the HW5 Worker) | 4 / 4 (local) |
| Noticed S-HW5-4 needs the server? | No: claimed it persists | No: claimed sending it in the POST was enough; did not ask | Yes: added a column and a migration |
| Time from paste to usable output | ~11 min | ~16 min | about 1 hour, including tests |

**Where the outputs agreed.** Given the same paste and the same instruction line, both tools made the same core choices: a labelled text box with a `YYYY-MM-DD` placeholder instead of a date picker, a camelCase field name (`renewalDate`) that my Worker does not store, a regex plus a round-trip check that rejects impossible dates like February 30, `textContent` for the new line, and no `localStorage`. Both sent the date to my Worker in the POST body and assumed the server would keep it. Neither asked, although the instruction said to ask before changing anything else, and both summaries said the storage row was done.

**Where they differed.** bolt stayed much closer to the boundaries I gave it (one empty lockfile), while AI Studio handed back 10 extra files and 19 packages, including React, Tailwind, and a Gemini SDK, that my page never uses. bolt's date check mixed local time and UTC, so it rejects every valid date for anyone east of UTC and an impossible month causes a console crash; AI Studio's check works in UTC and never threw. bolt formatted the date ("Renews October 15, 2026") with its own 14.4px raw-hex style; AI Studio printed the raw string ("renews 2026-10-15") and added no styles. AI Studio also hedged by sending the date under both `renewalDate` and `renewal_date`. Against my HW4 Worker, bolt passed 1 of 4 rows and AI Studio 2 of 4. bolt's output is the one integrated (DDR-001), because the assignment builds on bolt; that is not a ranking.

**Which Loose prediction resolved.** I predicted that bolt would follow my STYLE.md better than AI Studio. It resolved the other way: bolt used a raw hex color and 14.4px text even though my minimum is 16px, while AI Studio added no styles of its own. My Open prediction, that a tool would sneak in a dependency, also resolved: AI Studio did, by much more than I expected.

**What the agreement says about my spec.** Because two different tools independently chose the same text box, the same camelCase name, and the same assumption that the server would store the date, those gaps are in my FEATURES.md rows, not in either tool: my spec never named the field, the input type, or the fact that storage needs a Worker change.
