# Awesome RAG (Retrieval-Augmented Generation)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)

A curated registry of open-source tools, frameworks, models, and datasets for building **Retrieval-Augmented Generation (RAG)** systems.

The goal is to be a practical starting point for assembling production-grade RAG pipelines: frameworks, vector stores, embedding models, document parsers, evaluators, graph and multimodal retrieval, inference engines, and benchmarks.

**Inclusion criteria:** Resources must be directly useful for RAG pipelines — retrieval, indexing, embedding, parsing, evaluation, deployment, or benchmarking. General LLM chat apps or pure research papers are out of scope. See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full quality bar.

---

## Contents

- [RAG Frameworks](#rag-frameworks)
- [Vector Databases](#vector-databases)
- [Embedding Models](#embedding-models)
- [Document Loaders & Parsers](#document-loaders--parsers)
- [RAG Evaluation](#rag-evaluation)
- [Graph RAG](#graph-rag)
- [Multi-Modal RAG](#multi-modal-rag)
- [RAG Deployment & Inference](#rag-deployment--inference)
- [Benchmarks & Datasets](#benchmarks--datasets)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

---

## RAG Frameworks

End-to-end frameworks for building, orchestrating, and deploying RAG applications.

- **[LangChain](https://github.com/langchain-ai/langchain)** `Official` — Industry-standard framework with document loaders, retrievers, chains, and agents.
  - Install: `pip install langchain`
- **[LlamaIndex](https://github.com/run-llama/llama_index)** `Official` — Data framework for connecting custom data sources to LLMs with advanced indexing and retrieval.
  - Install: `pip install llama-index`
- **[Haystack](https://github.com/deepset-ai/haystack)** `Official` — Modular AI orchestration framework for production RAG, search, and agent pipelines.
  - Install: `pip install haystack-ai`
- **[DSPy](https://github.com/stanfordnlp/dspy)** `Official` — Stanford NLP framework for programming language models with declarative, retrieval-aware modules.
  - Install: `pip install dspy`
- **[RAGFlow](https://github.com/infiniflow/ragflow)** `Official` — Open-source RAG engine focused on deep document understanding and citation-backed answers.
  - Install: `docker compose -f docker/docker-compose.yml up -d`
- **[Cognita](https://github.com/truefoundry/cognita)** `Official` — Modular, production-ready RAG framework with pluggable components.
  - Install: clone repo, then `pip install -r requirements.txt`
- **[Verba](https://github.com/weaviate/Verba)** `Official` — Open-source, out-of-the-box RAG application powered by Weaviate.
  - Install: `pip install goldenverba`

## Vector Databases

Vector and hybrid search engines that power the retrieval layer of RAG systems.

- **[Chroma](https://github.com/chroma-core/chroma)** `Official` — Local-first, AI-native embedding database.
  - Install: `pip install chromadb`
- **[Qdrant](https://github.com/qdrant/qdrant)** `Official` — High-performance, Rust-based vector database with rich metadata filtering.
  - Run: `docker run -p 6333:6333 qdrant/qdrant`
- **[Weaviate](https://github.com/weaviate/weaviate)** `Official` — Cloud-native vector database with hybrid (BM25 + vector) search and built-in reranking.
  - Run: `docker compose up -d` via the [quickstart](https://weaviate.io/developers/weaviate/quickstart)
- **[Milvus](https://github.com/milvus-io/milvus)** `Official` — Distributed vector database designed for billion-scale ANN search.
  - Run: `docker run -p 19530:19530 milvusdb/milvus:latest`
- **[Pinecone](https://www.pinecone.io/)** `Official` — Fully managed vector database with serverless indexing.
- **[pgvector](https://github.com/pgvector/pgvector)** `Official` — PostgreSQL extension for vector similarity search.
  - Install: `CREATE EXTENSION vector;` in Postgres

## Embedding Models

Models and libraries for encoding text (and increasingly other modalities) into dense vectors for retrieval.

- **[Sentence Transformers](https://github.com/huggingface/sentence-transformers)** `Official` — Standard Python library for training and running embedding and reranker models.
  - Install: `pip install sentence-transformers`
- **[all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2)** `Official` — Fast, lightweight general-purpose sentence embedding model (384 dims).
- **[BGE-M3](https://huggingface.co/BAAI/bge-m3)** `Official` — State-of-the-art multilingual embedding model supporting dense, sparse, and multi-vector retrieval.
- **[Nomic Embed Text v1.5](https://huggingface.co/nomic-ai/nomic-embed-text-v1.5)** `Official` — Fully open-source (Apache 2.0) 768-dim embedding model with Matryoshka support.
- **[multilingual-e5-large](https://huggingface.co/intfloat/multilingual-e5-large)** `Official` — Microsoft E5 model trained for multilingual symmetric and asymmetric retrieval.
- **[Jina Embeddings v3](https://huggingface.co/jinaai/jina-embeddings-v3)** `Official` — Multilingual embedding model with task-specific instruction prefixes.

## Document Loaders & Parsers

Tools that extract clean, structured text from PDFs, web pages, office documents, and other sources.

- **[Unstructured](https://github.com/Unstructured-IO/unstructured)** `Official` — Platform for turning complex documents into LLM-ready chunks with semantic element types.
  - Install: `pip install unstructured`
- **[LlamaParse](https://cloud.llamaindex.ai/)** `Official` — GenAI-native document parser for complex PDFs, tables, and charts.
  - Install: `pip install llama-cloud-services`
- **[Docling](https://github.com/DS4SD/docling)** `Official` — IBM Research open-source toolkit for parsing PDFs, DOCX, and more into structured formats.
  - Install: `pip install docling`
- **[Marker](https://github.com/VikParuchuri/marker)** `Official` — GPU-accelerated PDF-to-Markdown converter with layout preservation.
  - Install: `pip install marker-pdf`
- **[Firecrawl](https://github.com/mendableai/firecrawl)** `Official` — API-first web scraping and document parsing service that outputs LLM-ready Markdown.
  - Install: `npm install -g firecrawl` or use the cloud API
- **[PyMuPDF4LLM](https://github.com/pymupdf/RAG)** `Official` — Fast PDF-to-Markdown extraction built on PyMuPDF for RAG pipelines.
  - Install: `pip install pymupdf4llm`

## RAG Evaluation

Frameworks and platforms for measuring retrieval quality, answer faithfulness, and end-to-end RAG performance.

- **[RAGAS](https://github.com/explodinggradients/ragas)** `Official` — Reference-free evaluation framework for RAG pipelines (faithfulness, relevancy, recall, etc.).
  - Install: `pip install ragas`
- **[ARES](https://github.com/stanford-futuredata/ARES)** `Official` — Automated RAG evaluation system with synthetic data generation and confidence intervals.
  - Install: `pip install ares-ai`
- **[DeepEval](https://github.com/confident-ai/deepeval)** `Official` — Pytest-like LLM evaluation framework with RAG-specific metrics.
  - Install: `pip install deepeval`
- **[TruLens](https://github.com/truera/trulens)** `Official` — Open-source library for evaluating and tracking LLM app quality, including RAG.
  - Install: `pip install trulens`
- **[MLflow](https://github.com/mlflow/mlflow)** `Official` — Open-source AI engineering platform with RAG evaluation, tracing, and monitoring.
  - Install: `pip install mlflow`
- **[Arize Phoenix](https://github.com/Arize-ai/phoenix)** `Official` — LLM observability and evaluation platform with RAG-specific judges.
  - Install: `pip install arize-phoenix`

## Graph RAG

Tools that combine knowledge graphs with retrieval to improve multi-hop reasoning and structured grounding.

- **[Microsoft GraphRAG](https://github.com/microsoft/graphrag)** `Official` — Modular graph-based RAG system using LLM-derived knowledge graphs and community summaries.
  - Install: `pip install graphrag`
- **[Neo4j GraphRAG Python](https://github.com/neo4j/neo4j-graphrag-python)** `Official` — First-party Neo4j package for building GraphRAG applications in Python.
  - Install: `pip install neo4j-graphrag`
- **[LightRAG](https://github.com/HKUDS/LightRAG)** `Community` — Simple and fast graph-based retrieval-augmented generation.
  - Install: `pip install lightrag-hku`
- **[MsGraphRAG-Neo4j](https://github.com/neo4j-contrib/ms-graphrag-neo4j)** `Community` — Neo4j implementation of the Microsoft GraphRAG methodology.
  - Install: `pip install ms-graphrag-neo4j`
- **[Neo4j](https://github.com/neo4j/neo4j)** `Official` — Native graph database with vector indexes and GraphRAG integrations.
  - Run: `docker run -p 7474:7474 -p 7687:7687 neo4j:latest`
- **[LLMGraphTransformer](https://python.langchain.com/docs/how_to/graph_constructing/)** `Official` — LangChain utility for building knowledge graphs from unstructured text.

## Multi-Modal RAG

Retrieval systems that handle images, documents-as-images, video frames, and other non-text modalities.

- **[ColPali](https://github.com/illuin-tech/colpali)** `Community` — Visual document retrieval using vision-language models and late-interaction embeddings.
  - Install: `pip install colpali-engine`
- **[ColQwen2](https://huggingface.co/vidore/colqwen2-v0.1)** `Official` — ColPali-style model based on Qwen2-VL for visual document retrieval.
- **[Byaldi](https://github.com/AnswerDotAI/byaldi)** `Community` — Simple wrapper around ColPali/ColQwen models for multimodal RAG.
  - Install: `pip install byaldi`
- **[CLIP](https://github.com/openai/CLIP)** `Official` — OpenAI's contrastive language-image pre-training model for cross-modal retrieval.
  - Install: `pip install git+https://github.com/openai/CLIP.git`
- **[SigLIP](https://github.com/google-research/big_vision)** `Official` — Google's sigmoid loss for language-image pre-training, used in multimodal retrieval.

## RAG Deployment & Inference

Inference engines and serving platforms for running the generation (and sometimes embedding) side of RAG.

- **[vLLM](https://github.com/vllm-project/vllm)** `Official` — High-throughput LLM inference engine with PagedAttention and OpenAI-compatible serving.
  - Install: `pip install vllm`
- **[Ollama](https://github.com/ollama/ollama)** `Official` — Local, easy-to-use LLM runner with built-in quantized model support.
  - Install: `curl -fsSL https://ollama.com/install.sh | sh`
- **[Text Generation Inference (TGI)](https://github.com/huggingface/text-generation-inference)** `Official` — Production LLM serving toolkit from Hugging Face.
  - Run: `docker run ghcr.io/huggingface/text-generation-inference:latest --model-id <model>`
- **[SGLang](https://github.com/sgl-project/sglang)** `Official` — Fast serving framework for LLMs and reasoning models.
  - Install: `pip install sglang`
- **[BentoML](https://github.com/bentoml/BentoML)** `Official` — Unified model-serving framework with RAG and vLLM deployment examples.
  - Install: `pip install bentoml`

## Benchmarks & Datasets

Standard datasets and leaderboards for evaluating retrieval and end-to-end RAG quality.

- **[MTEB](https://github.com/embeddings-benchmark/mteb)** `Official` — Massive Text Embedding Benchmark covering retrieval, classification, clustering, and more.
  - Install: `pip install mteb`
- **[BEIR](https://github.com/beir-cellar/beir)** `Official` — Heterogeneous benchmark for zero-shot information retrieval across 18 datasets.
  - Install: `pip install beir`
- **[Natural Questions](https://github.com/google-research-datasets/natural-questions)** `Official` — Real Google search queries with Wikipedia answers for open-domain QA.
- **[MS MARCO](https://microsoft.github.io/msmarco/)** `Official` — Large-scale passage-ranking dataset based on real Bing search queries.
- **[HotpotQA](https://hotpotqa.github.io/)** `Official` — Multi-hop question answering benchmark requiring reasoning across multiple Wikipedia documents.
- **[RAGTruth](https://github.com/lemuria-wcl/RAGTruth)** `Community` — Dataset for studying hallucinations in RAG-generated responses.
- **[FRAMES](https://github.com/google-deepmind/frames)** `Official` — Factuality, retrieval, and reasoning benchmark for multi-hop RAG evaluation.

## Related Awesome Lists

- [Awesome Vector Databases](https://github.com/mileszim/awesome-vector-databases) — Curated list of vector search engines, embeddings, and ANN libraries.
- [Awesome MCP Servers](https://github.com/appcypher/awesome-mcp-servers) — Registry of Model Context Protocol (MCP) servers that can augment RAG agents.
- [Awesome Open Source LLMs](https://github.com/eugeneyan/open-llms) — List of open-source large language models suitable for RAG generation.

## Notes

- **Official vs Community:** `Official` entries are maintained by the vendor or project owner; `Community` entries are third-party implementations.
- **Managed services:** Some entries (e.g., Pinecone, LlamaParse, Firecrawl) are primarily hosted APIs with local SDKs; see each project's docs for authentication and pricing.
- **Evolving ecosystem:** The RAG tooling landscape changes rapidly. If you spot a broken link or a missing high-quality project, see [CONTRIBUTING.md](./CONTRIBUTING.md).

## Contributing

Read [CONTRIBUTING.md](./CONTRIBUTING.md) for the quality bar, entry format, and PR process.

## License

This list is released into the public domain under [CC0-1.0](./LICENSE).

## Want us to build this for you?

Enterprise AI Atlas is maintained by [Vibe Coding Agency](https://vibecodingagency.com). We prototype and ship agentic systems, MCP servers, and enterprise AI integrations for teams that need working software fast — without hiring a full AI engineering team.
