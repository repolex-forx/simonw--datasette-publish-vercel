# Repolex Knowledge Graph of simonw/datasette-publish-vercel

RDF knowledge graph data for [simonw/datasette-publish-vercel](https://github.com/simonw/datasette-publish-vercel), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-publish-vercel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1559d979b4e3b1f2f83c51c3c0c10192ff9a6d0c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1559d979b4e3b1f2f83c51c3c0c10192ff9a6d0c
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 6677107a90d8f2d28b0bf877c7bdf8d6d120d93a.nq.gz
│   ├── 6cae2478c13a7bd0d9ba99579eff62a14068b5ba.nq.gz
│   ├── 6fdf934af028a0a31a303f29bf170fee7dcdf1c2.nq.gz
│   ├── 8292590cc4fc36cffd8b070cb2a72fcdc17fb184.nq.gz
│   ├── 9db3e060cf9d00939f94862a53b2b44480545a56.nq.gz
│   ├── b87fae6693af94b526b3c6f45af49e5bcb5fdf74.nq.gz
│   ├── c3fb588531ad4d777ddd6a7c5ddd6020b985fd92.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e9e6501a943ce38ff79b0b132e1e975d268e3db7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1559d979b4e3b1f2f83c51c3c0c10192ff9a6d0c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[simonw/datasette-publish-vercel](https://github.com/simonw/datasette-publish-vercel)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
