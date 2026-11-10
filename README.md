# Repolex Knowledge Graph of rayon-rs/either

RDF knowledge graph data for [rayon-rs/either](https://github.com/rayon-rs/either), parsed by [repolex](https://repolex.ai).

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
rlex download rayon-rs/either
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1e4326df5972eb4a0ced66cb3b67fa0c5aca8493
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1e4326df5972eb4a0ced66cb3b67fa0c5aca8493
│           └── chunk-001.nq.gz
├── blob
│   ├── 027e9431676947ab0e52adadcf6d9529b8f18738.nq.gz
│   ├── 0dae0804567a928545ccb1f2bf849725a0a4d5fe.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── 5462b23fd70cd7b95f8760de0390c26311471eae.nq.gz
│   ├── 73746c80f11f156cb6dfd27868d436e567d732ff.nq.gz
│   ├── 842e45d0435e595b972d7a5499bf3ed7142de7bf.nq.gz
│   ├── 9203baa055d41d89e1ab8f4d6aa9180a49e078a7.nq.gz
│   ├── d1316935c4dc823d1f396c1eca3d8d26705fa604.nq.gz
│   ├── d294c6e0f3ef9072b877e93be4c15117d10671d7.nq.gz
│   ├── d62dd7d06546653a1f94ee31f89d0df77dfb128b.nq.gz
│   └── d7d1ba0651cd972e400bf22708dc913925aa2018.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1e4326df5972eb4a0ced66cb3b67fa0c5aca8493.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[rayon-rs/either](https://github.com/rayon-rs/either)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
