# Project Management: Autonomous Backlog Refinement

This stream automates the bridge between human discussion and technical execution. It allows you to take meeting notes, transcripts, or recorded brainstorms and turn them into high-fidelity GitHub Issues with a built-in safety gate for human review.

## 🔄 The Value Stream

1.  **VS-001: Backlog Triage & Extraction**
    *   **Goal**: Analyze raw transcripts and extract structured issue proposals.
    *   **Result**: `triage-report.md`.

2.  **VS-002: GitHub Issue Drafting (Human Review Point)**
    *   **Goal**: Format extracted items into structured draft blocks.
    *   **Result**: `issues-to-create.md`.
    *   **Action**: **Human-in-the-Loop review**. Open the result, verify the titles/bodies, and make any final edits.

3.  **VS-003: GitHub Issue Publication**
    *   **Goal**: Take the approved drafts and programmatically create them in the GitHub repository using the internal MCP tool.
    *   **Result**: Live GitHub Issues and `publication-report.md`.

## 🛠 Prerequisites

- **GITHUB_PAT**: Ensure you have a personal access token set in your `.env` file with `repo` permissions.
- **Repository Context**: It is recommended to have your `README.md` or `ARCHITECTURE.md` available as context so the agent understands your labeling system and project domain.

## 🚀 Quick Start

1.  **Prepare your transcript**: Save your raw text to `avs-standard-library/value-stories/project-mgmt/backlog-intake/inputs/transcript.txt`.

2.  **Run Triage**:
    ```bash
    uv run avs run avs-standard-library/value-stories/project-mgmt/backlog-intake/value-stories/vs-001-backlog-triage.md
    ```

3.  **Run Drafting**:
    ```bash
    uv run avs run avs-standard-library/value-stories/project-mgmt/backlog-intake/value-stories/vs-002-issue-drafting.md
    ```

4.  **REVIEW**: Inspect `avs-standard-library/value-stories/project-mgmt/backlog-intake/outputs/issues-to-create.md`.

5.  **Run Publication**:
    ```bash
    uv run avs run avs-standard-library/value-stories/project-mgmt/backlog-intake/value-stories/vs-003-issue-publication.md
    ```

---
*Framework by Patrick Heaney. Part of the AVS Standard Library.*