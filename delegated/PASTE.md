# Delegation paste (HW5 Session B)

How to use: in bolt.new (GitHub **not** connected) and then in Google AI Studio
(Build tab), select everything from the line `===== BEGIN PASTE =====` to the
end of this file and paste it as one message. Same paste, same instruction
line, both tools. Download bolt's zip to `delegated/bolt-001.zip` and AI
Studio's to `delegated/aistudio-001.zip`, and commit them unmodified.

This file was generated from the repository *before* the feature was
integrated (commit after "EVALS.md: RAT and stake before build"), so the
tools see the same starting point the stake predicted against.

===== BEGIN PASTE =====

Implement the feature marked in FEATURES.md, in these three files only. Follow STYLE.md and STANDARDS.md. Do not add dependencies. Ask before changing anything else.

The rows to implement are marked [HW5 DELEGATE] near the end of FEATURES.md.

---

## FILE: context/PROJECT.md

````markdown
# PROJECT

Status: ACTIVE.

# HW1: Reframing a Wicked Problem

Name: Giancarlo Martinez-Saldana
Date: 9/3/26


## 1. Candidate Problem  
`20 pts`


I didn't like my original major which was biomedical engineering because all the work and studying I was doing didn't feel like something I wanted to actually do for the rest of my life. Everyday I worked towards something I knew wasn't going to fulfill me.

---

## 2. Wickedness Test  
`25 pts`

1. No stopping rule.
There's no moment where I can definitively say "this is solved." I could feel content in ITM for a year and still wonder later whether I made the right choice (I often do). Even after graduating and getting a job doesn't close it, fulfillment is something you keep re-checking, not a box you tick once.

2. Solutions are good/bad, not true/false.
There's no way to prove BME was "wrong" or ITM is "right" in an objective sense. I can only judge fit against criteria (day-to-day tasks, pace, people, autonomy) these are themselves value judgments, not facts.

3. No exhaustively describable solution set.
You can't enumerate every possible path and rank them: majors, double majors, minors, gap semesters, self-teaching, choosing a job over a major. ITM is one point in an open-ended space.

4. Multiple valid explanations of the discrepancy.
Why didn't BME work? It could honestly be: wrong subject matter, wrong pace/workload, wrong learning style (heavy lab/problem-set work vs. something more people-facing), or simply not having lived enough of the field yet to know if the dissatisfaction was BME-specific or general burnout. These aren't mutually exclusive and you can't run a controlled experiment to isolate the cause.

Verdict: The problem is wicked, but not entirely, the diagnosis (why BME didn't work) is the wicked core, while the action (switching to ITM) was a controlled decision made under uncertainty.

---

## 3. Three Framings  
`30 pts`

Framing A (the obvious one): BME was the wrong major for me; Business Administration with an ITM concentration is a better structural fit.

Framing B (stakeholder shift): This is also a problem for whoever is investing in my education (family, or future employers reading a transcript with a major switch on it) who need evidence that this wasn't a reaction to short-term discomfort but a genuine correction.

Framing C (goal shift): The real goal isn't finding the right major, it's identifying what fulfilling work feels like for me operationally (autonomy? tangible output? working with people vs. systems? pace?), so I can evaluate any path against that, not just the next major I try.

---

## 4. Commit and Justify  
`included in Framings`

Chosen framing:Framing B

Why: I'm committing to the framing that this is a validation problem, not just a personal-fit problem. Switching from BME to Business Administration/ITM because the daily work didn't feel fulfilling is a real signal, but it's a signal only I can currently see. Anyone reading my transcript, or anyone who supported the original BME choice, sees a switch with no evidence attached, it could read as commitment to a better fit, or it could read as giving up under pressure, and from the outside those look identical. The problem isn't "did I pick the right major" anymore; it's about how do I generate proof, for myself and for others, that this was a reasoned correction rather than an escape. That reframes what I need to build, not more introspection about ITM, but concrete evidence (an internship, a project, a portfolio piece) that tests the ITM choice against real work and gives skeptics (including a future version of me re-reading this) something other than my word to go on.

What this framing makes invisible: Choosing the validation framing means I stop asking whether ITM is actually the right fit and start asking only whether I can defend it. Those aren't the same question. It's possible to build a very convincing case for a choice that's still wrong for me (a strong internship, a clean transcript narrative) without that proof ever touching the question of whether I'd feel the same daily dread in ITM that I felt in BME, just on a longer fuse. This framing also quietly centers other people's judgment (family, employers, friends) as the thing I'm solving for, which risks repeating the exact pattern that may have put me in BME in the first place, optimizing for what looks defensible to others rather than checking in on what's actually sustainable for me. Framing 3, the goal-shift toward figuring out what fulfillment operationally means for me, is the one I'm setting aside, and it's worth admitting that's the harder, slower question I may be avoiding by picking the framing that has a clearer deliverable.

---

## 5. Oath Check  
`15 pts`

The tool I already assumed: Given the validation framing, the tool I catch myself picturing is an ITM internship or a resume-building project, something concrete I can point to as proof for the "haters" that the switch was a reasoned correction, not a retreat.

What would have to be true for it to be justified: That tool is only the right one if the gap I'm actually closing is a credibility gap,  if I already believe ITM fits me, and what's missing is just external proof. If that's the entire truth, an internship is exactly right: it produces the artifact skeptics need. But if I'm honest, part of what's underneath this is still an open question, not just an unproven one, I switched because BME didn't feel fulfilling, and I haven't yet fully tested whether ITM will fulfill me in a working environment, only that it looks better on paper and in early coursework. An internship built purely to generate proof for other people could end up validating a choice before I've validated it for myself. So the real condition is: the internship or project has to be something I choose because it would tell me something new about whether the work suits me, not just something that looks good on a resume. If I catch myself picking the internship for its optics rather than its value to me, then that's the sign I've reached for the tool the audience wants rather than the tool the problem needs.

---

## 6. Adequacy Sketch  
`10 pts`

"Good enough for now" means completing an ITM internship or substantial project where I can track whether the actual day-to-day work, not just the subject matter, felt closer to engaging than dreaded. I'll know I've reached it when I can compare that log against how BME felt and answer honestly whether the difference is in the work itself or just in the relief of having changed something.

---

## AI Use Note

I used claude to help me settle into my three framings.
````

---

## FILE: context/FEATURES.md

````markdown
# Features and specification

## Context

Streaming viewers who already subscribe to multiple platforms face two related but distinct frictions: they lose track of what they're actually paying for (both interviewees underestimated their subscription count when asked directly), and when they can't quickly find something appealing, they default to a low-risk rewatch or leave the platform entirely rather than searching harder (INT-01's Gilmore Girls fallback, INT-02's shift to YouTube). A related thread from INT-02 is a shift toward wanting to watch with focus and in order, rather than passively or out of sequence. The desired progress is for a viewer to make an intentional, low friction choice about what to watch and what to pay for, without needing to open five apps or mentally track five bills.

## Users

PROFILE-01 — College student who shares streaming accounts with roommates and family. Frequently can't decide what to watch and defaults to rewatching a familiar comfort show (Gilmore Girls) rather than risk disappointment on something new. Budget-conscious, shared-account friction includes ads on a roommate's cheaper tier and repeated logouts from an out-of-state location. Evidence: INT-01, JOB-01.
PROFILE-02 — Fraternity member with mostly personal subscriptions. Has shifted from casual, out of order childhood viewing to watching with deliberate focus and intent. Follows a structured decision path (time available → format → Recommended/My List → browse) and, when nothing fits, switches platforms (YouTube), waits, or pirates rather than adding a new subscription. Evidence: INT-02, JOB-02.

## Scope

Included behavior:

A dashboard where a user manually enters or confirms which streaming services they subscribe to and at what price.
A single search/browse view that lets a user filter by mood and format (short vs. long form) across the services they've entered.
A "pick for me" flow with two modes: a low-risk familiar pick, or a filtered new suggestion matched to available time and format.
Visibility into estimated monthly spend across entered subscriptions.

Non-goals:

The app does not log into or scrape streaming accounts via credentials; all subscription data is user-entered.
The app does not stream, host, or link to pirated content, regardless of what INT-02 reported doing.
The app does not execute cancellations or any payment action on the user's behalf, it surfaces information, the user acts on it elsewhere.
The app does not attempt to solve account sharing/login kickout problems (INT-01's HBO Max out-of-state issue), that's a platform side limitation, not something this app can fix.

### Kano hypotheses
Provide at least six features. For each, name the user segment, date, category, and evidence-based reasoning. These are tentative hypotheses, not validated survey findings.

| Feature ID | Feature | Kano hypothesis | Segment / date | Evidence and reasoning |
|---|---|---|---|---|
| F-01 |Subscription cost dashboard (all entered services + total monthly spend)|Must-be|Both segments/ 9/10/26|Both participants underestimated their own subscription count by 1–2 services when asked directly (INT-01: guessed 5, actual 7; INT-02: guessed 4, actual 5). Its absence is already causing quiet confusion; without it, users are surprised by their own spend.|
| F-02 |"Pick for me" - safe mode (surfaces a familiar/rewatched title)|Attractive|PROFILE-01 / 9/10/26|INT-01 described defaulting to Gilmore Girls ~99% of the time as a compromise, not a genuine first choice, an explicit low-effort, low-risk shortcut matches her reported workaround directly.|
| F-03 |Cross-platform mood/format filter (short vs. long-form, across all entered services)|Performance|PROFILE-02/ 9/10/26|INT-02 already performs this filtering manually and sequentially (time available → format → Recommended tab → My List → browse) inside a single app; consolidating it across apps is a direct extension of an existing behavior, and more coverage should map to more satisfaction.|
| F-04 |Per-service "last opened" usage nudges (e.g., "you haven't opened this in 60 days")|Reverse|PROFILE-01 / 9/10/26|INT-01 explicitly said she doesn't consider any subscription useless even if underused, framing each as providing unique value "even if not a lot." A nudge implying she should reconsider low-usage services works against that stated attitude and risks feeling judgmental rather than helpful.|
| F-05 |Manual subscription entry with price and renewal date|Must-be|Both segments / 9/10/26|This is the underlying data source that makes F-01 possible at all; without it, the cost dashboard cannot function. Neither participant mentioned wanting this specifically, which is typical of Must-be features, its absence would be the noticeable failure, not its presence.|
| F-06 |"Why I picked this" reasoning shown on suggestions (e.g., "You've watched this 3 times before" or "Matches: 20 min, comedy, on a service you already pay for")|Attractive|Both segments / 9/10/26|Neither participant asked for this, but it targets what both distrust about picking something new, INT-01 says new choices are "disappointing"; INT-02 relies on curated sources ("been told its good/recommended") rather than blind browsing. A visible reason turns a suggestion into something closer to a trusted recommendation instead of another blind gamble.|

## Behavior

1. On first use, the user manually enters each streaming service they subscribe to, its monthly price, and (optionally) its renewal date (F-05).
2. The dashboard displays the full list of entered services and a running total of monthly spend (F-01).
3. From the dashboard, the user selects "What should I watch?" and chooses one of two modes: Safe pick or Something new.
4. If Safe pick is chosen, the system returns one title (or a select few) that the user has marked as a past favorite and if they have none then the system will choose frequently rewatched, at random or by recency (F-02).
5. If Something new is chosen, the user selects a mood/format filter (short vs. long form; a small set of genre tags), and the system returns a filtered list of titles drawn only from the services the user has entered (F-03).
6. If the filtered list in step 5 returns zero results, the system displays a message stating no matches were found in the user's current subscriptions, rather than silently returning nothing or suggesting an unowned service.
7. Whenever the system returns a suggested title in either mode, it displays a one-line reason for that suggestion alongside it (F-06).
8. The user can, at any time, edit or remove a subscription entry, which immediately updates the spend total in step 2.

## Constraints

Platform: Web application, responsive for mobile browser use; no native app required for this spec.
Data: All subscription and price data is user-entered and self-reported; the system does not verify accuracy against any billing source.
Privacy: No streaming account credentials are collected, stored, or transmitted at any point.
Scope limit: The system does not access or index actual streaming catalogs; the "Something new" filter (F-03) operates only over content the user has manually tagged or a static demo dataset, not a live catalog integration.
Timing: The dashboard total (step 2) shall reflect an edited entry (step 8) without requiring a page reload.

## Acceptance

- Ubiquitous: The system shall not display, link to, or reference pirated content sources at any point in the "Something new" or "Safe pick" flows.
- Event-driven: When a user adds a new subscription entry with a price, the system shall update the total monthly spend shown on the dashboard within 2 seconds.
- State-driven: While a subscription list contains zero entered services, the system shall disable the "What should I watch?" button rather than allow the user to reach an empty Safe pick or Something new flow.
- Unwanted: If a mood/format filter returns zero matching titles, then the system shall display a message stating no matches were found, rather than an empty screen or a suggestion outside the user's entered services.
- Optional: Where a subscription entry includes a renewal date, the system shall display that date alongside the service in the dashboard list.
- Unwanted: If a submitted service name is empty or a submitted price is not a positive number, then the system shall display a distinct error message for each case and shall not save the entry.
- State-driven: While a save operation fails, the system shall preserve the entry in the input field and shall not modify the previously saved list or total.

## Handoff reflection

I asked a reader (Claude) to check FEATURES.md against the "could two competent people disagree" test. Three real gaps surfaced. First, Behavior step 4 never defines whether "favorite" is user-marked or system-inferred, and separately gives two conflicting selection rules ("at random or by recency"). Second, Behavior and Acceptance contradicted each other on F-06: Behavior implies a reason is always shown, while the Optional acceptance criterion implies it's sometimes absent. I revised step 4 to have an order of operations and reconciled F-06 to actually be optional instead of a more important feature. Smaller gaps remain unresolved: the empty-subscription-list state referenced in Acceptance never appears in the numbered Behavior sequence, and the zero-favorites edge case for Safe pick isn't handled anywhere. These are acceptable remaining limits for this pass, but a future revision should walk Behavior and Acceptance side by side to confirm every acceptance criterion maps to an explicit step.


## Verification

**Scope note:** Per ADR-001 and the assignment's "choose small" guidance, only F-01 (subscription cost dashboard) and F-05 (manual subscription entry) were selected for the HW3 build. Statements tied to unselected features (F-02 Safe pick, F-03 filtering, F-06 reasoning display) are marked CANNOT TEST YET, since those flows were never implemented this cycle.

| # | Acceptance statement | Result | Evidence / reason |
|---|---|---|---|
| 1 | Ubiquitous: no pirated content sources referenced in Safe pick / Something new flows | CANNOT TEST YET | Neither flow (F-02/F-03) was built this cycle; out of scope per ADR-001. |
| 2 | Event-driven: adding a subscription updates total spend within 2 seconds | PASS | Added three subscriptions (netflix $20, hulu $13, spotify $15); total updated to $48.00 immediately on each addition. See [screenshot](docs/subscription-dashboard.png). |
| 3 | State-driven: "What should I watch?" disabled with zero entries | CANNOT TEST YET | This button belongs to the F-02/F-03 flow, not built this cycle. |
| 4 | Unwanted: zero filter matches show a no-matches message | CANNOT TEST YET | Mood/format filter (F-03) not built this cycle. |
| 5 | Optional: renewal date displayed alongside service when given | FAIL | No renewal date field exists in `index.html`/`app.js`. Genuine gap between Behavior step 1 and shipped code. |
| 6 | Unwanted: invalid service name or price rejected with a distinct error, entry not saved | PASS | Tested empty service name and $0/negative price separately; each produced a distinct, correct error message and no invalid entry was saved. |
| 7 | State-driven: failed save preserves the entry and leaves prior list/total unchanged | PASS | Tested with `?failSave` in the URL; correct error message shown, entry remained in the input field, and the previously saved list and total were unmodified. |

## HW4: Acceptance additions (EARS)

HW4 moves F-01/F-05 storage from localStorage to Cloudflare D1 (ADR-002). These statements cover the new server and the failures it brings. Each Worker endpoint quotes its statement in a comment in `worker.js`.

- **U-HW4-0 (Ubiquitous):** THE SYSTEM SHALL return all saved subscriptions in creation order.
- **E-HW4-1 (Event-driven):** WHEN a valid subscription is submitted, THE SYSTEM SHALL store it on the server and confirm it on the page.
- **E-HW4-2 (Event-driven):** WHEN the user removes a subscription, THE SYSTEM SHALL delete it on the server so the total no longer includes it.
- **S-HW4-3 (Ubiquitous):** THE SYSTEM SHALL return stored subscriptions to any browser, including one whose site data was cleared.
- **U-HW4 (Unwanted, the HW4 validation rule in `worker.js`):** IF a submitted price is not a number greater than 0, THEN THE SYSTEM SHALL reject it and say why. *Why it's on the server too:* the page already checks this (HW3 statement 6), but anyone can `POST` with `curl`. One bad price would corrupt the total every user sees. The D1 column has `CHECK (price > 0)` as a backstop.
- **U-HW4-5 (Unwanted):** IF the service name is missing, empty, or longer than 200 characters, THEN THE SYSTEM SHALL reject it and say why.
- **U-HW4-6 (Unwanted):** IF the server can't be reached or returns an error, THEN THE SYSTEM SHALL tell the user on the page, keep what they typed, and not throw in the console.

## HW4: Verification

**How it was walked (9/24/26):** against `npm run dev` (the real `worker.js` on wrangler's local D1 emulator), with the page served on `http://127.0.0.1:5500`. Browser steps were scripted with Playwright (Chromium). Worker responses were checked with `curl`. The three rows a user can see (return entries in order, store a valid entry, survive a cleared cache) were then re-walked on the deployed Worker on 9/24/26 and passed (see [docs/see-it-work-deployed.gif](../docs/see-it-work-deployed.gif)). The other rows stand on the local walk of the same `worker.js`.

| Statement | HW3 verdict | HW4 verdict | Reason / evidence |
|---|---|---|---|
| Return entries in order (U-HW4-0) | PASS | PASS | `GET /entries` returned `[]` when empty, then rows in id order after three `POST`s. |
| Store valid entry (E-HW4-1) | PASS | PASS | `POST {"service":"Netflix","price":20}` returned `201`. The page showed Netflix, Hulu, and Spotify with a total of $48.00. |
| Reject missing text / invalid name (U-HW4-5) | PASS (page only) | PASS | The page rejects an empty name before sending. The server rejects a missing name and a 201-character name with `400 service name must be 1-200 characters`. |
| **Reject non-positive price (U-HW4, new rule)** | PASS (page only) | PASS | `price: 0`, `-3`, and `"12"` (a string) each returned `400 price must be a number greater than 0`. A forced 400 on the page showed "Could not save: price must be a number greater than 0. Your entry is still here." and kept the input. |
| Survive cleared cache (S-HW4-3) | CANNOT TEST YET | PASS | Cleared all site data for the page origin (cookies, localStorage, and the rest), reloaded, and all three entries plus the $48.00 total came back. A second, fresh browser profile saw the same three. See [docs/see-it-work-deployed.gif](../docs/see-it-work-deployed.gif). |
| Delete updates total (E-HW4-2) | PASS | PASS | Deleting Hulu took the total to $35.00. `DELETE /entries/99` returned `404 no such entry`. |
| Server unreachable (U-HW4-6) | — | PASS | Simulated with `?serverDown` (the page points at port 9, where nothing listens). The page showed "Could not reach the server. Your subscriptions are safe; try again shortly." and nothing was thrown in the console. See [docs/server-unreachable.png](../docs/server-unreachable.png). DevTools → Network → Offline works on the deployed page too. |
| Server returns 500 (U-HW4-6) | — | PASS | Ran the Worker with no D1 binding: it returned `500 server error: no D1 binding. Check database_id...`. A forced 500 on the page showed "Could not load your subscriptions (server said 500). Try reloading." |
| Server returns 400 (U-HW4-6) | — | PASS | Invalid JSON returned `400 body must be JSON`. A `null` body returned `400 body must be a JSON object`. The page shows the server's reason (see the price row). |
| User values can't rewrite the SQL | — | PASS | A service name of `x'); DROP TABLE entries;--` was stored as plain text and the table survived, because every value goes through `bind()`. |
| HTML in a name is not executed | PASS | PASS | A name of `<img src=x onerror=alert(1)>` rendered as text, with no `<img>` in the DOM (`textContent`). |
| CORS limited to my page | — | PASS | A preflight from `http://127.0.0.1:5500` got `Access-Control-Allow-Origin` echoed back. A preflight from `https://evil.example` got no allow-origin header, so the browser blocks it. |
| Second client writes to the same table | — | DEFERRED | Two browsers do share one table (verified above), but there's no per-user separation or conflict handling. ADR-002 defers private lists to ADR-003. |
| HW3 #1 (Ubiquitous): no pirated content in Safe pick / Something new | CANNOT TEST YET | CANNOT TEST YET | Still true for the same reason: F-02/F-03 were never built (ADR-001 scope). Moving storage to a server doesn't create those flows. |
| HW3 #2 (Event-driven): adding a subscription updates the total within 2 seconds | PASS | PASS | The total now comes back from the server after each save. In the scripted local run each add showed the new total before the next step. On the deployed page the $48.00 total loaded with the list (see the GIF). Not timed with a stopwatch against the 2-second limit. |
| HW3 #3 (State-driven): "What should I watch?" disabled with zero entries | CANNOT TEST YET | CANNOT TEST YET | The button belongs to F-02/F-03, which are still not built. |
| HW3 #4 (Unwanted): zero filter matches show a no-matches message | CANNOT TEST YET | CANNOT TEST YET | The mood/format filter (F-03) is still not built. |
| HW3 #5 (Optional): renewal date shown | FAIL | FAIL | Still not built. Out of scope for HW4, which changed where data lives, not what is collected. |
| HW3 #6 (Unwanted): invalid name or price rejected with a distinct message, not saved | PASS | PASS | The page still gives a distinct message for an empty name and for a $0 or negative price, and sends nothing. The Worker now enforces the same two rules with its own 400 messages (rows above). |
| HW3 #7 (State-driven): a failed save keeps the entry and leaves the list and total unchanged | PASS | PASS | HW3 tested this with `?failSave`. In HW4 a forced 400 from the server showed "Could not save: … Your entry is still here." The typed name stayed in the input, and the list and total were not redrawn. |

## AI assistance
I asked it to help me have arrows for clear visuals. It also helped me organize all my points to develop my kano hypotheses and other structural details. Lastly I made a new chat and dropped in all of the assignment info and what I wrote and asked it to be my peer because it is late on a Thursday (I hope this is allowed), and I knew it would be a more thorough check anyways.

**HW4:** Claude Code (Anthropic's coding agent, run from claude.ai) drafted the HW4 statements and ran the verification walk above: `curl` against the local Worker, plus a scripted Playwright browser. The verdicts come from that run's output, not from reading the code. The deployed-URL walk is still mine to do.

## HW5: The delegated feature (rows marked for the tool)

**Feature:** F-05 renewal date. HW3 statement #5 has been FAIL since HW3
because no renewal-date field was ever built. HW5 delegates it. The rows
marked **[HW5 DELEGATE]** are the ones the tool is asked to implement; every
other row in this file is context and must keep passing.

- **O-HW5-1 (Optional) [HW5 DELEGATE]:** WHERE a subscription entry includes a renewal date, THE SYSTEM SHALL display that date alongside the service in the dashboard list. *(HW3 #5, unchanged wording.)*
- **E-HW5-2 (Event-driven) [HW5 DELEGATE]:** WHEN a valid subscription is submitted without a renewal date, THE SYSTEM SHALL store it and show it with no date, exactly as before.
- **U-HW5-3 (Unwanted) [HW5 DELEGATE]:** IF a submitted renewal date is not a real calendar date in `YYYY-MM-DD` form, THEN THE SYSTEM SHALL reject the entry and say why.
- **S-HW5-4 (Ubiquitous) [HW5 DELEGATE]:** THE SYSTEM SHALL store the renewal date on the server with the rest of the entry, so it survives a cleared cache like the name and price do (ADR-002).

Out of scope for HW5: reminders before a renewal, sorting by renewal date,
editing an existing entry's date (delete and re-add instead).
````

---

## FILE: context/STYLE.md

````markdown
---
# Tokens: what a machine reads. Values are the ones the HW3/HW4 page
# already uses in styles.css, so this file and the code agree.
color-primary: "#123552"
color-text: "#172B40"
color-background: "#F7F9FB"
color-focus: "#B16D00"
color-error: "#922020"
color-border: "#526578"
font-body: "Arial, Helvetica, sans-serif"
font-size-min: 16px
target-min: 44px
radius: 0.3rem
---

# STYLE.md

Tokens above, rationale below. The frontmatter is what a machine reads; this
body is what a human reads. One sentence per token.

## Rationale

- **color-primary** (`#123552`): a dark navy for the only action on the page (Save/Delete), because white text on it is 12.7:1 and it reads as "money and records," not "entertainment."
- **color-text** (`#172B40`): near-black blue instead of pure black, which keeps 13.7:1 contrast on the background while matching the primary.
- **color-background** (`#F7F9FB`): an off-white so a long list of subscriptions doesn't glare, and still a light surface that every other color is checked against.
- **color-focus** (`#B16D00`): amber focus outlines, used only for keyboard focus, because 3.9:1 on the background clears the 3:1 non-text minimum while no other element uses the color.
- **color-error** (`#922020`): dark red at 8.1:1 for error messages only, never for decoration, so red on this page always means "your entry was not saved."
- **color-border** (`#526578`): input borders at 6:1 against white so the fields are findable by people with low vision (WCAG 1.4.11).
- **font-body**: one system sans-serif for everything, because a dashboard of names and prices needs no second family and loads with zero network requests.
- **font-size-min** (`16px`): nothing smaller than the browser default, because prices are the whole point and the users check them on phones.
- **target-min** (`44px`): every button is at least 44px tall, so Delete is as easy to hit as Save.
- **radius** (`0.3rem`): a slight rounding so controls look clickable without looking like toys.

## Refusals

Things this interface will never do, and why. Taken from the interface I
resent: a streaming service's home screen and its cancel flow, the same
places my interviewees described getting stuck (USERS.md, INT-01/INT-02).

1. **No autoplaying previews or auto-advancing countdowns.** A dashboard about what you pay should not also be competing for your attention while you read it. Breaks: **Cognitive Load** (every moving tile adds extraneous load to a decision the user is already struggling with).
2. **Delete is never smaller, lower-contrast, or further away than Save.** Streaming cancel flows bury the exit behind extra screens and grey links; here removing a subscription is one full-size button next to the thing it removes. Breaks: **Fitts's Law** (time to hit a target grows with distance and shrinks with size; hiding the exit is making it slow on purpose).
3. **No surprise modals.** Errors appear inline under the form, where the user is already looking, and never block the page. Breaks: **Jakob's Law** (people expect a form to report problems next to the field, the way every other form they use does).

## Sources

- Admired: iPhone Settings → Subscriptions: a calm, plain list of each service and its price, nothing autoplaying, the same job my dashboard does ![iPhone Subscriptions screen listing each subscription and its price](../docs/style-admired.png)
- Resented: Netflix home screen: the autoplaying preview banner competes for attention while you're deciding what to watch ![Netflix home screen with an autoplaying preview banner at the top which is overstimulating INT-01](../docs/style-resented.png)
````

---

## FILE: context/STANDARDS.md

````markdown
# Standards

Status: ACTIVE in Module 3. Adapt these rules to your feature and follow them.

1. **Naming.** Variables and functions use camelCase and describe what they hold or do in domain terms — `service`, `price`, `saveNotes` — not single letters or generic names like `data` or `x`.

2. **File structure.** The three concerns stay in three files: `index.html` holds structure only, `styles.css` holds presentation only, `app.js` holds behavior and data. No inline styles, and no `<script>` content in the HTML beyond the single tag that loads `app.js`.

3. **Comments.** Comments explain why code exists, never what it does line by line. A comment restating the next line in English is deleted, not written.

4. **Commit messages.** Each commit message is one imperative-mood line describing what changed and why it mattered — "Add price validation to submit handler," not "fixed stuff" or "updates."

5. **Forbidden pattern.** Never use `innerHTML` to display text a user typed. Always use `textContent`, so user input can never be interpreted as HTML or executed as a script.

6. **(HW4) SQL parameters.** User values reach SQL through `prepare(...).bind(...)`, never string concatenation or template literals. A service name is data, never part of the query.

7. **(HW4) No credentials in the repository.** Not in code, not in config, not in a context file. The wrangler login token stays in the Codespace. Database ids are addresses, not keys, and may appear in `wrangler.toml`.

8. **(HW4) Failures are shown, not thrown.** A failed request (unreachable server, 400, 500) is shown to the user on the page in plain words, and what they typed is kept. It is never left as an uncaught error in the console.

**Source of truth:** If STANDARDS.md and CLAUDE.md ever disagree, STANDARDS.md wins. It's written for a human to read and agree to first; CLAUDE.md is a restatement of the same rules for an agent, not an independent source of authority.

## Split Test

**Rule: Naming (camelCase, descriptive domain terms)**
This rule applies to every task in the project — there's no task that generates code without also naming something. It stays the same from task to task; nothing about it depends on what's currently being built. If it were missing from persistent context and only given per-task, the risk is *confusion*: without a standing convention, an agent might name things differently across sessions, and a reader stitching the file together would see inconsistent style with no way to tell if it was intentional.
**Verdict: belongs in CLAUDE.md.**

**Rule: Forbidden pattern (no innerHTML for user text)**
This also applies to every task that touches rendering, which is most of this project's tasks. It doesn't change — it's a hard security-relevant rule, not something that varies by context. If it were left out of persistent context, the risk is *poisoning*: a single generated snippet using `innerHTML` could introduce a real vulnerability, and unlike a style inconsistency, this kind of mistake compounds silently until an attacker exploits it.
**Verdict: belongs in CLAUDE.md.**

**Rule: Commit messages (imperative mood, what/why)**
This rule only applies to the narrow task of writing a commit — it has nothing to do with tasks like debugging, explaining a function, or reviewing code for a bug. It doesn't change task to task, but it's only *relevant* on a fraction of tasks. Leaving it in CLAUDE.md risks *distraction*: on every unrelated task (reading a stack trace, explaining a regex), the agent is still holding commit-formatting rules in its context that have nothing to do with the work in front of it.
**Verdict: belongs in the prompt, not CLAUDE.md.**

*Prompt snippet, to be used only when asking for a commit message:*
> "Write this commit message as one imperative-mood line describing what changed and why it mattered. Don't describe the diff mechanically — say what changed in plain terms."

## Colleague Test

Who read it: No classmate was reachable before the deadline. Simulated 
this test with Claude (Anthropic), disclosed here and in the README's 
AI Use section as a substitute for an unavailable classmate, not a 
real person's response.

What was misunderstood or asked about: The reader correctly inferred 
the file structure and security rule (rule 4), but could not tell what 
domain the app belonged to — the naming examples (service, price) hint 
at it but CLAUDE.md never states the app's purpose outright.

Revision made: Added a one-line context sentence at the top of CLAUDE.md 
stating the project is a subscription cost dashboard, so a reader (human 
or agent) doesn't have to infer the domain from variable-naming examples 
alone.
````

---

## FILE: context/TOOLS.md

````markdown
# TOOLS.md

The ledger of Trust Boundary crossings. One row per external service this
repository depends on. Read by the agent on every task, so keep it short: a
service not in use does not belong here.

Never put a credential in this file. A key, token, or password anywhere in
the repository is graded as a security failure regardless of the rest.

Each crossing statement answers three questions in one first-person sentence:
what crosses, to whom, and who is accountable.

| Service | Trusted with | Credentials live | Crossing statement | Switching cost |
|---|---|---|---|---|
| **Cloudflare Workers + D1**: runs the API (`worker.js`) and stores every subscription | Every subscription a user types (service name, monthly price, timestamp); request metadata (IP, user agent, time) that Cloudflare logs by default | Cloudflare dashboard login; wrangler OAuth token inside the Codespace (never in the repo) | "Users' subscription names and prices leave the browser and are stored in Cloudflare D1 under Cloudflare's free-plan terms, in a region I did not choose, readable by anyone with the Worker URL; I am accountable." | **Medium**: `npm run db:export` for the data, then rewrite one ~100-line Worker for another host |
| **GitHub + Codespaces**: hosts the repository and the cloud dev environment I build and deploy from | Source code, full commit history, context files, the devcontainer, and the running Codespace, where the wrangler token lives | GitHub account login | "My code, my history, and the Codespace that holds my Cloudflare token are hosted by GitHub under its terms, and the repository is public; I am accountable for keeping secrets out of every commit." | **Low**: `git clone` to any machine or host; the devcontainer is plain Node 22 |
| **GitHub Copilot** (VS Code extension the template's devcontainer installs): inline code suggestions in the Codespace editor | Whatever files are open in the editor, sent to GitHub/Microsoft as context whenever it is active, whether or not I accept a suggestion | GitHub account login (no separate key) | "The devcontainer installs Copilot in my Codespace, so any code I have open there can be sent to GitHub's Copilot service; I don't actively use its suggestions, and I am accountable for anything it suggests that I commit." | **Low**: remove `GitHub.copilot` from `.devcontainer/devcontainer.json`; nothing in the repo depends on it |
| **wrangler** (npm package, devDependency): the command-line tool that creates the database and deploys the Worker | Runs with my full user permissions in the Codespace during `npm install` and every `npx wrangler` call; holds and uses the Cloudflare login token | No credential of its own; it stores the Cloudflare OAuth token in the Codespace's home directory | "Installing wrangler runs code written by Cloudflare and every package it depends on, with access to my Codespace and my Cloudflare token, with the range `^4` locked to one exact version in `package-lock.json`; like the event-stream incident, a compromised dependency would inherit that trust, and I am accountable for what I install." | **Medium**: wrangler is the deploy path, so leaving it means leaving Workers (see first row) |
| **Claude Code** (Anthropic, run from claude.ai): the coding agent that wrote most of the HW4 code, and in HW5 integrated the renewal-date feature and drafted the HW5 docs | The whole repository and my public HW2–HW4 repositories, cloned into an Anthropic-hosted container; it edited files, ran the Worker and the evals locally, and pushed commits | claude.ai account login; GitHub access granted to the Claude GitHub app | "For HW4 and HW5, my repository contents went to Anthropic's Claude Code service, which wrote and pushed changes I review before submitting; I am accountable for every line I keep." | **Low**: stop using it; the repo does not depend on it |
| **bolt.new** (StackBlitz, HW5 Session B): AI builder given the delegation paste; GitHub **not** connected | PROJECT, FEATURES, STYLE, STANDARDS, TOOLS, and my three page files, pasted into its chat; the zip it returns comes back into `delegated/` | bolt.new account login (no key in the repo) | "For HW5 I pasted my project's context files and page code into StackBlitz's bolt.new under its terms, which may use prompts to improve its service; the paste holds no user data and no credentials, and I am accountable for every line of its output I integrate." | **Low**: nothing runs on bolt; its zip is an artifact I read, not a dependency |
| **Google AI Studio** (Google, HW5 Session B, Build tab): second AI builder, same paste, same instruction line | Same paste as bolt.new; the app it returns comes back as code I read | Google account login (no API key in the repo) | "For HW5 I pasted the same context files and page code into Google AI Studio under Google's terms, where free-tier prompts may be reviewed and used to improve Google's products; the paste holds no user data and no credentials, and I am accountable for anything of its output I keep." | **Low**: nothing depends on it; its output is read, not deployed |

Reverse crossing (what comes back in): a builder's zip can carry its own
`package.json`, framework, CDN `<script>` tags, or a hosted-storage client.
None of it is installed or deployed until it passes docs/CHECKLIST.md
question 4 and has its own row here.

## Revisit triggers

- A new service is added to the repository.
- A vendor changes pricing, terms, or region.
- A credential moves.
````

---

## FILE: index.html

````html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Subscription dashboard | MGT 3745 starter</title>
  <link rel="stylesheet" href="styles.css">
  <script src="app.js" defer></script>
</head>
<body>
  <main>
    <h1>Subscription dashboard</h1>
    <p>Track the streaming services you pay for and see your total monthly spend. Use fictional, non-sensitive information.</p>
    <form id="note-form" novalidate>
      <label for="note-input">Service name</label>
      <input id="note-input" name="service" type="text" aria-describedby="note-help note-error" autocomplete="off">
      <label for="price-input">Monthly price (USD)</label>
      <input id="price-input" name="price" type="number" step="0.01" min="0" aria-describedby="note-help note-error" autocomplete="off">
      <p id="note-help">Enter a service name (1–200 characters) and a price greater than 0. Entries are saved to a shared server (Cloudflare), not just this browser, so anyone with this page can see them.</p>
      <button type="submit">Save subscription</button>
      <p id="note-error" role="alert"></p>
    </form>
    <p id="save-status" role="status" aria-live="polite"></p>
    <h2>Your subscriptions</h2>
    <p id="spend-total" role="status" aria-live="polite"></p>
    <p id="empty-state">No saved subscriptions yet.</p>
    <ul id="note-list" aria-label="Saved subscriptions"></ul>
  </main>
</body>
</html>
````

---

## FILE: styles.css

````css
:root { font-family: Arial, Helvetica, sans-serif; color: #172b40; background: #f7f9fb; }
body { margin: 0; }
main { max-width: 44rem; margin: 2rem auto; padding: 0 1.25rem; }
h1 { font-size: 2rem; }
p { line-height: 1.5; }
label { display: block; font-weight: 700; }
input { box-sizing: border-box; display: block; width: 100%; font: inherit; padding: 0.8rem; border: 1px solid #526578; border-radius: 0.3rem; }
button { min-height: 44px; margin: 0.75rem 0; padding: 0.6rem 1rem; font: inherit; background: #123552; color: #fff; border: 2px solid #123552; border-radius: 0.3rem; cursor: pointer; }
button:focus-visible, input:focus-visible { outline: 3px solid #b16d00; outline-offset: 3px; }
input[aria-invalid="true"] { border: 2px solid #a02020; }
#note-error { color: #922020; }
#note-list { padding: 0; list-style: none; }
#note-list li { display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 0.5rem; border-bottom: 1px solid #b8c5d0; }
#note-list span { flex: 1 1 15rem; overflow-wrap: anywhere; line-height: 1.5; }
````

---

## FILE: app.js

````javascript
(() => {
  'use strict';

  // HW4: subscriptions now live in Cloudflare D1 behind the Worker (ADR-002).
  // Paste your deployed Worker URL here after `npx wrangler deploy`.
  const deployedApi = 'https://mgt3745-hw4.mgt3745-hw4-giancarlo.workers.dev';
  // A page served from this machine talks to `npm run dev` instead, so the
  // failure modes in FEATURES.md can be tested without touching the real table.
  const isLocalPage = ['localhost', '127.0.0.1'].includes(window.location.hostname);
  // The query switch makes "server unreachable" repeatable: nothing listens on port 9.
  const simulateServerDown = new URLSearchParams(window.location.search).has('serverDown');
  const api = simulateServerDown ? 'http://127.0.0.1:9'
    : isLocalPage ? 'http://127.0.0.1:8787'
    : deployedApi;

  // ---- HW3, for the record (superseded by ADR-002) ------------------------
  // loadNotes: JSON.parse(window.localStorage.getItem(storageKey))
  // saveNotes: window.localStorage.setItem(storageKey, JSON.stringify(nextNotes))
  // -------------------------------------------------------------------------

  const noteForm = document.querySelector('#note-form');
  const noteInput = document.querySelector('#note-input');
  const priceInput = document.querySelector('#price-input');
  const noteList = document.querySelector('#note-list');
  const noteError = document.querySelector('#note-error');
  const saveStatus = document.querySelector('#save-status');
  const emptyState = document.querySelector('#empty-state');
  const spendTotal = document.querySelector('#spend-total');
  let notes = [];

  function showError(message) {
    // The user sees it on the page. Nothing is thrown in the console.
    noteError.textContent = message;
    saveStatus.textContent = '';
  }

  async function loadNotes() {
    const response = await fetch(api + '/entries');
    if (!response.ok) {
      showError('Could not load your subscriptions (server said ' + response.status + '). Try reloading.');
      return [];
    }
    return response.json();
  }

  async function saveNote(entry) {
    const response = await fetch(api + '/entries', {
      method: 'POST',
      headers: { 'content-type': 'application/json' },
      body: JSON.stringify(entry),
    });
    if (!response.ok) {
      // The Worker's 400 path sends a short reason in the body. Show it.
      const reason = await response.text();
      showError('Could not save: ' + (reason || response.status) + '. Your entry is still here.');
      return false;
    }
    return true;
  }

  async function deleteNote(id) {
    const response = await fetch(api + '/entries/' + encodeURIComponent(id), { method: 'DELETE' });
    if (!response.ok) {
      showError('Could not delete that subscription. Nothing was changed.');
      return false;
    }
    return true;
  }

  function formatPrice(price) {
    return price.toLocaleString(undefined, { style: 'currency', currency: 'USD' });
  }

  function renderNotes() {
    noteList.replaceChildren();
    emptyState.hidden = notes.length > 0;

    const total = notes.reduce((sum, entry) => sum + entry.price, 0);
    spendTotal.textContent = notes.length > 0
      ? `Total monthly spend: ${formatPrice(total)}`
      : '';

    notes.forEach((note, index) => {
      const listItem = document.createElement('li');
      const noteText = document.createElement('span');
      // textContent, never innerHTML: the server does not get to write HTML into the page either.
      noteText.textContent = `${note.service} — ${formatPrice(note.price)}/mo`;
      const deleteButton = document.createElement('button');
      deleteButton.type = 'button';
      deleteButton.textContent = 'Delete';
      deleteButton.setAttribute('aria-label', `Delete subscription ${index + 1}: ${note.service}`);
      deleteButton.addEventListener('click', async () => {
        try {
          if (!(await deleteNote(note.id))) return;
          await refresh();
          saveStatus.textContent = 'Subscription deleted.';
          noteInput.focus();
        } catch {
          showError('Could not reach the server. Nothing was deleted.');
        }
      });
      listItem.append(noteText, deleteButton);
      noteList.append(listItem);
    });
  }

  async function refresh() {
    try {
      notes = await loadNotes();
    } catch {
      // The network itself failed (offline, DNS, CORS). fetch throws here.
      showError('Could not reach the server. Your subscriptions are safe; try again shortly.');
      notes = [];
    }
    renderNotes();
  }

  noteForm.addEventListener('submit', async event => {
    event.preventDefault();
    const service = noteInput.value.trim();
    const characterCount = Array.from(service).length;
    const price = Number(priceInput.value);

    if (characterCount < 1 || characterCount > 200) {
      noteError.textContent = 'Enter a service name containing 1–200 characters.';
      noteInput.setAttribute('aria-invalid', 'true');
      saveStatus.textContent = '';
      noteInput.focus();
      return;
    }
    if (!Number.isFinite(price) || price <= 0) {
      noteError.textContent = 'Enter a monthly price greater than 0.';
      priceInput.setAttribute('aria-invalid', 'true');
      saveStatus.textContent = '';
      priceInput.focus();
      return;
    }
    noteInput.removeAttribute('aria-invalid');
    priceInput.removeAttribute('aria-invalid');
    noteError.textContent = '';

    try {
      // Only clear the inputs after the server confirms, same rule as HW3.
      if (!(await saveNote({ service, price }))) return;
    } catch {
      showError('Could not reach the server. Your entry is still here; try again.');
      return;
    }
    await refresh();
    noteInput.value = '';
    priceInput.value = '';
    noteInput.focus();
    saveStatus.textContent = 'Subscription saved.';
  });

  refresh();
})();
````
