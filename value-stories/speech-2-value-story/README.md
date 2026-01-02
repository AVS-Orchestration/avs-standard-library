# Speech to Value Story: The Meta-Architect

This is a "Meta" use case: using the AVS Framework to build the AVS Framework. It allows you to transform a raw "Discovery Interview" transcript into a valid, executable AVS Value Story (.md) by simply "talking" through your intent rather than manually writing YAML syntax.

**Goal**: Lower the barrier to entry for creating high-fidelity agentic instructions by externalizing tacit knowledge into Algorithmically Legible logic.

## 🛠 Prerequisites
- **AVS Toolkit** installed and configured.
- **Ollama** (llama3) or a Cloud Provider (e.g., Gemini) configured in your `.env`.
- Review the [Value Story Interview Guide](../../avs-toolkit/docs/Guide-Value-Story-Interview.md).

## 🔄 The Workflow

### 1. Conduct the Interview
Start an audio recording (Apple Notes and Microsoft OneNote both have excellent built-in transcription features) and record yourself or your team answering the questions in the **Interview Guide**. Focus on the **Persona**, the **Outcome**, the **Step-by-Step Process**, and the **Context Assets**.

### 2. Transcribe & Paste
Copy the text of your transcribed discussion and paste it into the following file:
`avs-standard-library/value-stories/speech-2-value-story/paste-transcript-in-here.md`

### 3. Generate the Story
Run the compiler story from the root of your `AVS-Orchestration-Workspace`:

```bash
uv run avs run avs-standard-library/value-stories/speech-2-value-story/vs-001-generate-vs.md
```

### 4. Review & Rename
The agent will analyze your transcript and generate a valid AVS Value Story file here:
`avs-standard-library/value-stories/speech-2-value-story/vs-xxx-your-vs.md`

**Action Required**: Open the generated file, verify the instructions are accurate, and **rename it** (e.g., `vs-006-data-analysis.md`) before moving it to your active project folder.

## 📂 File Inventory

*   **`vs-001-generate-vs.md`**: The "Architect" story. It contains the instructions for mapping raw human intent into the AVS template structure.
*   **`paste-transcript-in-here.md`**: The input buffer. This is the "Source of Truth" for your interview.
*   **`vs-xxx-your-vs.md`**: The output target. This file is overwritten every time you run the compiler.
*   **`VS-001-assembled.yaml`**: The execution snapshot (Briefcase) created by the toolkit during the run.

---
*Framework by Patrick Heaney. Part of the AVS Standard Library.*