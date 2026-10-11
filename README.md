# Repolex Knowledge Graph of aio-libs/aioneo4j

RDF knowledge graph data for [aio-libs/aioneo4j](https://github.com/aio-libs/aioneo4j), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/aioneo4j
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ac72fc7704d54d48bcec6bffd021ff8a160253da
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ac72fc7704d54d48bcec6bffd021ff8a160253da
│           └── chunk-001.nq.gz
├── blob
│   ├── 170d664d18da46431d44640ce145c36d60245318.nq.gz
│   ├── 1743cd5eca2c985676f6e5cd3ae188cc620804e4.nq.gz
│   ├── 26bfd12ce1f05a4c00bb417527b65c14aa14f866.nq.gz
│   ├── 272442c5bf078cc019f035cda990323ea09a93c1.nq.gz
│   ├── 3006810f656077a4927a68fca197f9a504f2bfee.nq.gz
│   ├── 430d798358ff95fdfbb4bcad3b36e41d1d322bff.nq.gz
│   ├── 75bc828745416b87dbc7c7488cb3f343e51e5834.nq.gz
│   ├── 838d5298693a6c7fbcca68cd8258cdbb3821a722.nq.gz
│   ├── 8ad3aa2acf7dec7fab38df9db62d325e66da3132.nq.gz
│   ├── 8c48fa632ff186d5d3a36fa39d38d3325134ff99.nq.gz
│   ├── 9c9e34ea6c7ed436a3877fcd41f2b9d2c7794844.nq.gz
│   ├── 9f0d65618753dfa04b20e5f4054e741a3d2d41d2.nq.gz
│   ├── a846ecd3c826383bcd148c0e70ab6cfe546ac87e.nq.gz
│   ├── acbbab68c5b636a31360657669ddd9d0e8bcccac.nq.gz
│   ├── c2be657ee163c7dffbf492d6d1fe43a058f628c9.nq.gz
│   ├── e108e298f8d2483836d54094ebe0e91c66749547.nq.gz
│   └── e24206f7951ce600070c653a55f024bdf4d78a08.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ac72fc7704d54d48bcec6bffd021ff8a160253da.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[aio-libs/aioneo4j](https://github.com/aio-libs/aioneo4j)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
