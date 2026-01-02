# VS-001: Speech to Value Story Compiler

## Metadata

```yaml
metadata:
  story_id: "VS-001"
  version: "1.0"
  author: "AVS Standard Library"
  provider: "ollama"
  preferred_model: "llama3"
```

## THE MCP MANIFEST: Defines ephemeral servers

```yaml
mcp_servers: []
```

## THE GOAL: The "North Star" for the Agentic-Agent

```yaml
goal:
  as_a: >
    "AVS Solution Architect"
  i_want: >
    Analyze a raw 'Discovery Interview' transcript and compile it into a valid, executable AVS Value Story (.md) that strictly follows the 'vs-000-template.md' structure.
  so_that: >
    Non-technical users can simply 'speak' their intentions (via the interview) and have them automatically converted into precise, algorithmically legible agent instructions without learning YAML syntax.
```

## INSTRUCTIONS: The Core Algorithm (Execution Logic)

```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Analyze the 'transcript' asset. Extract the user's answers regarding the 'Goal' (The Why), 'Inputs' (Context), 'Process' (Instructions), and 'Output' (Product)."
      validation_rule: "The 4 core components of the user's intent are clearly identified."
    - step: 2
      action: "Map the extracted intent into the 'vs_template' structure:
        1. Map 'Goal' answers to the 'goal:' YAML block (as_a, i_want, so_that).
        2. Map 'Inputs' to the 'context_manifest:' YAML block (key, description, default_path).
        3. Map 'Process' to the 'instructions:' YAML block (create logical execution_steps).
        4. Map 'Output' to the 'product:' YAML block."
      validation_rule: "Every piece of the user's intent is mapped to a valid field in the template schema."
    - step: 3
      action: "Generate the final Markdown file. Ensure it includes the standard headers (# VS-XXX...) and correctly formatted YAML code blocks. Do not summarize the template structure; preserve the YAML syntax exactly."
      validation_rule: "The output is a valid Markdown file that would pass 'avs validate'."
```

## CONTEXT MANIFEST: The "Bill of Materials" for the Information Hunt

```yaml
context_manifest:
  - key: "transcript"
    description: "The raw text of the Discovery Interview containing the user's answers."
    default_path: "avs-standard-library/value-stories/speech-2-value-story/paste-transcript-in-here.md"
  - key: "vs_template"
    description: "The official AVS Building Code template that defines the required structure."
    default_path: "avs-standard-library/templates/vs-000-template.md"
```

## PRODUCT: The expected deliverable

```yaml
product:
  type: "Value Story"
  format: "Markdown"
  output_path: "avs-standard-library/value-stories/speech-2-value-story/vs-xxx-your-vs.md"
```
