---
**Purpose:**  
Describe Echo’s privacy principles, focusing on local-first processing while clarifying that Echo can run on other environments (servers, datacenters, or cloud) with associated limitations and security considerations.

**Audience:**  
Security teams, compliance officers, system architects, administrators.

**Contents:**  
- Local-first privacy model  
- Optional external deployment (servers, VMs, cloud)  
- Associated risks and limitations  
- Data processing categories  
- User consent and rights  
- Security expectations and disclaimers  

**When to update:**  
When processing architecture changes, when Echo introduces new data categories, or when deployment options evolve (e.g., additional supported runtimes or cloud models).
---

# Privacy Policy

Echo is designed around a **local-first privacy model**, ensuring that all audio, transcripts, embeddings, and summaries remain fully under the user’s control.  
However, Echo can also be deployed **outside a purely local environment** (e.g., private datacenter, dedicated server, cloud VM).  
This document clarifies what is protected, what depends on the hosting environment, and which risks must be considered.

---

## 1. Local-First Philosophy

Echo is **natively built to run fully on local infrastructure** such as:

- personal workstation  
- local server  
- on-premise GPU node  
- air-gapped environment  
- private virtualization or container environment  

In this mode:

- No data leaves the machine unless explicitly exported  
- Audio, transcripts, embeddings, summaries, and metadata remain local  
- Storage, encryption, retention, and access control are under the user's control  
- No telemetry or analytics are sent externally  
- No dependency on cloud services for inference (ASR/LLM)

This is the **recommended** and **most privacy-preserving** operating mode.

---

## 2. Running Echo on Other Environments (Servers, Datacenter, Cloud)

Echo can be deployed on:

- a remote server (dedicated or shared)  
- an enterprise datacenter  
- a cloud VM (Azure, AWS, GCP, OVH, Hetzner…)  
- container orchestration (Kubernetes, Nomad, Docker Swarm)  

**This is supported, but not fully controlled by Echo.**

In this mode:

### ✔ What Echo still guarantees:
- No external API calls from Echo itself  
- No cloud-based inference (unless user chooses optional external models)  
- Encryption features still available (storage encryption, secrets, configs)  
- Access logs and processing logs remain internal to the VM/container

### ⚠ What Echo **does not** control:
- Cloud provider hardware security (CPU/GPU isolation, multi-tenancy risks)  
- Underlying disk encryption policies  
- Snapshots or backups performed automatically by the provider  
- Physical access to servers  
- Hypervisor-level compromise  
- Network-layer interception if traffic is not properly secured  
- Key management outside of Echo’s boundary  
- Compliance posture of the hosting provider (GDPR, ISO, SOC2…)  

### ⚠ Important security disclaimer:
> Running Echo outside of local/on-prem infrastructure reduces the level of guaranteed privacy,  
> because storage, hardware, VM snapshots, and encryption at rest may not be under your exclusive control.

---

## 3. Data Categories Processed by Echo

Depending on modules used, Echo may process:

- raw audio  
- diarization segments  
- speaker embeddings  
- transcripts  
- summaries, decisions, action items  
- timestamps and metadata  
- meeting details (title, start/end time, participants, tags)

All files and intermediate artifacts are stored **locally**, unless manually exported.

---

## 4. Consent & User Transparency

When Echo Bot joins a meeting:

- Participants must be informed (via meeting banners or verbal notice).  
- For external meetings, explicit consent may be required depending on policies.  
- Echo does not attempt to circumvent meeting organizer consent rules.

Echo processes only the audio that is accessible to it as a participant (bot or technical account).

---

## 5. User Rights

In line with privacy and compliance requirements:

- Users may request deletion of transcripts or summaries  
- Raw audio is subject to strict retention controls  
- Individuals have the right to access their personal data if processed  
- Data portability is possible through exports (Markdown, JSON, raw text)

---

## 6. Data Retention & Storage Control

Echo applies retention rules defined in `docs/security/retention.md`.

When Echo is deployed locally:

- All data lives under user-controlled storage  
- Encryption keys remain local  
- The user decides retention and deletion policies  

When Echo is deployed elsewhere:

- Retention may depend on the hosting environment  
- Automatic backups or snapshots may make strict deletion impossible  
- Hosting provider may impose a minimum retention window  

Echo cannot guarantee full deletion if the provider keeps infrastructure-level snapshots.

---

## 7. Summary of Privacy Guarantees

| Deployment Mode | Privacy Level | What You Control | What You Don’t Control |
|-----------------|---------------|------------------|-------------------------|
| **Local (Recommended)** | ⭐⭐⭐⭐⭐ Maximum | Everything | Nothing |
| **On-prem server** | ⭐⭐⭐⭐ High | Storage, access, encryption | Physical access (shared IT) |
| **Private cloud** | ⭐⭐⭐ Medium | OS & software | Hypervisor, snapshots, hardware |
| **Public cloud (VM)** | ⭐⭐ Lower | VM content | Provider hardware, backups |
| **Public cloud (managed apps)** | ⭐ Minimal | Very limited | Everything below OS layer |

---

## 8. Final Disclaimer

> Echo guarantees privacy **only within the boundaries of the system it controls**.  
>  
> Any deployment outside local/on-prem infrastructure inherently depends on the privacy, hardware security, snapshot policies, and encryption guarantees of the chosen hosting provider.

---

# End of document
