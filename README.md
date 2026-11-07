# Repolex Knowledge Graph of borgbackup/borg-mcp

RDF knowledge graph data for [borgbackup/borg-mcp](https://github.com/borgbackup/borg-mcp), parsed by [repolex](https://repolex.ai).

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
rlex download borgbackup/borg-mcp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 78b9269f9ff62b3eb4407985cfb72ffa308edcba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 78b9269f9ff62b3eb4407985cfb72ffa308edcba
│           └── chunk-001.nq.gz
├── blob
│   ├── 083e8889d74fb9b0db26ea2f00c5a2740d04676a.nq.gz
│   ├── 0aca6c48e524f3032c9fd1f7be5ecb2bc8bf03f2.nq.gz
│   ├── 0e174958b1287e2ac083a8e23eb639171f8635c0.nq.gz
│   ├── 1c0a48f45f088602cca292f88a3e21c15f328838.nq.gz
│   ├── 344d9d2134dc44c3faa8cab046736a3f43f39382.nq.gz
│   ├── 4cf67d92f35e68532ae5b21dc66a81f188962587.nq.gz
│   ├── 4f50b7d61f2a5f200b055ceb85e5e1fa358eb40f.nq.gz
│   ├── 53ed6389cc6b0c68ff663f1ef514f711db4a69d5.nq.gz
│   ├── 5b5decbc4a998d5ae6d02b6536d3c9c79c825782.nq.gz
│   ├── 6106ab9fb1ed20ab8c41f839ed13d0d9f2e59c1f.nq.gz
│   ├── 63106e98b6cdd633bc7e48bfe0ac885642dfb3b6.nq.gz
│   ├── 63ebffda0b4cebac8b50e2c3171483baf8c2d25d.nq.gz
│   ├── 7da00438246db2730d5a513e61c31765afadcee6.nq.gz
│   ├── 8344f906229f1eab8a878642943aa393c5180a95.nq.gz
│   ├── 83c6d1bb284c1f46dc9d8db17c733cbd5569a79b.nq.gz
│   ├── 8596dcc10265f149c11182eba54416b0f9decb97.nq.gz
│   ├── 9d17f702b9994d4fbeb39492569b2612f60c257c.nq.gz
│   ├── b031cc8ac16469d76035feb83796518fb3dee739.nq.gz
│   ├── b63acbf296d43821d3355b56bc00d49b058209e7.nq.gz
│   ├── be793e1b1861b91b8955fdccca140d326f4b15b4.nq.gz
│   ├── e2b3ce538fd8c41f810f9dd64ac897422afc81fb.nq.gz
│   ├── ee3254105961f5f535a4fa003286d95ec6613828.nq.gz
│   ├── f6e469c0059bf32b860f984063baf4f4691b70f2.nq.gz
│   ├── fbaeedc1e932f3bbba8b8ecc400ffe6380668748.nq.gz
│   └── ff480818a1ac5c7378561a602a97bbd6aef567dc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 78b9269f9ff62b3eb4407985cfb72ffa308edcba.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 31 files
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

[borgbackup/borg-mcp](https://github.com/borgbackup/borg-mcp)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
