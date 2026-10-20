# Repolex Knowledge Graph of pyeve/events

RDF knowledge graph data for [pyeve/events](https://github.com/pyeve/events), parsed by [repolex](https://repolex.ai).

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
rlex download pyeve/events
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e8ec95bed91aa6f86d39a72cbcfb16a9dce819a4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e8ec95bed91aa6f86d39a72cbcfb16a9dce819a4
│           └── chunk-001.nq.gz
├── blob
│   ├── 014e41dcd9cddf46c1538b08a239ec8ea4dd5c0c.nq.gz
│   ├── 082c0ecac42a17beb17c98fff5178857ca8e7404.nq.gz
│   ├── 13da4f261a2703cc3b620d19fb25b7fa0e8543e2.nq.gz
│   ├── 45252707005da1089c36cdc06f7bdc76b030b447.nq.gz
│   ├── 485fd48c26016b3694de7d3aec1f8437f1cce5b8.nq.gz
│   ├── 4f723d575f295b009e3c15483d64fdca3ce73eaa.nq.gz
│   ├── 72c865c215d67e8febe132d7286a2c38e7c2365f.nq.gz
│   ├── a0775d51e3a8cf76f9bd61ac5c3e3a0fc796e141.nq.gz
│   ├── a5021c60e36ae085d1ef96c1fed9d88c2f65dd53.nq.gz
│   ├── a9f90412283130df22bdb7c4c4ad6aaf56cf679a.nq.gz
│   ├── afe9010b79f1615e5cb5a038059a8db8a8eb13ef.nq.gz
│   ├── c23776d45db6d6884d593793f5e478452a333479.nq.gz
│   ├── c5b03b212ec32b6a9094b6954e1116800308b254.nq.gz
│   ├── c69d175a618bf0d446c2fd8d2f89ba2d4e9d433f.nq.gz
│   ├── d44697564e26421518ead16d1a3484aeeeb0752f.nq.gz
│   ├── da7f94c449d3deb7590c400ef814869d0657d318.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e8ec95bed91aa6f86d39a72cbcfb16a9dce819a4.nq.gz
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

[pyeve/events](https://github.com/pyeve/events)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
