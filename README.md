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
- Documentation index
- License & contributing

## When to update
Whenever the project scope changes, architecture evolves, or major features are added.

---

# Echo — Local Multimodal Intelligence Framework

Echo is a modular, extensible, privacy-first intelligence framework designed to process,
analyze, and transform audio and multimodal content. All processing happens locally,
under the user’s full control.

Echo provides:
- multi-engine transcription
- diarization
- summarization (local LLM)
- translation
- action/decision extraction
- modular pipelines
- an intelligent meeting bot

---

# 1. Deployment & Privacy Model

## Local-first (recommended)
- Zero external calls
- Full control on encryption, storage, and retention
- No dependency on cloud inference

## External hosting (supported, reduced guarantees)
Echo may run on private/public cloud VMs, but privacy guarantees decrease because:
- snapshots
- backups
- encryption-at-rest settings
- hardware isolation
- hypervisor access

See: docs/security/privacy.md

---

# 2. Echo Architecture Overview

Echo is organized into three layers:

## Echo — Core Framework
Pipelines, orchestration, configuration, encryption, module registry.

## Echo Bot — Intelligent Meeting Agent
Joins Teams meetings, captures audio, processes workflow, publishes results.

## Echo Modules — Extensible Capabilities
Transcribe, Summarize, Diarize, Translate, Extract, Detect, Align, etc.

---

# 3. Key Features

- Multi-engine ASR (Whisper, Vosk, Voxtral)
- Local LLM summarization (Mistral/Mixtral)
- Speaker diarization
- Translation
- Action/decision extraction
- Modular architecture
- Offline by design
- Multilingual

---

# 4. Documentation

Full documentation is located under /docs:

- Architecture → docs/architecture.md
- Core Framework → docs/echo-core.md
- Echo Bot → docs/echo-bot.md
- Modules → docs/echo-modules.md
- Security & Privacy → docs/security/privacy.md
- Teams Integration → docs/integration/teams.md
- Roadmap → docs/roadmap.md
- FAQ → docs/faq.md

---

# 5. License

Echo is licensed under Apache 2.0.  
See LICENSE for details.

---

# 6. Contributing

Contributions and module proposals are welcome.  
Please follow contribution guidelines (coming soon).

---

# 7. Final Note

Capture the signal.  
Reveal the meaning.  
Keep all intelligence in your hands.
