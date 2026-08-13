### Hi, I'm Aashish 👋

**AI Engineer · Agentic Systems · RAG & LLM Engineering**
🎓 Master of Computer Science (AI & Data Science) — University of Sydney
📍 Sydney, NSW · 🔗 [LinkedIn](https://linkedin.com/in/aashish-patnaik)
💼 Open to AI Engineer, RAG Engineer, LLM Engineer and Agentic AI roles in Sydney · Full working rights in Australia

---

### 🔧 What I Build

I build agentic AI systems that are designed to be verified, not just trusted — multi-agent architectures with guardrails and human-in-the-loop review built in as first-class parts of the design, RAG pipelines with faithfulness and citation grounding measured rather than assumed, and evaluation harnesses that actually test where non-determinism bites.

---

### 🚀 Featured Work

#### 🛡️ AgentAudit — Governed Multi-Agent Compliance Research System
`Solo Project · AWS Bedrock AgentCore · Claude Agent SDK`
🔗 [Live Dashboard](https://ag-a60a4e28fe8b496cb1d0c942d6b6b14d.ecs.ap-southeast-2.on.aws/) · [GitHub](https://github.com/AashishPatnaik/agentaudit)

- Built a multi-agent system (coordinator + 3 specialist subagents + synthesis agent) on the Claude Agent SDK, with a runtime guardrail as a first-class part of the architecture: every citation is independently re-verified against the source corpus outside the agent's own reasoning loop, so the check can't be talked around by the model — unverifiable claims are flagged for human review, never silently passed through
- Designed and built a custom MCP (Model Context Protocol) server from scratch, exposing 4 tools against the AusRegBench corpus, deployed behind an AWS Bedrock AgentCore Gateway with a Cognito JWT / IAM-scoped authentication split
- Diagnosed and fixed a hard, non-configurable ~15-minute platform timeout on AWS Bedrock AgentCore Runtime by re-architecting the entrypoint as an SSE-streaming async generator with heartbeats and an explicit failure ceiling
- Root-caused a Postgres connection-pooler bug where an initial fix passed all 27 mocked unit tests but was a functional no-op in production — confirmed the failure and the fix through live reproduction against the real database
- Built a GitHub Actions CI pipeline (3 packages, 60 tests) that caught 2 real, previously invisible dependency-isolation bugs on its first run; deployed real AWS infrastructure with CloudFormation IaC and least-privilege IAM

#### ⚖️ AusRegBench — RAG Faithfulness Benchmark for Australian Regulatory Compliance
`Solo Project · Hybrid Retrieval · Two-Layer Evaluation Harness`
🔗 [Live Dashboard](https://huggingface.co/spaces/AashishPatnaik/AusRegBench) · [GitHub](https://github.com/AashishPatnaik/AusRegBench)

- Benchmarked 5 RAG configurations across 120 hand-verified Australian regulatory queries — citation-forcing cut obligation misstatements by 56% (naive faithfulness 76.5% → grounded 88.2%)
- Engineered a clause-aware chunker preserving paragraph IDs across 11,613 chunks from the Open Australian Legal Corpus (Corporations Act 2001, Banking Act 1959) and APRA Prudential Standards (CPS 220/230/234)
- Implemented hybrid BM25 + dense retrieval with Reciprocal Rank Fusion, cross-encoder reranking, and a citation-forced generation stage
- Validated a two-layer evaluation judge — a deterministic citation checker plus an LLM-as-a-judge model — at Cohen's κ = 0.78 against human labels across 595 benchmark evaluations
- Deployed a live dashboard with full stage-level tracing across all 5 RAG configurations

#### 🕸️ Semantic RAG & Knowledge Graph Systems
`Arc Intelligence Lab · USyd Capstone · 8-person team, individually built full-stack components`
🔗 [mmd-intelligence-explorer](https://github.com/AashishPatnaik/mmd-intelligence-explorer) · [cord19-semantic-search](https://github.com/AashishPatnaik/cord19-semantic-search)

- Built PreChunkingInjector from scratch and a 4-stage ablation runner — 70% retrieval latency reduction (33.7ms → 10.2ms), maintaining perfect P@5, MRR and Hit@5 = 1.000
- Built a 4-panel React web app (Metadata · NER · Knowledge Graph · Vector Search) with an interactive D3.js force-directed graph, 22 nodes and 21 typed semantic relations, confidence scores up to 92%
- Built a GLiNER + GLIREL NER and relation extraction pipeline — 59 entities and 287 semantic relations extracted from an ArXiv paper
- Built a validation suite covering 255 unique entities and 239 relations, with 100% round-trip document reconstruction fidelity (byte-for-byte SHA256 match) and a 13-test KG query suite across SPARQL, JSON-LD and Cypher

---

### 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Agentic Systems** | Claude Agent SDK · Model Context Protocol (MCP) · AWS Bedrock AgentCore · multi-agent orchestration · human-in-the-loop design |
| **LLM & RAG** | LangChain · LangGraph · ChromaDB · FAISS · pgvector · Sentence-Transformers · hybrid BM25+dense search · cross-encoder reranking |
| **NLP & Knowledge Graphs** | GLiNER · GLIREL · spaCy · HuggingFace Transformers · SPARQL · Cypher · JSON-LD · RDFLib |
| **Models & APIs** | OpenAI API · Claude API · Gemini API · OpenRouter · HuggingFace Hub |
| **ML & Training** | PyTorch · QLoRA · LoRA fine-tuning · scikit-learn |
| **Cloud & Infrastructure** | AWS (Bedrock, ECS, IAM, Cognito, Secrets Manager, CloudFormation) · Docker · GitHub Actions CI/CD |
| **Web & Dev** | Python · React · D3.js · Next.js · Tailwind CSS · Git · Redis · Pydantic · pytest · REST APIs |

---

*Open to AI Engineer, RAG Engineer, LLM Engineer and Agentic AI roles in Sydney · Full working rights in Australia*
