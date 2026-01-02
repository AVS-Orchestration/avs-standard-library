# VS-001 Analysis & Strategy

ARCHITECT'S GUIDE: VS-001
This story extracts the "Winning Strategy" by mapping candidate history to the specific semantic requirements of a job description.

```yaml
metadata:
  story_id: "VS-001"
  version: "1.2"
  author: "Patrick Heaney"
  repository: "https://github.com/AVS-Orchestration/avs-toolkit"
  license: "CC BY-SA 4.0"
  status: "active"
  provider: "ollama"
  preferred_model: "llama3"
```

```yaml
# THE GOAL: The "North Star" for the Agentic-Agent.
goal:
  as_a: "As a Senior Career Strategist"
  i_want: >
    A professsionally formatted markdown Job Strategy Report that Identifies key skills, experiences, and keywords from the job description and raw resume, and generate a high-fidelity Strategic Alignment Matrix.
    - Requirement 1: Identify at least 5 key skills/keywords from the job description.
    - Requirement 2: Map at least 3 specific candidate achievements to these skills.
  so_that: >
    The candidate has a clear blueprint for alignment that maximizes their 
    competitiveness for the specific role and eliminates "Context Blindness."
```

```yaml
# INSTRUCTIONS: Must be "Algorithmically Legible."
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Review the 'job_description' to understand the target company's mission, scale, and headquarters location."
      validation_rule: "Corporate context is successfully integrated into the strategy session."
    - step: 2
      action: "Parse provided `job description` to extract required skills, keywords, responsibilities, and company culture cues."
      validation_rule: "List of extracted requirements is comprehensive and accurate."
    - step: 3
      action: "Parse provided candidate's raw resume to identify relevant experience, education, achievements, and technical proficiencies."
      validation_rule: "List of candidate's relevant attributes is comprehensive and accurate."
    - step: 4
      action: "Perform a detailed gap analysis comparing job requirements with candidate attributes."
      validation_rule: "Gap analysis report highlights crucial alignment points and discrepancies."
    - step: 5
      action: "Synthesize a strategic plan for tailoring the resume into a Job-Strategy, including prioritization of content and specific keywords."
      validation_rule: "Strategic plan is human readible, actionable, and acurately addresses the job requirement."
  constraints:
    - "You MUST NOT invent, embellish, or infer any new facts outside of the sources."
    - "Output must be formatted as a professsionally formatted markdown Job Strategy Report."
```

```yaml
# CONTEXT MANIFEST: The "Bill of Materials" for this Value Story.
context_manifest:
  - key: "job_description"
    description: "The full text of the target job description and company metadata."
    default_path: "my-job-hunt/outputs/01-open/Oracle_TPgM_Cloud-Apps/job-description.md"
  - key: "raw_resume"
    description: "The candidate's original, untailored resume."
    default_path: "my-job-hunt/inputs/raw_resume.md"
```

```yaml
# PRODUCT: The expected deliverable.
product:
  type: "Document"
  format: "Markdown"
  output_path: "my-job-hunt/outputs/01-open/Oracle_TPgM_Cloud-Apps/job-strategy.md"
  handoff_target: "VS-002-resume-generation"
```
