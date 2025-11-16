---
**Purpose:**  
Provide a complete high-level introduction to the Echo project and guide new users.  
Echo operates fully on local systems by default. It may also be deployed on remote servers or cloud providers; however, hardware isolation, VM snapshots, backup policies, encryption at rest, and physical access controls reside outside Echo’s trust boundary. Deployments outside local/on-prem infrastructure inherently provide lower privacy guarantees.

**Audience:**  
New users, contributors, evaluators, architects.

**Contents:**  
- Project overview  
- Local-first + external hosting considerations  
- Core layers (Echo, Echo Bot, Echo Modules)  
- Features  
- Architecture summary  
- Quick start  
- Documentation links  

**When to update:**  
Whenever the project scope changes, architecture evolves, or major features are added.
---
# Echo — Local Multimodal Intelligence Framework

Echo is an open, modular, privacy-first framework for processing and understanding audio and multimodal content entirely on local infrastructure.

Echo consists of:
- **Echo** — the core orchestration framework  
- **Echo Bot** — the intelligent meeting agent  
- **Echo Modules** — specialized capabilities (Transcribe, Summarize, Diarize, etc.)

This repository contains:
- the core framework  
- the agent  
- the module system  
- the documentation in `/docs`  

See `/docs/index.md` for the full documentation.
