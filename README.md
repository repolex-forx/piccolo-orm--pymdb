# Repolex Knowledge Graph of piccolo-orm/pymdb

RDF knowledge graph data for [piccolo-orm/pymdb](https://github.com/piccolo-orm/pymdb), parsed by [repolex](https://repolex.ai).

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
rlex download piccolo-orm/pymdb
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a32f91f8ab99147c0d2fd848b5f393af309de078
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a32f91f8ab99147c0d2fd848b5f393af309de078
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d45d3a357e7dcecfbb9f3019448976b1edd7ef2.nq.gz
│   ├── 1b7340b80bf93851197567074298350540581f73.nq.gz
│   ├── 1c1cda62e1d06ba6d06c3f10572d2ae656813a8e.nq.gz
│   ├── 1efbe2a3750e015149bf7ad1efcdfb25a7ad1620.nq.gz
│   ├── 3fe2afba3daa8b7f4c9a04ca0844ca2779f18e0c.nq.gz
│   ├── 496cc43812d29eeb489e70c9ca64058ec8d4df14.nq.gz
│   ├── 4a52e264f8ca450c743a3ecd85a7f9f47f6f080e.nq.gz
│   ├── 502edc217a835fa04faf2335785ff28b7c308eb6.nq.gz
│   ├── 637a69853db4deb37b59beae2f13f4696648c939.nq.gz
│   ├── 8f6365d7db67b56916607f79a1834b73f4f24af7.nq.gz
│   ├── 9546f520d9e6cfca7fe1baafd33779d1888316e0.nq.gz
│   ├── 9b0bad1a6810f5003d344278b07d8cc7ed56f5a0.nq.gz
│   ├── b099a69bce04223a28c8f4892aa0c5d9f0f16174.nq.gz
│   ├── b846e13274c05245f64c5587cc817788c39f1d6f.nq.gz
│   ├── c10fd94fae7f72a9d0b7beb126ac7c6b9afe428f.nq.gz
│   ├── ce908d47dc6521cae04c90d805bcf4da98357a61.nq.gz
│   ├── dab5b5aef32212d00afdaf046dfbb801da65e717.nq.gz
│   ├── dd640d030a727ee827d3e2f0a68e59b50fe63a8e.nq.gz
│   ├── dda26687ec23e23dfe09eb68e8a05712bd51e447.nq.gz
│   ├── e7f1111c08acdd50fd04691a0d59045b4ad82a77.nq.gz
│   └── fdde65f1b9843a035da727be815876d63ea6bcad.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a32f91f8ab99147c0d2fd848b5f393af309de078.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 28 files
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

[piccolo-orm/pymdb](https://github.com/piccolo-orm/pymdb)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
