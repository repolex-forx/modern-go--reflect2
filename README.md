# Repolex Knowledge Graph of modern-go/reflect2

RDF knowledge graph data for [modern-go/reflect2](https://github.com/modern-go/reflect2), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download modern-go/reflect2
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2b33151c9bbc5231aea69b8861c540102b087070
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2b33151c9bbc5231aea69b8861c540102b087070.nq.gz
│   └── repolex
│       └── 2b33151c9bbc5231aea69b8861c540102b087070
│           └── chunk-001.nq.gz
├── blob
│   ├── 00003dbd7c57da7a18546b0daf4a4af3ff44dd3f.nq.gz
│   ├── 10ef811182d1c57274cfb705e52ccbdb66f5f270.nq.gz
│   ├── 13941716ce3a2591df867f64b888266ef080e520.nq.gz
│   ├── 1c6d876c7f50256a9d8e44f0a00cddcce3ff0b60.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2b4116f6c9bec1320b5bfffd1e8fa2b23228b29d.nq.gz
│   ├── 37872da819107fd907b397de9d589452146b4291.nq.gz
│   ├── 4b13c3155c80d9bb27447bd3f48026f26c8ad89c.nq.gz
│   ├── 5eb53130a20980ff9a150b60d3086b57077d9ddb.nq.gz
│   ├── 62f299e40453622ade6e53e91beba8b5694ffc3d.nq.gz
│   ├── 6f968aab9ecbaeb92002a65d39f49682324387f3.nq.gz
│   ├── 76cbdba6eb1bb5814a1b0449f7c0706066badc2f.nq.gz
│   ├── 7b26c946dc6c79f2daf40411c5671cdee7719cdf.nq.gz
│   ├── 804d9166397bb34b841b3081773a381c0758ca50.nq.gz
│   ├── 805010f3a0c553db57da2e791ebbe15672b798a5.nq.gz
│   ├── 88362205a2bb5d724b841bce797c75ff9893bb63.nq.gz
│   ├── 8e5ec9cf45ed86b762db6244e2cb31b5b7dcead4.nq.gz
│   ├── 9057e9b33f2a797b150bbd4961e1e5cf219e761b.nq.gz
│   ├── 974f7685e495deeaf4c55c3db47e0d99f027e3b7.nq.gz
│   ├── a9bc5061b042ad8b1e07c04f9cbdf9a86c9387b4.nq.gz
│   ├── b097728dbffdaf53d46524c1e967c4ef48d0375a.nq.gz
│   ├── b49f614efc58d9495df914e3a8b4dcb86ba467b6.nq.gz
│   ├── b60195533ccf5f8bdb8087ac0a009b9be3b456a0.nq.gz
│   ├── bcce6fd20e5cfa99137433e84e033eaf7e162a82.nq.gz
│   ├── c43c8b9d6297d2a29b9103e22be3b9a294cdefd0.nq.gz
│   ├── d4ba1f4f80e979f5157832f1f5014b9a63edbd9d.nq.gz
│   ├── e5fb9b313ecdbad6ec3a57cf39872ab3a7dbc564.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ee4e7bb6edfdd031eb6fc2c06a7550e249a6d0b7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2b33151c9bbc5231aea69b8861c540102b087070.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 38 files
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

## Source repository

[modern-go/reflect2](https://github.com/modern-go/reflect2)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
