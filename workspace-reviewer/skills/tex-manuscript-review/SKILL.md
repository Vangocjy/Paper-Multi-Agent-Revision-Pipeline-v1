---
name: tex-manuscript-review

description: review academic manuscript tex files without being distracted by latex boilerplate or template noise. use when reviewer needs to analyze a manuscript written in latex, locate issues by section or environment, separate content problems from presentation problems, or prepare review findings from tex source files.
---

  # TeX Manuscript Review

  Review manuscript `.tex` files in a way that prioritizes scientific content, structure, and review-relevant presentation.

  Use this skill when:
  - the manuscript is written in LaTeX
  - reviewer must inspect `.tex` source directly
  - reviewer needs to identify content, structure, or presentation problems from `.tex`
  - reviewer must separate writer-facing and latex-facing issues
  - reviewer must avoid being distracted by template boilerplate

  ## Goal

  Read `.tex` files as manuscript source, not as programming code.

  Extract and evaluate:
  - document structure
  - argument flow
  - contribution framing
  - section coherence
  - figure and table communication
  - equation presentation
  - reference usage
  - journal fit signals

  ## Core principle

  Ignore LaTeX mechanics unless they affect review quality.

  Do not spend attention on:
  - package imports
  - class declarations
  - harmless macros
  - formatting boilerplate
  - template scaffolding

  Pay attention only when LaTeX structure affects:
  - readability
  - manuscript organization
  - figure or table interpretation
  - equation clarity
  - cross-reference quality
  - citation presentation
  - template fit

  ## Primary reading targets

  Prioritize these parts of the `.tex` manuscript:

  1. title
  2. abstract
  3. introduction
  4. contribution statements
  5. method sections
  6. experiment and result sections
  7. discussion and conclusion
  8. figure environments
  9. table environments
  10. equation environments
  11. captions
  12. citation and cross-reference usage

  ## Review workflow

  Follow this order:

  1. identify the main manuscript file or the relevant section files
  2. skim the global structure from section commands and input/include patterns
  3. read the manuscript as prose first
  4. inspect figures, tables, equations, captions, and references second
  5. separate issues into:
     - content and argumentation issues
     - presentation and formatting issues
  6. hand off content issues to writer
  7. hand off presentation issues to latex-editor

  ## What to ignore

  Usually ignore these unless they create a visible manuscript problem:

  - `\documentclass`
  - `\usepackage`
  - macro definitions
  - spacing commands
  - harmless layout settings
  - bibliography style declarations
  - comments unrelated to manuscript meaning

  Do not confuse LaTeX noise with manuscript quality.

  ## What to inspect carefully

  Inspect these carefully because they often matter for review:

  - `\title{...}`
  - `\section{...}` and subsection hierarchy
  - abstract environment
  - figure environments
  - table environments
  - caption text
  - equation environments
  - labels and refs when they affect readability
  - citation clusters and citation support
  - conclusion wording
  - limitation statements if present

  ## Content versus presentation split

  ### Send to writer
  Send issues to writer when they concern:
  - unclear claims
  - missing motivation
  - weak problem framing
  - unsupported statements
  - poor logical flow
  - vague contribution statements
  - weak experiment narrative
  - overclaiming
  - missing explanation of results
  - unclear transitions

  ### Send to latex-editor
  Send issues to latex-editor when they concern:
  - unreadable figures
  - weak captions
  - crowded tables
  - equation formatting
  - broken or awkward cross-references
  - citation display issues
  - section formatting issues
  - numbering inconsistencies
  - template-level presentation problems

  If an issue mixes both, split it into:
  - a content task for writer
  - a presentation task for latex-editor

  ## Location reporting

  Always identify issue location as precisely as possible.

  Prefer this order:
  1. section name
  2. subsection name
  3. paragraph role or nearby sentence description
  4. figure, table, or equation number if available

  Examples:
  - Introduction, last paragraph
  - Methods, subsection "Semantic Routing"
  - Figure 3 caption
  - Table 2
  - Equation 5 discussion in Results section

  ## Multi-file manuscripts

  If the manuscript is split across multiple `.tex` files:
  - determine the main structure first
  - follow `\input{}` and `\include{}` references as needed
  - review the manuscript in logical reading order, not filesystem order

  Do not treat section file boundaries as conceptual boundaries.

  ## Journal-fit use

  When judging journal fit:
  - combine this skill with `journal-style-learner`
  - use `journal_style.md` as the primary style baseline
  - inspect sample papers only when needed

  ## Output expectations

  This skill does not replace `review-packet`.

  Use this skill to produce analysis that feeds into:
  - master review
  - writer action list
  - latex action list

  ## Safety and boundaries

  You must not:
  - rewrite the full manuscript
  - overfocus on LaTeX syntax trivia
  - fabricate structure, references, results, or claims
  - directly edit other agents' workspaces
  - perform external actions outside information retrieval
