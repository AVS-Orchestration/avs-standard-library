Here is the generated AVS Value Story (.md) file:

# VS-000: Template for New Value Stories

```txt
# ARCHITECT'S GUIDE: How to use this template
# 1. Provide a Story ID (VS-XXX) in the title above.
# 2. Fill in the 'goal' with a statement longer than 20 characters.
# 3. List at least 2 'execution_steps' with specific 'validation_rules'.
# 4. Define your 'context_manifest' using local paths or MCP URIs.
```

## Metadata

```yaml
metadata:
  story_id: "VS-000"
  version: "1.5"
  author: "Patrick Heaney"
  preferred_model: "llama3"
```

## THE GOAL: The "North Star" for the Agentic-Agent

```yaml
goal:
  as_a: "As a job applicant"
  i_want: >
    I need a value story that intakes a job description, strategy document, and a resume, and writes a cover letter to go with the resume in my application.
  so_that: >
    The agent understands the business value and rationale behind creating a compelling cover letter for my job application.
```

## INSTRUCTIONS: The Core Algorithm (Execution Logic)

```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Review the raw JSON asset containing the job description, strategy document, and resume. Extract the relevant information for the cover letter."
      validation_rule: "The JSON is successfully parsed and the necessary information is identified."
    - step: 2
      action: "Write a compelling cover letter based on the extracted information, highlighting my qualifications and enthusiasm for the position."
      validation_rule: "The cover letter is well-written and effectively communicates my value proposition to the hiring manager."
    - step: 3
      action: "Create a heading '# Cover Letter' and include the written cover letter as the output."
      validation_rule: "The cover letter is included in the output, formatted correctly, and ready for submission with my resume."
```

## CONTEXT MANIFEST: The "Bill of Materials" for the Information Hunt

```yaml
context_manifest:
  - key: "job_description"
    description: "The job posting or requirements document."
    default_path: "path/to/job_description.md"

  - key: "strategy_document"
    description: "A company strategy or vision statement."
    default_path: "path/to/strategy_document.pdf"

  - key: "resume"
    description: "My professional resume."
    default_path: "path/to/my_resume.pdf"
```

## PRODUCT: The expected deliverable

```yaml
product:
  type: "Document"
  format: "Markdown"
  output_path: "template-test-results/"
```

This generated AVS Value Story (.md) file follows the 'vs-000-template.md' structure and is ready for execution.