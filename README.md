# Repolex Knowledge Graph of glue-viz/glue-h5part

RDF knowledge graph data for [glue-viz/glue-h5part](https://github.com/glue-viz/glue-h5part), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-h5part
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 969aed7046e4965962e8ed5daa9c557baffc48bc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 969aed7046e4965962e8ed5daa9c557baffc48bc
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c26dc1954618efe30c11a0d05a826ffa37fd932.nq.gz
│   ├── 1f7f0b3a93a9fa90364b1f31da338abee707c048.nq.gz
│   ├── 3abd18a5d88bdcb24d63c7be53d9f860fdf1c93e.nq.gz
│   ├── 4a6bd8bf1d178c4bc8d1ee3cbbd238a427ec1dbb.nq.gz
│   ├── 79ea5e6d91c627945d21d5438e34ade8dbbf7a84.nq.gz
│   ├── 912ff25ce424e89249e4700676933bc1130ac468.nq.gz
│   ├── c23722130891150c4d790138abd003b41b284a27.nq.gz
│   ├── c7e9c11572b4efee42b29126f4d73dd1ae8984a5.nq.gz
│   └── e5a54fd49a50dd88075bce0ec3d49d76ce9672f7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 969aed7046e4965962e8ed5daa9c557baffc48bc.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[glue-viz/glue-h5part](https://github.com/glue-viz/glue-h5part)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
