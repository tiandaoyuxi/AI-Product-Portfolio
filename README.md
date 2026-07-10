# 📚 AI Product Portfolio — Tao Wei

<p>
  <img src="https://img.shields.io/badge/Role-AI%20Product%20Manager-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Domain-Game%20AI%20%7C%20Enterprise%20AI-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/Stack-LLM%20%7C%20Agent%20%7C%20RAG%20%7C%20AIGC-blue?style=flat-square" />
</p>

> This is my AI product case study portfolio. Each case documents a product I designed or led — covering business background, user pain points, product solution, AI architecture, and outcomes.  
> I'm an AI Product Manager. This repository shows how I think, not just what I built.

---

## 📋 Case Index

| # | Project | Domain | Core AI | Status |
|---|---|---|---|---|
| 01 | [RGM AI Search](#case-01--rgm-ai-search) | 🎮 Game | RAG · Vector Search · LLM | ✅ Done |
| 02 | [Game AI NPC](#case-02--game-ai-npc) | 🎮 Game | LLM · Persona · Memory | ✅ Done |
| 03 | [AI Knowledge Base](#case-03--ai-knowledge-base) | 🏢 Enterprise | RAG · Embedding | ✅ Done |
| 04 | [Enterprise AI Copilot](#case-04--enterprise-ai-copilot) | 🏢 Enterprise | LLM · Tool Use · Workflow | ✅ Done |
| 05 | [AI Agent Framework](#case-05--ai-agent-framework) | 🔧 Platform | Multi-Agent · LangChain | ✅ Done |
| 06 | [AI Video Transcriber](#case-06--ai-video-transcriber) | 🎥 Content | Whisper · LLM | ✅ Done |
| 07 | [AI OCR Pipeline](#case-07--ai-ocr-pipeline) | 🏢 Enterprise | OCR · LLM · Document AI | ✅ Done |
| 08 | [AIGC Content Platform](#case-08--aigc-content-platform) | 🎨 Content | Diffusion · Multimodal | 🔄 In Progress |

---

## Case 01 · RGM AI Search

**Domain:** Game · Search & Recommendation  
**My Role:** Product Lead — design, requirement spec, AI pipeline architecture

### Background
In large online games, players need to quickly find items, strategies, guides, and community posts. The existing keyword-based search returned poor results and couldn't understand game-specific semantics (e.g., "best AOE build for this boss").

### User Pain Points
- Players couldn't find what they needed in time, breaking game flow
- Search ignored context: player level, current quest, game meta
- Community content was siloed from official guides and item databases

### Product Goal
Build an AI-powered semantic search & recommendation system that covers all in-game and community content, understands game context, and returns answers — not just links.

### Product Solution

```
Player types: "best healing setup for raid boss level 50"
         ↓
Query Understanding (intent + context extraction)
         ↓
Vector Search over item DB + guide corpus + community posts
         ↓
LLM Rerank + Answer Generation with citations
         ↓
Player sees: structured answer + top 3 source links
```

- Unified search entry replacing 3 separate search systems
- Semantic retrieval via embedding + vector DB
- Personalization layer using player profile (level, class, current quest)
- LLM generates a direct answer with traceable sources

### AI Capabilities
`RAG` `Embedding` `Vector Search` `LLM Reranking` `Query Rewriting` `Personalization`

### Key Product Decisions
1. **Answer-first design** — don't just return a list; give a direct answer with source
2. **Context injection** — player state (level, class) injected into retrieval query
3. **Fallback strategy** — when confidence is low, fall back to traditional search
4. **Latency budget** — P95 < 800ms; sacrificed reranking depth for speed

### Product Thinking
> The hardest part wasn't the AI — it was defining what "good search" means in a game context. A level-60 player and a level-10 player asking the same question need completely different answers.

### Outcome
- Reduced average search-to-action time
- Improved player satisfaction score on search experience
- 3 previously separate search surfaces unified into 1

---

## Case 02 · Game AI NPC

**Domain:** Game · AI Character & Dialogue  
**My Role:** Product design, persona framework, dialogue quality evaluation, safety spec

### Background
Static NPC dialogue in games is scripted and repetitive. Players increasingly expect characters that can respond contextually, remember past interactions, and feel alive. Traditional dialogue trees don't scale to the level of player creativity.

### User Pain Points
- NPCs give the same response regardless of player history or game state
- Scripted dialogue trees can't handle player-initiated questions
- High cost of manual dialogue authoring for large game worlds

### Product Goal
Build LLM-powered NPCs that hold contextual, in-character conversations with players, with persistent memory and consistent personality — without breaking game immersion or narrative.

### Product Solution

```
Player input
    ↓
Safety Filter (block out-of-character / harmful content)
    ↓
Context Assembly: character persona + memory summary + game state
    ↓
LLM generation (in-character response)
    ↓
Response post-processing (tone consistency check)
    ↓
Player sees NPC response
```

- **Persona System:** Each NPC has a structured persona card (name, backstory, speech style, relationship to player, knowledge boundary)
- **Memory Module:** Short-term (current session) + long-term (summarized past interactions)
- **Knowledge Boundary:** NPC only knows what they "should" know — prevents immersion breaks
- **Safety Layer:** Two-pass filter for harmful content and out-of-character behavior

### AI Capabilities
`LLM` `Prompt Engineering` `Persona Design` `Memory (short + long term)` `Safety Filter`

### Key Product Decisions
1. **Hard knowledge boundary** — NPC doesn't know things their character shouldn't know
2. **Memory summarization** — full conversation history too expensive; summarize every N turns
3. **Graceful refusal** — when NPC can't answer, stay in character ("That's not something I know about, traveler.")
4. **Player tone adaptation** — NPC subtly mirrors player's conversation style

### Product Thinking
> The challenge isn't making NPCs sound smart — it's making them sound consistently like *themselves*. Persona consistency over multiple sessions is harder than any benchmark.

### Outcome
- Significantly reduced dialogue authoring cost for open-world content
- Increased player engagement time in NPC interaction areas
- Foundation for future AI-driven quest generation

---

## Case 03 · AI Knowledge Base

**Domain:** Enterprise · Internal Knowledge Management  
**My Role:** Product strategy, use case definition, chunking strategy, evaluation framework

### Background
Enterprises accumulate large volumes of internal documents — wikis, SOPs, reports, meeting notes — that employees can't efficiently search or use. Knowledge becomes siloed and expires silently.

### User Pain Points
- Employees can't find answers in scattered documents; ask colleagues instead
- Traditional keyword search misses semantic relationships and synonyms
- Knowledge silos across departments; onboarding takes too long

### Product Goal
Build an enterprise internal knowledge base with AI-powered Q&A, supporting natural language queries over company documents, with traceable source citations.

### Product Solution

```
Document Ingestion (PDF, Word, Confluence, Notion, Feishu)
    ↓
Parsing + Chunking (smart chunking by section/header)
    ↓
Embedding + Vector Storage
    ↓
User asks question in natural language
    ↓
Retrieve top-K chunks → LLM generates answer with citations
    ↓
User sees: Answer + "Source: [document name, section]"
```

### AI Capabilities
`RAG` `Embedding` `LLM` `Document Parsing` `Semantic Chunking` `Citation Generation`

### Key Product Decisions
1. **Citation is mandatory** — no answer without source; builds trust
2. **Chunk strategy matters** — fixed-size chunking was bad; switched to semantic section-based chunking
3. **Permission-aware retrieval** — only retrieve from documents the user has access to
4. **Confidence threshold** — low-confidence answers shown with warning, not hidden

### Outcome
- Reduced average time-to-answer for internal queries
- Increased knowledge reuse across teams
- Onboarding time for new employees reduced

---

## Case 04 · Enterprise AI Copilot

**Domain:** Enterprise · Workflow Automation  
**My Role:** Product vision, tool integration design, prompt engineering, UAT

### Background
Enterprise workflows involve repetitive tasks across CRM, ERP, and internal tools. Employees spend significant time on manual data lookup, report generation, and cross-system operations.

### Product Goal
Build an AI Copilot that understands natural language instructions and executes multi-step workflows across enterprise systems — CRM lookup, report generation, calendar scheduling, approval triggering.

### Product Solution
- Natural language → intent recognition → tool routing
- Tool registry: each enterprise system exposed as a callable tool
- Multi-step planning: Copilot breaks complex requests into sub-tasks
- Human confirmation for high-stakes actions (e.g., "send email to all customers")

### AI Capabilities
`LLM` `Function Calling` `Tool Use` `Multi-Step Planning` `Workflow Automation`

### Key Product Decisions
1. **Confirm before execute** — Copilot shows plan before executing irreversible actions
2. **Partial execution recovery** — if step 3 fails, resume from step 3 not step 1
3. **Scope limitation** — Copilot only touches systems the user has permission to

---

## Case 05 · AI Agent Framework

**Domain:** Platform · AI Infrastructure  
**My Role:** Framework product design, agent capability taxonomy, tool registry, evaluation

### Background
Multiple product teams were building their own AI agents independently, duplicating planning logic, tool integration, and memory management. A shared platform was needed.

### Product Goal
Design a reusable multi-agent orchestration framework with standardized interfaces for planning, tool calling, memory, and human-in-the-loop — usable by 3+ product teams.

### Architecture (High-Level)
```
Task Input
    ↓
Planner Agent (breaks task into steps)
    ↓
Executor Agent (calls tools per step)
    ↓
Tool Registry (CRM, Search, DB, API, Code...)
    ↓
Memory Module (session + long-term)
    ↓
Human-in-the-loop checkpoint (for risky actions)
    ↓
Result
```

### AI Capabilities
`Multi-Agent` `LangChain` `Tool Use` `Task Planning` `Memory` `HITL`

---

## Case 06 · AI Video Transcriber

**Domain:** Content · Video AI  
**My Role:** Product design, open source contribution, user testing

### Background
Content creators and researchers need to extract information from long video content quickly, without watching hours of footage.

### Product Goal
Build a tool that transcribes video audio, timestamps key segments, and generates structured summaries using AI — supporting multiple languages.

### AI Capabilities
`Whisper` `LLM Summarization` `Multi-language ASR` `Structured Output`

🔗 [View Repository →](https://github.com/tiandaoyuxi/AI-Video-Transcriber)

---

## Case 07 · AI OCR Pipeline

**Domain:** Enterprise · Document Processing  
**My Role:** Pipeline architecture, accuracy evaluation, edge case catalog

### Background
Enterprises process large volumes of scanned and photographed documents that need to be digitized, structured, and validated for downstream systems (ERP, compliance, archival).

### Product Goal
Build an AI-enhanced OCR pipeline that extracts, structures, and validates document content with high accuracy — handling handwriting, tables, and mixed layouts.

### AI Capabilities
`OCR` `LLM Post-processing` `Table Extraction` `Document Structure Recognition` `Validation`

### Key Product Decisions
1. **LLM as post-processor** — OCR extracts raw text; LLM fixes errors and structures output
2. **Confidence scoring** — low-confidence fields flagged for human review
3. **Template-free approach** — no predefined templates; LLM infers document structure

---

## Case 08 · AIGC Content Platform

**Domain:** Content · Multimodal Generation  
**My Role:** Platform product design, generation workflow, review & approval flow, content moderation spec

### Background
Game content teams need to generate high volumes of concept art, marketing images, and in-game assets. Manual creation is too slow for the pace of live game operations.

### Product Goal
Build an internal AIGC platform for content teams to generate, review, curate, and manage AI-generated assets at scale — with brand consistency and safety controls.

### AI Capabilities
`Text-to-Image` `Diffusion Models` `Style Control` `Content Moderation` `Batch Generation`

### Key Product Decisions
1. **Brand style LoRA** — fine-tuned model on existing art assets for style consistency
2. **Human curation layer** — all generated assets reviewed before production use
3. **IP safety check** — automated check against known IP patterns before publishing

---

## 💡 Product Principles

> How I think about building AI products:

- **AI should solve real workflows** — not be a feature that demos well
- **Human-in-the-loop first** — AI proposes, human approves on high-stakes actions
- **Explainability is a product feature** — users need to trust the AI, not just use it
- **Measure outcomes, not model metrics** — latency, user behavior, task completion rate
- **Fail gracefully** — every AI product needs a non-AI fallback

---

## 📬 Contact

- GitHub: [@tiandaoyuxi](https://github.com/tiandaoyuxi)
- Open to: **AI Product Manager** · **Game AI PM** · **Enterprise AI PM**

---

*Continuously updated as I build and explore new AI products.*
