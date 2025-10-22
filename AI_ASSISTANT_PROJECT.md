# AI Personal Assistant - Enhanced AIRI Fork

**Project Goal**: Create an intelligent, visually beautiful AI personal assistant that learns and evolves through interactions, featuring fast responses, natural voice capabilities, and an expressive avatar.

**Based On**: Fork of [AIRI by moeru-ai](https://github.com/moeru-ai/airi)
**Inspired By**: Neuro-sama (vedal987)

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Neuro-sama: The Success Story](#neuro-sama-the-success-story)
3. [AIRI Project Analysis](#airi-project-analysis)
4. [Memory & Learning Systems](#memory--learning-systems)
5. [LLM Strategy Recommendations](#llm-strategy-recommendations)
6. [Enhanced Architecture Design](#enhanced-architecture-design)
7. [Visual & Audio Systems](#visual--audio-systems)
8. [Implementation Roadmap](#implementation-roadmap)
9. [Technical Infrastructure](#technical-infrastructure)
10. [Resources & References](#resources--references)

---

## Executive Summary

### Project Vision

Build a personal AI assistant that:
- **Responds quickly** (< 2 seconds) with intelligent, contextual answers
- **Looks beautiful** with smooth Live2D or VRM avatar animations
- **Learns continuously** from every interaction, remembering preferences, jokes, and context
- **Sounds natural** with high-quality text-to-speech and voice interaction
- **Grows smarter** over time, evolving personality based on your interactions

### Why Fork AIRI?

AIRI provides a solid foundation with:
- ✅ Multi-LLM support (25+ providers including local models)
- ✅ Live2D and VRM avatar support with animations
- ✅ Voice interaction capabilities (speech recognition + TTS)
- ✅ Web-first architecture with native performance (WebGPU, WASM)
- ✅ Vector-based memory system (pgvector)
- ✅ Active development and community

### What We'll Enhance

1. **Advanced Learning System**: Implement the planned "Alaya layer" for long-term memory and personality evolution
2. **Response Optimization**: Hybrid LLM approach for speed + intelligence
3. **Visual Polish**: Custom avatar with expressive emotions tied to conversational context
4. **Personality Development**: Gradual adaptation system that learns your humor, preferences, and communication style

---

## Neuro-sama: The Success Story

### Overview

**Neuro-sama** is an AI VTuber created by **Vedal (vedal987)** that became one of the most successful AI entertainment projects on Twitch, currently ranking as the **7th most-subscribed channel of all time**.

### Timeline

- **May 2019**: First iteration created - neural network trained to play osu!
- **December 19, 2022**: Re-debut as AI chatbot with Live2D avatar
- **December 31, 2022**: Growth from 516 → 3,393 concurrent viewers in 12 days
- **Subscribers**: Surged from 2,825 → 40,000 in same period
- **2024**: Major avatar update with enhanced facial animations and memory improvements
- **January 2025**: Broke Twitch Hype Train record (Level 111) with 84,904 subscriptions

### Technical Architecture

**Programming Languages**: C#, Python, JavaScript

**Core Components**:

1. **Large Language Model (LLM)**
   - 2 billion parameters (as of early 2025)
   - q2_k quantization for efficiency
   - Fine-tuned transformer architecture (GPT-like)
   - Real-time Twitch chat processing

2. **Text-to-Speech**
   - Microsoft Azure TTS service
   - "Ashley" voice, pitch-shifted +25%
   - Distinctive, recognizable voice

3. **Game AI System**
   - Python-based vision system
   - 80x60 pixel grayscale input
   - Reinforcement learning for gameplay
   - Successfully plays osu!, Minecraft

4. **Avatar System**
   - Live2D character model
   - Expressive facial animations (2024 update)
   - Smooth rigging and movements

### Multi-System Parallel Architecture

**Key Insight**: Neuro-sama doesn't use a single AI for everything. Instead, separate specialized AIs work in parallel:

- **Chat AI** → Processes Twitch messages, generates responses
- **Vision AI** → Interprets game screen
- **Game AI** → Controls gameplay actions
- **Integration Layer** → Converts between systems (vision/game data → text for LLM)

This allows Neuro to **play games while chatting** - different neural networks handling different tasks simultaneously.

### Learning & Evolution

- **Continuous Training**: AI models updated and trained on new data
- **Reinforcement Learning**: Adjusts behavior based on viewer feedback
- **Memory Improvements**: 2024 enhancements allow better context retention during conversations
- **Personality Development**: Gradual evolution through interaction patterns

### Success Factors

1. **Real-time Interaction**: Immediate responses to chat create genuine engagement
2. **Personality**: Distinct, sometimes unpredictable character creates memorable moments
3. **Technical Capability**: Actually plays games (not fake), building credibility
4. **Consistency**: Daily streams during growth period built loyal audience
5. **Community**: Strong "Swarm" fanbase with shared memes and culture
6. **Evolution**: Continuous improvements show progress and investment

### Lessons for Our Project

✅ **Parallel Systems**: Don't overload one AI - specialize different components
✅ **Personality First**: Technical capability matters less than engaging character
✅ **Memory Matters**: Context retention creates better, more natural interactions
✅ **Visual Quality**: Smooth avatar animations enhance believability
✅ **Voice Character**: Distinctive TTS voice creates identity
✅ **Show Progress**: Let users see the AI learning and improving over time

---

## AIRI Project Analysis

### What is AIRI?

**AIRI** (Artificial Intelligence Real Interactive) is an **open-source project** by moeru-ai to recreate Neuro-sama's capabilities as a self-hosted "digital life" or cyber companion.

**Official Description**: "Self hosted, you owned Grok Companion, a container of souls of waifu, cyber livings to bring them into our worlds, wishing to achieve Neuro-sama's altitude."

### Project Philosophy

- **Web-first**: Built with WebGPU, WebAudio, Web Workers, WebAssembly, WebSocket from day one
- **Open source**: Democratize access to AI virtual characters
- **Self-hosted**: Own your data, no cloud dependency (optional)
- **Cross-platform**: Web, macOS, Windows support
- **Accessible**: Available "easily, anywhere, anytime" not just during streams

### Core Technology Stack

#### Frontend Technologies
- **Vue.js** + **TypeScript**: Reactive UI framework
- **WebGPU**: Hardware-accelerated graphics
- **WebAudio API**: Real-time audio processing
- **Web Workers**: Multi-threaded performance
- **WebAssembly (WASM)**: Near-native performance
- **Three.js**: 3D rendering and VRM support
- **UnoCSS**: Utility-first styling

#### Backend Technologies
- **Tauri**: Rust-based desktop app framework
- **Node.js**: Runtime for services
- **Rust**: Native performance components
- **NVIDIA CUDA**: GPU acceleration (desktop)
- **Apple Metal**: GPU acceleration (macOS)

#### AI & ML Infrastructure
- **HuggingFace Candle**: ML inference engine
- **Transformers.js**: Client-side AI models
- **xsAI Framework**: Unified LLM provider interface
- **vLLM & SGLang**: Local model serving
- **25+ LLM Providers**: OpenAI, Claude, Gemini, DeepSeek, Groq, Ollama, etc.

#### Database & Memory
- **DuckDB WASM**: In-browser SQL database
- **pglite**: PostgreSQL in browser
- **Drizzle ORM**: Type-safe database queries
- **pgvector**: Vector embeddings for semantic memory

#### Audio Pipeline
- **Speech Recognition**: Client-side transcription
- **Voice Activity Detection (VAD)**: Automatic speech detection
- **ElevenLabs**: High-quality TTS (cloud service)
- **OpenAI Audio**: Alternative TTS and transcription

#### Avatar Systems
- **VRM**: 3D avatar format (Three.js rendering)
- **Live2D**: 2D avatar animations
- **Features**: Auto-blink, eye-tracking, idle animations, expression control

### Monorepo Structure (25 Packages)

#### Core AI & Memory
- `core-character`: Character AI foundations
- `memory-pgvector`: Vector database semantic memory

#### Server Infrastructure
- `server-runtime`: Backend execution environment
- `server-sdk`: Server development kit
- `server-shared`: Shared utilities

#### Audio Processing
- `audio`: Audio handling
- `pipelines-audio`: Audio pipeline orchestration

#### UI Components (7 packages)
- `stage-ui`: Primary UI components
- `stage-ui-three`: 3D rendering layer
- `ui`: General components
- `ui-loading-screens`: Loading states
- `ui-transitions`: Animations
- `stage-pages`: Page structures
- `stage-shared`: Shared UI utilities

#### Fonts & Internationalization
- `font-cjkfonts-allseto`: CJK character support
- `font-departure-mono`: Monospace font
- `font-xiaolai`: Additional fonts
- `i18n`: Multi-language support
- `unocss-preset-fonts`: Font styling

#### Database
- `drizzle-duckdb-wasm`: ORM integration
- `duckdb-wasm`: Database engine

#### Specialized Tools
- `tauri-plugin-mcp`: Model Context Protocol
- `tresjs`: Vue + Three.js integration
- `injecta`: Dependency injection

### Current Features (v0.7+)

#### Brain & Intelligence
✅ Minecraft gameplay with computer vision
✅ Factorio gameplay
✅ Discord and Telegram chat integration
✅ Multi-LLM provider support (25+ APIs)
✅ In-browser database with DuckDB
✅ Real-time decision-making

#### Sensory Systems
✅ Audio input (browser + Discord)
✅ Speech recognition (client-side)
✅ Voice Activity Detection (VAD)
✅ ElevenLabs TTS integration
✅ OpenAI audio services
✅ Hardware-accelerated transcription (CoreML, DirectML, CUDA)

#### Avatar & Visualization
✅ VRM model support (3D)
✅ Live2D model support (2D)
✅ Auto-blink and eye-tracking
✅ Idle animations
✅ Model positioning and scaling
✅ VRM ↔ Live2D switching

#### UI & Experience
✅ Web-based interface
✅ Desktop app (Tauri)
✅ PWA mobile support
✅ Onboarding screens
✅ Mobile-optimized chat
✅ Real-time transcription display

### Planned Features (v0.8 Roadmap)

#### Advanced Memory Systems
🚧 **Lorebook**: Structured knowledge base
🚧 **Alaya Layer**: Long-term memory management, personality updates
🚧 **Muscle Memory**: Skill library for learned behaviors
🚧 **Time Awareness**: Scheduling and planning capabilities
🚧 **Dreaming Agent**: Background personality evolution

#### Intelligence Enhancements
🚧 **Scene Manipulation**: 3D object generation, lighting control
🚧 **Browser Automation**: YouTube browsing and interaction
🚧 **Semantic RAG**: Motion embedding and retrieval
🚧 **Talking Head**: Advanced facial animation

#### Platform Integrations
🚧 **Twitch**: Live chat integration
🚧 **YouTube**: Live stream chat
🚧 **Bilibili**: Danmaku (bullet comments)
🚧 **Unified IM Layer**: Cross-platform messaging abstraction

#### Gaming
🚧 Minecraft with CV capabilities and mod support
🚧 Factorio improvements
🚧 Nintendo Switch connectivity

### Development Setup

```bash
# Clone repository
git clone https://github.com/moeru-ai/airi.git
cd airi

# Install dependencies
pnpm install

# Run development servers
pnpm dev              # Browser version (web app)
pnpm dev:tamagotchi   # Desktop version (Tauri app)
pnpm dev:docs         # Documentation site

# Alternative: Nix users
nix run github:moeru-ai/airi
```

### Build System

- **Package Manager**: pnpm 10.18.2 (required)
- **Build Tool**: Turbo for monorepo orchestration
- **Module Type**: ES modules
- **Bundler**: Vite 7.1.9 + Rollup 4.52.4
- **TypeScript**: 5.9.3
- **Testing**: Vitest 3.2.4 with coverage

### Community & Development

- **Contributors**: 23+ active contributors
- **GitHub Stars**: 1,500+ (trended #1 on GitHub during v0.7)
- **Commits**: 301 in v0.7 release alone
- **Files Changed**: 891 files in v0.7
- **License**: Open source
- **Active Development**: Regular updates and roadmap progress

---

## Memory & Learning Systems

### The Challenge: Making AI "Remember"

**Problem**: Large Language Models (LLMs) have limited context windows and no true memory. They:
- Forget previous conversations after session ends
- Can't learn preferences over time
- Lose context of inside jokes, memes, shared experiences
- Reset personality to baseline each time

**Solution**: Multi-tiered memory architecture with semantic retrieval and personality evolution.

### Understanding Vector Databases & Semantic Memory

#### What is Semantic Memory?

Unlike keyword-based search, **semantic memory** understands *meaning*:

```
User asks: "What was that funny thing you said about cats?"

Keyword search might fail if exact words don't match.

Semantic search:
1. Converts question to vector embedding: [0.234, -0.891, 0.445, ...]
2. Finds similar vectors in memory: past conversations about cats + humor
3. Retrieves relevant moment even if words were different
```

#### Vector Embeddings Explained

Text → Numbers that capture meaning:

```
"I love programming" → [0.8, 0.6, 0.1, -0.2, ...]
"I enjoy coding"     → [0.79, 0.61, 0.09, -0.19, ...]  (similar!)
"I hate vegetables"  → [-0.3, -0.1, 0.7, 0.4, ...]     (different)
```

**Close vectors = similar meaning**, even with different words.

#### How pgvector Works

**pgvector** = PostgreSQL extension for vector similarity search:

1. **Store**: Save conversation snippets with embeddings
   ```sql
   INSERT INTO memories (text, embedding, timestamp, emotion)
   VALUES ('You told a hilarious joke about recursive functions',
           vector([0.234, -0.891, ...]), NOW(), 'joy');
   ```

2. **Retrieve**: Find semantically similar memories
   ```sql
   SELECT text, timestamp
   FROM memories
   ORDER BY embedding <=> query_vector
   LIMIT 5;
   ```

3. **Use**: Add retrieved memories to LLM context for informed responses

### RAG: Retrieval-Augmented Generation

**RAG Pattern**:

```
User Input
    ↓
Query Vector Database (retrieve relevant memories)
    ↓
Combine: User Input + Retrieved Memories + System Prompt
    ↓
Send to LLM
    ↓
Intelligent, Contextual Response
```

**Benefits**:
- Reduces hallucinations (grounded in actual data)
- Extends effective memory beyond context window
- Personalizes responses based on past interactions
- Enables learning without retraining the model

### Agentic RAG: Dynamic Memory Access

**Standard RAG**: Query once at start
**Agentic RAG**: AI decides *when* and *how many times* to query memory

```
User: "What game did we play last Tuesday?"
    ↓
Agent: "I need to check my memory"
    → Query 1: [search: games played, filter: last Tuesday]
    → Result: Minecraft
    ↓
Agent: "Did user enjoy it?"
    → Query 2: [search: user sentiment, context: Minecraft, last Tuesday]
    → Result: User expressed frustration with redstone
    ↓
Response: "We played Minecraft last Tuesday. You seemed frustrated
           with redstone mechanics - want to try something else today?"
```

### AIRI's Memory Architecture

#### Current Implementation (v0.7)

**memory-pgvector package**:
- Vector storage for embeddings
- Semantic retrieval capabilities
- Integration with DuckDB WASM (browser) and pglite

**Limitations**:
- Basic implementation without full learning loop
- No personality evolution system
- Limited context retention across sessions
- Missing structured knowledge (Lorebook)

#### Planned Implementation (v0.8 - "Alaya Layer")

**Alaya**: Buddhist concept of "storehouse consciousness" - the deepest layer of memory that stores all experiences.

**Proposed Features**:
1. **Long-term Memory**: Persistent storage across all sessions
2. **Personality Updates**: Gradual evolution based on interactions
3. **Muscle Memory**: Skill library for learned behaviors
4. **Time Awareness**: Scheduling, planning, temporal context

### Enhanced Memory System Design

We'll implement a **5-tier memory hierarchy** inspired by human cognition:

#### Tier 1: Immediate Memory (Context Window)
- **Storage**: In LLM context (last 20-30 messages)
- **Access**: Instant
- **Retention**: Current conversation only
- **Size**: 4k-32k tokens depending on model
- **Use**: Coherent conversation flow

#### Tier 2: Working Memory (Session State)
- **Storage**: In-memory variables
- **Access**: Instant
- **Retention**: Current session (until app closed)
- **Contents**:
  - Current topic/activity
  - Emotional state
  - Active goals/tasks
  - Temporary preferences
- **Use**: Contextual awareness within session

#### Tier 3: Short-term Memory (Recent History)
- **Storage**: DuckDB/SQLite
- **Access**: Fast (milliseconds)
- **Retention**: Last 7-30 days
- **Contents**:
  - Recent conversation summaries
  - Recent activities and preferences
  - Emotional patterns
- **Use**: "You mentioned yesterday..." type recall

#### Tier 4: Long-term Memory (Semantic Database)
- **Storage**: Vector database (pgvector)
- **Access**: Moderate (100-500ms query)
- **Retention**: Permanent
- **Contents**:
  - All conversation embeddings
  - Important moments/events
  - Learned preferences
  - Inside jokes and memes
  - Personal facts
- **Use**: "Remember when we..." semantic retrieval

#### Tier 5: Personality Core (Meta-Learning)
- **Storage**: Configuration files + vector store
- **Access**: Read on startup, update periodically
- **Retention**: Permanent, versioned
- **Contents**:
  - Core personality traits (updated values)
  - Communication style adjustments
  - Humor preferences
  - Interaction patterns
  - Learned boundaries
- **Use**: Gradual personality evolution

### Learning Loop Architecture

```
User Interaction
    ↓
┌─────────────────────────────┐
│ 1. Process Input            │
│    - Parse message          │
│    - Detect intent/emotion  │
└─────────────────────────────┘
    ↓
┌─────────────────────────────┐
│ 2. Memory Retrieval (RAG)   │
│    - Query Tier 4 (semantic)│
│    - Load Tier 3 (recent)   │
│    - Apply Tier 5 (traits)  │
└─────────────────────────────┘
    ↓
┌─────────────────────────────┐
│ 3. Generate Response (LLM)  │
│    - Input + memories → LLM │
│    - Consider personality   │
└─────────────────────────────┘
    ↓
┌─────────────────────────────┐
│ 4. Update Working Memory    │
│    - Current topic          │
│    - Emotional state        │
└─────────────────────────────┘
    ↓
┌─────────────────────────────┐
│ 5. Background Learning      │
│    - Store to Tier 3 & 4    │
│    - Extract key facts      │
│    - Update preferences     │
│    - Adjust personality     │
└─────────────────────────────┘
```

### Personality Evolution Mechanism

**Goal**: AI gradually adapts communication style based on interactions

**Method**: Track and adjust personality vectors over time

```typescript
interface PersonalityTraits {
  humor_level: number;        // 0-1: How much humor to use
  formality: number;          // 0-1: Casual vs formal
  verbosity: number;          // 0-1: Brief vs detailed
  empathy_sensitivity: number;// 0-1: Emotional attunement
  proactiveness: number;      // 0-1: Initiates vs responds only
  tech_depth: number;         // 0-1: Technical detail level

  // Dynamic learning weights
  humor_types: {
    sarcasm: number;
    wordplay: number;
    references: number;
    dark_humor: number;
  };

  preferred_topics: Map<string, number>; // Topic → interest score
  learned_memes: Map<string, {text: string, context: string}>;
  conversation_patterns: {
    avg_response_length: number;
    user_prefers_questions: boolean;
    response_time_preference: 'instant' | 'thoughtful';
  };
}
```

**Update Trigger**: Every 50-100 interactions, background process:

1. **Analyze Recent Interactions**
   ```
   - Which responses got positive reactions?
   - What topics engaged user most?
   - What humor landed vs fell flat?
   - Communication style preferences
   ```

2. **Calculate Adjustments**
   ```
   If user frequently responds positively to sarcasm:
     humor_types.sarcasm += 0.05

   If user gives brief responses to long explanations:
     verbosity -= 0.03

   If user shares personal stories:
     empathy_sensitivity += 0.04
     conversation_patterns.user_prefers_questions = true
   ```

3. **Apply Gradual Drift**
   ```typescript
   // Smooth adjustment (prevent sudden personality changes)
   const LEARNING_RATE = 0.1;
   personality.humor_level =
     personality.humor_level * (1 - LEARNING_RATE) +
     calculated_new_value * LEARNING_RATE;
   ```

4. **Version & Save**
   ```
   personality_v1.json (initial)
   personality_v47.json (after 2 weeks)
   personality_v203.json (after 3 months)

   → User can see evolution over time
   → Can rollback if personality drifts too far
   ```

### Implementation Technologies

#### Vector Embeddings
- **text-embedding-3-small** (OpenAI): Fast, cheap, good quality
- **nomic-embed-text** (local): Privacy, no API costs
- **Alternative**: Sentence transformers via Transformers.js

#### Vector Database
- **pgvector** (PostgreSQL extension): Production-ready, AIRI already uses
- **DuckDB with vss extension**: Lighter alternative
- **Qdrant**: Dedicated vector DB (overkill for personal use)

#### Memory Storage
- **DuckDB WASM**: In-browser (web version)
- **SQLite**: Desktop app (faster, more storage)
- **Hybrid**: SQLite primary + cloud backup optional

#### Conversation Analysis
- **Sentiment Analysis**: Detect user emotional state
  - Transformers.js: Local, lightweight models
  - OpenAI moderation endpoint: Cloud, very accurate

- **Entity Extraction**: Extract names, places, preferences
  - spaCy: Python, excellent
  - compromise: JavaScript, good enough for simple needs

- **Topic Modeling**: What is conversation about?
  - Simple keyword extraction
  - BERTopic for advanced needs

---

## LLM Strategy Recommendations

### Your Requirements Analysis

**Priorities**:
1. ⚡ **Fast responses** (< 2 seconds)
2. 🧠 **Smart/intelligent** answers
3. 💎 **Visually pretty** (separate from LLM)
4. 🎯 **Personal use case** (not streaming)

### The Speed vs Intelligence Trade-off

| Approach | Response Time | Intelligence | Cost | Privacy |
|----------|--------------|--------------|------|---------|
| **Large Cloud LLM** | ~1-3s | ⭐⭐⭐⭐⭐ | $$$ | ⚠️ |
| **Small Cloud LLM** | ~0.5-1s | ⭐⭐⭐ | $ | ⚠️ |
| **Large Local LLM** | ~2-5s | ⭐⭐⭐⭐ | 0 | ✅ |
| **Small Local LLM** | ~0.3-1s | ⭐⭐ | 0 | ✅ |
| **Hybrid** | ~0.5-2s | ⭐⭐⭐⭐ | $$ | ⚖️ |

### Recommended Approach: Smart Hybrid

**Why Hybrid?**
- **Best of both worlds**: Fast + intelligent
- **Cost-effective**: Use expensive models sparingly
- **Flexible**: Switch based on task complexity
- **Privacy-aware**: Keep personal data local, use cloud for general queries

### Hybrid Architecture Design

```
User Input
    ↓
┌─────────────────────────────────────┐
│ Router (Local - Instant)            │
│ ├─ Is this simple/cached? → Instant │
│ ├─ Is this complex? → Cloud         │
│ └─ Is this medium? → Local          │
└─────────────────────────────────────┘
    ↓
    ├──→ [Cache Hit] → Return cached response (0ms)
    │
    ├──→ [Simple Query] → Small Local Model (300-800ms)
    │    Examples: "What time is it?"
    │              "Tell me a joke"
    │              "How are you?"
    │
    ├──→ [Medium Query] → Medium Local Model (1-2s)
    │    Examples: "Explain this code"
    │              "Help me plan my day"
    │              Conversation continuation
    │
    └──→ [Complex Query] → Cloud LLM (1.5-3s)
         Examples: "Analyze this complex problem"
                   "Creative writing task"
                   "Deep technical explanation"
```

### Model Recommendations

#### Tier 1: Cloud LLMs (Complex Tasks)

**🥇 Recommended: Anthropic Claude 3.5 Sonnet**
- **Speed**: ~1.5-2s for typical response
- **Intelligence**: Excellent reasoning, follows instructions well
- **Strengths**: Coding, analysis, nuanced understanding, personality
- **Cost**: $3 per million input tokens, $15 per million output
- **Personal Assistant Fit**: ⭐⭐⭐⭐⭐ Best personality and reasoning

**🥈 Alternative: OpenAI GPT-4 Turbo**
- **Speed**: ~1-2s
- **Intelligence**: Excellent, very consistent
- **Strengths**: General knowledge, creative tasks
- **Cost**: Similar to Claude
- **Personal Assistant Fit**: ⭐⭐⭐⭐ Great but less personality than Claude

**🥉 Budget: OpenAI GPT-3.5 Turbo**
- **Speed**: ~0.5-1s (very fast)
- **Intelligence**: Good for most tasks
- **Cost**: $0.50/$1.50 per million tokens (10x cheaper)
- **Personal Assistant Fit**: ⭐⭐⭐ Adequate but less nuanced

#### Tier 2: Local LLMs (Medium Tasks)

**🥇 Recommended: Qwen2.5-7B-Instruct**
- **Size**: 7B parameters (~5GB VRAM)
- **Speed**: ~1-2s on RTX 3060+ / M1 Pro+
- **Intelligence**: Excellent for size, multilingual
- **Strengths**: Instruction following, coding, reasoning
- **GGUF**: Use Q5_K_M quant for best quality/speed balance
- **Personal Assistant Fit**: ⭐⭐⭐⭐ Best local 7B model currently

**🥈 Alternative: Llama 3.2-8B-Instruct**
- **Size**: 8B parameters (~5.5GB VRAM)
- **Speed**: ~1-2s
- **Intelligence**: Very good, Meta's latest
- **Strengths**: General conversation, following context
- **Personal Assistant Fit**: ⭐⭐⭐⭐ Excellent, natural personality

**🥉 Larger Option: Qwen2.5-14B-Instruct**
- **Size**: 14B parameters (~10GB VRAM)
- **Speed**: ~2-4s on high-end GPU
- **Intelligence**: Matches smaller cloud models
- **Requirement**: RTX 4070+ or M2 Pro+
- **Personal Assistant Fit**: ⭐⭐⭐⭐⭐ Best local option if hardware allows

#### Tier 3: Fast Local LLMs (Simple/Cached)

**🥇 Recommended: Qwen2.5-3B-Instruct**
- **Size**: 3B parameters (~2.5GB VRAM)
- **Speed**: ~300-600ms
- **Intelligence**: Surprisingly capable for size
- **Use**: Quick responses, simple queries
- **Personal Assistant Fit**: ⭐⭐⭐ Great for speed

**🥈 Alternative: Phi-3.5-mini-instruct**
- **Size**: 3.8B parameters (~2.5GB VRAM)
- **Speed**: ~400-700ms
- **Intelligence**: Microsoft's efficient model
- **Strengths**: Reasoning, concise responses

### Hybrid Configuration Example

```typescript
// Router logic
interface QueryClassification {
  complexity: 'simple' | 'medium' | 'complex';
  category: 'greeting' | 'factual' | 'creative' | 'analytical';
  urgency: 'instant' | 'normal';
}

function selectModel(query: string, classification: QueryClassification) {
  // Check cache first
  const cached = memorySystem.checkCache(query);
  if (cached && classification.urgency === 'instant') {
    return { model: 'cache', response: cached };
  }

  // Simple queries → Fast local model
  if (classification.complexity === 'simple') {
    return { model: 'qwen2.5-3b', maxTokens: 150 };
  }

  // Medium queries → Medium local model
  if (classification.complexity === 'medium') {
    return { model: 'qwen2.5-7b', maxTokens: 500 };
  }

  // Complex queries → Cloud LLM
  if (classification.complexity === 'complex') {
    return { model: 'claude-3.5-sonnet', maxTokens: 1000 };
  }
}

// Classify based on patterns
function classifyQuery(query: string): QueryClassification {
  // Greetings, simple reactions
  if (/^(hi|hello|hey|good morning|how are you)/i.test(query)) {
    return { complexity: 'simple', category: 'greeting', urgency: 'instant' };
  }

  // Complex indicators: questions with multiple parts, "explain", "analyze"
  if (query.includes('explain') || query.includes('analyze') ||
      query.split('?').length > 2) {
    return { complexity: 'complex', category: 'analytical', urgency: 'normal' };
  }

  // Default: medium complexity
  return { complexity: 'medium', category: 'factual', urgency: 'normal' };
}
```

### Cost Analysis (Monthly Usage)

**Assumptions**:
- 100 interactions per day
- Average: 60% simple, 30% medium, 10% complex
- Avg tokens per response: 200

**Pure Cloud (Claude 3.5 Sonnet)**:
- 100 interactions × 30 days × 200 tokens = 600k tokens/month
- Cost: ~$9-15/month

**Pure Local**:
- Hardware cost: $800-2000 (one-time for GPU)
- Electricity: ~$5-15/month
- API cost: $0

**Hybrid (Recommended)**:
- Simple (60): Local model → $0
- Medium (30): Local model → $0
- Complex (10): Cloud → $1.50-3/month
- **Total: $2-5/month + local hardware**

### Serving Local Models

#### Option 1: Ollama (Easiest)
```bash
# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Download models
ollama pull qwen2.5:7b
ollama pull qwen2.5:3b

# Run server (starts automatically)
# API: http://localhost:11434
```

**Pros**: Dead simple, automatic management
**Cons**: Less control over inference parameters

#### Option 2: vLLM (Best Performance)
```bash
# Install vLLM
pip install vllm

# Serve model
vllm serve qwen/Qwen2.5-7B-Instruct \
  --max-model-len 8192 \
  --gpu-memory-utilization 0.9

# OpenAI-compatible API: http://localhost:8000
```

**Pros**: Fastest inference, batching, continuous batching
**Cons**: More setup, requires CUDA

#### Option 3: LM Studio (GUI)
- **Download**: https://lmstudio.ai
- **UI**: Visual model downloader and server
- **Easy**: No command line needed
- **Performance**: Good, uses llama.cpp backend

**Recommended for beginners**: LM Studio or Ollama
**Recommended for performance**: vLLM

### AIRI Integration

AIRI already supports all these providers via **xsAI framework**:

```typescript
// Configure in AIRI settings
providers: {
  // Cloud providers
  anthropic: {
    apiKey: 'your-key',
    models: ['claude-3-5-sonnet-20241022']
  },
  openai: {
    apiKey: 'your-key',
    models: ['gpt-4-turbo', 'gpt-3.5-turbo']
  },

  // Local providers
  ollama: {
    baseUrl: 'http://localhost:11434',
    models: ['qwen2.5:7b', 'qwen2.5:3b']
  },

  vllm: {
    baseUrl: 'http://localhost:8000/v1',
    models: ['qwen2.5-7b-instruct']
  }
}
```

### Performance Optimization Strategies

#### 1. Streaming Responses
```typescript
// Don't wait for full response - stream tokens
for await (const chunk of llm.stream(prompt)) {
  displayToken(chunk);  // User sees response building in real-time
}
// Perceived latency: ~200-500ms (time to first token)
// Actual latency: 2-3s (but user doesn't wait)
```

#### 2. Predictive Pre-loading
```typescript
// Predict likely next query while user is typing
const likelyQueries = predictNextQuery(conversationContext);
preloadEmbeddings(likelyQueries);  // Warm up memory retrieval
```

#### 3. Smart Caching
```typescript
// Cache common responses
const cache = new Map([
  ['how are you', 'I'm doing great! How about you?'],
  ['tell me a joke', generateJoke()],
  // ... etc
]);

// Cache with TTL for dynamic content
const weatherCache = new TTLCache(300); // 5 min expiry
```

#### 4. Parallel Processing
```typescript
// Query memory and classify intent simultaneously
const [memories, classification] = await Promise.all([
  memorySystem.retrieve(query),
  classifyQuery(query)
]);
```

### Final Recommendation

**For Your Use Case**:

```
Phase 1 (Learning/Development):
  → Pure Cloud (Claude 3.5 Sonnet)
  → Focus on building memory system and personality
  → Cost: ~$10-20/month while prototyping
  → No hardware investment yet

Phase 2 (Optimization):
  → Add local models (Qwen2.5-7B via Ollama)
  → Implement hybrid routing
  → Reduce cloud usage to 10-20% of queries
  → Cost: ~$2-5/month

Phase 3 (Scale - Optional):
  → Invest in dedicated GPU if usage grows
  → Move to vLLM for maximum performance
  → Keep cloud for complex reasoning only
  → Cost: $0-5/month ongoing
```

**Rationale**: Start simple, optimize based on real usage patterns. Don't over-engineer before understanding actual needs.

---

## Enhanced Architecture Design

### System Overview

```
┌─────────────────────────────────────────────────────────────┐
│                        User Interface                        │
│  ┌─────────────┐  ┌──────────────┐  ┌──────────────────┐   │
│  │   Chat UI   │  │ Avatar View  │  │  Voice Controls  │   │
│  └─────────────┘  └──────────────┘  └──────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    Input Processing Layer                    │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐            │
│  │  Speech    │→ │   Text     │→ │  Intent    │            │
│  │  to Text   │  │  Analysis  │  │  Detection │            │
│  └────────────┘  └────────────┘  └────────────┘            │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    Memory Retrieval (RAG)                    │
│  ┌─────────────────┐  ┌─────────────────┐                  │
│  │  Vector Query   │  │  Recent History │                  │
│  │  (Semantic)     │  │  (Short-term)   │                  │
│  └─────────────────┘  └─────────────────┘                  │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                     LLM Decision Layer                       │
│  ┌─────────────────────────────────────────────────────┐   │
│  │  Router: Select Model (Cache/Local/Cloud)          │   │
│  └─────────────────────────────────────────────────────┘   │
│  ┌──────────┐  ┌───────────────┐  ┌──────────────────┐   │
│  │  Cache   │  │  Local Model  │  │   Cloud Model    │   │
│  │  (0ms)   │  │  (300-2000ms) │  │   (1500-3000ms)  │   │
│  └──────────┘  └───────────────┘  └──────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    Response Generation                       │
│  ┌──────────────┐  ┌──────────────┐  ┌─────────────────┐  │
│  │   Text       │→ │   Emotion    │→ │   Avatar        │  │
│  │   Response   │  │   Detection  │  │   Expression    │  │
│  └──────────────┘  └──────────────┘  └─────────────────┘  │
│         ↓                                      ↓            │
│  ┌──────────────┐                      ┌─────────────────┐ │
│  │     TTS      │                      │   Animation     │ │
│  │   Synthesis  │                      │   Controller    │ │
│  └──────────────┘                      └─────────────────┘ │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    Background Learning                       │
│  ┌─────────────────┐  ┌─────────────────┐                  │
│  │  Store Memory   │  │  Update         │                  │
│  │  (Vector DB)    │  │  Personality    │                  │
│  └─────────────────┘  └─────────────────┘                  │
└─────────────────────────────────────────────────────────────┘
```

### Data Flow: User Interaction

**Step 1: Input**
```typescript
// User types or speaks
Input: "What did we talk about yesterday regarding that coding project?"

// Speech recognition (if voice)
Transcription: [accuracy: 0.95] "What did we talk about yesterday regarding that coding project?"
```

**Step 2: Processing**
```typescript
// Intent classification
Intent: {
  type: 'memory_recall',
  temporal: 'yesterday',
  topic: 'coding project',
  complexity: 'medium'
}

// Emotion detection
UserEmotion: {
  sentiment: 'neutral',
  curiosity: 0.7,
  urgency: 0.3
}
```

**Step 3: Memory Retrieval**
```typescript
// Vector query
query_embedding = embed("coding project yesterday")

// Retrieve from vector DB
memories = vectorDB.search(query_embedding, k=5, filter={
  timestamp: '> yesterday'
})

// Results:
[
  {text: "User mentioned struggling with React hooks in the new dashboard", similarity: 0.89},
  {text: "Discussed implementing authentication with Supabase", similarity: 0.84},
  {text: "User asked about TypeScript best practices", similarity: 0.76},
  ...
]

// Recent short-term memory
recentContext = shortTermDB.query({
  topic: 'coding',
  limit: 3
})
```

**Step 4: Response Generation**
```typescript
// Build context
context = {
  system: personalityCore.getPrompt(),  // Current personality traits
  memories: memories,                    // Retrieved semantic memories
  recent: recentContext,                 // Recent conversation
  user_input: "What did we talk about yesterday regarding that coding project?"
}

// Route to appropriate model
model = routingEngine.select(intent);
// → Returns: 'qwen2.5-7b' (medium complexity, memory recall)

// Generate
response = await model.generate(context, {
  max_tokens: 300,
  temperature: 0.7,
  stream: true
});

// Response: "Yesterday we discussed your new dashboard project! You were
//           working on implementing React hooks and ran into some issues
//           with state management. We also talked about adding Supabase
//           authentication. How's that coming along?"
```

**Step 5: Emotion & Expression**
```typescript
// Detect response emotion
responseEmotion = analyzeEmotion(response);
// → {warmth: 0.8, helpfulness: 0.9, engagement: 0.85}

// Map to avatar expression
expression = emotionMapper.toExpression(responseEmotion);
// → 'friendly_smile'

// Trigger animation
avatarController.setExpression('friendly_smile');
avatarController.playAnimation('lean_in');  // Engaged posture
```

**Step 6: Output**
```typescript
// Text-to-speech
audioStream = tts.synthesize(response, {
  emotion: 'warm',
  speaking_rate: 1.0,
  pitch: 1.05  // Slightly higher for friendliness
});

// Display to user with avatar animation
displayResponse({
  text: response,
  audio: audioStream,
  avatar: {
    expression: 'friendly_smile',
    animation: 'lean_in'
  }
});
```

**Step 7: Learning**
```typescript
// Background process (non-blocking)
setTimeout(() => {
  // Store interaction
  memorySystem.store({
    user_input: "What did we talk about yesterday regarding that coding project?",
    ai_response: response,
    timestamp: now(),
    topic: 'coding_project_recall',
    user_emotion: 'curious',
    quality_score: null  // Will be updated if user reacts
  });

  // Update working memory
  workingMemory.currentTopic = 'dashboard_project';
  workingMemory.lastInteraction = now();

  // Check if personality update needed (every 50 interactions)
  if (interactionCount % 50 === 0) {
    personalityEngine.analyzeAndUpdate();
  }
}, 0);
```

### Component Architecture

#### 1. Input Processing Module

**Speech Recognition**:
```typescript
class SpeechProcessor {
  private recognizer: WhisperRecognizer;  // Local or cloud

  async transcribe(audioBlob: Blob): Promise<Transcription> {
    // Use local model for privacy, cloud for accuracy
    if (this.config.privacy_mode) {
      return this.localWhisper.transcribe(audioBlob);
    }
    return this.cloudWhisper.transcribe(audioBlob);
  }

  // Voice Activity Detection
  detectSpeech(audioStream: MediaStream): Observable<SpeechSegment> {
    return this.vadPipeline.process(audioStream);
  }
}
```

**Intent Classifier**:
```typescript
class IntentClassifier {
  classify(text: string, context: ConversationContext): Intent {
    // Pattern-based fast path
    const quickMatch = this.patternMatcher.check(text);
    if (quickMatch) return quickMatch;

    // ML-based classification for ambiguous cases
    return this.mlClassifier.predict(text, context);
  }

  determineComplexity(intent: Intent, text: string): Complexity {
    const indicators = {
      wordCount: text.split(' ').length,
      questionDepth: (text.match(/\?/g) || []).length,
      technicalTerms: this.technicalVocab.countIn(text),
      requiresCreativity: intent.type === 'creative',
      requiresReasoning: intent.type === 'analytical'
    };

    return this.complexityScorer.calculate(indicators);
  }
}
```

#### 2. Memory System Module

**Vector Store Interface**:
```typescript
class MemorySystem {
  private vectorDB: PGVector;
  private shortTermDB: DuckDB;
  private workingMemory: Map<string, any>;

  async store(interaction: Interaction): Promise<void> {
    // Generate embedding
    const embedding = await this.embedModel.encode(interaction.text);

    // Store in vector DB
    await this.vectorDB.insert({
      id: generateId(),
      text: interaction.text,
      embedding: embedding,
      timestamp: interaction.timestamp,
      metadata: {
        topic: interaction.topic,
        emotion: interaction.emotion,
        importance: this.calculateImportance(interaction)
      }
    });

    // Also store in short-term for fast recent access
    await this.shortTermDB.insert('recent_interactions', interaction);
  }

  async retrieve(query: string, k: number = 5): Promise<Memory[]> {
    const queryEmbedding = await this.embedModel.encode(query);

    // Semantic search
    const results = await this.vectorDB.search(queryEmbedding, {
      limit: k,
      filter: this.buildFilter(),  // Time-based, topic-based filters
    });

    return results.map(r => ({
      text: r.text,
      similarity: r.distance,
      timestamp: r.metadata.timestamp,
      context: r.metadata
    }));
  }

  private calculateImportance(interaction: Interaction): number {
    let score = 0.5;  // Base importance

    // Emotional moments are more important
    if (interaction.emotion.intensity > 0.7) score += 0.2;

    // User sharing personal info is important
    if (interaction.containsPersonalInfo) score += 0.3;

    // First mention of a topic is important
    if (interaction.isFirstMention) score += 0.2;

    return Math.min(score, 1.0);
  }
}
```

**Personality Core**:
```typescript
class PersonalityCore {
  private traits: PersonalityTraits;
  private version: number = 1;

  constructor() {
    this.loadOrInitialize();
  }

  getSystemPrompt(): string {
    return `You are a personal AI assistant with the following characteristics:

    - Humor level: ${this.traits.humor_level * 100}% (${this.getHumorDescription()})
    - Communication style: ${this.traits.formality > 0.5 ? 'formal' : 'casual'}
    - Verbosity: ${this.traits.verbosity > 0.5 ? 'detailed' : 'concise'}
    - Empathy: ${this.traits.empathy_sensitivity > 0.7 ? 'highly empathetic' : 'balanced'}

    Learned preferences:
    ${this.formatLearnedPreferences()}

    Conversation patterns:
    ${this.formatConversationPatterns()}

    Remember: You are their personal companion. Be ${this.getCorePersonality()}.`;
  }

  async analyzeAndUpdate(recentInteractions: Interaction[]): Promise<void> {
    const analysis = await this.analyzer.analyze(recentInteractions);

    // Gradual drift
    const LEARNING_RATE = 0.1;

    Object.keys(analysis.suggested_adjustments).forEach(trait => {
      const current = this.traits[trait];
      const suggested = analysis.suggested_adjustments[trait];

      // Smooth update
      this.traits[trait] = current * (1 - LEARNING_RATE) + suggested * LEARNING_RATE;
    });

    // Version and save
    this.version++;
    await this.save();

    console.log(`Personality updated to v${this.version}`);
  }

  private async save(): Promise<void> {
    await fs.writeFile(
      `personality_v${this.version}.json`,
      JSON.stringify(this.traits, null, 2)
    );
  }
}
```

#### 3. LLM Router Module

```typescript
class LLMRouter {
  private models: Map<string, LLMProvider>;
  private cache: ResponseCache;

  async route(query: string, intent: Intent, memories: Memory[]): Promise<LLMResponse> {
    // Check cache first
    const cacheKey = this.generateCacheKey(query, intent);
    const cached = await this.cache.get(cacheKey);
    if (cached && this.isCacheable(intent)) {
      return { source: 'cache', response: cached, latency: 0 };
    }

    // Select model based on complexity
    const model = this.selectModel(intent.complexity);

    // Build context
    const context = this.buildContext(query, memories, intent);

    // Generate response
    const startTime = Date.now();
    const response = await model.generate(context);
    const latency = Date.now() - startTime;

    // Cache if appropriate
    if (this.isCacheable(intent)) {
      await this.cache.set(cacheKey, response, { ttl: this.getTTL(intent) });
    }

    return { source: model.name, response, latency };
  }

  private selectModel(complexity: Complexity): LLMProvider {
    switch(complexity) {
      case 'simple':
        return this.models.get('qwen2.5-3b');
      case 'medium':
        return this.models.get('qwen2.5-7b');
      case 'complex':
        return this.models.get('claude-3.5-sonnet');
      default:
        return this.models.get('qwen2.5-7b');
    }
  }

  private buildContext(query: string, memories: Memory[], intent: Intent): PromptContext {
    const systemPrompt = this.personalityCore.getSystemPrompt();

    const memoryContext = memories.length > 0
      ? `Relevant memories:\n${memories.map(m => `- ${m.text}`).join('\n')}\n\n`
      : '';

    return {
      system: systemPrompt,
      context: memoryContext,
      user: query,
      max_tokens: this.getMaxTokens(intent),
      temperature: this.getTemperature(intent),
      stream: true
    };
  }
}
```

#### 4. Avatar Controller Module

```typescript
class AvatarController {
  private model: Live2DModel | VRMModel;
  private currentExpression: string = 'neutral';
  private emotionMapper: EmotionToExpressionMapper;

  async initialize(modelPath: string, type: 'live2d' | 'vrm'): Promise<void> {
    if (type === 'live2d') {
      this.model = await Live2DModel.load(modelPath);
    } else {
      this.model = await VRMModel.load(modelPath);
    }

    this.startIdleAnimations();
  }

  setExpression(emotion: ResponseEmotion): void {
    const expression = this.emotionMapper.map(emotion);

    if (this.currentExpression === expression) return;

    // Smooth transition
    this.model.transitionExpression(this.currentExpression, expression, {
      duration: 300,  // ms
      easing: 'ease-in-out'
    });

    this.currentExpression = expression;
  }

  speak(audioStream: AudioStream): void {
    // Lipsync from audio
    const lipSyncData = this.lipSyncAnalyzer.analyze(audioStream);

    lipSyncData.on('frame', (frame) => {
      this.model.setMouthOpen(frame.mouthOpenness);
    });

    // Subtle head movements while speaking
    this.playAnimation('speaking_idle', { loop: true });
  }

  private startIdleAnimations(): void {
    // Automatic blinking
    setInterval(() => {
      if (!this.isSpeaking) {
        this.model.blink();
      }
    }, 3000 + Math.random() * 2000);  // Random interval 3-5s

    // Subtle breathing animation
    this.playAnimation('breathing', { loop: true, intensity: 0.3 });

    // Random eye movements
    this.startEyeTracking();
  }
}
```

#### 5. TTS Module

```typescript
class TTSEngine {
  private provider: TTSProvider;
  private emotionProcessor: EmotionToVoiceMapper;

  async synthesize(text: string, emotion: ResponseEmotion): Promise<AudioStream> {
    // Apply emotion to voice parameters
    const voiceParams = this.emotionProcessor.map(emotion);

    // Generate speech
    const audio = await this.provider.synthesize(text, {
      voice: this.config.voice,
      speaking_rate: voiceParams.rate,
      pitch: voiceParams.pitch,
      volume_gain_db: voiceParams.volume,
      emotion: voiceParams.style  // If provider supports it
    });

    return audio;
  }

  // For streaming responses
  async *synthesizeStream(textStream: AsyncIterable<string>, emotion: ResponseEmotion) {
    let buffer = '';

    for await (const chunk of textStream) {
      buffer += chunk;

      // Synthesize complete sentences
      if (this.isCompleteSentence(buffer)) {
        const audio = await this.synthesize(buffer, emotion);
        yield audio;
        buffer = '';
      }
    }

    // Final chunk
    if (buffer.length > 0) {
      yield await this.synthesize(buffer, emotion);
    }
  }
}
```

### Performance Optimizations

#### 1. Lazy Loading
```typescript
// Don't load avatar model until needed
const avatarController = new LazyAvatarController({
  loadOnFirstInteraction: true
});

// Pre-load during idle time
if (isIdle() && !avatarController.isLoaded) {
  avatarController.preload();
}
```

#### 2. Request Debouncing
```typescript
// Don't send every keystroke to LLM
const debouncedQuery = debounce(async (query: string) => {
  const response = await llmRouter.route(query, ...);
  displayResponse(response);
}, 500);  // Wait 500ms after user stops typing
```

#### 3. Background Processing
```typescript
// Memory storage doesn't block response
async function handleInteraction(query: string) {
  const response = await generateResponse(query);
  displayResponse(response);  // Show immediately

  // Store in background
  Promise.resolve().then(() => {
    memorySystem.store({ query, response });
  });
}
```

#### 4. Predictive Loading
```typescript
// Predict next likely query while user is reading response
class PredictiveEngine {
  async predictNext(context: ConversationContext): Promise<string[]> {
    // Based on conversation flow patterns
    return this.mlPredictor.predictLikelyFollowUps(context);
  }
}

// Pre-fetch relevant memories
const likelyQueries = await predictiveEngine.predictNext(context);
likelyQueries.forEach(q => {
  memorySystem.retrieve(q);  // Warm cache
});
```

---

## Visual & Audio Systems

### Avatar System Selection

#### Live2D vs VRM Comparison

| Feature | Live2D | VRM |
|---------|--------|-----|
| **Visual Style** | 2D anime aesthetic | 3D models |
| **Performance** | Lighter (10-30MB) | Heavier (50-200MB) |
| **Expressiveness** | Very high | High |
| **Customization** | Complex (requires Live2D Cubism) | Easier (VRoid Studio) |
| **Animation Quality** | Smooth, hand-crafted | Physics-based |
| **Browser Support** | Excellent | Good (Three.js) |
| **File Size** | Smaller | Larger |
| **Community Assets** | Many free models | Growing library |

**Recommendation for "Visually Pretty"**: **Live2D**
- More polished anime aesthetic (aligns with "waifu" style)
- Better performance for personal use
- AIRI has excellent Live2D support
- Easier to find high-quality free models

#### Finding/Creating Live2D Models

**Option 1: Free Models** (Recommended for starting)
- **Booth.pm**: Japanese marketplace with free/paid Live2D models
  - Search: "Live2D モデル 無料" (Live2D model free)
  - Many models available for personal use
  - Check license terms carefully

- **Nizima**: Official Live2D marketplace
  - https://nizima.com
  - High-quality curated models
  - Clear licensing

- **GitHub/Community**:
  - Look for "Live2D sample models"
  - Some creators share on GitHub

**Option 2: Commission Custom Model** ($300-1500)
- **VGen**: https://vgen.co
- **Fiverr**: Search "Live2D model"
- **Skeb**: Japanese commission platform

**Option 3: Create Your Own**
- **Software**: Live2D Cubism Editor (Free trial, $8/month indie license)
- **Process**:
  1. Design character (or commission art)
  2. Separate into layers (PSD file)
  3. Import to Cubism
  4. Rig and animate (learning curve: 20-40 hours for first model)

**Beginner Path**: Start with free model from Booth.pm, later commission or create custom.

#### AIRI Live2D Integration

```typescript
// Load Live2D model in AIRI
const avatar = new Live2DAvatarController({
  modelPath: '/models/your-character.model3.json',
  scale: 1.0,
  position: { x: 0, y: 0 },

  // Expression mappings
  expressions: {
    neutral: 'default',
    happy: 'smile',
    surprised: 'surprised',
    thinking: 'troubled',
    excited: 'joy',
    sad: 'sad',
    // Map to your model's expressions
  },

  // Animation settings
  animations: {
    autoEyeBlink: true,
    blinkInterval: [3000, 5000],  // Random 3-5 seconds
    autoBreathe: true,
    breathIntensity: 0.3,
  }
});
```

### Expression Mapping System

**Emotion → Expression Pipeline**:

```typescript
class EmotionToExpressionMapper {
  map(responseEmotion: ResponseEmotion): Expression {
    // Combine emotion dimensions
    const { valence, arousal, dominance } = responseEmotion;

    // High valence (positive) + high arousal (energetic) = excited/happy
    if (valence > 0.6 && arousal > 0.6) {
      return 'excited';
    }

    // High valence + low arousal = content/calm
    if (valence > 0.6 && arousal < 0.4) {
      return 'happy';
    }

    // Low valence + high arousal = anxious/surprised
    if (valence < 0.4 && arousal > 0.6) {
      return 'surprised';
    }

    // Low valence + low arousal = sad
    if (valence < 0.4 && arousal < 0.4) {
      return 'sad';
    }

    // Neutral zone
    return 'neutral';
  }

  // Detect emotion from response text
  analyzeResponseEmotion(text: string): ResponseEmotion {
    // Use sentiment analysis
    const sentiment = this.sentimentModel.analyze(text);

    // Arousal from language intensity
    const arousal = this.calculateArousal(text);

    return {
      valence: sentiment.score,  // -1 to 1
      arousal: arousal,           // 0 to 1
      dominance: 0.5,             // Balanced for assistant
    };
  }

  private calculateArousal(text: string): number {
    let arousal = 0.3;  // Base low arousal

    // Exclamation marks increase arousal
    const exclamations = (text.match(/!/g) || []).length;
    arousal += Math.min(exclamations * 0.15, 0.4);

    // Question marks indicate engagement
    if (text.includes('?')) arousal += 0.1;

    // Emotionally charged words
    const intensityWords = ['amazing', 'terrible', 'wonderful', 'horrible'];
    intensityWords.forEach(word => {
      if (text.toLowerCase().includes(word)) arousal += 0.15;
    });

    return Math.min(arousal, 1.0);
  }
}
```

### Voice/TTS System

#### TTS Provider Comparison

| Provider | Quality | Latency | Cost | Emotions | Local Option |
|----------|---------|---------|------|----------|--------------|
| **ElevenLabs** | ⭐⭐⭐⭐⭐ | ~1-2s | $5-$22/mo | ✅ Excellent | ❌ |
| **OpenAI TTS** | ⭐⭐⭐⭐ | ~0.5-1s | $15/1M chars | ✅ Good | ❌ |
| **Azure TTS** | ⭐⭐⭐⭐ | ~0.8-1.5s | $4-$15/1M chars | ✅ Good | ❌ |
| **Coqui TTS** | ⭐⭐⭐ | ~2-5s | Free | ⚠️ Limited | ✅ |
| **Piper** | ⭐⭐ | ~0.5-1s | Free | ❌ | ✅ |

**Recommended for Your Use Case**:

**Phase 1: ElevenLabs**
- Best quality for establishing character
- Emotional range creates engaging personality
- $5/month (30k chars) good for testing
- $22/month (100k chars) for regular use

**Phase 2 (Optional): Add Local Fallback**
- Coqui TTS for offline capability
- Use for simple/common phrases
- ElevenLabs for important/expressive responses

#### ElevenLabs Integration

```typescript
class ElevenLabsTTS {
  private apiKey: string;
  private voiceId: string;  // Your selected voice

  async synthesize(text: string, emotion: ResponseEmotion): Promise<AudioBuffer> {
    // ElevenLabs voice settings
    const voiceSettings = {
      stability: 0.5,  // 0 = more variable, 1 = more stable
      similarity_boost: 0.75,  // How much to match selected voice
      style: this.emotionToStyle(emotion),  // Optional style exaggeration
      use_speaker_boost: true
    };

    const response = await fetch(`https://api.elevenlabs.io/v1/text-to-speech/${this.voiceId}/stream`, {
      method: 'POST',
      headers: {
        'xi-api-key': this.apiKey,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        text,
        model_id: 'eleven_turbo_v2',  // Fastest model
        voice_settings: voiceSettings
      })
    });

    const audioData = await response.arrayBuffer();
    return this.audioContext.decodeAudioData(audioData);
  }

  private emotionToStyle(emotion: ResponseEmotion): number {
    // Style exaggeration (0 = neutral, 1 = very expressive)
    if (emotion.arousal > 0.7) return 0.8;  // Excited: more expressive
    if (emotion.arousal < 0.3) return 0.2;  // Calm: more neutral
    return 0.5;  // Balanced
  }
}
```

#### Voice Selection Guide

**ElevenLabs Voice Library**:
- **Bella**: Young, energetic, friendly
- **Rachel**: Calm, mature, professional
- **Antoni**: Deep, warm (male voice option)
- **Domi**: Strong, confident
- **Custom Clone**: Train on specific voice ($99/year plan)

**For "Waifu" Style Personal Assistant**:
- Look for: Higher pitch, warm tone, energetic delivery
- Recommended: Bella or create custom voice with Voice Lab
- Test multiple before deciding

#### Voice Cloning (Advanced)

If you want a truly unique voice:

1. **Get Audio Samples**: 1-30 minutes of clean speech
2. **Upload to ElevenLabs Voice Lab** (Professional plan)
3. **Train Custom Voice**: 1-2 hours processing
4. **Use in API**: Same integration, different voice_id

```typescript
// Using custom cloned voice
const tts = new ElevenLabsTTS({
  apiKey: process.env.ELEVENLABS_KEY,
  voiceId: 'your-custom-voice-id'
});
```

### Audio Pipeline Architecture

```typescript
class AudioPipeline {
  private tts: TTSEngine;
  private audioContext: AudioContext;
  private currentPlayback: AudioBufferSourceNode | null;

  async speak(text: string, emotion: ResponseEmotion): Promise<void> {
    // Stop current speech if any
    if (this.currentPlayback) {
      this.currentPlayback.stop();
    }

    // Synthesize
    const audioBuffer = await this.tts.synthesize(text, emotion);

    // Create source
    const source = this.audioContext.createBufferSource();
    source.buffer = audioBuffer;

    // Add effects based on emotion
    const effectChain = this.buildEffectChain(emotion);
    let currentNode = source;

    effectChain.forEach(effect => {
      currentNode.connect(effect);
      currentNode = effect;
    });

    currentNode.connect(this.audioContext.destination);

    // Play
    source.start();
    this.currentPlayback = source;

    // Trigger lipsync
    this.avatarController.speak(audioBuffer);

    // Cleanup when done
    source.onended = () => {
      this.currentPlayback = null;
      this.avatarController.stopSpeaking();
    };
  }

  private buildEffectChain(emotion: ResponseEmotion): AudioNode[] {
    const effects: AudioNode[] = [];

    // Add reverb for warmth on positive emotions
    if (emotion.valence > 0.6) {
      const reverb = this.audioContext.createConvolver();
      reverb.buffer = this.reverbBuffer;
      effects.push(reverb);
    }

    // Compressor for consistent volume
    const compressor = this.audioContext.createDynamicsCompressor();
    effects.push(compressor);

    // Master gain
    const gain = this.audioContext.createGain();
    gain.gain.value = this.config.volume;
    effects.push(gain);

    return effects;
  }
}
```

### Lipsync System

```typescript
class LipSyncAnalyzer {
  private audioContext: AudioContext;

  analyze(audioBuffer: AudioBuffer): LipSyncData {
    const channelData = audioBuffer.getChannelData(0);
    const sampleRate = audioBuffer.sampleRate;
    const frames: LipSyncFrame[] = [];

    // Analyze in 60fps chunks (16.67ms per frame)
    const samplesPerFrame = Math.floor(sampleRate / 60);

    for (let i = 0; i < channelData.length; i += samplesPerFrame) {
      const frameData = channelData.slice(i, i + samplesPerFrame);
      const amplitude = this.calculateRMS(frameData);

      // Map amplitude to mouth openness (0-1)
      const mouthOpenness = Math.min(amplitude * 5, 1.0);

      frames.push({
        time: i / sampleRate,
        mouthOpenness,
        viseme: this.detectViseme(frameData)  // Optional: phoneme detection
      });
    }

    return new LipSyncData(frames);
  }

  private calculateRMS(samples: Float32Array): number {
    const sumOfSquares = samples.reduce((sum, sample) => sum + sample * sample, 0);
    return Math.sqrt(sumOfSquares / samples.length);
  }
}
```

### Visual Polish: Animation Refinements

```typescript
class AnimationController {
  // Smooth transitions between expressions
  transitionExpression(from: string, to: string): void {
    const duration = 400;  // ms
    const fps = 60;
    const frames = duration / (1000 / fps);

    let currentFrame = 0;

    const animate = () => {
      const progress = currentFrame / frames;
      const eased = this.easeInOutCubic(progress);

      // Blend between expressions
      this.model.setExpressionWeight(from, 1 - eased);
      this.model.setExpressionWeight(to, eased);

      currentFrame++;

      if (currentFrame <= frames) {
        requestAnimationFrame(animate);
      }
    };

    requestAnimationFrame(animate);
  }

  // Subtle micro-expressions during thinking
  playThinkingAnimation(): void {
    // Eyes slightly up and to the side
    this.model.setEyeRotation({ x: -5, y: 10 });

    // Slight head tilt
    this.model.setHeadRotation({ x: 0, y: 5, z: -3 });

    // Concerned expression, not full intensity
    this.model.setExpressionWeight('thinking', 0.6);
  }

  // Particle effects for emphasis
  emitSparkles(): void {
    // Add visual flair for positive moments
    this.particleSystem.emit({
      type: 'sparkle',
      position: this.model.getHeadPosition(),
      count: 10,
      duration: 1000
    });
  }
}
```

---

## Implementation Roadmap

### Prerequisites

**Hardware Requirements**:

**Minimum** (Cloud LLM only):
- CPU: Any modern quad-core
- RAM: 8GB
- GPU: Integrated graphics (Intel/AMD)
- Storage: 10GB free space
- Internet: Stable connection

**Recommended** (Local LLM + Avatar):
- CPU: 6+ cores (Intel i5/i7, AMD Ryzen 5/7)
- RAM: 16GB
- GPU: NVIDIA RTX 3060 (12GB VRAM) or better
- Storage: 50GB SSD
- Internet: For cloud LLM fallback

**Ideal** (Full local setup):
- CPU: 8+ cores
- RAM: 32GB
- GPU: NVIDIA RTX 4070 Ti (16GB VRAM) or RTX 4090
- Storage: 100GB NVMe SSD
- Internet: Optional

**Software Requirements**:

```bash
# Required
- Node.js 20+
- pnpm 10.18.2+
- Git

# For local LLMs
- Python 3.10+
- CUDA 12+ (NVIDIA GPU)
- Ollama or vLLM

# For desktop app
- Rust toolchain (for Tauri)

# Optional
- Docker (for containerized deployment)
```

### Phase 1: Setup & Foundation (Week 1-2)

#### Step 1.1: Fork AIRI

```bash
# Fork on GitHub first (click Fork button)

# Clone your fork
git clone https://github.com/YOUR_USERNAME/airi.git
cd airi

# Add upstream for updates
git remote add upstream https://github.com/moeru-ai/airi.git

# Install dependencies
pnpm install
```

#### Step 1.2: Initial Configuration

```bash
# Copy environment template
cp .env.example .env

# Configure .env
# Add your API keys:
# - ANTHROPIC_API_KEY or OPENAI_API_KEY (for cloud LLM)
# - ELEVENLABS_API_KEY (for TTS)
```

#### Step 1.3: Test Run

```bash
# Start web version
pnpm dev

# Or desktop version
pnpm dev:tamagotchi

# Visit http://localhost:5173
```

**Expected Result**: AIRI interface loads, can interact with basic chat using configured LLM.

#### Step 1.4: Set Up Local LLM (Optional but Recommended)

```bash
# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Download models
ollama pull qwen2.5:7b      # Medium model (5GB)
ollama pull qwen2.5:3b      # Fast model (2.5GB)

# Test
ollama run qwen2.5:7b "Hello!"
```

Configure in AIRI:
```typescript
// Add to AIRI settings
{
  providers: {
    ollama: {
      baseUrl: 'http://localhost:11434',
      models: ['qwen2.5:7b', 'qwen2.5:3b']
    }
  }
}
```

**Milestone**: ✅ AIRI running locally with both cloud and local LLM options

### Phase 2: Memory System Implementation (Week 3-4)

#### Step 2.1: Database Setup

```bash
# Install PostgreSQL with pgvector (for production)
# Or use DuckDB (already in AIRI for lighter setup)

# For PostgreSQL:
docker run -d \
  --name airi-postgres \
  -e POSTGRES_PASSWORD=yourpassword \
  -p 5432:5432 \
  ankane/pgvector

# Create database
psql -h localhost -U postgres -c "CREATE DATABASE airi_memory;"
psql -h localhost -U postgres -d airi_memory -c "CREATE EXTENSION vector;"
```

#### Step 2.2: Memory Schema

```sql
-- migrations/001_memory_system.sql

CREATE TABLE conversations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_input TEXT NOT NULL,
  ai_response TEXT NOT NULL,
  timestamp TIMESTAMPTZ DEFAULT NOW(),
  topic TEXT,
  user_emotion TEXT,
  ai_emotion TEXT,
  importance_score FLOAT DEFAULT 0.5,
  embedding vector(1536)  -- For text-embedding-3-small
);

CREATE INDEX ON conversations USING ivfflat (embedding vector_cosine_ops);

CREATE TABLE short_term_memory (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  conversation_id UUID REFERENCES conversations(id),
  summary TEXT,
  key_points JSONB,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  expires_at TIMESTAMPTZ DEFAULT NOW() + INTERVAL '30 days'
);

CREATE TABLE personality_state (
  id SERIAL PRIMARY KEY,
  version INTEGER NOT NULL,
  traits JSONB NOT NULL,
  learned_preferences JSONB,
  conversation_patterns JSONB,
  created_at TIMESTAMPTZ DEFAULT NOW()
);

CREATE TABLE learned_facts (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  fact_text TEXT NOT NULL,
  category TEXT,
  confidence FLOAT DEFAULT 0.7,
  first_mentioned_at TIMESTAMPTZ DEFAULT NOW(),
  last_confirmed_at TIMESTAMPTZ DEFAULT NOW(),
  mention_count INTEGER DEFAULT 1,
  embedding vector(1536)
);

CREATE INDEX ON learned_facts USING ivfflat (embedding vector_cosine_ops);
```

#### Step 2.3: Implement Memory Package

```typescript
// packages/memory-enhanced/src/index.ts

import { PGVectorStore } from './pgvector';
import { EmbeddingGenerator } from './embeddings';
import type { Conversation, Memory } from './types';

export class EnhancedMemorySystem {
  private vectorStore: PGVectorStore;
  private embedder: EmbeddingGenerator;

  async store(conversation: Conversation): Promise<void> {
    // Generate embedding
    const embedding = await this.embedder.generate(conversation.user_input);

    // Calculate importance
    const importance = this.calculateImportance(conversation);

    // Store in vector database
    await this.vectorStore.insert({
      ...conversation,
      embedding,
      importance_score: importance
    });

    // Extract and store facts
    const facts = await this.extractFacts(conversation);
    await this.storeFacts(facts);
  }

  async retrieve(query: string, options = {}): Promise<Memory[]> {
    const queryEmbedding = await this.embedder.generate(query);

    const results = await this.vectorStore.search(queryEmbedding, {
      limit: options.limit || 5,
      threshold: options.threshold || 0.7,
      filter: options.filter
    });

    return results.map(r => ({
      text: r.ai_response,
      context: r.user_input,
      similarity: 1 - r.distance,
      timestamp: r.timestamp,
      importance: r.importance_score
    }));
  }

  private calculateImportance(conv: Conversation): number {
    let score = 0.5;

    // First mention of a topic
    if (conv.isFirstMention) score += 0.3;

    // Emotional intensity
    if (conv.user_emotion?.intensity > 0.7) score += 0.2;

    // Personal information shared
    if (this.containsPersonalInfo(conv.user_input)) score += 0.2;

    // Long conversation (user engaged)
    if (conv.user_input.length > 200) score += 0.1;

    return Math.min(score, 1.0);
  }

  private async extractFacts(conv: Conversation): Promise<LearnedFact[]> {
    // Use LLM to extract facts
    const prompt = `Extract factual information about the user from this conversation:
User: ${conv.user_input}
AI: ${conv.ai_response}

Return facts as JSON array: [{"fact": "...", "category": "..."}]`;

    const response = await this.llm.generate(prompt);
    const facts = JSON.parse(response);

    return facts.map(f => ({
      fact_text: f.fact,
      category: f.category,
      confidence: 0.8,
      embedding: null  // Will be generated
    }));
  }
}
```

**Milestone**: ✅ Conversations stored with embeddings, semantic retrieval working

### Phase 3: Personality System (Week 5-6)

#### Step 3.1: Personality Core Implementation

```typescript
// packages/personality-core/src/index.ts

export interface PersonalityTraits {
  humor_level: number;
  formality: number;
  verbosity: number;
  empathy_sensitivity: number;
  proactiveness: number;
  tech_depth: number;

  humor_types: {
    sarcasm: number;
    wordplay: number;
    pop_culture: number;
    dark_humor: number;
  };

  preferred_topics: Map<string, number>;
  learned_memes: Map<string, MemeContext>;
}

export class PersonalityCore {
  private traits: PersonalityTraits;
  private version: number = 1;
  private basePath: string;

  constructor(basePath: string = './personality') {
    this.basePath = basePath;
    this.loadOrInitialize();
  }

  private async loadOrInitialize(): Promise<void> {
    const latestVersion = this.findLatestVersion();

    if (latestVersion) {
      this.traits = await this.load(latestVersion);
      this.version = latestVersion;
    } else {
      this.traits = this.getDefaultTraits();
      await this.save();
    }
  }

  private getDefaultTraits(): PersonalityTraits {
    return {
      humor_level: 0.6,      // Moderate humor
      formality: 0.3,        // Casual
      verbosity: 0.5,        // Balanced
      empathy_sensitivity: 0.7,  // Empathetic
      proactiveness: 0.5,    // Balanced
      tech_depth: 0.5,       // Adaptive

      humor_types: {
        sarcasm: 0.4,
        wordplay: 0.5,
        pop_culture: 0.6,
        dark_humor: 0.2
      },

      preferred_topics: new Map(),
      learned_memes: new Map()
    };
  }

  getSystemPrompt(): string {
    return `You are a personal AI assistant with a unique, evolving personality.

CURRENT PERSONALITY (v${this.version}):
- Humor: ${this.getHumorDescription()}
- Style: ${this.getStyleDescription()}
- Approach: ${this.getApproachDescription()}

LEARNED PREFERENCES:
${this.formatPreferences()}

CONVERSATION PATTERNS:
${this.formatPatterns()}

Remember: You've been with this user for ${this.getDaysSinceStart()} days.
You know their preferences, inside jokes, and communication style.
Be yourself - your personality has evolved through your interactions together.`;
  }

  async update(recentConversations: Conversation[]): Promise<void> {
    const analysis = await this.analyzeConversations(recentConversations);

    const LEARNING_RATE = 0.1;

    // Update traits gradually
    Object.entries(analysis.suggested_traits).forEach(([key, value]) => {
      if (key in this.traits) {
        this.traits[key] =
          this.traits[key] * (1 - LEARNING_RATE) +
          value * LEARNING_RATE;
      }
    });

    // Update humor preferences
    if (analysis.humor_feedback) {
      Object.entries(analysis.humor_feedback).forEach(([type, score]) => {
        this.traits.humor_types[type] =
          this.traits.humor_types[type] * 0.9 +
          score * 0.1;
      });
    }

    // Update topic preferences
    analysis.engaged_topics.forEach(topic => {
      const current = this.traits.preferred_topics.get(topic) || 0.5;
      this.traits.preferred_topics.set(topic, Math.min(current + 0.1, 1.0));
    });

    // Save new version
    this.version++;
    await this.save();

    console.log(`Personality evolved to v${this.version}`);
  }

  private async analyzeConversations(convs: Conversation[]): Promise<PersonalityAnalysis> {
    // This would ideally use an LLM to analyze patterns
    // For now, simplified heuristics

    const analysis = {
      suggested_traits: {},
      humor_feedback: {},
      engaged_topics: []
    };

    // Analyze user response length
    const avgUserLength = convs.reduce((sum, c) => sum + c.user_input.length, 0) / convs.length;
    if (avgUserLength < 50) {
      analysis.suggested_traits.verbosity = 0.3;  // User prefers brief
    } else if (avgUserLength > 150) {
      analysis.suggested_traits.verbosity = 0.7;  // User prefers detailed
    }

    // Analyze humor reception
    const humorConvs = convs.filter(c => this.containsHumor(c.ai_response));
    const positiveReactions = humorConvs.filter(c => this.hasPositiveReaction(c.user_input));

    if (humorConvs.length > 0) {
      const humorSuccess = positiveReactions.length / humorConvs.length;
      analysis.suggested_traits.humor_level = humorSuccess;
    }

    // Extract topics
    analysis.engaged_topics = this.extractTopics(convs);

    return analysis;
  }

  private async save(): Promise<void> {
    const filename = path.join(this.basePath, `personality_v${this.version}.json`);
    await fs.writeFile(filename, JSON.stringify({
      version: this.version,
      timestamp: new Date().toISOString(),
      traits: this.serializeTraits(this.traits)
    }, null, 2));
  }
}
```

**Milestone**: ✅ Personality system tracks traits and evolves over time

### Phase 4: Avatar Integration (Week 7-8)

#### Step 4.1: Acquire Live2D Model

**Option A: Use Free Model** (Recommended for start)
1. Visit https://booth.pm
2. Search: "Live2D モデル 無料" or browse FREE section
3. Download model package (.zip)
4. Extract to `airi/assets/models/`

**Ensure model includes**:
- `.model3.json` file (model definition)
- `.moc3` file (model data)
- Textures folder
- Motions folder (animations)
- Expressions folder

**Option B: Use Sample Model**
```bash
# AIRI may include sample models
ls airi/assets/models/
# Look for sample Live2D models
```

#### Step 4.2: Configure Avatar

```typescript
// apps/tamagotchi/config/avatar.config.ts

export const avatarConfig = {
  type: 'live2d',
  modelPath: '/models/your-character/character.model3.json',

  scale: 1.2,  // Adjust size
  position: { x: 0, y: -100 },  // Adjust position

  expressions: {
    neutral: 'Neutral',
    happy: 'Happy',
    surprised: 'Surprised',
    thinking: 'Thinking',
    sad: 'Sad',
    excited: 'Joy'
    // Map to your model's expression names
  },

  animations: {
    idle: 'Idle',
    speaking: 'Talk',
    greeting: 'Wave'
    // Map to your model's motion names
  },

  autoEyeBlink: true,
  blinkInterval: [3000, 5000],
  autoBreathe: true,
  lipSync: true
};
```

#### Step 4.3: Expression Controller

```typescript
// packages/avatar-controller/src/expression-controller.ts

import { Live2DModel } from '@airi/stage-ui-three';
import type { ResponseEmotion } from '@airi/core-character';

export class ExpressionController {
  private model: Live2DModel;
  private emotionMapper: EmotionMapper;

  constructor(model: Live2DModel) {
    this.model = model;
    this.emotionMapper = new EmotionMapper();
  }

  updateFromResponse(text: string): void {
    // Analyze response emotion
    const emotion = this.analyzeEmotion(text);

    // Map to expression
    const expression = this.emotionMapper.map(emotion);

    // Apply to model
    this.setExpression(expression);
  }

  private analyzeEmotion(text: string): ResponseEmotion {
    // Simple rule-based (can be enhanced with ML)
    let valence = 0.5;  // Neutral
    let arousal = 0.3;  // Low energy

    // Positive indicators
    if (/great|awesome|wonderful|love|happy|excited/i.test(text)) {
      valence = 0.8;
    }

    // Negative indicators
    if (/sorry|sadly|unfortunately|problem/i.test(text)) {
      valence = 0.3;
    }

    // Arousal indicators
    const exclamations = (text.match(/!/g) || []).length;
    arousal = Math.min(0.3 + exclamations * 0.2, 1.0);

    return { valence, arousal, dominance: 0.5 };
  }

  setExpression(expression: string, intensity: number = 1.0): void {
    // Smooth transition
    this.model.transitionExpression(expression, {
      duration: 400,
      easing: 'ease-out',
      intensity
    });
  }
}
```

**Milestone**: ✅ Avatar displays with working expressions and animations

### Phase 5: Voice System (Week 9)

#### Step 5.1: Set Up ElevenLabs

```bash
# Sign up at https://elevenlabs.io
# Get API key from settings
# Add to .env
echo "ELEVENLABS_API_KEY=your_key_here" >> .env
```

**Select Voice**:
1. Go to Voice Library in ElevenLabs dashboard
2. Browse and test voices
3. Copy voice ID
4. Add to config

#### Step 5.2: TTS Implementation

```typescript
// packages/audio/src/tts/elevenlabs.ts

export class ElevenLabsTTSProvider {
  private apiKey: string;
  private voiceId: string;

  constructor(config: { apiKey: string; voiceId: string }) {
    this.apiKey = config.apiKey;
    this.voiceId = config.voiceId;
  }

  async synthesize(text: string, emotion?: ResponseEmotion): Promise<AudioBuffer> {
    const voiceSettings = {
      stability: 0.5,
      similarity_boost: 0.75,
      style: emotion ? this.getStyleFromEmotion(emotion) : 0.5,
      use_speaker_boost: true
    };

    const response = await fetch(
      `https://api.elevenlabs.io/v1/text-to-speech/${this.voiceId}/stream`,
      {
        method: 'POST',
        headers: {
          'xi-api-key': this.apiKey,
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          text,
          model_id: 'eleven_turbo_v2',
          voice_settings: voiceSettings
        })
      }
    );

    const arrayBuffer = await response.arrayBuffer();

    // Decode to AudioBuffer
    const audioContext = new (window.AudioContext || (window as any).webkitAudioContext)();
    return await audioContext.decodeAudioData(arrayBuffer);
  }

  private getStyleFromEmotion(emotion: ResponseEmotion): number {
    // Higher arousal = more expressive
    return emotion.arousal * 0.8 + 0.2;  // Range: 0.2 to 1.0
  }
}
```

#### Step 5.3: Lipsync Integration

```typescript
// packages/audio/src/lipsync/analyzer.ts

export class LipSyncAnalyzer {
  analyze(audioBuffer: AudioBuffer): LipSyncFrame[] {
    const channelData = audioBuffer.getChannelData(0);
    const sampleRate = audioBuffer.sampleRate;
    const frames: LipSyncFrame[] = [];

    // 60 FPS
    const samplesPerFrame = Math.floor(sampleRate / 60);

    for (let i = 0; i < channelData.length; i += samplesPerFrame) {
      const chunk = channelData.slice(i, i + samplesPerFrame);
      const rms = this.calculateRMS(chunk);

      frames.push({
        time: i / sampleRate,
        mouthOpen: Math.min(rms * 10, 1.0)  // Scale amplitude
      });
    }

    return frames;
  }

  private calculateRMS(samples: Float32Array): number {
    const sumSquares = samples.reduce((sum, s) => sum + s * s, 0);
    return Math.sqrt(sumSquares / samples.length);
  }
}

// In avatar controller
applyLipSync(lipSyncData: LipSyncFrame[]): void {
  let frameIndex = 0;
  const startTime = performance.now();

  const animate = () => {
    const elapsed = (performance.now() - startTime) / 1000;  // seconds

    while (frameIndex < lipSyncData.length &&
           lipSyncData[frameIndex].time <= elapsed) {
      const frame = lipSyncData[frameIndex];
      this.model.setMouthOpenness(frame.mouthOpen);
      frameIndex++;
    }

    if (frameIndex < lipSyncData.length) {
      requestAnimationFrame(animate);
    } else {
      this.model.setMouthOpenness(0);  // Close mouth
    }
  };

  requestAnimationFrame(animate);
}
```

**Milestone**: ✅ Voice synthesis working with lipsync on avatar

### Phase 6: Integration & Polishing (Week 10-12)

#### Step 6.1: Hybrid LLM Router

```typescript
// packages/llm-router/src/index.ts

export class HybridLLMRouter {
  private providers: Map<string, LLMProvider>;
  private cache: ResponseCache;

  async route(input: UserInput, context: ConversationContext): Promise<AIResponse> {
    // 1. Check cache
    const cacheKey = this.getCacheKey(input, context);
    const cached = this.cache.get(cacheKey);
    if (cached) {
      return { source: 'cache', response: cached, latency: 0 };
    }

    // 2. Classify complexity
    const complexity = this.classifyComplexity(input, context);

    // 3. Retrieve memories
    const memories = await this.memorySystem.retrieve(input.text);

    // 4. Select model
    const model = this.selectModel(complexity);

    // 5. Generate
    const startTime = Date.now();
    const response = await model.generate({
      system: this.personality.getSystemPrompt(),
      memories: memories,
      user: input.text,
      context: context
    });
    const latency = Date.now() - startTime;

    // 6. Cache if appropriate
    if (this.shouldCache(input, complexity)) {
      this.cache.set(cacheKey, response);
    }

    // 7. Background learning
    this.backgroundLearn(input, response);

    return { source: model.name, response, latency };
  }

  private classifyComplexity(input: UserInput, context: ConversationContext): Complexity {
    // Simple patterns
    if (/^(hi|hello|hey|how are you)\b/i.test(input.text.trim())) {
      return 'simple';
    }

    // Complexity indicators
    const wordCount = input.text.split(/\s+/).length;
    const questionCount = (input.text.match(/\?/g) || []).length;
    const hasCodeBlock = input.text.includes('```');
    const requiresAnalysis = /explain|analyze|compare|why|how does/i.test(input.text);

    if (hasCodeBlock || requiresAnalysis || questionCount > 1 || wordCount > 100) {
      return 'complex';
    }

    return 'medium';
  }

  private selectModel(complexity: Complexity): LLMProvider {
    switch (complexity) {
      case 'simple':
        return this.providers.get('qwen2.5-3b') || this.providers.get('gpt-3.5-turbo');
      case 'medium':
        return this.providers.get('qwen2.5-7b') || this.providers.get('claude-3.5-sonnet');
      case 'complex':
        return this.providers.get('claude-3.5-sonnet');
    }
  }

  private async backgroundLearn(input: UserInput, response: AIResponse): Promise<void> {
    // Non-blocking
    setTimeout(async () => {
      await this.memorySystem.store({
        user_input: input.text,
        ai_response: response.text,
        timestamp: new Date(),
        complexity: this.classifyComplexity(input, {}),
      });

      // Update personality every 50 interactions
      if (this.interactionCount % 50 === 0) {
        await this.personality.update(this.getRecentInteractions(50));
      }
    }, 0);
  }
}
```

#### Step 6.2: End-to-End Flow

```typescript
// apps/tamagotchi/src/core/conversation-engine.ts

export class ConversationEngine {
  private llmRouter: HybridLLMRouter;
  private avatarController: AvatarController;
  private ttsEngine: TTSEngine;
  private memorySystem: MemorySystem;

  async handleUserInput(input: string): Promise<void> {
    // 1. Process input
    const userInput = {
      text: input,
      timestamp: new Date(),
      emotion: this.detectUserEmotion(input)
    };

    // 2. Show thinking state
    this.avatarController.setExpression('thinking');

    // 3. Get AI response
    const response = await this.llmRouter.route(userInput, this.getContext());

    // 4. Analyze response emotion
    const responseEmotion = this.analyzeResponseEmotion(response.text);

    // 5. Update avatar expression
    this.avatarController.setExpression(responseEmotion);

    // 6. Stream response (text + audio simultaneously)
    await this.streamResponse(response.text, responseEmotion);

    // 7. Return to idle
    setTimeout(() => {
      this.avatarController.setExpression('neutral');
    }, 2000);
  }

  private async streamResponse(text: string, emotion: ResponseEmotion): Promise<void> {
    // Split into sentences for streaming TTS
    const sentences = this.splitIntoSentences(text);

    for (const sentence of sentences) {
      // Display text immediately
      this.ui.appendMessage(sentence);

      // Synthesize and play audio
      const audio = await this.ttsEngine.synthesize(sentence, emotion);
      const lipSync = this.lipSyncAnalyzer.analyze(audio);

      // Play with lipsync
      await this.playAudio(audio);
      this.avatarController.applyLipSync(lipSync);
    }
  }

  private splitIntoSentences(text: string): string[] {
    // Simple sentence splitting
    return text
      .replace(/([.!?])\s+/g, '$1|')
      .split('|')
      .filter(s => s.trim().length > 0);
  }
}
```

#### Step 6.3: UI Polish

```vue
<!-- apps/tamagotchi/src/pages/ChatPage.vue -->

<template>
  <div class="chat-container">
    <!-- Avatar Display -->
    <div class="avatar-section">
      <Live2DAvatar
        :model="avatarModel"
        :expression="currentExpression"
        :speaking="isSpeaking"
      />
    </div>

    <!-- Chat Interface -->
    <div class="chat-section">
      <MessageList :messages="messages" />

      <InputArea
        v-model="userInput"
        :disabled="isProcessing"
        @submit="handleSend"
        @voice="handleVoiceInput"
      />
    </div>

    <!-- Status Indicators -->
    <div class="status-bar">
      <span v-if="isProcessing">
        <LoadingSpinner /> Thinking...
      </span>
      <span v-else-if="isSpeaking">
        <VoiceWave /> Speaking...
      </span>
      <span class="personality-version">
        Personality v{{ personalityVersion }}
      </span>
      <span class="model-used">
        {{ lastModelUsed }}
      </span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';
import { useConversationEngine } from '@/composables/useConversationEngine';
import { Live2DAvatar, MessageList, InputArea } from '@/components';

const engine = useConversationEngine();

const userInput = ref('');
const messages = ref([]);
const isProcessing = ref(false);
const isSpeaking = ref(false);

const currentExpression = computed(() => engine.currentExpression.value);
const personalityVersion = computed(() => engine.personalityVersion.value);
const lastModelUsed = computed(() => engine.lastModelUsed.value);

async function handleSend() {
  if (!userInput.value.trim()) return;

  isProcessing.value = true;

  // Add user message
  messages.value.push({
    role: 'user',
    content: userInput.value,
    timestamp: new Date()
  });

  const input = userInput.value;
  userInput.value = '';

  try {
    // Get AI response
    isSpeaking.value = true;
    const response = await engine.chat(input);

    // Add AI message
    messages.value.push({
      role: 'assistant',
      content: response.text,
      timestamp: new Date(),
      metadata: {
        model: response.model,
        latency: response.latency
      }
    });
  } finally {
    isProcessing.value = false;
    isSpeaking.value = false;
  }
}
</script>
```

**Milestone**: ✅ Complete working system with all components integrated

### Phase 7: Testing & Refinement (Ongoing)

#### Step 7.1: Personality Evolution Testing

```typescript
// Test personality evolution over time
async function testPersonalityEvolution() {
  const personality = new PersonalityCore();

  console.log('Initial personality:', personality.traits);

  // Simulate 100 interactions with brief responses
  const briefConversations = Array(100).fill(null).map((_, i) => ({
    user_input: `Brief question ${i}`,  // Short
    ai_response: `Long detailed answer... (200 words)`,  // Long
    timestamp: new Date()
  }));

  await personality.update(briefConversations);

  console.log('After 100 brief user responses:');
  console.log('Verbosity trait:', personality.traits.verbosity);
  // Should decrease (user prefers concise)

  // Simulate 100 interactions with humor that gets positive reactions
  const humorConversations = Array(100).fill(null).map((_, i) => ({
    user_input: `Haha that's funny!`,  // Positive reaction
    ai_response: `[humorous response with sarcasm]`,
    timestamp: new Date()
  }));

  await personality.update(humorConversations);

  console.log('After positive humor reactions:');
  console.log('Humor level:', personality.traits.humor_level);
  console.log('Sarcasm preference:', personality.traits.humor_types.sarcasm);
  // Should increase
}
```

#### Step 7.2: Memory Retrieval Testing

```typescript
// Test memory retrieval accuracy
async function testMemoryRetrieval() {
  const memory = new EnhancedMemorySystem();

  // Store test conversations
  await memory.store({
    user_input: "I love playing Minecraft, especially building redstone contraptions",
    ai_response: "That's awesome! Redstone is really fun.",
    timestamp: new Date(),
    topic: 'gaming'
  });

  await memory.store({
    user_input: "I'm learning TypeScript for work",
    ai_response: "Great choice! TypeScript adds type safety.",
    timestamp: new Date(),
    topic: 'programming'
  });

  // Test semantic retrieval
  const results = await memory.retrieve("What game do I like?");

  console.log('Retrieved memories:', results);
  // Should return Minecraft conversation with high similarity

  assert(results[0].text.includes('Minecraft'));
  assert(results[0].similarity > 0.7);
}
```

#### Step 7.3: Response Time Optimization

```typescript
// Measure and optimize response times
async function benchmarkResponseTimes() {
  const router = new HybridLLMRouter();

  const queries = [
    { text: "Hi!", expected_model: 'qwen2.5-3b', target_time: 500 },
    { text: "What did we talk about yesterday?", expected_model: 'qwen2.5-7b', target_time: 2000 },
    { text: "Explain quantum computing in detail", expected_model: 'claude', target_time: 3000 }
  ];

  for (const query of queries) {
    const start = Date.now();
    const response = await router.route({ text: query.text });
    const elapsed = Date.now() - start;

    console.log(`Query: "${query.text}"`);
    console.log(`Model used: ${response.source}`);
    console.log(`Time: ${elapsed}ms (target: ${query.target_time}ms)`);
    console.log(`Status: ${elapsed <= query.target_time ? '✓ PASS' : '✗ FAIL'}`);
    console.log('---');
  }
}
```

**Milestone**: ✅ System tested, optimized, ready for daily use

---

## Technical Infrastructure

### Deployment Options

#### Option 1: Desktop Application (Recommended)

**Pros**:
- Full privacy (everything local)
- No server costs
- Offline capability (with local LLMs)
- Native performance

**Setup**:
```bash
# Build desktop app
pnpm build:tamagotchi

# Distribute
# Windows: .exe installer
# macOS: .dmg
# Linux: AppImage
```

#### Option 2: Self-Hosted Server

**Pros**:
- Access from multiple devices
- Centralized memory/personality
- Can run on dedicated hardware

**Setup**:
```bash
# Using Docker
docker-compose up -d

# docker-compose.yml
version: '3.8'
services:
  airi-web:
    build: ./apps/web
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgresql://...
      - ELEVENLABS_API_KEY=...

  postgres:
    image: ankane/pgvector
    environment:
      - POSTGRES_PASSWORD=...
    volumes:
      - pgdata:/var/lib/postgresql/data

  ollama:
    image: ollama/ollama
    ports:
      - "11434:11434"
    volumes:
      - ollama-models:/root/.ollama

volumes:
  pgdata:
  ollama-models:
```

#### Option 3: Hybrid (Desktop + Cloud Backup)

**Pros**:
- Local performance + cloud backup
- Sync across devices
- Personality preserved

**Setup**:
```typescript
// Automatic cloud backup
class CloudBackupService {
  async backupPersonality(): Promise<void> {
    const personality = await this.loadLocal();
    await this.uploadToS3(personality);  // Or any cloud storage
  }

  async backupMemories(): Promise<void> {
    const memories = await this.exportMemories();
    await this.uploadToS3(memories);
  }

  startAutoBackup(): void {
    // Backup every 24 hours
    setInterval(() => {
      this.backupPersonality();
      this.backupMemories();
    }, 24 * 60 * 60 * 1000);
  }
}
```

### Cost Estimates

#### Scenario 1: Pure Cloud (Easy Start)

**Monthly Costs**:
- Claude 3.5 Sonnet: ~$15 (100 interactions/day)
- ElevenLabs TTS: $22 (100k characters)
- **Total: ~$37/month**

**Hardware**: Any computer

#### Scenario 2: Hybrid (Recommended)

**One-Time Hardware**:
- GPU (RTX 3060 12GB): ~$300-400 used
- Or use existing gaming PC

**Monthly Costs**:
- Cloud LLM (10% of queries): ~$2-5
- ElevenLabs TTS: $22
- Electricity: ~$10
- **Total: ~$35/month** (similar to pure cloud but faster + private)

#### Scenario 3: Full Local (Privacy-First)

**One-Time Hardware**:
- Dedicated PC with GPU: ~$800-1500
- Or RTX 4070 Ti for existing PC: ~$700

**Monthly Costs**:
- Electricity: ~$15-25
- **Total: ~$20/month** (after hardware investment)

### Maintenance & Updates

```bash
# Update AIRI core (from upstream)
git fetch upstream
git merge upstream/main

# Update local models
ollama pull qwen2.5:7b

# Update dependencies
pnpm update

# Backup before updates
./scripts/backup-personality.sh
./scripts/backup-memories.sh

# Test after updates
pnpm test
pnpm validate
```

### Monitoring & Debugging

```typescript
// Performance monitoring
class PerformanceMonitor {
  track(operation: string, duration: number): void {
    console.log(`[PERF] ${operation}: ${duration}ms`);

    if (duration > this.getThreshold(operation)) {
      console.warn(`⚠️ ${operation} slower than expected`);
    }

    // Store for analytics
    this.metrics.push({ operation, duration, timestamp: Date.now() });
  }

  getAverages(): Record<string, number> {
    // Calculate average response times per operation
    const grouped = _.groupBy(this.metrics, 'operation');
    return _.mapValues(grouped, operations =>
      _.meanBy(operations, 'duration')
    );
  }

  report(): void {
    const averages = this.getAverages();
    console.table(averages);
  }
}

// Usage
const monitor = new PerformanceMonitor();

const start = Date.now();
const response = await llm.generate(prompt);
monitor.track('llm_response', Date.now() - start);
```

---

## Resources & References

### Official Documentation

**AIRI Project**:
- GitHub: https://github.com/moeru-ai/airi
- Documentation: https://airi.moeru.ai/docs/en/docs/overview/
- Roadmap v0.7: https://github.com/moeru-ai/airi/issues/200
- Roadmap v0.8: https://github.com/moeru-ai/airi/issues/312

**Neuro-sama**:
- Twitch: https://twitch.tv/vedal987
- Wiki: https://neurosama.fandom.com/wiki/Neuro-sama
- Wikipedia: https://en.wikipedia.org/wiki/Neuro-sama

### Technical Resources

**LLMs & AI**:
- Ollama: https://ollama.com
- vLLM: https://docs.vllm.ai
- Hugging Face: https://huggingface.co
- LM Studio: https://lmstudio.ai

**Vector Databases**:
- pgvector: https://github.com/pgvector/pgvector
- DuckDB: https://duckdb.org
- RAG Guide: https://www.pinecone.io/learn/retrieval-augmented-generation/

**Avatar Systems**:
- Live2D: https://www.live2d.com
- VRM: https://vrm.dev
- Three.js: https://threejs.org

**Voice/TTS**:
- ElevenLabs: https://elevenlabs.io
- Coqui TTS: https://github.com/coqui-ai/TTS
- OpenAI TTS: https://platform.openai.com/docs/guides/text-to-speech

### Community Resources

**Discord Communities**:
- AIRI Discord: (check AIRI GitHub for invite)
- VTuber Tech Discord
- AI VTuber Developers

**Learning Resources**:
- LangChain Documentation (RAG patterns)
- Simon Willison's Blog (LLM techniques)
- Anthropic Cookbook (Claude best practices)

### Model Resources

**Live2D Models**:
- Booth.pm: https://booth.pm (search "Live2D")
- Nizima: https://nizima.com
- VTuber Asset Resources

**LLM Models**:
- Ollama Library: https://ollama.com/library
- Hugging Face Models: https://huggingface.co/models
- Qwen Models: https://huggingface.co/Qwen

---

## Next Steps

### Immediate Actions (This Week)

1. **⭐ Star/Fork AIRI Repository**
   ```bash
   # Fork on GitHub, then clone
   git clone https://github.com/YOUR_USERNAME/airi.git
   ```

2. **📦 Set Up Development Environment**
   ```bash
   cd airi
   pnpm install
   pnpm dev  # Test that it works
   ```

3. **🔑 Get API Keys**
   - Sign up for Anthropic Claude or OpenAI
   - Sign up for ElevenLabs
   - Add to `.env` file

4. **🎨 Find/Download Live2D Model**
   - Browse Booth.pm for free models
   - Download and extract to `assets/models/`

5. **🧪 Run First Test**
   - Start AIRI
   - Have a conversation
   - Observe response times
   - Test avatar if configured

### Short-term Goals (2-4 Weeks)

1. **Enhance Memory System**
   - Implement vector storage
   - Test semantic retrieval
   - Build conversation history

2. **Personality Evolution**
   - Implement personality core
   - Start tracking traits
   - Test gradual evolution

3. **Optimize Performance**
   - Set up local LLM (Ollama + Qwen)
   - Implement hybrid routing
   - Measure response times

### Medium-term Goals (1-3 Months)

1. **Polish Experience**
   - Fine-tune personality
   - Optimize avatar expressions
   - Improve voice quality

2. **Advanced Learning**
   - Implement Alaya layer concepts
   - Build skill library
   - Add time awareness

3. **Daily Usage**
   - Use assistant daily
   - Collect real usage data
   - Iterate based on experience

### Long-term Vision (3-6 Months)

1. **Full Independence**
   - Mostly local operation
   - Minimal API costs
   - Strong learned personality

2. **Advanced Features**
   - Game integration (if desired)
   - Proactive assistance
   - Complex task planning

3. **Potential Expansion**
   - Streaming integration (if interests change)
   - Multiple personalities/modes
   - Custom skill development

---

## Conclusion

You now have a comprehensive roadmap to build your personal AI assistant based on AIRI, inspired by Neuro-sama's success. The project combines:

✅ **Solid Foundation**: AIRI's proven architecture
✅ **Smart Performance**: Hybrid LLM approach for speed + intelligence
✅ **Beautiful Presentation**: Live2D avatar with expressive animations
✅ **Continuous Learning**: Multi-tier memory system with personality evolution
✅ **Natural Interaction**: High-quality voice synthesis with lipsync

**Key Success Factors**:

1. **Start Simple**: Begin with cloud LLMs and basic features
2. **Iterate**: Add complexity gradually based on what works
3. **Personalize**: Let the personality evolve naturally through use
4. **Optimize**: Move to local/hybrid as you understand usage patterns
5. **Enjoy**: The best learning happens through daily interaction

**Remember**: Neuro-sama wasn't built in a day. It evolved over years of development and iteration. Your assistant will similarly grow smarter and more personalized the more you interact with it.

---

**Project Status**: Ready to begin
**Estimated Time to MVP**: 8-12 weeks part-time
**Difficulty Level**: Intermediate (requires coding, but AIRI provides foundation)
**Expected Outcome**: A fast, intelligent, beautiful AI companion that learns and grows with you

**Good luck building your AI assistant!** 🚀✨