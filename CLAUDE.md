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
- No subagents, deep research, or extended web search unless asked.
- Edit in place; never rewrite a whole file for a small change.
- Run only the tests relevant to the change, not the full suite.
- Ask one short question when blocked instead of exploring blindly.
- Replies: answer first, no recap of what was done, no restating the request.
