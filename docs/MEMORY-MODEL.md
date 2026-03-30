# Memory Model

## Goal

Keep the agents recoverable after context loss without forcing them to reread the entire project every time.

## Layers

### Short-term memory

Location:

- `memory/agent-x/short-term/`

Use for:

- current-day notes
- temporary blockers
- immediate observations
- subagent findings that may soon expire

### Mid-term memory

Location:

- `memory/agent-x/mid-term/`

Use for:

- current task or milestone summary
- rolling execution summaries
- patterns that matter across several cycles

### Long-term memory

Location:

- `memory/agent-x/long-term/`

Use for:

- stable project structure
- recurring workflow lessons
- known conventions
- repeated pitfalls

## Promotion rule

If a fact is useful only today, keep it in short-term.
If it matters for the current milestone, move it to mid-term.
If it will matter again next week or next month, move it to long-term.

## Compression rule

Agents should periodically compress:

- short-term into mid-term
- mid-term into long-term

This is how we keep token usage low while keeping recovery strong.
