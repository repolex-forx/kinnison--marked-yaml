# Repolex Knowledge Graph of kinnison/marked-yaml

RDF knowledge graph data for [kinnison/marked-yaml](https://github.com/kinnison/marked-yaml), parsed by [repolex](https://repolex.ai).

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
lexq download kinnison/marked-yaml
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 76470a02f356b727d60d99d6210645f3813a0f2e
│   │   │   └── chunk-001.nq.gz
│   │   └── ace1cc4f8af7c38b7c07ec5ed35678955fbb2759
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   ├── 76470a02f356b727d60d99d6210645f3813a0f2e.nq.gz
│   │   └── ace1cc4f8af7c38b7c07ec5ed35678955fbb2759.nq.gz
│   └── repolex
│       ├── 76470a02f356b727d60d99d6210645f3813a0f2e
│       │   └── chunk-001.nq.gz
│       └── ace1cc4f8af7c38b7c07ec5ed35678955fbb2759
│           └── chunk-001.nq.gz
├── blob
│   ├── 0049ff18aff12768ee5353c2f465082f3138a30d.nq.gz
│   ├── 0ab690ecb3987605fea8141dee7d015df8598bf4.nq.gz
│   ├── 0fc9e728b1933e6741f3683ef5de92580197caf6.nq.gz
│   ├── 191328c470f3fa2aac15260f5df939e008b00fa6.nq.gz
│   ├── 298d86cb1f613cb6cd9259dc1725b2bf442c6d99.nq.gz
│   ├── 2ab093da013d40a09ff26656af39cb8c97a8492f.nq.gz
│   ├── 315a1cb0f3a5c41d5485dc22ee7dfdf1d4f0dc13.nq.gz
│   ├── 3ae2ff5400ed9fc062ca83726fba42308d37029d.nq.gz
│   ├── 61fde960f1627d8a7c299e502f4e68e96af2562d.nq.gz
│   ├── 660fdbe3a114a26d16cd319c15d4f97bf7d5d41f.nq.gz
│   ├── 66ece771cc9f495d044a138018b6e0dbed37888e.nq.gz
│   ├── 78cce8bd6788cc314ee44e665bcb9603a504e5fe.nq.gz
│   ├── 7e494c39a0b432751ae4b9a7902bdea9110c7fef.nq.gz
│   ├── 7eeec2009029fba399cf066018e44be5a3e5a8fb.nq.gz
│   ├── 93e0f22515fb9875d08efe3c68ec3cd048776ec3.nq.gz
│   ├── 96f7e4ee582ef7726ed09ed702efe4cb57e59f4d.nq.gz
│   ├── a86f5db1f6fc3ee6437b920b55fb91fcf06744c7.nq.gz
│   ├── ab38666060d599349844ab8e188d63cfea3528d3.nq.gz
│   ├── ba149be222bd2f0ef6ba9ed04e3f0394ae5e2c16.nq.gz
│   ├── bf69b9827659e453783bc10cfce4bf3ee406ec7c.nq.gz
│   ├── c814e438e65340026aa7fdf7e459ec49e7cfc7e3.nq.gz
│   ├── cdfa0cdea32e8812a5e1e661203f04cba18a1da5.nq.gz
│   ├── cf342d800ba6acde6a8cd774850b45ef20cf8c31.nq.gz
│   ├── cfbfc3cb770f58c7bc793f7bde8528d4c2744982.nq.gz
│   ├── d5aabfe8907d3913d5a5e3ca54a8b6f7ac70d32b.nq.gz
│   ├── d5c9449cc995b14290dcfe3efef7601755d83ca8.nq.gz
│   ├── db5f357069d9b0bba8dc44499e3b1f7876ef8677.nq.gz
│   ├── f04fbfc44c0c59cf72ea30658de95d52ab90e7b6.nq.gz
│   ├── f98d1a1a2bec89c3cb484fd89d8b8cddd72bebe5.nq.gz
│   └── fb7a43b488d595c3dce1f26f43e8efd8dac4735a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   ├── 76470a02f356b727d60d99d6210645f3813a0f2e.nq.gz
│   └── ace1cc4f8af7c38b7c07ec5ed35678955fbb2759.nq.gz
├── filetree
│   ├── 76470a02f356b727d60d99d6210645f3813a0f2e.nq.gz
│   └── ace1cc4f8af7c38b7c07ec5ed35678955fbb2759.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

17 directories, 45 files
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

[kinnison/marked-yaml](https://github.com/kinnison/marked-yaml)

---
*Parsed on 2026-05-11 by [repolex](https://repolex.ai)*
