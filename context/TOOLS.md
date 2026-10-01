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
