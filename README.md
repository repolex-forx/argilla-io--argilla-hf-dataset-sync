# Repolex Knowledge Graph of argilla-io/argilla-hf-dataset-sync

RDF knowledge graph data for [argilla-io/argilla-hf-dataset-sync](https://github.com/argilla-io/argilla-hf-dataset-sync), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/argilla-hf-dataset-sync
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8fd061909f5bc0f59f942acc132b432e71af8d64
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8fd061909f5bc0f59f942acc132b432e71af8d64
│           └── chunk-001.nq.gz
├── blob
│   ├── 0cbed81c3c9c4305067f423c00d77e6d18e976c0.nq.gz
│   ├── 180d415e509fb079745904c69c59991e7dd01395.nq.gz
│   ├── 52d9fb4e61151cb7c458cfdbd7eddbc2c3fbb026.nq.gz
│   ├── 8664b1130c0f4b6649a218451b0fa4e157902794.nq.gz
│   ├── 8e0e0e1a9e8f249926e828971408ce6b82704ff0.nq.gz
│   └── c2eabecac229425be9003d3f259451381494ff1c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8fd061909f5bc0f59f942acc132b432e71af8d64.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 13 files
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

[argilla-io/argilla-hf-dataset-sync](https://github.com/argilla-io/argilla-hf-dataset-sync)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
