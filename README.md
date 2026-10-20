# Repolex Knowledge Graph of klen/pytest-redislite

RDF knowledge graph data for [klen/pytest-redislite](https://github.com/klen/pytest-redislite), parsed by [repolex](https://repolex.ai).

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
rlex download klen/pytest-redislite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 41885984231f989137c1f72f39eb50cd6132fdf9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 41885984231f989137c1f72f39eb50cd6132fdf9
│           └── chunk-001.nq.gz
├── blob
│   ├── 04793fcc5d6bb125a804cc9e475f0e6adee87558.nq.gz
│   ├── 65cd23ccd489b059472333d654b8029856fd8bc9.nq.gz
│   ├── 6c8fb2aa53856018854a8952e25e28a72aa55192.nq.gz
│   ├── 8cec47bab7a317f8b6d8ea464f30b59f782fbd14.nq.gz
│   ├── 8f9ba978b63e3c658a8e7d748d0fc37c5d1296be.nq.gz
│   ├── bb9a2d8dcfb7bcae9511c3adebf087aca48d693f.nq.gz
│   ├── ca434b77fcfa19b6b8e8dbfc2fff2dc90c9f7cba.nq.gz
│   ├── d063574d7f82f53b73cccb989fc0dc1b523251e9.nq.gz
│   ├── d5c6f1f71f070f5fc901e85f3ef072199ee741f7.nq.gz
│   ├── e4bce2447ba72edd22869c7b3a61acd1a398dc3b.nq.gz
│   ├── e5d11aa557ed05d0bd9cde644c007570eef0ffac.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eba8fc9f95ed477e4496169499769f4106e70f5c.nq.gz
│   └── f9e571075dbb245ba53f16b92417d0b114862b99.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 41885984231f989137c1f72f39eb50cd6132fdf9.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 21 files
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

[klen/pytest-redislite](https://github.com/klen/pytest-redislite)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
