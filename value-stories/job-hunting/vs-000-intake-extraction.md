# VS-000: Intake & Extraction

**ARCHITECT'S GUIDE: VS-000**
This is the "Entry Gate" for the Resume Tailoring Stream. It uses an ephemeral Firecrawl MCP server to scrape a job URL and extract the fundamental identity of the opportunity.

```yaml
metadata:
  story_id: "VS-000"
  version: "1.5"
  author: "Patrick Heaney"
  repository: "https://github.com/AVS-Orchestration/avs-toolkit"
  license: "CC BY-SA 4.0"
  status: "active"
  preferred_model: "llama3"
```

```yaml
mcp_servers:
  - name: "firecrawl"
    command: "npx"
    args: ["-y", "firecrawl-mcp"]
```

```yaml
goal:
  as_a: "As a Career Intake Specialist"
  i_want: >
    A professsionally formatted markdown Job Research Report.  List the target URL, 
    the comapny's official name, headquarters, scale, and mission statement, job title, and full job description
  so_that: >
    1. I have a human readable copy for my records
    2. The Agentic Value Stream has a grounded "Source of Truth" and a direct link back to the original job description for subsequent steps in producing a tailored resume.
```

```yaml
instructions:
  reasoning_pattern: "Chain-of-Thought"
  execution_steps:
    - step: 1
      action: "Review the `company_profile_search` asset and extract the Scale (Employees), Presence (HQ Address), and the Strategic Mission Statement."
      validation_rule: "The corporate data points are extracted; use 'Not Provided' if missing."
    - step: 2
      action: "Synthesize the company profile findings into a Job-Report starting the 'Target URL' followed by a heading of '## Company Profile'. Ensure  is displayed prominently at the top of the report."
      validation_rule: >
        The report is professionally formatted in Markdown with the URL included and it clearly lists 
        1. The official name of the hiring company.
        2. The mailing address for their corporate headquarters.
        3. The approximate global employee headcount.
        4. The company's official Mission Statement or stated core purpose.
    - step: 3
      action: "Review the 'job-description' asset. Note that it is a JSON object. Locate the 'markdown' field within it; this contains the full, raw job posting text."
      validation_rule: "The JSON is parsed and the 'markdown' field is identified for extraction."
    - step: 4
      action: "Append to the Job-Report a heading '## Full Job Description'. Under this heading, reproduce the content of the 'markdown' field from Step 3 VERBATIM. Do NOT summarize. Do NOT omit sections. Output the text exactly as it appears in the source, stripped only of JSON curly braces and quotes."
      validation_rule: "The full, un-summarized job posting is included in the output."
```

```yaml
context_manifest:
  - key: "company_profile_search"
    description: "Corporate and posting data retrieved via Google Search grounding."
    search_query: >
      Target URL: https://careers.oracle.com/en/sites/jobsearch/jobs/preview/316074

      Please research and provide a summary containing:
      1. The official name of the hiring company.
      2. The mailing address for their corporate headquarters.
      3. The approximate global employee headcount.
      4. The company's official "Mission Statement" or stated core purpose.
  - key: "job-description"
    description: "Corporate and posting data retrieved via Firecrawl MCP tool."
    mcp_tool_name: "firecrawl_scrape"
    mcp_tool_args:
      url: "https://careers.oracle.com/en/sites/jobsearch/jobs/preview/316074"
      formats: ["markdown"]
      onlyMainContent: true
```

```yaml
product:
  type: "Document"
  format: "Markdown"
  output_path: "my-job-hunt/outputs/01-open/Oracle_TPgM_Cloud-Apps/job-description.md"
```
