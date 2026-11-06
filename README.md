# Repolex Knowledge Graph of sphinx-contrib/rubydomain

RDF knowledge graph data for [sphinx-contrib/rubydomain](https://github.com/sphinx-contrib/rubydomain), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/rubydomain
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3f5466091839c4cdee036ed0fa7817c3f18fa348
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3f5466091839c4cdee036ed0fa7817c3f18fa348
│           └── chunk-001.nq.gz
├── blob
│   ├── 0bc1aa3bcc40008447e6c114613cdb3034d4649e.nq.gz
│   ├── 1c87b12aab7e00a72495f55ff81d6478e10f4f34.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 4310ae15746fc35a2a0fe40d0d7cf7919c5ac17b.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 57c201a93751def9abfbcb29d282c3ad32d3a50d.nq.gz
│   ├── 5d2c566438d46cd8f2733200dbf5e478933a5893.nq.gz
│   ├── 62a096d36baede736e7e26579e2ef285771222cf.nq.gz
│   ├── 853151b6c433a8670600318078b28dcfc2acacbf.nq.gz
│   ├── 999d1c46260fbdc18622105f7087e573dd9766bc.nq.gz
│   ├── a0e0bbb7656fd39f8c03d10e3408aa97208cfa49.nq.gz
│   ├── a560d7597d33842d3c3e7a19557d43c26576c13a.nq.gz
│   ├── b3f12423dd7a528d72e9f6e67ecf1a41d81f585e.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── babdf9ef2d7274ac94758d55e600b237b91881a5.nq.gz
│   ├── bba02f5d399dc8480786d4361bbed77e0e971c66.nq.gz
│   ├── e67575c380e74b9e55cb41b1642e15073d390944.nq.gz
│   ├── f4961ce14841fe0a4ea86519db1df5c5a74bbcab.nq.gz
│   ├── f61d988721c77634c75cb33586a7521fbb81817c.nq.gz
│   └── fb1e50d20e0136f629d8f8d4a06736e7c2fa9e74.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3f5466091839c4cdee036ed0fa7817c3f18fa348.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[sphinx-contrib/rubydomain](https://github.com/sphinx-contrib/rubydomain)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
