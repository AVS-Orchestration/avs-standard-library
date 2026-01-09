# AVS Standard Library

Welcome to the canonical collection of Value Stories for the Agentic Value Stream (AVS) framework.

This repository serves as a community resource and "Standard Library" of algorithmically legible work units. It is designed to be used in conjunction with the AVS Toolkit.

## 📂 Repository Structure

The library is organized by **"Jobs to be Done"** rather than industry verticals, mapping directly to functional personas within an organization:

- **`/value-stories`**
  - **`01-personal-productivity`**: *Target: The Individual Contributor (Alex)*. Quick wins for reclaiming time (e.g., meeting synthesis, email drafting).
  - **`02-project-alignment`**: *Target: The TPM (Alex)*. Automation for status reporting, dependency mapping, and blocker analysis.
  - **`03-strategic-governance`**: *Target: The Director (Jordan)*. Portfolio-level visibility, risk heat maps, and resource modeling.
  - **`04-executive-briefing`**: *Target: The Executive (Casey)*. High-velocity decision support and market intelligence.
  - **`05-career-management`**: *(Legacy/Specialized)* Tools for job hunting and career development.
  - **`99-meta-tools`**: Builders, compilers, and generators for creating other Value Stories.

- **`/templates`**: Blank YAML and Markdown templates for creating your own stories.

## 🚀 How to Use

The AVS Standard Library is designed to be referenced, not modified.

### Try the "Hello World" Story

If you are new to AVS, start with the **Meeting Minute Synthesis**:

```bash
# Example: Running the 'Hello World' story
# Note: This example assumes your project folder and the library are siblings.
# If your setup differs, replace the relative path with the full path to the file.
cd my-avs-workspace/my-active-project
avs run ../avs-standard-library/value-stories/01-personal-productivity/vs-meeting-minute-synthesis.md

# Generic Syntax:
# avs run <path-to-library>/value-stories/01-personal-productivity/vs-meeting-minute-synthesis.md
```

### General Usage

1.  **Clone this repo** into your **AVS Private Workspace** (alongside the toolkit).
2.  **Reference templates** using their relative path from your active project folder.

```bash
# Example: Running a standard story from your private project folder
cd my-avs-workspace/my-active-project
avs run ../avs-standard-library/value-stories/05-career-management/vs-resume-tailor.md
```

## 🛠 Prerequisites

To execute these stories, ensure your workstation is AVS-ready:

1. Install the [AVS Toolkit](https://github.com/AVS-Orchestration/avs-toolkit), per the [Guide-Setup-for-Non-Developers](https://github.com/AVS-Orchestration/avs-toolkit/blob/main/docs/Guide-Setup-for-Non-Developers.md).

2. Create a `.env` file in the root of your project folder (where you run the commands) and add your required API keys (e.g., `GEMINI_API_KEY`, `TAVILY_API_KEY`, `FIRECRAWL_API_KEY`).

3. Run `avs doctor` to verify your environment (Node.js, uv, and API keys).

## 🤝 Contributing

We welcome community contributions! If you have built a Value Story that solves a specific business problem:

1. **Sanitize**: Ensure no PII or absolute local paths are present.

2. **Template**: Follow the AVS "Building Code" (Schema v1.0).

3. **PR**: Open a Pull Request into the /stories directory.

## 📜 License

This library is licensed under **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**.

Privacy Note: While the structure of these stories is public, the data you populate into them remains your proprietary content. See the [LICENSE](https://github.com/AVS-Orchestration/avs-toolkit/blob/main/LICENSE.md) in the main toolkit for the "Empty Container" principle.
