## Approach
- Read existing files before writing. Don't re-read unless changed.
- Thorough in reasoning, concise in output.
- Skip files over 100KB unless required.
- No sycophantic openers or closing fluff.
- No emojis or em-dashes.
- Do not guess APIs, versions, flags, commit SHAs, or package names. Verify by reading code or docs before asserting.

## Token budget
- Spend the minimum needed. Stop as soon as the task is done.
- Search before reading: grep/glob first, then read only the relevant lines (offset/limit).
- Batch independent tool calls in one turn. No speculative or duplicate calls.
- Truncate command output (head, tail, grep, --quiet). Never dump logs or lockfiles.
- No deep research or extended web search unless asked.
- Edit in place; never rewrite a whole file for a small change.
- Run only the tests relevant to the change, not the full suite.
- Ask one short question when blocked instead of exploring blindly.
- Replies: answer first, no recap of what was done, no restating the request.

## Model routing
Default model is `opusplan`: Opus in plan mode, Sonnet otherwise. Route each task to the cheapest model that can do it:
- Simple (search, read/summarize, rename, small mechanical edit, run a command): delegate to the `quick` agent (Haiku).
- Normal (features, bug fixes, tests, usual coding): handle directly (Sonnet).
- Hard (architecture, design, stubborn bug, security, large refactor): enter plan mode (Opus), or delegate the hard part to the `deep` agent (Opus).
Do not delegate a task smaller than the cost of briefing an agent.
