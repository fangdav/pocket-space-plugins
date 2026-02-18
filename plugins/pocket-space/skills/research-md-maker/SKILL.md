---
name: research-md-maker
description: >
  This skill should be used when the user asks to "research a topic", "create a research doc",
  "explore options for X", "what are the different approaches to X", "write up research on X",
  or needs a broad landscape scan on any subject. Produces a concise, well-segmented .md research
  file covering a diverse range of options, approaches, or findings.
---

# Research MD File Maker

Create a well-segmented markdown research file that covers a topic broadly and diversely. Writing is parsimonious — no filler, no padding, every sentence earns its place.

## Writing Style

- **Parsimonious.** Short sentences. No throat-clearing. Cut any word that doesn't add information.
- **Direct.** Lead with the finding, not the setup. State what IS, not what "it is important to note that."
- **Factual.** Cite sources where possible. Flag speculation as speculation.
- **Scannable.** Use headers, bullets, and bold keywords so a reader can skim in 30 seconds.

## Execution Flow

### Step 1: Clarify Scope

Ask the user:
- What topic or question to research?
- Any constraints? (geography, budget, timeline, industry)
- What is this research for? (decision-making, background knowledge, a specific deliverable)

### Step 2: Cast a Wide Net

Before writing, brainstorm the broadest possible landscape of segments. The goal is diversity and coverage — not depth yet.

Segmentation strategies to consider (use whichever fit the topic):
- By category or type
- By geography or market
- By size or scale (enterprise vs SMB vs individual)
- By approach or methodology
- By stage or maturity (emerging vs established vs declining)
- By stakeholder or user type
- By price tier or business model
- By technology or platform
- By use case or application
- By risk profile or trade-off

Present the proposed segments to the user for confirmation before writing. Aim for **6-12 clean, non-overlapping segments** that collectively cover the full landscape.

### Step 3: Write the Research File

Structure:

```markdown
# [Topic] Research

**Author:** [Name]
**Date:** [YYYY-MM-DD]

## Overview

[2-3 sentences framing the topic and why it matters. State the research question.]

## Landscape

[One paragraph summarizing the full range of what exists. Set up the segments.]

## [Segment 1 Name]

**What it is:** [1-2 sentences]
**Key players/examples:** [Names, links if available]
**Strengths:** [Bullets]
**Weaknesses:** [Bullets]
**Relevance to Pocket Space:** [1 sentence — how this connects]

## [Segment 2 Name]
[Same structure]

...

## Key Takeaways

- [3-5 bullets distilling the most important findings]

## Open Questions

- [What this research didn't answer]
- [What needs deeper investigation]

## Sources

- [List of sources used]
```

### Step 4: File Placement

- If a topic folder with a `Research/` subfolder already exists for this topic, place the .md file inside `Research/` (or a nested subfolder within it)
- If this is the start of a new research effort that will eventually produce a .docx deliverable, create the topic folder structure:
  ```
  [Department_Folder]/
  └── [Topic_of_Research]/
      └── Research/
          ├── README.md
          └── [Topic]_Research.md   ← This file goes here
  ```
  The .docx will be added later by the research-synthesizer skill at the top level of the topic folder.
- If this is standalone research with no planned .docx, place it directly in the appropriate department research folder
- Name: `[Topic]_Research.md` using underscore convention
- Follow naming conventions from contribution guidelines

## Sources & Citations (Vancouver Style)

All research files use **Vancouver citation style** — numbered references in order of first appearance.

**Inline:** Use superscript or bracketed numbers in the text where a claim is made.
- Example: `Bonding curves were first proposed in 2017 [1] and later adopted in DeFi protocols [2].`

**Reference list:** A numbered `## References` section at the end of the document.
- Format: `[Number] Author(s). Title. Source/Publication. Year. URL (if applicable).`
- Example:
  ```
  ## References
  [1] de la Rouviere S. Tokens 2.0: Curved token bonding. Medium. 2017. https://example.com
  [2] Zargham M. An introduction to bonding curves. BlockScience. 2019. https://example.com
  ```

**Rules:**
- Every factual claim, statistic, or finding must have a numbered citation
- Numbers are assigned in order of first appearance in the text
- If a finding cannot be sourced, explicitly mark it as `[Author's analysis]`
- Prefer primary sources over secondhand summaries

## Segment Quality Checklist

Before finalizing segments, verify:
- [ ] Segments are **mutually exclusive** — no overlap
- [ ] Segments are **collectively exhaustive** — no major gap in coverage
- [ ] At least one segment is **unconventional** — something the user might not have considered
- [ ] Each segment can stand alone as a meaningful category
- [ ] Segments are at roughly the **same level of abstraction**
