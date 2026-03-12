# Output Templates

Use these templates when generating revision packet files.

---

## 1. Revised Manuscript File

Filename:

`roundN_writer_revised.tex`

Guidance:

- This is the revised manuscript source.
- Apply reviewer-requested textual revisions conservatively.
- Preserve scientific meaning.
- Avoid unnecessary structural disturbance.
- Keep terminology consistent.
- Prepare the manuscript for downstream latex formatting.

---

## 2. Writer Change Log Template

Filename:

`roundN_writer_change_log.md`

Template:

```markdown
# roundN_writer_change_log.md

## Overview
This revision round focuses on content-level manuscript improvements based on reviewer feedback, with emphasis on clarity, logic, claim restraint, and section-level readability.

## Change log

| Reviewer item | Section | Issue summary | Action taken | Status | Notes |
|---|---|---|---|---|---|
| R1 | Abstract | Abstract is too diffuse and does not clearly identify the proposed method. | Compressed background sentences, made the method identity explicit, and tightened the closing implication statement. | implemented | Kept claims conservative. |
| R2 | Introduction | Contribution framing is unclear. | Rewrote the gap-to-contribution transition and made the contribution statement explicit near the end of the introduction. | implemented | No new claims added. |
| R3 | Methods | Method description is hard to follow. | Clarified module roles and input-output flow in the methods prose. | partially-implemented | Did not add unsupported technical detail. |
| R4 | Results | Figure presentation is inconsistent. | Redirected to latex-editor. | redirected-to-latex | Formatting/presentation issue, not content-owned. |
| R5 | Conclusion | Conclusion overstates generalizability. | Softened the conclusion and restricted claims to the evaluated setting. | implemented | Scope explicitly bounded. |

## Unresolved or deferred items

| Reviewer item | Reason | Status | Recommended next owner |
|---|---|---|---|
| R6 | Requires new evidence or additional experiment support. | unresolved | author / future revision |
| R7 | Depends on template and figure formatting changes. | redirected-to-latex | latex-editor |

## Summary of revision posture
The manuscript was revised conservatively. No new results, unsupported claims, or unverified references were added.