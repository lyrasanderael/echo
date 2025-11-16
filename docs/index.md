---
**Purpose:**  
Serve as the main table of contents and entry point for Echo documentation.

**Audience:**  
All users, developers, and maintainers.

**Contents:**  
- Overview of documentation sections  
- Links to architecture, modules, integrations, security, roadmap, etc.  

**When to update:**  
Whenever new documentation pages are added, removed, or reorganized.
---
# Echo Documentation Index
Purpose: Table of contents and doc navigation entrypoint.
Audience: Everyone.
Contents: What is Echo, architecture overview, links to all sections, terminology.
When to update: Whenever a new doc page is added.

## 1. Introduction
- What is Echo?
- Project philosophy
- Core components (Echo / Echo Bot / Echo Modules)
- Local-first & privacy guarantees

## 2. Architecture Overview
- System diagram
- Data flow (audio → ASR → NLP → outputs)
- Module lifecycle

## 3. Echo — Core Framework
- Responsibilities & boundaries
- Pipeline orchestration
- Module registry & plugin system
- Data schema standards

## 4. Echo Bot — The Agent Layer
- Meeting participation logic
- Audio capture strategies
- Internal vs external meeting modes
- Publishing outputs (Teams, files, API)

## 5. Echo Modules
- Module concept & naming
- How modules are loaded
- Common patterns
- Adding a new module

### 5.x Specific Modules
- Echo Transcribe
- Echo Summarize
- Echo Diarize
- Echo Translate
- Echo Detect
- Echo Extract
- Echo Align

## 6. Design Specifications
- Data flows
- Pipelines (meeting pipeline, batch pipeline)
- Model selection strategy
- Performance considerations (GPU/CPU)

## 7. Integration
- Microsoft Teams integration
- Graph API permissions
- External meetings (technical account)

## 8. Security & Privacy
- Local-only philosophy
- Data retention policies
- Encryption at rest
- Compliance considerations

## 9. Roadmap
- MVP → V1 → V2
- Feature plans
- Future modules

## 10. FAQ
