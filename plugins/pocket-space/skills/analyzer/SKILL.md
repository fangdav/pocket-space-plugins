---
name: analyzer
description: >
  This skill should be used when the user asks to "compare options", "analyze alternatives",
  "build a comparison matrix", "which option is best", "evaluate these against each other",
  "score these options", "rank these", or needs a structured side-by-side evaluation of
  multiple options across defined criteria. Produces a comparison matrix in either .md or
  .xlsx format based on user preference.
---

# Analyzer

Compare a wide array of options across carefully selected criteria using a structured matrix. Designed to turn fuzzy "which is better?" questions into clear, evidence-based side-by-side evaluations.

## When to Use

- User needs to choose between multiple options (tools, strategies, markets, vendors, approaches)
- A research file or deep dive has surfaced several alternatives that need ranking
- Any decision that benefits from structured multi-criteria comparison

## Relationship to Other Research Skills

The Analyzer can work standalone or as part of the research workflow:
- Typically follows **research-md-maker** — takes the segments from a broad landscape scan and ranks them
- Typically feeds into **deep-researcher** — the top-ranked options become candidates for deep dives
- If source research files exist, the analyzer must **hyperlink to them** in the output

## Execution Flow

### Step 1: Identify the Options

Ask the user:
- What are you comparing? (products, strategies, markets, tools, approaches, etc.)
- Do you already have a list, or should I pull options from an existing research file?

If pulling from existing research:
1. Locate the relevant .md file(s) in the shared drive
2. Extract the options/segments listed
3. Present them to the user for confirmation

Aim for **4-12 options** — enough for meaningful comparison, not so many the matrix becomes unreadable.

### Step 2: Select Criteria

This is the most important step. Propose criteria that are:
- **Relevant** to the decision at hand
- **Differentiating** — criteria where options actually vary (skip criteria where everything scores the same)
- **Measurable** — each criterion can be assessed with evidence, not just gut feeling
- **Balanced** — cover multiple dimensions, not just one angle

Criteria selection strategies (use whichever fit):

| Dimension | Example Criteria |
|---|---|
| **Financial** | Cost, revenue potential, ROI, funding required, unit economics |
| **Technical** | Complexity, scalability, integration effort, maintenance burden |
| **Market** | Market size, growth rate, competition intensity, timing |
| **User** | Ease of use, adoption barrier, retention potential, NPS |
| **Strategic** | Alignment with vision, defensibility, network effects, optionality |
| **Risk** | Regulatory risk, execution risk, dependency risk, reversibility |
| **Operational** | Time to implement, team capability, resource requirements |
| **Competitive** | Differentiation, barriers to entry, incumbent strength |

Propose **5-10 criteria** and present them to the user for confirmation. Explain why each was chosen.

### Step 3: Ask Output Format

Before building the matrix, ask the user:
- **Markdown (.md)** — Good for quick reference, lives alongside research files, easy to scan
- **Excel (.xlsx)** — Good for sorting, filtering, weighted scoring, sharing with stakeholders

### Step 4: Score and Build the Matrix

For each option × criterion cell:

1. **Research the answer** — Use web search, existing .md files, or the user's input
2. **Assign a score** — Use a consistent scale:
   - **Qualitative:** Low / Medium / High
   - **Numeric:** 1-5 scale (1 = worst, 5 = best)
   - Ask the user which scoring style they prefer
3. **Add a brief justification** — One line explaining why this score, with a citation where possible

### Step 5: Produce the Output

#### Markdown Format (.md)

```markdown
# [Topic] — Comparison Matrix

**Author:** [Name]
**Date:** [YYYY-MM-DD]
**Source Research:** [Hyperlink to parent research .md file(s) if applicable]

## Context

[1-2 sentences. What decision is this matrix informing? Link to relevant research files.]

## Criteria Definitions

| # | Criterion | Why It Matters | Scale |
|---|---|---|---|
| 1 | [Name] | [One-line rationale] | 1-5 |
| 2 | [Name] | [One-line rationale] | 1-5 |
| ... | ... | ... | ... |

## Comparison Matrix

| Option | Criterion 1 | Criterion 2 | Criterion 3 | ... | Total |
|---|---|---|---|---|---|
| [Option A] | 4 | 3 | 5 | ... | [Sum] |
| [Option B] | 2 | 5 | 3 | ... | [Sum] |
| [Option C] | 5 | 2 | 4 | ... | [Sum] |

## Justifications

### [Option A]
| Criterion | Score | Rationale |
|---|---|---|
| [Criterion 1] | 4 | [One-line explanation with citation] [1] |
| [Criterion 2] | 3 | [One-line explanation] [2] |

### [Option B]
[Same structure]

...

## Summary

**Top ranked:** [Option] with a score of [X]
**Runner-up:** [Option] with a score of [X]

### Caveats
- [Any important nuance the scores don't capture]
- [Criteria that were close calls]
- [What would change the ranking]

## References

[Vancouver style]
[1] Author. Title. Source. Year. URL.
[2] ...
```

#### Excel Format (.xlsx)

Create a workbook with three sheets:

**Sheet 1: Matrix**
- Row 1: Headers (Option | Criterion 1 | Criterion 2 | ... | Total)
- Rows 2+: One row per option with scores
- Final column: SUM formula for total score
- Conditional formatting: color scale (red=1, yellow=3, green=5)

**Sheet 2: Justifications**
- Columns: Option | Criterion | Score | Rationale | Source
- One row per option × criterion combination

**Sheet 3: Criteria Definitions**
- Columns: # | Criterion | Why It Matters | Scale
- Documents what each criterion means and how it's scored

### Step 6: File Placement

Comparison matrices live inside the `Research/` folder of the topic folder.

- If a topic folder structure exists (`[Topic_of_Research]/Research/`), place the matrix there:
  ```
  [Topic_of_Research]/
  ├── [Topic_of_Research].docx
  └── Research/
      ├── README.md
      ├── Landscape_Research.md
      ├── [Topic]_Comparison_Matrix.md   ← or .xlsx — goes here
      ├── Segment_A/
      │   └── Segment_A_Deep_Dive.md
      └── ...
  ```
- If the matrix is comparing options within a specific segment, place it inside that segment's subfolder within `Research/`
- If no topic folder exists yet, create the structure:
  ```
  [Department_Folder]/
  └── [Topic_of_Research]/
      └── Research/
          ├── README.md
          └── [Topic]_Comparison_Matrix.md
  ```
- Name: `[Topic]_Comparison_Matrix.md` or `[Topic]_Comparison_Matrix.xlsx`
- Follow naming conventions: underscores, descriptive name
- Follow author sign-off rules from contribution guidelines
- Update the `Research/README.md` to reflect the new file

### Step 7: Hyperlinks

1. **Link to source research files** — If the options came from a research-md-maker or deep-researcher file, hyperlink to it in the header and Context section (use relative paths within the `Research/` folder)
2. **Link from source file back** — Update the parent research .md to add a note: `See also: [Topic_Comparison_Matrix.md](link)` or `[Topic_Comparison_Matrix.xlsx](link)`
3. **Cross-link deep dives** — If any options have deep-dive documents in segment subfolders, link to them in the Justifications section

## Sources & Citations (Vancouver Style)

Use **Vancouver citation style** — numbered references in order of first appearance.

**Rules:**
- Every score justification should cite its source where possible
- Scores based on the author's judgment must be marked `[Author's assessment]`
- Numbers assigned in order of first appearance
- Prefer quantitative sources (market data, benchmarks, metrics) over opinion
- Include URLs for all web-accessible sources
