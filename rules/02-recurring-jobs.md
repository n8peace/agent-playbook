# Four things every recurring agent job gets

Scheduled agents fail quietly: they start from zero, repeat mistakes and run forever. Four parts stop all three.

Paste into your CLAUDE.md or AGENTS.md:

```markdown
## Recurring and long-running jobs

Every recurring or long-running job gets four things before it starts:
1. A state file it reads first and updates last, so no run starts from zero.
2. A check that verifies its own output on every pass.
3. A stop condition (done, a budget or a date), so it never runs forever on its own. A job that fails 3 runs in a row stops and reports.
4. Reading-heavy steps split into subagents, so the main loop's context stays small.

No model for what a script can do: health checks, "did it go live" checks, retries and log scans are scripts, not model turns.
```

For alerts when a scheduled job does not run at all, see Spooky Particles (github.com/banana-intelligence-dot-ai/spookyparticles) or the minimal Vercel cron check-in example (github.com/n8peace/vercel-cron-monitoring-example).
