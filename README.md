# Documentation Overview

## Purpose
Provide a complete high-level introduction to the Echo project, including its purpose,
architecture, modules, deployment model, and usage guidelines.
Echo operates fully on local systems by default. It may also be deployed on remote servers
or cloud providers; however, hardware isolation, VM snapshots, backup policies, encryption
at rest, and physical access controls reside outside Echo’s trust boundary. Deployments
outside local/on-prem infrastructure inherently provide lower privacy guarantees.

## Audience
New users, contributors, architects, system integrators, and anyone evaluating or using Echo.

## Contents
- Project overview  
- Local-first + external hosting model  
- Echo / Echo Bot / Echo Modules  
- Key capabilities  
- Repository structure  
- Getting started  
- Links to documentation  

## When to update
Whenever the project scope changes, architecture evolves, or major features are added.

---

# Echo — Local Multimodal Intelligence Framework

Echo is a **modular, extensible, privacy-first intelligence framework** designed to process,
analyze, and transform **audio and multimodal content**—including transcription, diarization,
summarization, translation, alignment, and information extraction.

All processing is performed **locally**, on user-controlled hardware, with **zero external data flow**
unless explicitly configured.

Echo provides an ecosystem of interchangeable modules, an intelligent meeting bot, and a unified
core engine capable of running end-to-end pipelines.

---

# 1. Deployment & Privacy Model

### Local-first (recommended)
Echo runs entirely on local hardware, ensuring:
- zero data exposure  
- full encryption and retention control  
- deterministic handling of all artifacts  
- strict compliance and privacy guarantees  

### External hosting (supported, reduced guarantees)
Echo can be deployed on:
- private servers  
- enterprise datacenters  
- private cloud  
- public cloud virtual machines  
- Kubernetes clusters  

However, privacy guarantees decrease because:
- VM snapshots  
- provider-level backups  
- hardware isolation  
- encryption at rest  
- physical access controls  

…are no longer fully controlled by Echo.

See: `docs/security/privacy.md`

---

# 2. Echo Architecture Overview

Echo is organized into **three major layers**:

## A. Echo — Core Framework
The orchestration backbone of the system:
- pipeline management  
- module registry  
- configuration  
- resource routing  
- encryption  
- logging  

It ensures consistency and interoperability across modules.

## B. Echo Bot — The Intelligent Agent
The operational automation layer:
- joins Teams meetings  
- captures audio streams  
- performs diarization  
- handles transcription  
- runs summarization and extraction modules  
- publishes outputs (Teams, SharePoint, files, API)  

Echo Bot is the “active assistant” that brings Echo into real workflows.

## C. Echo Modules — Extensible Capabilities
Modular, independent components that handle specific tasks:

- **Echo Transcribe** — ASR (Whisper, Vosk, Voxtral)  
- **Echo Summarize** — LLM summarization  
- **Echo Diarize** — speaker segmentation  
- **Echo Translate** — multilingual handling  
- **Echo Extract** — action/decision extraction  
- **Echo Detect** — classification/event detection  
- **Echo Align** — forced alignment  

Each module is replaceable, versioned, and fully configurable.

---

# 3. Key Features

- 🎙 **Multi-engine transcription**  
- 🗣 **Diarization**  
- 🧠 **Local LLM summarization** (Mistral/Mixtral or compatible)  
- 🔍 **Actionable extraction** (actions, decisions, risks)  
- 🌍 **Multilingual support** (EN · FR · DE · ZH · IT)  
- 🧩 **Module-based architecture**  
- 🔐 **Private by design**  
- 📦 **Ready for automation & integration**  

---

# 4. Repository Structure

```text
echo/
├─ README.md
├─ LICENSE
├─ .env.example
├─ docker-compose.yml
│
├─ docs/
│  ├─ index.md
│  ├─ architecture.md
│  ├─ echo-core.md
│  ├─ echo-bot.md
│  ├─ echo-modules.md
│  ├─ modules/
│  ├─ design/
│  ├─ security/
│  ├─ integration/
│  ├─ roadmap.md
│  └─ faq.md
│
├─ echo/          # Echo Core
├─ echo_bot/      # Bot agent
└─ modules/       # Capability modules
