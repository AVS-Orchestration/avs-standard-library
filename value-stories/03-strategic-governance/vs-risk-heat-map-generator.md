# vs-risk-heat-map-generator.md

## Metadata
```yaml
metadata:
  story_id: "VS-XXX"
  version: "0.1"
  author: "AVS Strategy"
  target_persona: "The Director (Jordan)"
```

## THE GOAL: The "North Star" for the Agentic-Agent
```yaml
goal:
  as_a: "The Director (Jordan)"
  i_want: "Ingest Status Reports -> Aggregate risks into a portfolio view. Visualize the 'Diagonal Threads.'"
  so_that: "I can achieve the specific outcome defined in the strategy."
```

## INSTRUCTIONS: The Core Algorithm (Execution Logic)
```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "[TODO: Define step 1]"
      validation_rule: "[TODO: Define validation for step 1]"
    - step: 2
      action: "[TODO: Define step 2]"
      validation_rule: "[TODO: Define validation for step 2]"
```

## CONTEXT MANIFEST
```yaml
context_manifest:
  - key: "input_data"
    description: "The primary input for this story."
    default_path: "./inputs/sample.txt"
```

## PRODUCT
```yaml
product:
  type: "Document/Report"
  format: "Markdown"
  output_path: "./outputs/"
```
