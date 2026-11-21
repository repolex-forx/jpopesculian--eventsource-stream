# Repolex Knowledge Graph of jpopesculian/eventsource-stream

RDF knowledge graph data for [jpopesculian/eventsource-stream](https://github.com/jpopesculian/eventsource-stream), parsed by [repolex](https://repolex.ai).

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
rlex download jpopesculian/eventsource-stream
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3d46f1c758f9ee4681e9da0427556d24c53f9c01
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 3d46f1c758f9ee4681e9da0427556d24c53f9c01.nq.gz
│   └── repolex
│       └── 3d46f1c758f9ee4681e9da0427556d24c53f9c01
│           └── chunk-001.nq.gz
├── blob
│   ├── 0cb80bd8c2d8888d650615dd701a9238da580252.nq.gz
│   ├── 3f2425e6260b7be87df28a4f5dcddbfc6f37c229.nq.gz
│   ├── 3f6ba7c83d74eaf5cd6fa3f322b2591daa043e0e.nq.gz
│   ├── 6b3a84bd71fdec71f17665ff8f4fabbce66d92d7.nq.gz
│   ├── 850b222ca79929048f1b21d0861baa87770a5cc5.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   ├── a84c85d32d9bf41d133ca6c013e1e05502dc30ba.nq.gz
│   ├── adb01c750a529aa8d5daa3700033ca8fe5db8670.nq.gz
│   ├── bdcb4809e4140669b677db00839a99170ac55f1c.nq.gz
│   ├── ced88fec08ab4b4694d133dfee3fa05b02a36c7f.nq.gz
│   ├── d5c1b953b395ea9153db11fa7f9e6f584da99298.nq.gz
│   ├── dee046f995eb4594482bc60fc975e8e9b1b4b597.nq.gz
│   └── f0465740db4771921615fbb4fb2055218f216f48.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 3d46f1c758f9ee4681e9da0427556d24c53f9c01.nq.gz
├── filetree
│   └── 3d46f1c758f9ee4681e9da0427556d24c53f9c01.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[jpopesculian/eventsource-stream](https://github.com/jpopesculian/eventsource-stream)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
