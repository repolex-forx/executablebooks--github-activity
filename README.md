# Repolex Knowledge Graph of executablebooks/github-activity

RDF knowledge graph data for [executablebooks/github-activity](https://github.com/executablebooks/github-activity), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/github-activity
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a73faf108258dd3350c8eed84693dcfec149b6d8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a73faf108258dd3350c8eed84693dcfec149b6d8
│           └── chunk-001.nq.gz
├── blob
│   ├── 04396d26d11952c639bdd09943f6bc809047d5c1.nq.gz
│   ├── 0b8a7ded198557ba34e6cbf7c14d18392521bc77.nq.gz
│   ├── 0d8dfc34ad5aace7c0746f418e5bd2ff8da923e8.nq.gz
│   ├── 170b8d788e889c7529d273ae4890d78ab1ebe078.nq.gz
│   ├── 1add150bb110a7e92a442bd51c9f915516c5edbe.nq.gz
│   ├── 20a85398b60ddd6861947694393003ce693d8a6b.nq.gz
│   ├── 28a86509a85683cc565adf754a45a3969a04ce8a.nq.gz
│   ├── 29b10eda70850c388978069fd428631fc88652df.nq.gz
│   ├── 29efcfd49ea6b5a8f4d83397dc4126ff0d43fdc2.nq.gz
│   ├── 2b5e694bf84d14a6581009210a64024904bb8eaf.nq.gz
│   ├── 2d3377a6413d83adf806de10d9ccda7580300557.nq.gz
│   ├── 34940cb24ead3e47a89aedfaa2402aaa20c37f32.nq.gz
│   ├── 3a18192aea67217ef52b13b65ccd43f660f30acf.nq.gz
│   ├── 3f0a9a63156ebe48290f62aa32b95fb3d8bb31fc.nq.gz
│   ├── 3febccf7590f4caa2ad45e38c5d9573faa4ec25a.nq.gz
│   ├── 44d753cc8ffc7361773e570d9a6998d9f36d94ac.nq.gz
│   ├── 4bf10017504f69d577adf0113ca06d7656504dd8.nq.gz
│   ├── 5f3c5dd0fa23b30eafffc7b79c324f667e0624d2.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 62e5ae5a19f321d7d37f3efabf1459ba8e3fdf4f.nq.gz
│   ├── 6369e327eb8e297e4cf37b2fcdb281102ce1d691.nq.gz
│   ├── 649279a47e39938f61c3b3266d31e245a4a8145d.nq.gz
│   ├── 85d27c95ba2eda6fd65431e27b6b1ec050d7da83.nq.gz
│   ├── 8c62366eae7e5ef6ad7c1c038206b22f0df2ebc4.nq.gz
│   ├── a3dd7f30344bb32149de3b3b47de8a71f76f0779.nq.gz
│   ├── ae0ac907be9b1004ce2881d6a3e279ca318566d4.nq.gz
│   ├── c32163fbd1956e7eb88b179add8ff79feacca01f.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── d4ce96df21c2133e3682842a9886159632ffd5c0.nq.gz
│   ├── d83959de0c8a6208a821aae8612c5f23a121222a.nq.gz
│   ├── d9e79ba64848091a9bccd21dc241c61c669dad7f.nq.gz
│   ├── d9edbfaa0f37ed6ef4370e2da552c5d6d94de9f5.nq.gz
│   ├── dba8c77e5f34253956fa481ce4f4732d3dc508aa.nq.gz
│   ├── e222104b8a79c94d548cd75e8ffc8f74a67d0761.nq.gz
│   ├── e67844b9ae7f05ae7090f6964c627b746a116b77.nq.gz
│   ├── e6d1e4fdbf5e6df4266eec4693e3cf86451102f3.nq.gz
│   └── fd9abba71206f833b296ad00da44f6fa4c74f80b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a73faf108258dd3350c8eed84693dcfec149b6d8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[executablebooks/github-activity](https://github.com/executablebooks/github-activity)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
