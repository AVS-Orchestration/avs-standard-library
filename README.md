# AVS Standard Library

Welcome to the canonical collection of Value Stories for the Agentic Value Stream (AVS) framework.

This repository serves as a community resource and "Standard Library" of algorithmically legible work units. It is designed to be used in conjunction with the AVS Toolkit.

## 📂 Repository Structure

- `/value-stories`: Sanitized, production-ready Value Stories for various industries.

    - `/job-hunting`: Resumes, Cover Letters, and Interview Prep.

    - `/speech-2-value-story`: **The Meta-Architect**. A workflow to convert raw voice transcripts into valid AVS Value Stories automatically.

    - `/research`: Market analysis and data synthesis.

- `/templates`: Blank YAML and Markdown templates for creating your own stories.

## 🚀 How to Use

The AVS Toolkit allows you to run these stories directly from GitHub without cloning this repository.

### 1. Identify a Story

Browse the /stories folder and find a story you'd like to use. Copy its Raw URL.

### 2. Run with AVS

From your terminal, use the avs global command:

```
# Assemble the context (The Information Hunt)
avs assemble [https://github.com/AVS-Orchestration/standard-library/blob/main/stories/job-hunting/tailor-resume.md](https://github.com/AVS-Orchestration/standard-library/blob/main/stories/job-hunting/tailor-resume.md)

# Execute the stream
avs run VS-001-assembled.yaml
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
