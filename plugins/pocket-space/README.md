# Pocket Space Plugin

Plugin for contributing to the Pocket Space shared drive. Enforces folder conventions, file format rules, naming standards, citation requirements, and README maintenance. Includes a full research workflow — from broad landscape scans to deep dives, comparison matrices, synthesized deliverables, and comment review.

## Skills

### Foundation
- **contribution-guidelines** — Universal rules for contributing: file formats, naming conventions, author sign-off, README standards, the research folder rule for .docx deliverables, and before/after change checklists. Activates whenever files are created or modified.
- **folder-navigation** — Map of the entire shared drive structure with a routing guide for where different content types belong. Includes the research topic folder pattern.

### Research Workflow
These skills form a pipeline, each feeding into the next:

1. **research-md-maker** — Broad landscape research. Casts a wide net across diverse segments (6-12), confirms with the user, then produces a concise, parsimonious .md file with Vancouver citations. Start here.
2. **analyzer** — Structured comparison matrix. Takes the segments from step 1, evaluates them across 5-10 criteria, scores them, and produces a table in .md or .xlsx format (user's choice). Surfaces the top options.
3. **deep-researcher** — Drill into the top-ranked options from the analyzer. Produces thorough, standalone deep-dive .md files with case studies, data, and detailed analysis for each selected segment.
4. **research-synthesizer** — Pull it all together into a final .docx deliverable. Reads across all the .md files from steps 1-3 and produces a unified document. Creates the topic folder structure with a `Research/` subfolder containing all source files.
5. **comment-reviewer** — Process feedback from teammates. Reads comments and tracked changes left by others on the .docx, categorizes by priority and type, and produces an actionable editing guide .md inside the `Research/` folder.

## Research Topic Folder Pattern

When research produces a .docx deliverable, everything lives in a self-contained topic folder:

```
[Department_Folder]/
└── [Topic_of_Research]/
    ├── [Topic_of_Research].docx
    └── Research/
        ├── README.md
        ├── Landscape_Research.md
        ├── Comparison_Matrix.md
        ├── Comment_Review.md
        ├── Segment_A/
        │   ├── Segment_A_Deep_Dive.md
        │   └── Sub_Topic/
        │       └── Sub_Topic_Research.md
        └── Segment_B/
            └── Segment_B_Deep_Dive.md
```

The `Research/` folder can be deeply nested. All .md files referenced in the .docx live here.

## Usage

Install this plugin and it works automatically. Skills activate when relevant context is detected — no slash commands needed.
