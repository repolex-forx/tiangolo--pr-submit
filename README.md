# Repolex Knowledge Graph of tiangolo/pr-submit

RDF knowledge graph data for [tiangolo/pr-submit](https://github.com/tiangolo/pr-submit), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/pr-submit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e9feee6f7575f0483fe523a2ecc9308bdd6bd573
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e9feee6f7575f0483fe523a2ecc9308bdd6bd573
│           └── chunk-001.nq.gz
├── blob
│   ├── 0965a2f2ca1dd78b5cce1eb4ec6f08c667a59caf.nq.gz
│   ├── 0ff7116d903047cceb942abb10981226e0dfb676.nq.gz
│   ├── 11f29d2247da8b21a709315adfb6d0402d695e6d.nq.gz
│   ├── 17d0b360a4180666d7457b5e380b5dcea83a2848.nq.gz
│   ├── 2836813fc9aedc9fb04fa4447582e6d97fdfd1eb.nq.gz
│   ├── 289d8a8b3e49a2ee6034b5111101d7227338e55f.nq.gz
│   ├── 2c715e5d4e1abae5879be9966e9e45bcd32fbb8c.nq.gz
│   ├── 41a4a77b71283cb1850ce5b7ef93918cf6efa21b.nq.gz
│   ├── 420c81cc5d542776df1cdafbb6548e36f8b36c80.nq.gz
│   ├── 4a6fee5525834061437e07672e3bb817d2333485.nq.gz
│   ├── 4b77dcddf1b670cb0f5089a1941f863a617b1d6b.nq.gz
│   ├── 4e8ce8015d6864f86658ece9a8d62c2439e6701a.nq.gz
│   ├── 505f44404f867c8153eac8f6f5e42efe25aa8ac7.nq.gz
│   ├── 5473b12c4a15ac44ca89b187e6b49ae32236abd9.nq.gz
│   ├── 5f1cba39fab80a617b0f6cda9d0a867acf6c89c8.nq.gz
│   ├── 5f2bc01f8447e1927a8e653bc2b6937bb40e2fd6.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 784f00a349a141a7b2dd7897e47430a425e10a31.nq.gz
│   ├── 79308f91a1b1c0cafe1067dc604ef38dafb69114.nq.gz
│   ├── 7aea8b77090513534e55fdd468941c14fcd276dc.nq.gz
│   ├── 85e2343a41195b82944fe23d01f8245d2a4d1bad.nq.gz
│   ├── 88bb106db31f90a71b3d673ef0b0188ab7fd28b5.nq.gz
│   ├── 8921e8df69b886f9baafcc6e3a1f504de8f45373.nq.gz
│   ├── 8b137891791fe96927ad78e64b0aad7bded08bdc.nq.gz
│   ├── 8dc006060a91211097221b51302dfa60d1fee337.nq.gz
│   ├── 9a3615dde623fc365fc82c238e7a7fe314e6b855.nq.gz
│   ├── 9a40423971b3ee917951f3750114c1d320e77ef4.nq.gz
│   ├── ab691199d2e4f6fb95883a26c9406c4a58d7e564.nq.gz
│   ├── b4b376fbf0398cb12cf42c6095f9163d1a1e53c2.nq.gz
│   ├── b7df89ceaf897656fdf9692cd21bbf5258f0c855.nq.gz
│   ├── b8b44119a4fb246d5f310ea991c64cf1da1a35f3.nq.gz
│   ├── bde54cc88576c72a50830b17ed76529805bba8d3.nq.gz
│   ├── c03cca90b698696ba18bcf31c5f83d079a1a6eb3.nq.gz
│   ├── ca3c2467dde78e00839895c22386b4392f8fcd5a.nq.gz
│   ├── d076998d0d177a2afff6e1ad33ee57b489ef820d.nq.gz
│   ├── df71f626ef2d5ba271afbf50aad8fc34618d52a9.nq.gz
│   └── f903509340ad941848f6933a9ba52afa1df1833e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e9feee6f7575f0483fe523a2ecc9308bdd6bd573.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[tiangolo/pr-submit](https://github.com/tiangolo/pr-submit)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
