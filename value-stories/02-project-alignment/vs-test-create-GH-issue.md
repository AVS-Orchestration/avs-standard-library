# VS-GH-ISSUE-TEST: GitHub Issue Creation Test

## Metadata
```yaml
metadata:
  story_id: "vs-test-create-GH-issue"
  version: "1.0"
  author: "AVS Agent"
  provider: "ollama"
  preferred_model: "llama3"
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
  as_a: "System Integration Tester"
  i_want: "To verify that the internal GitHub MCP tool can successfully create a new issue in the avs-toolkit repository."
  so_that: "I can automate the creation of tasks and bug reports directly from my value streams."
```

## INSTRUCTIONS: The Core Algorithm (Execution Logic)
```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Use the 'create_github_issue' tool to post a new issue."
      validation_rule: "The tool returns a SUCCESS message with a URL to the created issue."
```

## CONTEXT MANIFEST: The "Bill of Materials" for the Information Hunt
```yaml
context_manifest:
  - key: "issue_creation_result"
    description: "The result of creating a test issue on GitHub."
    mcp_tool_name: "create_github_issue"
    mcp_tool_args:
      owner: "AVS-Orchestration"
      repo: "avs-toolkit"
      title: "AVS MCP Integration Test: Issue Creation"
      body: "This is an automated test issue created by the AVS Toolkit to verify MCP GitHub tool functionality. Date: 2026-01-05."
      labels: ["test", "integration"]
```

## PRODUCT: The expected deliverable
```yaml
product:
  type: "Test Report"
  format: "Markdown"
  output_path: "avs-standard-library/value-stories/project-mgmt/vs-test-create-GH-issue-output.md"
```
