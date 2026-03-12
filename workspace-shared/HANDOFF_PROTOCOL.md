\# HANDOFF\_PROTOCOL.md



\## Purpose



This file defines the shared handoff protocol for the manuscript revision pipeline.



The pipeline consists of three core agents:

\- reviewer

\- writer

\- latex-editor



All collaboration must happen through the shared workspace.

Agents do not directly modify each other’s workspaces.



\## Shared workspace structure



The shared workspace contains:



\- `review\_packets/`

\- `revision\_packets/`

\- `latex\_packets/`

\- `final/`



\### Directory roles



\- `review\_packets/`: reviewer outputs for writer and latex-editor

\- `revision\_packets/`: writer outputs for latex-editor and later reviewer rounds

\- `latex\_packets/`: latex-editor outputs for reviewer and final convergence

\- `final/`: near-submission or submission-candidate outputs



\## Round semantics



\### Round 0

Round 0 is the writer-side initial cleanup round.



Purpose:

\- clean Word-to-LaTeX manuscript noise

\- improve sentence quality, local structure, and readability

\- avoid heavy journal-fit judgment at this stage

\- avoid template-heavy formatting work at this stage



Expected output:

\- `round0\_writer\_revised.tex`

\- `round0\_writer\_change\_log.md`

\- optional `round0\_writer\_unresolved\_issues.md`



\### Round 1

Round 1 is the first journal-oriented review cycle.



Typical sequence:

1\. writer round0 cleanup output is available

2\. latex-editor performs first template integration for JBHI

3\. reviewer performs round1 review

4\. writer performs round1 revision

5\. latex-editor performs round1 formatting refinement



\### Round N

For `roundN` where `N >= 1`, the standard cycle is:



1\. reviewer reviews current manuscript state

2\. writer addresses writer-owned issues

3\. latex-editor addresses latex-owned issues

4\. reviewer checks the updated manuscript in the next round



\## Naming convention



All shared outputs must use versioned round-based filenames.



Use the following pattern:



\- `roundN\_<agent>\_<artifact>.<ext>`



Examples:

\- `round1\_reviewer\_master\_review.md`

\- `round1\_writer\_revised.tex`

\- `round1\_latex\_formatted.tex`



Do not silently overwrite major milestones.



If a file is revised within the same round, use an explicit suffix such as:

\- `round1\_writer\_revised\_v2.tex`

\- `round1\_latex\_format\_report\_v2.md`



\## Reviewer packet requirements



The reviewer writes to:

\- local archive first

\- then `workspace-shared/review\_packets/`



\### Required reviewer outputs

For every formal review round, reviewer must generate:



\- `roundN\_reviewer\_master\_review.md`

\- `roundN\_reviewer\_writer\_action\_list.md`

\- `roundN\_reviewer\_latex\_action\_list.md`



\### Optional reviewer outputs

When applicable, reviewer may also generate:



\- `round1\_reviewer\_style\_bootstrap\_notes.md`

\- additional evidence notes or journal-fit notes



\### Reviewer packet completion rule

A reviewer packet is considered complete only when all three required files are present.



Writer must not begin formal roundN revision without:

\- `roundN\_reviewer\_master\_review.md`

\- `roundN\_reviewer\_writer\_action\_list.md`



Latex-editor should not rely on reviewer guidance for roundN without:

\- `roundN\_reviewer\_latex\_action\_list.md`



\## Writer packet requirements



The writer reads from:

\- `review\_packets/`

\- the latest manuscript source version



The writer writes to:

\- local archive first

\- then `workspace-shared/revision\_packets/`



\### Required writer outputs

For each revision round, writer must generate:



\- `roundN\_writer\_revised.tex`

\- `roundN\_writer\_change\_log.md`



\### Optional writer outputs

When applicable, writer may also generate:



\- `roundN\_writer\_execution\_plan.md`

\- `roundN\_writer\_unresolved\_issues.md`



\### Writer packet completion rule

A writer packet is considered complete only when both required files are present.



Latex-editor should not begin roundN formatting work without:

\- `roundN\_writer\_revised.tex`

\- `roundN\_writer\_change\_log.md`



\## Latex packet requirements



The latex-editor reads from:

\- `revision\_packets/`

\- `review\_packets/` when latex-specific reviewer instructions exist

\- local journal template assets

\- local figure assets and figure manifest



The latex-editor writes to:

\- local archive first

\- then `workspace-shared/latex\_packets/`



\### Required latex-editor outputs

For each latex round, latex-editor must generate:



\- `roundN\_latex\_formatted.tex`

\- `roundN\_latex\_build\_status.md`

\- `roundN\_latex\_format\_report.md`



\### Optional latex-editor outputs

When applicable, latex-editor may also generate:



\- `roundN\_latex\_execution\_plan.md`

\- `roundN\_latex\_unresolved\_issues.md`



\### Latex packet completion rule

A latex packet is considered complete only when all three required files are present.



Reviewer should not perform the next formal review round without:

\- `roundN\_latex\_formatted.tex`

\- `roundN\_latex\_build\_status.md`

\- `roundN\_latex\_format\_report.md`



\## Figure asset handling



Figure assets are owned operationally by latex-editor.



Latex-editor may use:

\- `workspace-latex/figures/raw/`

\- `workspace-latex/figures/processed/`

\- `workspace-latex/figures/manifest/figure\_manifest.yaml`



Figure-related decisions should be recorded in:

\- `roundN\_latex\_format\_report.md`

\- or `roundN\_latex\_unresolved\_issues.md` if unresolved



\## Responsibility boundaries



\### Reviewer owns

\- issue identification

\- journal-fit judgment

\- action list generation

\- distinction between writer-owned and latex-owned issues



\### Writer owns

\- content-level revision

\- logic, wording, flow, terminology consistency

\- claim restraint

\- change logging

\- unresolved content issues



\### Latex-editor owns

\- journal template integration

\- figure/table/equation formatting

\- path repair and figure insertion when assets exist

\- compile-facing cleanup

\- build and format reporting



\## Forwarding rule



If an issue is discovered by one agent but belongs to another agent:

\- do not silently fix it outside scope unless it is trivial and harmless

\- record it in the appropriate packet or unresolved issues file

\- keep handoff traceable



\## Completion gates



\### Gate: reviewer to writer

Writer may proceed only after reviewer packet is complete.



\### Gate: writer to latex-editor

Latex-editor may proceed only after writer packet is complete.



\### Gate: latex-editor to reviewer

Reviewer may proceed to the next review round only after latex packet is complete.



\## Final outputs



When the manuscript reaches near-submission quality, selected outputs may be copied to:



\- `workspace-shared/final/`



Typical final candidates include:

\- latest formatted manuscript

\- latest build status

\- latest format report

\- latest reviewer summary if helpful



\## Practical rule



Prefer conservative progression over premature finalization.



A round is considered usable when:

\- required handoff files are complete

\- unresolved blockers are explicitly documented

\- downstream agent can work without guessing missing context

