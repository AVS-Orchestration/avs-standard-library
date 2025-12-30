AVS Orchestration Sequence: Job-Hunting Stream

This document illustrates the temporal and data-driven hand-off between the Human Architect, the AVS Toolkit (Automation), and the Agentic Agent. Unlike a standard script, the AVS Framework uses a "Digital Thread" where each product is released back into the context store to fuel the next unit of work.

🔄 The Multi-Story Value Stream

```mermaid
sequenceDiagram
    participant H as Human Architect
    participant T as AVS Toolkit (CLI)
    participant C as Context Store (Local/Web)
    participant AG as Agentic Agent

    Note over H, AG: VS-000: Intake & Extraction (The Scrape)
    H->>T: avs assemble VS-000.md
    T->>C: Scrape Job URL (Firecrawl)
    C-->>T: Raw Corporate Data
    T->>AG: Execute Goal: Generate Intake Report
    AG-->>H: VS-000_output.md (Intake Report)
    H->>C: Release to Context Store

    Note over H, AG: VS-001: Analysis & Strategy (The Map)
    H->>T: avs assemble VS-001.md
    T->>C: Fetch Intake Report + Raw Resume + JD
    C-->>T: All Required Context
    T->>AG: Execute Goal: Create Strategic Matrix
    AG-->>H: VS-001_output.md (Strategy Plan)
    H->>C: Release to Context Store

    Note over H, AG: VS-002: Resume Generation (The Draft)
    H->>T: avs assemble VS-002.md
    T->>C: Fetch Strategy Plan + Raw Resume
    C-->>T: Execution-Ready Briefcase
    T->>AG: Execute Goal: Draft Tailored Resume
    AG-->>H: VS-002_output.md (Draft Resume)
    H->>C: Release to Context Store

    Note over H, AG: VS-003: Audit & Remediate (The Gatekeeper)
    H->>T: avs assemble VS-003.md
    T->>C: Fetch Draft Resume + Raw Resume (Ground Truth)
    C-->>T: Forensic Briefcase
    T->>AG: Execute Goal: Forensic Fact-Check
    AG-->>H: VS-003_output.md (Final Remediated Resume)
    H->>H: Accept & Submit Application
```

## 🔍 Key Orchestration Principles

### 1. The "Information Hunt" (Assembler)

In each story, the AVS Toolkit (T) performs the hunt for you. In VS-000, it reaches out to the web; in VS-001 through VS-003, it reaches back into the products created in the previous steps. This eliminates "Context Blindness" for the Agent.

### 2. The "Accept & Release" Loop

A product is only used as context once the Human Architect (H) reviews and releases it. This ensures that errors or "hallucinations" in an early stage (like the Intake Report) are caught before they propagate into the Strategy or Resume Draft.

### 3. Algorithmically Legible Handoffs

The handoff is not a vague prompt. It is a Briefcase (.yaml) that contains:

1. **The Goal**: (e.g., "As a Forensic Auditor...")
2. **The Instructions**: (e.g., "Cross-reference every bullet point...")
3. **The Context**: (The actual text of the Raw Resume and the Draft).

Framework Attribution: Patrick Heaney (CC BY-SA 4.0).

Repository: AVS-Orchestration/avs-standard-library