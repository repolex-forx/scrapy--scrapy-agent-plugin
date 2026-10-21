# Repolex Knowledge Graph of scrapy/scrapy-agent-plugin

RDF knowledge graph data for [scrapy/scrapy-agent-plugin](https://github.com/scrapy/scrapy-agent-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/scrapy-agent-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d424e42a35116c108e986614b75ec7cd9cf9909e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d424e42a35116c108e986614b75ec7cd9cf9909e
│           └── chunk-001.nq.gz
├── blob
│   ├── 15a5a5388f84ba2942e8a0f77ceba212bf70870b.nq.gz
│   ├── 1b10c012a9f6f24827be461cf7f911562ba35e1b.nq.gz
│   ├── 3a3fe69757e22530c5cf848e061acb180e69444d.nq.gz
│   ├── 4edb626b20a6fd4de811afdd390028d70c8dda04.nq.gz
│   ├── 57f9c3618789a2779c9a60d1b6a7e374cdfa98a9.nq.gz
│   ├── 7a79fafb4211db519aa5cb0d23c997c396f4beeb.nq.gz
│   ├── b0eb6d8d209dae15532968124102d0708e724a3c.nq.gz
│   ├── b7e851bd219ea8dc0cbe5945bfb9b095c865b5c7.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d797e20a37ea6684048f5fabf40efacc1626e44e.nq.gz
│   └── e3922457465a86a60cb6d866fd494bd51583186d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d424e42a35116c108e986614b75ec7cd9cf9909e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 18 files
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

[scrapy/scrapy-agent-plugin](https://github.com/scrapy/scrapy-agent-plugin)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
