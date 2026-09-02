<div align="center">

<img src="banner.svg" width="100%" alt="Hillary Ikhais - ML Systems Engineer">

# Hillary Ikhais

**I build the machinery around models — not just the models themselves.**

Retrieval · Ranking · Evaluation · Agent Systems · Local Inference

[`GitHub`](https://github.com/HillaryIkhais) · [`Featured Work`](#-featured-work) · [`How I Think`](#-how-i-think-about-building)

</div>

---

> *"The model is the easy part. Everything around it is the actual engineering problem."*

I care about what happens underneath the API call. The retrieval pipeline that decides what the model sees. The evaluation framework that proves whether it actually works. The engineering that makes inference run on hardware that doesn't have a GPU. The agent architecture that doesn't fall apart when two agents disagree about the state of the world.

Most of my work lives at the intersection of **ML systems engineering** and **applied AI** — building things that need to work under real constraints, not just in a demo.

---

<div align="center">

## <img src="https://em-content.zobj.net/source/twitter/408/magic-wand_1fa84.png" width="28"> Featured Work

</div>

<br/>

<table>
<tr>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/Sylon">SYLON</a>

<p><img src="https://img.shields.io/badge/Status-Live-00c853?style=flat-square" alt="Live"> <img src="https://img.shields.io/badge/Domain-Behavioral_Intelligence-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/Models-Cerebras_Qwen_235B-e11d48?style=flat-square" alt="Model"></p>

**Agentic behavioral intelligence platform.**

Sylon reads raw customer feedback and builds psychological timelines — tracking how taste evolves, where expectations shift, and what actually drives churn. It treats customers as evolving psychological entities, not static segments.

<details>
<summary><b>What I built</b></summary>

- Temporal phase analysis engine that splits user histories into behavioral phases and extracts drift signals
- Cross-domain translation engine that cold-starts recommendations by mapping psychological drivers across unrelated domains
- Multi-agent orchestration with intent routing, parallel extraction swarms, and a conversational strategist
- Zero-shot ranking evaluated against hold-out data

</details>

<details>
<summary><b>Evaluation metrics</b></summary>

| Metric | Score |
|:---|:---|
| RMSE (rating prediction) | **0.7906** |
| NDCG@10 (ranking) | **0.1605** |
| HitRate@10 | **0.2000** |
| ROUGE-L (generation fidelity) | **0.1311** |

**Ablation without temporal phase splitting:**
RMSE degrades to 1.4491, NDCG@10 drops to 0.0652.
Static summaries aren't enough.

</details>

<p><code>Python</code> <code>FastAPI</code> <code>Next.js</code> <code>SQLite</code> <code>ElevenLabs</code></p>

<p><a href="https://sylon.vercel.app/">Live Demo →</a></p>

</td>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/MOVA">MOVA</a>

<p><img src="https://img.shields.io/badge/Status-Benchmarked-00c853?style=flat-square" alt="Benchmarked"> <img src="https://img.shields.io/badge/Domain-Financial_NLP-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/Model-Llama_3.2_3B-0ea5e9?style=flat-square" alt="Model"></p>

**Offline financial intelligence for African SMEs.**

MOVA converts messy WhatsApp messages, OPay SMS, and Pidgin voice-note transcripts into structured financial records — completely offline on an 8GB laptop. No cloud. No API fees. No internet required after model download.

<details>
<summary><b>The hard problem</b></summary>

Correctly understanding who owes whom in informal African commerce.

> "Chinedu still dey owe me 85k" → receivable
> "I wan pay Alhaji Bello 250k" → payable

Mixed Pidgin/English. Implicit context. Multiple transactions per message.

</details>

<details>
<summary><b>Benchmark (130-example Nigerian economic test set)</b></summary>

| Metric | Score |
|:---|:---|
| Entity extraction | **98%** |
| Debt direction | **92%** (improved from 35% via prompt engineering) |
| Status detection | **91%** |
| Amount extraction | **88%** |
| Full record accuracy | **78%** |

| On-device | Value |
|:---|:---|
| Model | Llama 3.2 3B (Q4_K_M) |
| Throughput | 7.32 tok/s on Apple M3 |
| Peak RAM | 4 GB |
| Disk | 2.02 GB |

</details>

<p><code>Llama</code> <code>llama.cpp</code> <code>Tauri</code> <code>Rust</code> <code>TypeScript</code></p>

</td>
</tr>
</table>

<br/>

<table>
<tr>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/PulseRelay">PulseRelay</a>

<p><img src="https://img.shields.io/badge/Status-Hackathon_Winner-00c853?style=flat-square" alt="Winner"> <img src="https://img.shields.io/badge/Domain-Healthcare_AI-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/AI-Gemini_3.5_Flash-0ea5e9?style=flat-square" alt="AI"></p>

**Hands-free AI agent for paramedic patient transport.**

Paramedics talk. PulseRelay listens, remembers, and hands it off. It extracts structured clinical data from natural speech in real time — vitals, medications, patient demographics — tracks trends, asks for clarification on incomplete data, and generates a complete handoff summary for the receiving hospital.

> **The critical design choice:** Gemini handles understanding language. Deterministic Python code handles everything else — storing values, validating ranges, calculating trends, tracking confidence.
> **No hallucinated vitals. No invented medications. The AI understands; the code decides.**

<p><code>Gemini</code> <code>Google ADK</code> <code>FastAPI</code> <code>Cloud Run</code> <code>Firestore</code></p>

</td>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/RECKON">RECKON</a>

<p><img src="https://img.shields.io/badge/Status-Competition-00c853?style=flat-square" alt="Competition"> <img src="https://img.shields.io/badge/Domain-Agent_Safety-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/Runtime-Ollama-0ea5e9?style=flat-square" alt="Runtime"></p>

**Control layer for autonomous AI agents.**

No consequential action should execute simply because the agent is confident. RECKON enforces that principle through an 11-phase state machine with recovery contracts, red-team subagents, and human approval gates.

```text
INTAKE → INVESTIGATION → ANALYSIS → ACTION_PLAN → RECOVERY_CONTRACT
→ SANDBOX_VALIDATION → RED_TEAM → DECISION → HUMAN_CHECKPOINT
→ EXECUTION → VERIFICATION
```

| Action Type | RECKON Behavior |
|:---|:---|
| Read-only | Execute autonomously |
| Reversible | Requires human approval |
| Destructive | Blocked entirely |
| Unknown | Blocked entirely |

<p><code>TypeScript</code> <code>TrueForge</code> <code>MCP</code> <code>Ollama</code> <code>Node.js</code></p>

</td>
</tr>
</table>

<br/>

<table>
<tr>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/Vanished">VANISHED</a>

<p><img src="https://img.shields.io/badge/Status-9%2F9_Tests_Passing-00c853?style=flat-square" alt="Tests"> <img src="https://img.shields.io/badge/Domain-Data_Integrity-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/Integration-Bright_Data-ff6600?style=flat-square" alt="Integration"></p>

**Semantic data-integrity detection for self-healing scrapers.**

Self-healing scrapers fix broken extraction logic automatically. But how do you know the repaired scraper is still returning the right data? Vanished is the verification layer — it compares scraper output across snapshots and detects information loss, contract changes, contradictions, and pipeline drift.

> **A scraper that runs isn't necessarily a scraper you can trust.**

<p><code>Python</code> <code>pytest</code> <code>Bright Data</code> <code>Next.js</code> <code>React</code></p>

<p><a href="https://vanished-six.vercel.app/">Live Demo →</a></p>

</td>
<td width="50%" valign="top">

### <a href="https://github.com/HillaryIkhais/CREDO">CREDO</a>

<p><img src="https://img.shields.io/badge/Status-Live-00c853?style=flat-square" alt="Live"> <img src="https://img.shields.io/badge/Domain-Pharma_Verification-7c3aed?style=flat-square" alt="Domain"> <img src="https://img.shields.io/badge/Architecture-Offline_First-0ea5e9?style=flat-square" alt="Architecture"></p>

**Offline-first Edge AI for pharmaceutical verification.**

Counterfeit drugs kill over 100,000 people annually in sub-Saharan Africa. CREDO eliminates verification friction by running drug authentication entirely on-device — no internet, no cloud API, no latency.

> Built for the hardware that exists in the places where this problem is most acute.

<p><code>Python</code> <code>Edge AI</code> <code>Offline-first</code></p>

<p><a href="https://credo-lime.vercel.app/">Live Demo →</a></p>

</td>
</tr>
</table>

---

<div align="center">

## <img src="https://em-content.zobj.net/source/twitter/408/brain_1f9e0.png" width="28"> How I Think About Building

</div>

> These aren't principles I wrote on a whiteboard. They're patterns I keep running into.

<table>
<tr>
<td width="50%">

#### Evaluation before demos

A system that runs isn't a system that works. I'd rather show you an RMSE score than a screenshot. Every project above has real numbers attached — and where the numbers are weak, I say so.

</td>
<td width="50%">

#### Abstractions earn their place

I use frameworks when they solve the problem. I drop down to llama.cpp when they don't. MOVA runs on-device because the constraint demanded it, not because offline-first sounds good on a landing page.

</td>
</tr>
<tr>
<td width="50%">

#### Complexity should be provable

Vanished's semantic comparison engine, Sylon's ablation studies, MOVA's benchmark suite — I keep building verification into the system, not after it.

</td>
<td width="50%">

#### The interesting work is in the plumbing

Retrieval quality, ranking signals, data pipelines, inference optimization, agent coordination — the model is the easy part. Everything around it is the actual engineering problem.

</td>
</tr>
</table>

---

<div align="center">

## <img src="https://em-content.zobj.net/source/twitter/408/compass_1f9ed.png" width="28"> Currently Exploring

</div>

<table>
<tr>
<td width="33%" align="center">

**<img src="https://em-content.zobj.net/source/twitter/408/hammer-and-wand_1fa89.png" width="20"> Actively Building**

Retrieval and ranking systems with real evaluation

Agent coordination that survives multi-turn state

Local inference optimization for constrained hardware

</td>
<td width="33%" align="center">

**<img src="https://em-content.zobj.net/source/twitter/408/books_1f4da.png" width="20"> Learning**

Knowledge graph memory for agent coherence

Structured evaluation for generative systems

Robotics and embodied AI

</td>
<td width="33%" align="center">

**<img src="https://em-content.zobj.net/source/twitter/408/sparkles_2728.png" width="20"> Interested In**

When agents reason about their own reliability

ML systems that degrade gracefully

Retrieval augmentation meets agent memory

</td>
</tr>
</table>

---

<div align="center">

## <img src="https://em-content.zobj.net/source/twitter/408/wrench_1f527.png" width="28"> Tech I Work With

</div>

<table>
<tr>
<td align="center"><img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"></td>
<td align="center"><img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"></td>
<td align="center"><img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust"></td>
<td align="center"><img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch"></td>
</tr>
<tr>
<td align="center"><img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI"></td>
<td align="center"><img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js"></td>
<td align="center"><img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React"></td>
<td align="center"><img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"></td>
</tr>
<tr>
<td align="center"><img src="https://img.shields.io/badge/Llama-Followed_by_6-FF6B35?style=for-the-badge&logo=meta&logoColor=white" alt="Llama"></td>
<td align="center"><img src="https://img.shields.io/badge/llama.cpp-000000?style=for-the-badge" alt="llama.cpp"></td>
<td align="center"><img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"></td>
<td align="center"><img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel"></td>
</tr>
</table>

---

<div align="center">

*Currently building. Open to interesting problems.*

[<img src="https://img.shields.io/badge/Follow-@HillaryIkhais-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">](https://github.com/HillaryIkhais)

</div>
