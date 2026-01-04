# VS-001: Backlog Triage & Extraction

## Metadata

```yaml
metadata:
  story_id: "VS-001"
  version: "1.0"
  author: "AVS Standard Library"
  provider: "ollama"
  preferred_model: "qwen2.5-coder:32b"
```

## THE MCP MANIFEST: Defines ephemeral servers

```yaml
mcp_servers:
  - name: "internal-github"
    command: "python"
    args: ["avs-toolkit/src/avs_toolkit/github_mcp.py"]
```

## THE GOAL: The "North Star" for the Agentic-Agent

```yaml
goal:
  as_a: "Technical Project Manager"
  i_want: >
    Analyze a raw discussion transcript and extract one or more structured GitHub Issues. 
    Each issue must include a concise title, detailed description, categorized issue type (Bug, Feature, Task), 
    and a list of relevant labels.
  so_that: >
    Raw human intent is converted into actionable, well-defined work items that can be 
    seamlessly transitioned into a technical backlog.
```

## INSTRUCTIONS: The Core Algorithm (Execution Logic)

```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Review the 'transcript' asset and the target 'repository_context' (if provided). Identify distinct requests, bug reports, or feature ideas mentioned by the stakeholders."
      validation_rule: "A mental list of independent work items is formed."

    - step: 2
      action: "For each identified item, determine the appropriate 'Issue Type' based on the definitions in the provided template assets (`template_issue`, `template_user_story`) or standard GitHub conventions."
      validation_rule: "Every item is categorized correctly."

    - step: 3
      action: "Draft a high-fidelity 'GitHub Issue Proposal' for each item. 
        Format:
        ### [Issue Type]: [Concise Title]
        **Description**: [Detailed technical or business summary]
        **Acceptance Criteria**: [Bullet points defining success]
        **Labels**: [Suggested labels based on the repo context]"
      validation_rule: "Proposals are drafted with sufficient detail for a developer to understand."

    - step: 4
      action: "Compile all proposals into a single Markdown report. Use '## Issue X' headers for each proposal."
      validation_rule: "The final report is well-structured and contains all extracted items."
```

## CONTEXT MANIFEST: The "Bill of Materials" for the Information Hunt

```yaml
context_manifest:
  - key: "transcript"
    description: "The raw text of the backlog discussion or meeting notes."
    default_path: "avs-standard-library/value-stories/project-mgmt/backlog-intake/inputs/transcript.txt"

  - key: "repository_context"
    description: "Repo README."
    mcp_tool_name: "fetch_github_file"
    mcp_tool_args:
      owner: "AVS-Orchestration"
      repo: "avs-toolkit"
      path: "README.md"

  - key: "template_issue"
    description: "The General Issue template."
    mcp_tool_name: "fetch_github_file"
    mcp_tool_args:
      owner: "AVS-Orchestration"
      repo: "avs-toolkit"
      path: ".github/ISSUE_TEMPLATE/issue.md"

  - key: "template_user_story"
    description: "The User Story template."
    mcp_tool_name: "fetch_github_file"
    mcp_tool_args:
      owner: "AVS-Orchestration"
      repo: "avs-toolkit"
      path: ".github/ISSUE_TEMPLATE/user-story.md"
```

## PRODUCT: The expected deliverable

```yaml
product:
  type: "Triage Report"
  format: "Markdown"
  output_path: "avs-standard-library/value-stories/project-mgmt/backlog-intake/outputs/vs-001-extracted-issues.md"
```
