# Repolex Knowledge Graph of BerriAI/agentchat

RDF knowledge graph data for [BerriAI/agentchat](https://github.com/BerriAI/agentchat), parsed by [repolex](https://repolex.ai).

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
rlex download BerriAI/agentchat
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 766bae16afe73e5f5d61dd657af632d39c0e692f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 766bae16afe73e5f5d61dd657af632d39c0e692f
│           └── chunk-001.nq.gz
├── blob
│   ├── 009cd84c8c73d1bfa6afc763a857250cd0b6e6b1.nq.gz
│   ├── 0309eb9d8fb70b5f5c906b2811d7e9549334b335.nq.gz
│   ├── 03a87577af52e48964b31fc31ed9ff99b8bea674.nq.gz
│   ├── 0ba19ee5518b717c4f04a98a97cbadee3238d5dc.nq.gz
│   ├── 0f7fd60ce1acbd87d6ea458449ae3d0ea486a2b1.nq.gz
│   ├── 19f531a5b320183d4d1a23e111fe5f543f0e7754.nq.gz
│   ├── 2960a7fe0d23c950ef35a47de829f19d67c56ebd.nq.gz
│   ├── 2e933e27e3c70fa7fb10389c8fc87d35408a8e6d.nq.gz
│   ├── 32b172806738cc518fcccc9153e6ddfba7f8e96e.nq.gz
│   ├── 3443aab6f5a9cb188cdb77f029fa2d2d09318212.nq.gz
│   ├── 345adb64ac583c9ee71509c325303b2c02a74793.nq.gz
│   ├── 3f23d7393b2b859982b8f5df64e5d284b5770c3c.nq.gz
│   ├── 49f72ac5dd724f78c356644b40fbdbf828dc9f85.nq.gz
│   ├── 542b71c598f14f752f72cdb4482a1c7db4892ffe.nq.gz
│   ├── 6242ffb6f062333e7ba903d155b8a950afde4e3f.nq.gz
│   ├── 664aa4a560a737aa5f2c58928ce0c21465a66854.nq.gz
│   ├── 6f7736252944457911f61c8885edc714760d76bf.nq.gz
│   ├── 72afa625f145724882a0fb286ea43afae4287ea7.nq.gz
│   ├── 74cad0ab697b21bfee0e42178099b0bd46cdb43e.nq.gz
│   ├── 77d96749dd16d4e40220c7903f4b35497c4c9592.nq.gz
│   ├── 979d660571ae7016a7bdad99a7159a85912c8a66.nq.gz
│   ├── a30f5de0c7937d0fee748b435ff7c1fc053214a7.nq.gz
│   ├── aeceac999bb5ee435be6b305ea407bb9ccd670bf.nq.gz
│   ├── b1150fcedd5bf0e3df729b0f5c30642751a510d6.nq.gz
│   ├── b361212d24ae8e0936b8859f3e0b8a83bacd01e1.nq.gz
│   ├── b53fcb0eb5eca14ed454fc508a232db807561419.nq.gz
│   ├── cfc6cbbd08330c89e9430ff5e34322240adf242a.nq.gz
│   ├── e56b89bfd270c7cb49e026ec6fbc8dd3e4fd50b3.nq.gz
│   ├── e67a770d429c34201480e12340abfcc8ccf8bc74.nq.gz
│   └── fbf1ed897fd7ecf3808dc0f9c7ad67f83017f6ac.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 766bae16afe73e5f5d61dd657af632d39c0e692f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 37 files
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

[BerriAI/agentchat](https://github.com/BerriAI/agentchat)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
