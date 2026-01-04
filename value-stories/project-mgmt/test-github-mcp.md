# VS-GHTEST: GitHub MCP Tool Test

## Metadata
```yaml
metadata:
  story_id: "VS-GH-ISSUE"
  provider: "ollama"
  preferred_model: "llama3"
```

## THE MCP MANIFEST
```yaml
mcp_servers:
  - name: "internal-github"
    command: "python"
    args: ["avs-toolkit/src/avs_toolkit/github_mcp.py"]
```

## THE GOAL
```yaml
goal:
  as_a: "System Integration Tester"
  i_want: "To verify that the internal GitHub MCP tool can successfully fetch a file from a public repository."
  so_that: "I can use remote GitHub assets as context for my value streams."
```

## INSTRUCTIONS
```yaml
instructions:
  execution_steps:
    - step: 1
      action: "Review the 'fetched_file' asset and summarize its contents in exactly two sentences."
      validation_rule: "The summary is accurate and follows the length constraint."
```

## CONTEXT MANIFEST
```yaml
context_manifest:
  - key: "fetched_file"
    description: "The README from the AVS Toolkit repo."
    mcp_tool_name: "fetch_github_file"
    mcp_tool_args:
      owner: "AVS-Orchestration"
      repo: "avs-toolkit"
      path: "README.md"
```

## PRODUCT
```yaml
product:
  type: "Test Report"
  format: "Markdown"
  output_path: "my-job-hunt/outputs/tests/github-mcp-test.md"
```
