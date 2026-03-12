# TeX Review Rules

Use these rules when reviewing manuscript `.tex` source.

The objective is to read LaTeX as a manuscript container, not as a coding exercise.

---

## 1. Read for meaning first

Start by extracting the paper's scientific story:

- what problem is being solved
- what the claimed contribution is
- how the method is presented
- how experiments support the claims
- what conclusion is drawn

Do not start with package-level or formatting-level details.

---

## 2. Recover structure before details

Before judging local paragraphs, identify:

- title
- abstract
- section sequence
- subsection sequence
- where methods begin
- where experiments begin
- where conclusions appear

This helps avoid fragmented review comments.

---

## 3. Ignore boilerplate aggressively

Treat these as low-priority unless they visibly affect the manuscript:

- preamble settings
- macro declarations
- package imports
- formatting tweaks
- bibliography engine setup
- template comments

Review quality should not be diluted by implementation noise.

---

## 4. Identify review-relevant environments

Focus attention on these environments and commands:

- abstract
- section
- subsection
- figure
- table
- equation
- align
- caption
- label / ref / eqref / cite

These often map directly to reviewer-visible issues.

---

## 5. Review figures as communication objects

For each important figure, ask:

- Is the figure necessary?
- Is the message clear?
- Is the caption self-contained?
- Does the figure support the claimed result?
- Does the text explain the figure properly?

Common writer-facing issues:
- figure is mentioned but not interpreted
- figure claim is vague
- figure relevance is underexplained

Common latex-facing issues:
- poor placement
- weak caption formatting
- cluttered layout
- inconsistent subfigure labeling

---

## 6. Review tables as evidence displays

For each important table, ask:

- What comparison is this table meant to support?
- Are rows and columns interpretable?
- Are metric names and abbreviations clear?
- Is the table too dense?
- Does the text explain the key takeaway?

Common writer-facing issues:
- table is reported but not interpreted
- baseline comparison is underexplained
- result significance is unclear

Common latex-facing issues:
- overfull layout
- poor alignment
- unreadable abbreviations in heading
- caption not informative enough

---

## 7. Review equations for communication, not elegance

Do not judge equations by mathematical sophistication alone.

Ask:
- Is notation introduced clearly?
- Are equations needed?
- Are symbols explained nearby?
- Is the equation readable in context?
- Is the surrounding explanation sufficient?

Common writer-facing issues:
- equation introduced without conceptual explanation
- symbols not explained in prose
- transition from formulation to implementation is unclear

Common latex-facing issues:
- poor equation environment choice
- inconsistent numbering
- awkward line breaking
- display math used where numbered equation would help

---

## 8. Watch contribution framing carefully

In LaTeX manuscripts, contribution statements often appear:
- near the end of the Introduction
- as bullet points
- in a dedicated subsection

Check whether contributions are:
- explicit
- non-redundant
- aligned with experiments
- phrased without exaggeration

This is almost always writer-facing.

---

## 9. Watch citation behavior

From `.tex`, citation patterns are often more visible than in rendered PDF.

Inspect:
- citation density in Introduction and Related Work
- unsupported claims without citations
- citation clusters that suggest shallow comparison
- uneven support for prior work discussion

Usually:
- missing support or shallow comparison is writer-facing
- broken citation formatting or awkward citation presentation is latex-facing

---

## 10. Distinguish source problems from rendered problems

A problem seen in `.tex` may reflect either:
- a true manuscript weakness
- a rendering or layout issue
- both

Examples:
- long caption text may be fine conceptually but bad visually
- weak figure explanation may be a content problem even if formatting is fine
- missing `\label` may matter only when references become confusing

Always classify the problem by downstream responsibility.

---

## 11. Use precise issue locations

When describing issues, do not say only:
- "the method is unclear"
- "the figures need work"

Instead, locate them precisely:
- "Methods, subsection 3.2, first paragraph"
- "Figure 4 caption"
- "Results, discussion after Table 2"

Precise localization makes downstream revision possible.

---

## 12. Prefer review-relevant summaries over source-level commentary

Do not produce comments like:
- "there are too many packages"
- "this macro name is confusing"
- "the preamble is messy"

Unless these directly affect the paper, they are not useful review comments.

Instead produce:
- "The caption of Figure 2 is too terse to stand alone."
- "The final paragraph of the Introduction does not clearly state the paper's contributions."
- "Equation 4 is used before the notation is explained."

---

## 13. Connect source reading to reviewer outputs

The final purpose of `.tex` review is to support these outputs:

- master review
- writer action list
- latex action list

All observations should be convertible into one of those outputs.

If an observation cannot support a meaningful review action, deprioritize it.