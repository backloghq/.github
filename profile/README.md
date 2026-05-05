# BacklogHQ

Open-source tools that AI agents use as infrastructure. Pure TypeScript, zero native dependencies, MCP-first, event-driven, crash-safe by default.

### [AgentDB](https://github.com/backloghq/agentdb)

AI-first embedded database for LLM agents. Zero native dependencies, pure TypeScript.

- **MCP tools** — CRUD, schema lifecycle, search, archive, vector search, blob storage, real-time subscriptions
- **Persisted schemas** — `defineSchema()` with typed fields, validation, defaults, hooks, auto-indexing; agent-discoverable at runtime via `db_get_schema`
- **Vector search** — HNSW nearest neighbor with 6 embedding providers
- **Blob storage** — attach files to records, works on filesystem and S3
- **Crash-safe** — append-only WAL with immutable snapshots

```bash
npm install @backloghq/agentdb
```

### [Backlog](https://github.com/backloghq/backlog)

Persistent task management for Claude Code. Tasks survive sessions so work started by one agent can be picked up by another.

- **MCP tools** — full task lifecycle: add, modify, done, delete, start, stop, annotate, archive
- **Skills** — `/backlog:plan`, `/backlog:tasks`, `/backlog:standup`, `/backlog:refine`, `/backlog:spec`, `/backlog:implement`, `/backlog:handoff`
- **Agent coordination** — tasks auto-assign to spawned agents, sync with Claude's built-in task system

```
/plugin marketplace add backloghq/backlog
```

### [opslog](https://github.com/backloghq/opslog)

Embedded event-sourced document store. The engine under AgentDB.

- **Append-only WAL** — every mutation recorded as an operation, state derived by replay
- **Immutable snapshots** — fast cold-start without replaying the full log
- **Multi-writer** — Lamport clocks for last-writer-wins across concurrent agents
- **Tradeoff** — a crash can lose buffered ops (up to 100ms). Default `"immediate"` mode is safe.

```bash
npm install @backloghq/opslog
```

### [opslog-s3](https://github.com/backloghq/opslog-s3)

S3 storage backend for opslog. Enables multi-writer concurrency across machines via Amazon S3.

```bash
npm install @backloghq/opslog-s3
```

### [termlog](https://github.com/backloghq/termlog)

Log-structured full-text search index. Segment-based posting lists with LSM compaction, BM25 ranking, zero native dependencies.

- **Size-tiered LSM compaction** — fanout-based merge; write amplification bounded at `O(N log_fanout N)`
- **BM25 ranking** — configurable `k1`/`b`, top-k heap
- **Streaming segment writes** — atomic commits via manifest swap; crash-safe orphan recovery
- **Pluggable storage** — local FS by default, S3 via `@backloghq/termlog-s3`
- **Scales** — 1M+ docs per index without per-file size cliffs

```bash
npm install @backloghq/termlog
```

### [termlog-s3](https://github.com/backloghq/termlog-s3)

S3 storage backend for termlog. Streaming segment writes via S3 multipart upload; supports Amazon S3, MinIO, and LocalStack.

```bash
npm install @backloghq/termlog-s3
```

---

**[Documentation](https://backloghq.io)** &middot; **[GitHub](https://github.com/backloghq)**
