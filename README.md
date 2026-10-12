# Repolex Knowledge Graph of datasette/datasette-agent-modeler

RDF knowledge graph data for [datasette/datasette-agent-modeler](https://github.com/datasette/datasette-agent-modeler), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-agent-modeler
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 99844d7b5010bb33a2bb6a07cbd7c6c3dbcdf509
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 99844d7b5010bb33a2bb6a07cbd7c6c3dbcdf509
│           └── chunk-001.nq.gz
├── blob
│   ├── 020ac8a3c84a3d7961c3b8de581a5f2bef5ef16d.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 57f0cfdf9183a2b2029d0446bad3451ebc7d8012.nq.gz
│   ├── 6d461e915a3b9570bbc4e1d748595dfbe38e4f2a.nq.gz
│   ├── 7b989cbccc5e3ab9cd039afd21acb262f4580197.nq.gz
│   ├── 843e57d0581ea264f7b4bb9dec01788717cfe548.nq.gz
│   ├── a6a96bb7d486d9df8e33c862f4bf8cecc51059ac.nq.gz
│   ├── b8a2a436b293016758b373603c0d35e3fb9ebbf4.nq.gz
│   ├── bf8b98af886de513e45bba57effdba7d72fa98de.nq.gz
│   ├── de314fa05458fa1482962590dd81b551176771b7.nq.gz
│   ├── eb22e74eaaaf0edc4aa2c0f8900a55750d1660f9.nq.gz
│   ├── f93f09cc2e42c94de424f3b9bb4df9337b12652a.nq.gz
│   └── f9db6178e08ac5e4ddd067387b9589ae1b212297.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 99844d7b5010bb33a2bb6a07cbd7c6c3dbcdf509.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 19 files
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

[datasette/datasette-agent-modeler](https://github.com/datasette/datasette-agent-modeler)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
