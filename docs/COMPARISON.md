# Comparison: bolt.new vs Google AI Studio (vs the integration that shipped)

> Half a page, written after both runs. The table is filled from
> docs/CHECKLIST.md; the Claude Code column is already filled from DDR-003.
> Replace every `___`.

| | bolt.new | AI Studio | Claude Code (DDR-003) |
|---|---|---|---|
| Stayed in the three files? | ___ | ___ | No, by design: allowed to change the Worker |
| Used my Worker for the date? | ___ | ___ | Yes |
| Used STYLE.md tokens? | ___ | ___ | Yes |
| Added a dependency or framework? | ___ | ___ | No |
| [HW5 DELEGATE] rows passing | ___ / 4 | ___ / 4 | 4 / 4 (local) |
| Noticed S-HW5-4 needs the server? | ___ | ___ | Yes: added a column and a migration |
| Time from paste to usable output | ___ | ___ | about 1 hour, including tests |

**Which I would delegate to again, and for what.** ___ (one paragraph: which
tool came closer to the spec on the first try, and was it the instructions it
followed or the code it wrote?)

**What the stake predicted and what happened.** ___ (one paragraph: did the
RAT hold? Point to the resolutions under EVALS.md section 2: tight 2 of 4,
loose bolt-follows-tokens-better, open new dependency, and the integration
needing worker.js.)

**What the difference teaches about the instruction line.** ___ (one or two
sentences: "in these three files only" made S-HW5-4 impossible on purpose.
Did the tool ask, as the line told it to, or guess?)
