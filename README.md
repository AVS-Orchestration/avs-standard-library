# AVS Standard Library

Welcome to the canonical collection of Value Stories for the Agentic Value Stream (AVS) framework.

This repository serves as a community resource and "Standard Library" of algorithmically legible work units. It is designed to be used in conjunction with the AVS Toolkit.

## 📂 Repository Structure

- '/stories': Sanitized, production-ready Value Stories for various industries.

    - '/job-hunting': Resumes, Cover Letters, and Interview Prep.

    - '/research': Market analysis and data synthesis.

    - '/coding': Code reviews and architectural planning.

- '/templates': Blank YAML and Markdown templates for creating your own stories.

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

1. Install the [AVS Toolkit](https://github.com/AVS-Orchestration/avs-toolkit).

2. Run 'avs doctor' to verify your environment (Node.js, uv, and API keys).

## 🤝 Contributing

We welcome community contributions! If you have built a Value Story that solves a specific business problem:

1. **Sanitize**: Ensure no PII or absolute local paths are present.

2. **Template**: Follow the AVS "Building Code" (Schema v1.0).

3. **PR**: Open a Pull Request into the /stories directory.

## 📜 License

This library is licensed under **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**.

Privacy Note: While the structure of these stories is public, the data you populate into them remains your proprietary content. See the [LICENSE](https://github.com/AVS-Orchestration/avs-toolkit/blob/main/LICENSE.md) in the main toolkit for the "Empty Container" principle.
