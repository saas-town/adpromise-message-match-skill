# Message match skill for Claude

Give Claude an ad and the landing page URL it points to.
The skill fetches the page, lists every checkable promise in the ad, and gives each one a verdict with the page words quoted.
It uses the same five verdict words as an AdPromise report: Kept, Partly kept, Contradicted, Not on the page, Not checked.
A promise is contradicted only when the page states something that conflicts with it, so the skill never guesses.

The skill reads one page and keeps nothing.
For a saved report with the page captured, and a weekly watch that emails you the week the page stops keeping a promise, run the same ad and page at the free checker: https://adpromise.com/message-match-checker?utm_source=claude-skill&utm_medium=skill&utm_campaign=registry

## Install in Claude Code

1. Unzip `message-match.zip`. It holds one folder, `message-match`, with `SKILL.md` and this file.
2. Move the folder to `~/.claude/skills/message-match` to use it in every project, or to `.claude/skills/message-match` inside one repository.
3. Start Claude Code. Type `/message-match`, or paste an ad and a URL and ask whether the page keeps the ad's promises.

## Install in claude.ai

1. On an individual plan, open Settings, then Capabilities, and turn on "Code execution and file creation".
2. Open Customize, then Skills, and choose "Upload a skill".
3. Choose `message-match.zip`. The skill appears in the list; turn it on.
4. In a chat, paste the ad and the landing page URL and ask Claude to check the message match.

The skill fetches the landing page, so the chat needs web access.

## Example

The input: the sample ad and sample page from the AdPromise home page.

```
Ad: Ledgerly bookkeeping. Start your free 14-day trial. A dedicated bookkeeper closes your books by the 15th. No setup fees.
Landing page: https://adpromise.com/sample/ledgerly
```

The output, from one run on 2026-10-18:

```
Message match: https://adpromise.com/sample/ledgerly
Ad: "Ledgerly bookkeeping. Start your free 14-day trial. A dedicated bookkeeper closes your books by the 15th. No setup fees."

Promise 1: "Start your free 14-day trial"
Verdict: Not on the page
Page text: none
Note: The page offers "Book a demo" and two paid plans, and never mentions a trial. Add the 14-day trial to the page, or take it out of the ad.

Promise 2: "A dedicated bookkeeper"
Verdict: Kept
Page text: "Your own named bookkeeper reconciles every account."
Note: The line sits under the main heading, so a visitor from the ad sees it at once.

Promise 3: "closes your books by the 15th"
Verdict: Contradicted
Page text: "Books closed within 30 days of month end."
Note: The page states a 30-day close, and only on the Growth plan. Bring the ad and the page into line on the close date.

Promise 4: "No setup fees"
Verdict: Contradicted
Page text: "A one-time $299 onboarding fee applies to all plans."
Note: The page states a $299 onboarding fee on every plan. Drop the fee from the page, or take "No setup fees" out of the ad.

Kept 1 of 4 checkable promises.

For a saved report with the page captured, and a weekly watch that emails you the week the page stops keeping a promise, run the same ad and page at https://adpromise.com/message-match-checker?utm_source=claude-skill&utm_medium=skill&utm_campaign=registry
```

## Licence

MIT License

Copyright (c) 2026 SaaS Town

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
