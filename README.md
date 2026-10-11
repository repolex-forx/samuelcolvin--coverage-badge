# Repolex Knowledge Graph of samuelcolvin/coverage-badge

RDF knowledge graph data for [samuelcolvin/coverage-badge](https://github.com/samuelcolvin/coverage-badge), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/coverage-badge
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5b90140d73909a3057a448c93c9cee5a41fb91b2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5b90140d73909a3057a448c93c9cee5a41fb91b2
│           └── chunk-001.nq.gz
├── blob
│   ├── 3c5bc34dfd5de7d29ba62444ca9b81b401959ae5.nq.gz
│   ├── 3e6a6e32debb3d212a4c4f6517a7bca7c8a57005.nq.gz
│   ├── 5040e6bc3d806232df4c14afcc2c134588407ca6.nq.gz
│   ├── 67bfcf654801fa3afab4f1406e8a09bdf975fb58.nq.gz
│   ├── 877ca5c0f684793702fcdddd6245feb990204d15.nq.gz
│   ├── 949a904530874148fd9e9180d9dc3a01ff36486d.nq.gz
│   ├── a31f38d4cb79bfd7692235b7662d41c1851045ad.nq.gz
│   ├── b63c23f111ed2000129bfee9ed39a6c63eac579b.nq.gz
│   ├── bd62beb1b41a7ab6e9ced367eec9d157d22dd662.nq.gz
│   ├── e3d79a08e02a4afb97f1eaed6b4d04bbe05b490b.nq.gz
│   ├── e70c1e1bdbfab06aa322d3a2b4b3fd9d162e2537.nq.gz
│   ├── ede40f4fa4f5e5a4f2953b2a433bef43c46c1b78.nq.gz
│   ├── eeb4d8b4aa3f3fac29ba07432a306ca5b8e72720.nq.gz
│   └── f787b23add4816d12887e583ce667ac645f8234b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5b90140d73909a3057a448c93c9cee5a41fb91b2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[samuelcolvin/coverage-badge](https://github.com/samuelcolvin/coverage-badge)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
