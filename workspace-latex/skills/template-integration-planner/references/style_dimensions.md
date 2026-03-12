# style_dimensions.md

Use this file as a compact checklist for latex-side planning.

## Planning dimensions

### 1. template fit
Check:
- title and author block compatibility
- abstract and keywords placement
- section hierarchy alignment
- bibliography placement and style compatibility

### 2. compile stability
Check:
- missing files
- malformed environments
- broken references
- citation command mismatches
- package conflicts visible from local source structure

### 3. float handling
Check:
- figures/tables placed in valid environments
- captions attached consistently
- labels placed sensibly
- subfigure/subtable usage aligned with template conventions

### 4. math and display structure
Check:
- equation environments are syntactically consistent
- labels and references are present where needed
- alignment environments are not obviously malformed

### 5. content-boundary safety
Check:
- whether a proposed latex fix would silently change scientific meaning
- whether a wording issue should instead be redirected to writer
