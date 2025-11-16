---
**Purpose:**  
Describe Echo’s privacy principles and guarantees, emphasizing the local-first security model while clarifying that Echo can also run on external servers or cloud environments with reduced and limited privacy guarantees.  
Echo operates fully on local systems by default. It may also be deployed on remote servers or cloud providers; however, hardware isolation, VM snapshots, backup policies, encryption at rest, and physical access controls reside outside Echo’s trust boundary. Deployments outside local/on-prem infrastructure inherently provide lower privacy guarantees.

**Audience:**  
Security teams, compliance officers, administrators, architects, and any user responsible for data protection.

**Contents:**  
- Local-first philosophy  
- External hosting and associated risks  
- Data categories processed by Echo  
- Consent and user transparency  
- User rights and GDPR considerations  
- Retention and deletion guarantees  
- Privacy limitations outside the local trust boundary  

**When to update:**  
When new modules process new data categories, when hosting recommendations change, when regulatory requirements evolve, or when external deployment models introduce new risks.
---

# Privacy Policy

Echo is designed around a **local-first, privacy-by-design architecture**, ensuring that all processing, storage, and inference remain under the user's direct control.  
However, Echo may also be deployed on **remote servers, enterprise datacenters, or cloud VMs**, where hardware-level and storage-level privacy controls no longer fall exclusively under Echo’s control.

This document explains the privacy guarantees Echo provides—and the limitations that appear when the system is executed outside local or on-prem infrastructure.

---

## 1. Local-First Privacy Philosophy

Echo is **natively built to run entirely on local hardware**, such as:

- a personal workstation  
- an on-prem server or GPU node  
- an air-gapped machine  
- a private local VM or Docker host  
- any self-controlled edge device  

In this mode:

- No data leaves your environment unless you explicitly export it  
- All audio, transcripts, embeddings, and summaries remain local  
- Encryption at rest is fully controlled by the user  
- No telemetry, analytics, or external calls are made  
- Raw audio and sensitive artifacts never reach external systems  

**This is the recommended mode for maximum confidentiality.**

---

## 2. Running Echo on Remote or Cloud Infrastructure

Echo can also be executed on:

- enterprise servers  
- private cloud infrastructure  
- public cloud VMs (Azure, AWS, GCP, OVH, Hetzner…)  
- Kubernetes clusters  
- remote GPU hosts  

This deployment mode is supported, but with significant caveats.

### ✔ What Echo still guarantees:
- No outgoing external API calls (unless manually configured)  
- No cloud inference (unless the user explicitly activates a cloud module)  
- Encryption features still available  
- Local access controls inside the VM/container  

### ⚠ What Echo does NOT control outside local/on-prem deployments:
- underlying **hardware isolation**  
- **disk encryption at rest** (if disabled or provider-managed)  
- creation of **snapshots** (automatic or invisible to the user)  
- **hypervisor-level access**  
- **provider staff** physical access controls  
- **backup replication** outside your geographic/legal region  
- network traffic exposure if improperly configured  

### ⚠ Critical disclaimer  
> When Echo runs on external or cloud hosting, **privacy guarantees decrease**,  
> because hardware isolation, VM snapshots, backup retention, and encryption at rest can no longer be assumed.

---

## 3. Data Categories Processed by Echo

Depending on the configuration and modules used, Echo may process:

- raw audio streams  
- speaker diarization segments  
- embeddings for speaker recognition  
- full transcripts  
- structured summaries  
- detected actions, decisions, risks  
- meeting metadata (title, time, tags, participants)  

All these artifacts are:

- **stored locally** when running on local hardware  
- **stored within the hosted environment** if running remotely  

Echo **never sends any data externally** unless explicitly configured.

---

## 4. Consent and Transparency

When Echo Bot joins a meeting:

- Teams will display a **recording/transcription banner** (when policies allow)  
- Participants must be **informed that audio is being processed**  
- For external guests, **explicit verbal or written consent** may be required  
- Echo does not bypass or circumvent consent policies  

Echo only processes audio streams that it is legitimately allowed to access.

---

## 5. User Rights (GDPR & Equivalent)

Users may request:

- access to their personal data  
- correction of inaccuracies  
- deletion of their information (subject to retention rules)  

Echo enables these rights **only when running locally**, since:

- data is stored entirely under user control  
- deletion is fully effective  

When Echo is hosted remotely:

- deletion may not remove **provider snapshots or backups**  
- full erasure cannot be guaranteed by Echo

---

## 6. Data Retention and Deletion Guarantees

Retention rules are defined in `docs/security/retention.md`.

### In local/on-prem deployment:
- retention is fully enforceable  
- deletion is complete and final  
- encryption keys never leave the user's environment  

### In remote/cloud deployment:
- deletion may not apply to provider snapshots  
- backups may persist outside Echo’s control  
- encryption at rest policies may be controlled by the provider  

Echo cannot guarantee full deletion in environments outside the local trust boundary.

---

## 7. Summary of Privacy Implications

| Deployment Mode | Privacy Level | What You Control | What You Don't Control |
|-----------------|---------------|------------------|-------------------------|
| **Local (Recommended)** | ⭐⭐⭐⭐⭐ | Everything | Nothing |
| **On-Prem Server** | ⭐⭐⭐⭐ | Storage, OS, access | Physical rack access |
| **Private Cloud** | ⭐⭐⭐ | VM, OS | Hypervisor, snapshots |
| **Public Cloud VM** | ⭐⭐ | OS content | Hardware, encryption at rest |
| **Managed Cloud Apps** | ⭐ | Minimal | Almost everything |

---

## 8. Final Privacy Disclaimer

> **Echo guarantees privacy only within the boundaries of the environment it controls directly.**  
>  
> When Echo is executed outside local or on-prem infrastructure,  
> privacy guarantees depend entirely on the hosting provider’s isolation, encryption,  
> snapshot behavior, physical access controls, and governance practices.

---

# End of document
