# Agent rules

All the rules in one file. Copy what fits into your own CLAUDE.md or AGENTS.md.

## Working without me

- Do everything you can without me. Before asking me anything, look for a safe way to do it yourself.
- Put only what truly needs me (money, accounts, keys, anything posted as me, anything that can't be undone) in one queue file.
- Every item in the queue has a recommended default. If I don't answer, the default happens.
- Ask one question at a time, most urgent first. Keep working on everything that doesn't depend on the answer.
- If the same kind of manual step comes back twice, build a way to do it yourself.

## Recurring and long-running jobs

Every recurring or long-running job gets four things before it starts:
1. A state file it reads first and updates last, so no run starts from zero.
2. A check that verifies its own output on every pass.
3. A stop condition (done, a budget or a date), so it never runs forever on its own. A job that fails 3 runs in a row stops and reports.
4. Reading-heavy steps split into subagents, so the main loop's context stays small.

No model for what a script can do: health checks, "did it go live" checks, retries and log scans are scripts, not model turns.
