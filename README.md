# Repolex Knowledge Graph of augmentcode/auggie-zed-extension

RDF knowledge graph data for [augmentcode/auggie-zed-extension](https://github.com/augmentcode/auggie-zed-extension), parsed by [repolex](https://repolex.ai).

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
rlex download augmentcode/auggie-zed-extension
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b377ae129e6bb1f5297b9f0a191dbad03f3ce8ec
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b377ae129e6bb1f5297b9f0a191dbad03f3ce8ec.nq.gz
│   └── repolex
│       └── b377ae129e6bb1f5297b9f0a191dbad03f3ce8ec
│           └── chunk-001.nq.gz
├── blob
│   ├── 022db64195e4076ab41c0d3e06ee62aa10bf1096.nq.gz
│   ├── 16f226ce0e01ef48fb87a6af900bfcd52d7f7637.nq.gz
│   ├── 512a7b1fb58bbfd094f3b96c9e582637488eb02a.nq.gz
│   ├── dd017ec8b6c00a75ae3e7037e8e7da8ecb42051d.nq.gz
│   └── e3e189df75f7231040853ce0ae74e9c64bca064f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b377ae129e6bb1f5297b9f0a191dbad03f3ce8ec.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 14 files
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

[augmentcode/auggie-zed-extension](https://github.com/augmentcode/auggie-zed-extension)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
