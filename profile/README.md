## Open-source tools for AI agents

### [AgentDB](https://github.com/backloghq/agentdb)

AI-first embedded database for LLM agents. Zero native dependencies, pure TypeScript.

- **32 MCP tools** — CRUD, search, archive, vector search, blob storage, real-time subscriptions
- **Declarative schemas** — `defineSchema()` with typed fields, validation, defaults, hooks, auto-indexing
- **Vector search** — HNSW nearest neighbor with 6 embedding providers
- **Blob storage** — attach files to records, works on filesystem and S3
- **Crash-safe** — append-only WAL with immutable snapshots

```bash
npm install @backloghq/agentdb
```

### [Backlog](https://github.com/backloghq/backlog)

Persistent task management for Claude Code. Tasks survive sessions so work started by one agent can be picked up by another.

- **24 MCP tools** — full task lifecycle: add, modify, done, delete, start, stop, annotate, archive
- **7 skills** — `/backlog:plan`, `/backlog:tasks`, `/backlog:standup`, `/backlog:refine`, `/backlog:spec`, `/backlog:implement`, `/backlog:handoff`
- **Agent coordination** — tasks auto-assign to spawned agents, sync with Claude's built-in task system

```
/plugin marketplace add backloghq/backlog
```

**[Documentation](https://backloghq.io)**
