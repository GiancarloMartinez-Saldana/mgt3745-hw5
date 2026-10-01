# Reading a Delegated Build: the seven questions

Binary answers only. Each No is a row in the EVALS.md error-analysis log.

Feature: renewal date (F-05, FEATURES.md rows marked [HW5 DELEGATE]).
The bolt and AI Studio columns are read from `delegated/*.zip`. The third
column is the integration that ships (DDR-003), graded with the same seven
questions so the three can be compared; it was allowed to touch the Worker,
the two builders were not.

| # | Question | bolt | AI Studio | Claude Code (integration) | Log category |
|---|---|---|---|---|---|
| 1 | Did it touch only the files you named? | | | Yes (the 8 named in DDR-003) | scope |
| 2 | Any `innerHTML` with user input? Any concatenated SQL? (Yes is bad) | | | No / No | STANDARDS |
| 3 | Are colors and fonts the STYLE.md tokens, or its own? | | | Tokens (every value is a `var(--…)`) | STYLE |
| 4 | Did it add a dependency? Which? What does that package do? | | | No | dependency |
| 5 | Does it call your Worker, or did it invent its own storage? | | | Worker (POST and GET `/entries`) | architecture |
| 6 | Run the feature's EARS rows by hand. How many pass? | / 4 | / 4 | 4 / 4 (local Worker) | EARS |
| 7 | Is there anything you cannot explain? Name the line. | | | No line; the deployed D1 table is not inspectable (DDR-003) | cannot verify |
