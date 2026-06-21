# Contributing

Contributions are welcome. Please read this guide before opening a pull request.

## What belongs in this list

This registry is for resources that help build, evaluate, deploy, or operate **Retrieval-Augmented Generation (RAG)** systems. Acceptable entries include:

- RAG frameworks, orchestrators, and reference pipelines.
- Vector databases, embedding databases, and hybrid search engines used for retrieval.
- Embedding and reranker models (and the libraries that run them) designed for retrieval.
- Document loaders, parsers, and extraction tools that feed RAG ingestion pipelines.
- RAG evaluation frameworks, metrics libraries, and observability platforms.
- Graph RAG tools, knowledge graph builders, and graph database integrations.
- Multi-modal retrieval tools and vision-language embedding models.
- Inference engines, model-serving platforms, and deployment patterns for RAG.
- Benchmarks and datasets used to evaluate retrieval or end-to-end RAG quality.

## What does **not** belong

- General LLM chat interfaces or prompt engineering tutorials that are not RAG-specific.
- Pure research papers without an accompanying open-source implementation or dataset.
- Closed-source or paywalled-only tools with no public documentation or free tier.
- Duplicate entries or projects where RAG support is incidental rather than core.

## Quality bar

Every submission must be:

1. **Publicly accessible** — open source or publicly documented.
2. **Actively maintained** — last meaningful commit or release within the last 12 months (exceptions for foundational reference projects).
3. **Documented** — a real README with setup or install instructions.
4. **Correctly categorized** — placed under the RAG component it primarily targets.
5. **Honestly labeled** — use the `Official` or `Community` badge.

## Entry format

Use this pattern:

```markdown
- **[Name](URL)** `Official` — One-sentence description.
  - Install: `command here`
```

If there is no install command, omit the install line.

## Category sections

The README is organized by **RAG pipeline component**, not by programming language. New category sections are allowed only if they contain at least three entries.

## Pull request process

1. Fork the repository.
2. Add your entry in the correct category section.
3. Run `./scripts/validate-links.sh` and fix any broken links or anchors.
4. Open a pull request with a clear description of the resource and why it fits.

One resource per pull request is preferred.
