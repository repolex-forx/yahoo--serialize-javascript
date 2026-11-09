# Repolex Knowledge Graph of yahoo/serialize-javascript

RDF knowledge graph data for [yahoo/serialize-javascript](https://github.com/yahoo/serialize-javascript), parsed by [repolex](https://repolex.ai).

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
rlex download yahoo/serialize-javascript
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4d0d8a686a2a6121f78f2f0ef7bb14dc1f92371a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4d0d8a686a2a6121f78f2f0ef7bb14dc1f92371a
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b1070066675576ea6d0508a5491c8d38b04aa6c.nq.gz
│   ├── 263382ae7a94fd05da38f8c2ef83d989d857d4ed.nq.gz
│   ├── 3c3629e647f5ddf82548912e337bea9826b434af.nq.gz
│   ├── 42aa4b282c864b25c60817f5e931a24614e92005.nq.gz
│   ├── 4a257c0b52b6e08cdc8728296bf2da25f10415a3.nq.gz
│   ├── 574da77531bfdcea79acdcf29deb8e00051e3b64.nq.gz
│   ├── 60186e3ffd82653a977cdfe869d7361dcb83cb0a.nq.gz
│   ├── 6a2ae3d3920eb60e822c1a89493fa55521846085.nq.gz
│   ├── 6f6b73825a2f13ef5bda084a8ff1c069dae50809.nq.gz
│   ├── 90e3b30a4f3b9c25bc57bb1a5e33c45a4651cc15.nq.gz
│   ├── b2a86efeeef7d7782bdb935cab5825388e78543f.nq.gz
│   ├── d38e0bb3286e186f348bb6704075f042ce04bad9.nq.gz
│   └── ed937621e80875c7cb1f612a8719ba5f8f3283c2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4d0d8a686a2a6121f78f2f0ef7bb14dc1f92371a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[yahoo/serialize-javascript](https://github.com/yahoo/serialize-javascript)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
