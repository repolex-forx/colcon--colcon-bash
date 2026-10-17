# Repolex Knowledge Graph of colcon/colcon-bash

RDF knowledge graph data for [colcon/colcon-bash](https://github.com/colcon/colcon-bash), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-bash
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7f850b6eb264e00ace34b9967a6cb6ea2d7ed9a2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7f850b6eb264e00ace34b9967a6cb6ea2d7ed9a2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0efe609ee067e3e0b79e0428e979f4250981f974.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 29f2d06570b1f2a86a2be17975dd42d1875d3416.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 32cf4f9081e7c189de11dadb89eff234c010b286.nq.gz
│   ├── 4b798b7bb25faa193edce7cd6c35660e8dd106d4.nq.gz
│   ├── 73f14e904911a27fee75364ef30aa4bcec201d95.nq.gz
│   ├── 790fe7f683ed1db3007faf2521239a225f63b3f7.nq.gz
│   ├── 7fcdeb13ddec293e45a8a2d9d54a9ba9f0e4dc65.nq.gz
│   ├── 823f08d26437aa4a55057c660578509ee7677eae.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── b63df1cb4c10d35628c05d496e378c24a1c90b78.nq.gz
│   ├── b8631d92166c48c39f1d957a88d1cfd76207ed86.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e5542827ee3fdba67c3fd8134713b5fdfe7942c3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   └── eca76bf1e2d2b5b65bf3872ea711d1afc2c92cda.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7f850b6eb264e00ace34b9967a6cb6ea2d7ed9a2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[colcon/colcon-bash](https://github.com/colcon/colcon-bash)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
