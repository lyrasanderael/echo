---
purpose: |
  Provide a complete high-level introduction to the Echo project, including its purpose,
  architecture, modules, deployment model, and usage guidelines. Echo operates fully on
  local systems by default. It may also be deployed on remote servers or cloud providers;
  however, hardware isolation, VM snapshots, backup policies, encryption at rest, and
  physical access controls reside outside Echo’s trust boundary. Deployments outside
  local/on-prem infrastructure inherently provide lower privacy guarantees.

audience: |
  New users, contributors, architects, system integrators, and anyone evaluating or using Echo.

contents:
  - Project overview
  - Local-first + external hosting model
  - Echo, Echo Bot, and Echo Modules architecture
  - Key capabilities
  - Supported features
  - Repository structure
  - Getting started instructions
  - Links to documentation

when_to_update: |
  Whenever the project scope changes, architecture evolves, or major features are added.
---

# Echo — Local Multimodal Intelligence Framework

Echo is a **modular, extensible, privacy-first intelligence framework** designed to process, analyze, and transform **audio and multimodal content**.  
All processing — transcription, diarization, summarization, translation, extraction — is performed **locally**, on hardware fully controlled by the user.

Echo is built to be:

- 🔐 **Local-first** (no cloud dependency)  
- 🧩 **Modular** (plug-in capabilities called Echo Modules)  
- 🧠 **LLM-powered** (Mistral/Mixtral or compatible local models)  
- 🎙 **Multi-engine ASR** (Whisper, Vosk, Voxtral…)  
- 🌍 **Multilingual** (EN, FR, DE, ZH, IT)  
- 🏗 **Extensible** (add new modules, new engines, new analyzers)  
- 🧱 **Deterministic & predictable** (unified data contracts, stable pipelines)

Echo gives you **full control** of your data, your inference, and your workflows.

---

# 1. Deployment & Privacy Model

### 🟩 Local-first (recommended)

Echo runs **entirely on local hardware**, guaranteeing:

- full data sovereignty  
- no external API calls  
- zero data exposure  
- encrypted local storage  
- predictable retention and deletion  
- on-prem GPU / CPU compatibility  

### 🟧 Remote servers / Cloud VMs (supported with reduced guarantees)

Echo *can* run on:

- enterprise servers  
- private cloud  
- public cloud VMs  
- Kubernetes clusters  

However:

> When Echo runs outside of local/on-prem hardware, **privacy guarantees decrease**, because hardware isolation, VM snapshots, provider backups, and encryption-at-rest are no longer controlled by Echo.

See: `docs/security/privacy.md`

---

# 2. Echo Architecture Overview

Echo is organized into **three major layers**:

## **A. Echo — Core Framework**
The foundational engine that orchestrates:

- pipelines  
- module lifecycle  
- resource scheduling  
- storage & encryption  
- data routing  
- logging & governance  

It ensures consistency across all modules.

---

## **B. Echo Bot — The Intelligent Agent**
The operational layer connecting Echo to real workflows:

- joins Teams meetings  
- captures audio  
- diarizes speakers  
- transcribes using local ASR  
- summarizes with LLMs  
- extracts actions, decisions, risks  
- publishes results (Teams, SharePoint, Files, API)

Echo Bot is the **active assistant**.

---

## **C. Echo Modules — Capability Extensions**
Each capability is a standalone module:

- **Echo Transcribe** — multi-engine ASR  
- **Echo Summarize** — LLM-based summarization  
- **Echo Diarize** — speaker segmentation  
- **Echo Extract** — action/decision extraction  
- **Echo Translate** — multilingual translation  
- **Echo Detect** — classification, risk detection  
- **Echo Align** — word-level forced alignment  
- **Echo Index** — semantic search (future)

Modules are plug-and-play, versioned, and replaceable.

---

# 3. High-Level Architecture Diagram

```mermaid
flowchart LR
    A[Microsoft Teams Meeting] --> B[Echo Bot<br/>(join strategy)]
    B --> C[Audio Capture<br/>(Graph/Bot media)]
    C --> D[Echo Transcribe<br/>(ASR engines)]
    D --> E[Echo Diarize<br/>(optional)]
    D --> F[Echo Translate<br/>(optional)]
    D --> G[Echo Summarize<br/>(LLM)]
    E --> G
    F --> G
    G --> H[Echo Extract<br/>(actions/decisions)]
    G --> I[Publishers<br/>(Teams / SharePoint / Files)]
    G --> J[Local Encrypted Storage]

    classDef local fill:#e8f5e9,stroke:#2e7d32,color:#1b5e20;
    class C,D,E,F,G,H,I,J local;
