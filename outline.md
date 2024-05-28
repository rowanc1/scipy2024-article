---
title: Outline
---

Aiming to get a flow for the paper here:

- Introduction
  - Motivation
  - The gap (not connected/continuous, not computational)
  - Continuous Science Practices
  - Existing Tools / LitReview (Pandoc, Quarto, IdyllLang, LaTeX, RST...)
  - our efforts at Curvenote with scientific publishers, conferences, and lab groups to (1) support continuous science practices and (2) improve the integrations of computation into professional scientific publications.
  - Building these tools, then upstream-ing them as part of a grant and leading open source development on the mystmd command-line tools. These aim to be part of the Jupyter community (JEP). We also talk about some of the communities that we are serving on top of these and some of the design goals of bringing continuous practices into scientific workflows.
  - **Working with an upstream community.** (talk about the two hats)
- Authoring (MyST Markdown examples and libraries)
  - MyST is a OS project
  - Syntax overview (directives/roles) - this is very brief
  - AST Approach
  - Features & Goals
    - Citations and data-rich references
    - Deep dive links
    - Computation (via thebe)
    - Cross project references and embedding
    - Export to PDF
  - Believe in the future of this foundation. Interop, reuse, etc.
- Publishing (Curvenote-based examples and libraries)
  - Myst is a OS project
  - MyST in action, managing this via Curvenote infrastructure
  - Overview
    - CI on github, following JOSS
  - Checks
  - Archiving and computation (MECA // JATS // PDF)
  - Templates
- Case Studies
  - SciPy, AGU, MSA
- Conclusions

Curvenote developed the internals ... the critical components need to be in a open.
Don't pretend the tensions don't exist.
