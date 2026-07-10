# 🗂️ AI Product Portfolio — Tao Wei

> AI Product Manager | Game AI | Enterprise AI | LLM · Agent · RAG · AIGC

This repository is my personal AI product portfolio. Each case documents a product I designed or led — including background, user pain points, product solution, AI capabilities, architecture, and outcomes.

---

## 📋 Project Index

| # | Project | Domain | Core AI Capability |
|---|---|---|---|
| 01 | [RGM AI Search](#01-rgm-ai-search) | Game | RAG · LLM · Vector Search |
| 02 | [AI Knowledge Base](#02-ai-knowledge-base) | Enterprise | RAG · Embedding · LLM |
| 03 | [Enterprise AI Copilot](#03-enterprise-ai-copilot) | Enterprise | LLM · Tool Use · Workflow |
| 04 | [AI Agent Framework](#04-ai-agent-framework) | Platform | Multi-Agent · LangChain |
| 05 | [Game AI NPC](#05-game-ai-npc) | Game | LLM · Prompt Engineering · Memory |
| 06 | [AI Video Transcriber](#06-ai-video-transcriber) | Content | Whisper · LLM · Summarization |
| 07 | [AI OCR Pipeline](#07-ai-ocr-pipeline) | Enterprise | OCR · LLM · Document AI |
| 08 | [AIGC Content Platform](#08-aigc-content-platform) | Content | Diffusion · Multimodal |

---

## 01 RGM AI Search

**Domain:** Game · Search & Recommendation

### Background
Players in large online games struggle to find relevant items, guides, and community content across fragmented sources. Traditional keyword search returns low-quality results.

### User Pain Points
- Hard to find specific game items or strategies quickly
- Existing search ignores game-context semantics
- No personalization based on player profile or current game state

### Product Goal
Build an AI-powered semantic search & recommendation system for game content, covering items, strategies, guides, and community posts.

### Product Solution
- Unified search UI with semantic understanding
- RAG pipeline: retrieve relevant chunks → LLM rerank & generate answer
- Personalization layer based on player profile and session context

### AI Capabilities
`RAG` `Vector Search` `Embedding` `LLM Re-ranking` `Personalization`

### Architecture (High-Level)
```
User Query → Query Embedding → Vector DB Search → Top-K Chunks
→ LLM Rerank + Answer Generation → Response to User
```

### My Role
Product design, requirement spec, AI pipeline architecture, cross-team coordination between AI infra and game platform teams.

### Outcome
Reduced average search-to-action time. Improved player satisfaction score on search experience.

---

## 02 AI Knowledge Base

**Domain:** Enterprise · Internal Knowledge Management

### Background
Enterprises have large volumes of internal documents (wikis, SOP, reports) that employees struggle to search and use efficiently.

### User Pain Points
- Employees can't find answers in scattered internal documents
- Traditional keyword search misses semantic relationships
- Knowledge becomes siloed across departments

### Product Goal
Build an enterprise internal knowledge base with AI-powered Q&A, supporting natural language queries over company documents.

### Product Solution
- Document ingestion pipeline (PDF, Word, Confluence, Notion)
- Embedding + vector storage for semantic retrieval
- LLM-powered Q&A with source citations

### AI Capabilities
`RAG` `Embedding` `LLM` `Document Parsing` `Chunk Strategy`

### My Role
Product strategy, use case definition, chunking strategy design, evaluation framework for answer quality.

### Outcome
Reduced average time-to-answer for internal queries. Increased knowledge reuse across teams.

---

## 03 Enterprise AI Copilot

**Domain:** Enterprise · Workflow Automation

### Background
Enterprise workflows involve repetitive tasks across CRM, ERP, and communication tools. Employees spend significant time on manual data entry and report generation.

### Product Goal
Build an AI Copilot that integrates into existing enterprise tools and automates common workflows via natural language instructions.

### AI Capabilities
`LLM` `Tool Use` `Function Calling` `Workflow Automation`

### My Role
Product vision, tool integration design, prompt engineering for workflow parsing, user acceptance testing.

---

## 04 AI Agent Framework

**Domain:** Platform · AI Infrastructure

### Background
Multiple product teams needed autonomous AI agents that could plan, use tools, and execute multi-step tasks. A shared framework was needed to avoid duplicate work.

### Product Goal
Design a reusable multi-agent orchestration framework supporting task planning, tool calling, memory, and human-in-the-loop.

### AI Capabilities
`Multi-Agent` `LangChain` `Tool Use` `Memory` `Planning`

### My Role
Framework product design, agent capability taxonomy, tool registry design, evaluation criteria.

---

## 05 Game AI NPC

**Domain:** Game · AI Character

### Background
Static NPCs in games provide repetitive, scripted dialogue that breaks immersion. Players increasingly expect dynamic, context-aware character interactions.

### Product Goal
Build LLM-powered NPCs that can hold contextual, in-character conversations with players, with persistent memory and personality consistency.

### AI Capabilities
`LLM` `Prompt Engineering` `Character Persona` `Memory` `Safety Filter`

### My Role
NPC product design, persona definition framework, dialogue quality evaluation, safety guardrail specification.

---

## 06 AI Video Transcriber

**Domain:** Content · Video AI

### Background
Content creators and researchers need to extract information from long video content quickly, without watching entire videos.

### Product Goal
Build a tool that transcribes video audio, segments content, and generates structured summaries using AI.

### AI Capabilities
`Whisper` `LLM Summarization` `Multi-language` `Timestamps`

### My Role
Product design, open source contribution, user testing.

🔗 [View Repository](https://github.com/tiandaoyuxi/AI-Video-Transcriber)

---

## 07 AI OCR Pipeline

**Domain:** Enterprise · Document Processing

### Background
Enterprises process large volumes of paper-based and scanned documents that need to be digitized and structured for downstream systems.

### Product Goal
Build an AI-enhanced OCR pipeline that extracts, structures, and validates document content with high accuracy.

### AI Capabilities
`OCR` `LLM Post-processing` `Document Structure Recognition` `Validation`

### My Role
Pipeline architecture, accuracy evaluation framework, edge case catalog.

---

## 08 AIGC Content Platform

**Domain:** Content · Multimodal Generation

### Background
Content teams need to generate high volumes of images, short videos, and creative assets to support game marketing and in-game content.

### Product Goal
Build an internal AIGC platform for content teams to generate, review, and manage AI-generated assets at scale.

### AI Capabilities
`Diffusion Models` `Text-to-Image` `Video Generation` `Content Moderation`

### My Role
Platform product design, generation workflow, review & approval flow, content moderation spec.

---

## 📬 Contact

- GitHub: [@tiandaoyuxi](https://github.com/tiandaoyuxi)
- Open to AI Product Manager roles in Game AI and Enterprise AI

---

*This portfolio is continuously updated as I build and explore new AI products.*
