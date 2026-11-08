# Repolex Knowledge Graph of NousResearch/hermes-plugin-solstice

RDF knowledge graph data for [NousResearch/hermes-plugin-solstice](https://github.com/NousResearch/hermes-plugin-solstice), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-solstice
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fecdeb10533c7bd1edf635594624162ed8844c28
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fecdeb10533c7bd1edf635594624162ed8844c28
│           └── chunk-001.nq.gz
├── blob
│   ├── 280d2c8fe18a5f4ad4e0e4e959e193449988a60f.nq.gz
│   ├── 3d87b06d0c9812c363d7ea4cf94d5e9af8a8d113.nq.gz
│   ├── 409affaad3c4efe1316f8e9d1a1a2e4094f81b3f.nq.gz
│   ├── 6a933f666efe54b7684bbbd31235297837ec2705.nq.gz
│   ├── 6efadc7c40d575af0a8a92cb3d27d7f6eaf305cb.nq.gz
│   ├── 75c61823b87164dde85ad0f2c78c300e011cc8a2.nq.gz
│   ├── 7dcda60013b5a460da674be9a897f60290121f94.nq.gz
│   ├── 9d39f5caf8506dac0f1826957f2d9324f7610ea1.nq.gz
│   └── eccb269b4ee7c35689a69ed961e8cd7b34c877ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fecdeb10533c7bd1edf635594624162ed8844c28.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[NousResearch/hermes-plugin-solstice](https://github.com/NousResearch/hermes-plugin-solstice)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
