# Repolex Knowledge Graph of UKPLab/emnlp2025-automatic-error-discovery

RDF knowledge graph data for [UKPLab/emnlp2025-automatic-error-discovery](https://github.com/UKPLab/emnlp2025-automatic-error-discovery), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/emnlp2025-automatic-error-discovery
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 556dcf1c4c8a07a9b0c13515d5a356cf6a67132b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 556dcf1c4c8a07a9b0c13515d5a356cf6a67132b
│           └── chunk-001.nq.gz
├── blob
│   ├── 05c6d70892d9a3cbb12bd289b3e3b9f6a7afe57a.nq.gz
│   ├── 229edba242bb190698662cdce6bdacde9f0769fe.nq.gz
│   ├── 2ff4edc28e4eb0cd72dd5c8f65f0953691100d57.nq.gz
│   ├── 32b18c2ea7b0397c5ef90dc4a0e1f7cdb2e3f65e.nq.gz
│   ├── 3469812e298d54b076863a639b5b1bfdf711a9d9.nq.gz
│   ├── 3647a54d9ef34663f4c7380a0465e451c11c5501.nq.gz
│   ├── 413b1a22c9807c7fb254d9ff18183ca23d9c365b.nq.gz
│   ├── 5089a440cbfc8b72975101f51c43e79b298848b4.nq.gz
│   ├── 536e578b5c00901298fad4fbde7429455b6abfe8.nq.gz
│   ├── 5fd4ee8eec27030b5f31f8973cff149811c1e048.nq.gz
│   ├── 61fd35397f1595e4a0823624e9c77a04f53a1304.nq.gz
│   ├── 7423199e2e9146dd8b0eb800445275de4b69e0fd.nq.gz
│   ├── 7b58fe0ed9dc60bd8d0cd4d06537b6b09e078af6.nq.gz
│   ├── 7c0e81b22f352f3aaec7773632ceac2987df6191.nq.gz
│   ├── 7fc94e9deea4430896e88710e8e144a5523107a8.nq.gz
│   ├── 80511bf08174be29483c3809d79856f0255bbff4.nq.gz
│   ├── 817e23de0bf24c58c6608c5785b2f0b43b06c337.nq.gz
│   ├── 8b73aa4be60a811e65a2fdcfc247d67002668754.nq.gz
│   ├── 9b3703a912d40f58fb0fb57d20742e53d9fe7671.nq.gz
│   ├── 9e823f5d0c08c290a39768d0641cf79d48101e5c.nq.gz
│   ├── 9eca256dc9464e00f6326de3ff3a86ac0cc9dd09.nq.gz
│   ├── a980b06fc199d38c3debbb1ca49fd4c4f33a917b.nq.gz
│   ├── ad908a3a04c2f8fe32465355d78e28ad9ea54baf.nq.gz
│   ├── b95cd5872a8865e31eabd5ed175fe25bca850752.nq.gz
│   ├── c0278cc2a5080ef701cf35a98807192b6c5e6888.nq.gz
│   ├── c08a79032592be8f5e7318991b0242323389469d.nq.gz
│   ├── c6718de5c5ae59d2c22141a147f5afba41af9cbb.nq.gz
│   ├── c820c621b6e004fae801c051284525af99376b87.nq.gz
│   ├── ce383f41d069dcc68c67683603f6939b7c899fb6.nq.gz
│   ├── d11966f8f02f74a0e54638f6e9232fcef2688ee9.nq.gz
│   ├── d4edebf5b8e887e99e1ad1ec294077864d032b23.nq.gz
│   ├── d62fc66df4b9acdd5381753fde4173a5775b1ddf.nq.gz
│   ├── d958277324790f39be66ab33a267feac548fbbb9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed3a9d377ba3c30e6eb8b2a35e08e8dc814a0725.nq.gz
│   ├── efd9a649af0171037c6bb92a2873aedf109c8063.nq.gz
│   └── f49a4e16e68b128803cc2dcea614603632b04eac.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 556dcf1c4c8a07a9b0c13515d5a356cf6a67132b.nq.gz
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

[UKPLab/emnlp2025-automatic-error-discovery](https://github.com/UKPLab/emnlp2025-automatic-error-discovery)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
