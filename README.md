# Repolex Knowledge Graph of sphinx-contrib/autorun

RDF knowledge graph data for [sphinx-contrib/autorun](https://github.com/sphinx-contrib/autorun), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download sphinx-contrib/autorun
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── be1cbd304c86c05b9aae50a2d9f151e435a7ea30
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── be1cbd304c86c05b9aae50a2d9f151e435a7ea30
│           └── chunk-001.nq.gz
├── blob
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 45f0c5260bcae8ba06276a311e47fba22bedc875.nq.gz
│   ├── 4a7fe6c46352696ebfad64ca65558792ac822bd9.nq.gz
│   ├── 61340813d8152c8c51b9c770e841cecdd4b8647d.nq.gz
│   ├── 6430c3442e9aad81a8a402e53ed0b76a70400210.nq.gz
│   ├── 7d4cf513382309ecdd2edc5ee15eb0f7fa6e5d48.nq.gz
│   ├── a063c0617dfda9fb3f3b8f957907e008832225a2.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   └── ba4a3a57deb1644c0b313ecf5104a7b23a6ab28d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── be1cbd304c86c05b9aae50a2d9f151e435a7ea30.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[sphinx-contrib/autorun](https://github.com/sphinx-contrib/autorun)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
