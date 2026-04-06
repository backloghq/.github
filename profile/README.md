## Persistent task management for Claude Code

**[backlog](https://github.com/backloghq/backlog)** is a Claude Code plugin that makes tasks survive across sessions. Plan work, track progress, hand off context — agents pick up where others left off.

### What it does

- **24 MCP tools** — full task lifecycle: add, modify, done, delete, start, stop, annotate, archive, and more
- **7 skills** — `/backlog:plan`, `/backlog:tasks`, `/backlog:standup`, `/backlog:refine`, `/backlog:spec`, `/backlog:implement`, `/backlog:handoff`
- **Agent coordination** — tasks auto-assign to spawned agents, sync with Claude's built-in task system
- **Doc-driven development** — attach specs to tasks, implement against them
- **Zero dependencies** — pure TypeScript with event-sourced storage, works everywhere

### Install

```
/plugin marketplace add backloghq/backlog
/plugin install backlog@backloghq-backlog
```

**[Documentation](https://backloghq.io)** &bull; **[GitHub](https://github.com/backloghq/backlog)**
