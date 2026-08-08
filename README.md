# wooju-brain

<p align="center">
  <img src="./assets/readme/hero.svg" width="100%" alt="wooju-brain: a durable memory boundary for humans and long-lived AI assistants">
</p>

> **Wooju thinks and acts. Wooju Brain remembers.**

`wooju-brain` is a local-first personal knowledge and memory system for human use and long-lived AI assistants. It preserves what should survive across runs while keeping evidence, world knowledge, personal memory, and active work distinct.

## Start here

1. Read [`AGENTS.md`](AGENTS.md), the repository constitution.
2. Put unprocessed material in [`inbox/`](inbox/), or point an agent at the material directly.
3. Use [`docs/INGEST.md`](docs/INGEST.md) to classify and promote useful material.
4. Add only the durable knowledge, memory, projects, and areas that will improve future work.

The filesystem is intentionally conservative: structure should grow from real usage, not from a pre-built topic taxonomy.

## Core model

<p align="center">
  <img src="./assets/readme/core-model.svg" width="100%" alt="The four wooju-brain boundaries: evidence, world knowledge, personal memory, and action context">
</p>

The repository is not just a wiki. Its boundaries answer different questions:

| Boundary        | Canonical paths                                      | Question                                         |
| --------------- | ---------------------------------------------------- | ------------------------------------------------ |
| Evidence        | `library/` → `sources/`                              | What does this identifiable source support?      |
| World knowledge | `wiki/`                                              | What do we currently understand about the world? |
| Personal memory | `memory/records/`, `memory/events/`, `memory/state/` | What is known about the user, and when?          |
| Action context  | `projects/`, `areas/`                                | What is being done or managed?                   |

Keep one canonical record and link to it. A source note is not automatically general knowledge; a personal memory is not a universal fact; and project context is not a timeless claim.

## Memory and work have different lifecycles

Personal memory uses folders for lifecycle and metadata for meaning:

```text
memory/
├── records/   # durable knowledge
├── events/    # historical timeline
└── state/     # current projection
```

Two rules matter most:

1. **Events preserve history; state represents the latest projection.**
2. **Inference must never be silently promoted into an explicit personal fact.**

Use `projects/` for work with a finish line and `areas/` for responsibilities that continue indefinitely. An area is a context hub: it links to canonical memory, knowledge, and project records instead of duplicating them.

## From input to durable context

- **Learn from a source:** source artifact → `library/` → source-grounded note → `sources/` → reusable synthesis → `wiki/`.
- **Capture something about the user:** conversation, observation, or imported record → decide whether it is worth remembering → record, event, or state → `memory/`.
- **Work on a goal:** project context → `projects/<project>/` → links to `wiki/` and `memory/`, with durable outputs promoted when appropriate.

## Working with AI agents

`AGENTS.md` should be read first by any agent working here. Detailed procedures keep the core rules small and stable:

| Task                                     | Read                                       |
| ---------------------------------------- | ------------------------------------------ |
| Add or synthesize knowledge              | [`docs/KNOWLEDGE.md`](docs/KNOWLEDGE.md)   |
| Create or update personal memory         | [`docs/MEMORY.md`](docs/MEMORY.md)         |
| Work on a project or area                | [`docs/WORK.md`](docs/WORK.md)             |
| Capture or ingest new material           | [`docs/INGEST.md`](docs/INGEST.md)         |
| Search or answer from the knowledge base | [`docs/RETRIEVAL.md`](docs/RETRIEVAL.md)   |
| Change repository mechanics              | [`docs/OPERATIONS.md`](docs/OPERATIONS.md) |

The intended hierarchy is:

```text
AGENTS.md          always-loaded invariants
    ↓
docs/*.md          task-specific procedures
    ↓
repository data    retrieved only when relevant
```

## What belongs here

Keep things a future reader or assistant is likely to need again:

- durable concepts and explanations;
- source-backed research notes;
- reusable procedures and mental models;
- meaningful personal preferences, goals, constraints, and decisions;
- current-state summaries and important historical events;
- active project and life-area context.

Do not turn the repository into a transcript archive. Greetings, filler, temporary chatter, raw chain-of-thought, one-off details, duplicate explanations, credentials, and highly sensitive secrets do not belong in the durable knowledge graph.

<details>
<summary>Repository map</summary>

```text
wooju-brain/
├── README.md                 # human-facing introduction
├── AGENTS.md                 # repository constitution for AI agents
├── CLAUDE.md -> AGENTS.md    # same rules for Claude Code
│
├── docs/                     # task-specific operating manuals
│   ├── KNOWLEDGE.md          # sources, wiki, synthesis, evidence quality
│   ├── MEMORY.md             # personal-memory admission and lifecycle rules
│   ├── WORK.md               # projects and ongoing areas
│   ├── INGEST.md             # capture, classify, promote
│   ├── RETRIEVAL.md          # search order, freshness, conflicts
│   └── OPERATIONS.md         # naming, links, validation, logs, indexes
│
├── inbox/                    # unprocessed capture
├── library/                  # retained original source artifacts/references
├── sources/                  # notes grounded in identifiable sources
├── wiki/                     # durable knowledge about the world
├── memory/                   # durable knowledge about the user
│   ├── records/              # facts, preferences, goals, constraints, decisions
│   ├── events/               # append-oriented personal history
│   └── state/                # current-state projections
├── projects/                 # finite goal-oriented work
├── areas/                    # ongoing responsibilities and life/work domains
├── logs/                     # meaningful repository change history
├── scripts/                  # deterministic maintenance and validation tools
├── index.md                  # root navigation / generated summary
├── indexes/                  # generated secondary indexes
└── archive/                  # retired but historically useful material
```

</details>

## Design principles

- **Local-first.** Plain files remain readable without a specific application or model.
- **Provenance-aware.** Durable claims preserve where they came from.
- **Temporal.** Mutable personal facts do not silently become timeless truths.
- **Connected.** Useful knowledge accumulates into synthesis rather than isolated notes.
- **Selective.** Future usefulness matters more than maximum capture.
- **Agent-neutral.** The system should work with different AI assistants.
- **Evolutionary.** Start simple; add indexing, automation, and runtime components only when scale requires them.

## Future direction

Wooju Brain is intended to become a durable knowledge and memory foundation for the [Wooju](https://github.com/seulchan/wooju) agent runtime while remaining useful on its own.

- **Wooju** is the cognitive runtime: it decides what matters now, what to focus on, and what action to take.
- **Wooju Brain** preserves what should survive across runs: world knowledge, personal memory, project context, and history.

The projects should remain architecturally independent. Retrieval should come before automatic persistence, and any future durable writes should continue to respect provenance, privacy, temporal, and memory-admission rules.

> **Memory is what survives. Context is what matters now.**

## Status

Early architecture. The immediate goal is to validate the boundaries and workflows with real usage before adding heavier retrieval infrastructure or runtime integration.

## License

Wooju Brain is licensed under the PolyForm Noncommercial License 1.0.0.

Noncommercial use is permitted. Commercial use requires separate permission.

See [LICENSE](LICENSE) for details.
