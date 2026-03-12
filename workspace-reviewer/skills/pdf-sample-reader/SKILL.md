---
name: pdf-sample-reader

description: read and analyze journal sample pdf papers for reviewer use. use when reviewer needs to inspect target-journal sample papers, extract structural and stylistic signals from academic pdfs, answer a specific journal-fit question, or support updates to journal_style.md from local sample papers.
---

  # PDF Sample Reader

  Read local journal sample PDF papers in a targeted way for manuscript review.

  Use this skill when:
  - reviewer needs evidence from target-journal sample papers
  - `journal_style.md` is incomplete or uncertain
  - a specific journal-fit question needs confirmation
  - reviewer must compare manuscript style against real sample papers
  - reviewer needs to extract structural or rhetorical patterns from academic PDFs

  ## Goal

  Read sample PDFs as evidence for journal-style inference.

  Do not summarize the paper for its scientific content unless needed.
  Instead, extract review-relevant style signals such as:

  - section structure
  - abstract organization
  - contribution framing
  - method detail level
  - experiment organization
  - figure and table usage
  - caption style
  - citation density
  - conclusion tone
  - overall editorial style

  ## Scope

  This skill is for reading and analyzing local sample PDFs in:

  `D:\apps\openclaw\workspace-reviewer\journal_samples\`

  Use it to support:
  - `journal-style-learner`
  - journal-fit judgments during review
  - evidence-based stylistic comparison

  ## Primary working principle

  Read sample PDFs with a question in mind.

  Bad usage:
  - reading all sample PDFs end to end without purpose
  - producing long paper summaries unrelated to review

  Good usage:
  - checking how introductions usually state contributions
  - checking whether figure captions are self-contained
  - checking whether methods sections are dense or concise
  - checking whether conclusions are cautious or strong

  ## Reading priority

  When reading a sample PDF, prioritize these parts:

  1. title
  2. abstract
  3. introduction
  4. contribution statements
  5. section headings
  6. method section structure
  7. experiments and results structure
  8. figure captions
  9. table captions
  10. conclusion and discussion

  Read the minimum amount needed to answer the current style question.

  ## Suggested extraction method

  Prefer text extraction first.

  If PDF text is machine-readable:
  - extract text from key pages or sections
  - inspect headings, captions, and rhetorical patterns

  If PDF text is difficult to read:
  - use page-to-image conversion and visual inspection
  - inspect layout, figure density, caption length, and section presentation

  ## Strategic sampling

  Do not read every sample paper by default.

  Use this order:
  1. start with 2 to 4 representative papers
  2. compare patterns
  3. read additional papers only if the evidence is inconsistent or insufficient

  Prefer samples that are:
  - closest in topic to the manuscript
  - closest in method type
  - most representative of the target venue style

  Use `references/sampling_strategy.md` to guide observation.

  ## Output expectations

  This skill usually supports one of two outputs:

  ### A. local style observations
  Short notes used internally by reviewer or `journal-style-learner`

  ### B. updates to journal_style.md
  When enough evidence has been gathered, refine:

  `D:\apps\openclaw\workspace-reviewer\journal_style.md`

  Keep outputs concise and review-oriented.

  ## What to observe

  Observe only review-relevant signals:
  - common section sequence
  - whether contributions are explicit
  - whether abstracts include numerical results
  - how strong claims are phrased
  - how much related work is discussed
  - whether methods are equation-heavy
  - how results are narrated
  - whether captions stand alone
  - whether conclusions acknowledge limitations

  ## What not to do

  Do not:
  - produce long irrelevant summaries
  - imitate paper wording
  - overgeneralize from one paper
  - treat one sample as a hard rule
  - fabricate journal norms
  - perform external posting or upload actions

  ## Relationship to other reviewer skills

  Use this skill together with:

  - `journal-style-learner` for maintaining `journal_style.md`
  - `tex-manuscript-review` for reviewing the target manuscript source
  - `review-packet` for producing downstream action files

  This skill provides evidence.
  It does not replace final reviewer judgment.

  ## Safety and boundaries

  You may:
  - read local PDFs
  - extract text or layout observations
  - inspect public author guidelines if needed

  You must not:
  - post, upload, publish, or comment externally
  - fabricate style requirements
  - copy large passages from sample papers
