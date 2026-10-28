# Repolex Knowledge Graph of huggingface/ipython-harness

RDF knowledge graph data for [huggingface/ipython-harness](https://github.com/huggingface/ipython-harness), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/ipython-harness
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33e4bb042ae91a2d2042d67e553440786f22b8c8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 33e4bb042ae91a2d2042d67e553440786f22b8c8
│           └── chunk-001.nq.gz
├── blob
│   ├── 0804c625ba2e2530d1e1f8a737c95f578d753dc5.nq.gz
│   ├── 0af73bc09fd134344094359cdc0dc25776439b96.nq.gz
│   ├── 2186bb9cc937d5dacd35419f1a5c0b6f9523df4b.nq.gz
│   ├── 35833c790610cc9af3d1ff97c2b6b911bb039e98.nq.gz
│   ├── 37e0eed3034d8ee4c7664b55944cf64d8b0e941b.nq.gz
│   ├── 3cab65d0fde14f982fcb6646692bb7c98be3d990.nq.gz
│   ├── 3e95b719050df0be96da5d3a8bc40c769328777b.nq.gz
│   ├── 482158174d651950e814fc74715b9cea5599535c.nq.gz
│   ├── 64ac73fab4bd050b776895db16ffbf5761e4f24b.nq.gz
│   ├── 759d10b9e56139c8eca3f388bcc675bb66075c51.nq.gz
│   ├── 783d513fccdf202e8668a195815458418ec72568.nq.gz
│   ├── d2e5b64fe1828fed6611b13203cf61281f2268ce.nq.gz
│   ├── d723f0e17369e984b3507e2f67d58ad10abdc0f1.nq.gz
│   └── e282e5460a1477e10093ba86cdf2feca50c89206.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 33e4bb042ae91a2d2042d67e553440786f22b8c8.nq.gz
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

[huggingface/ipython-harness](https://github.com/huggingface/ipython-harness)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
