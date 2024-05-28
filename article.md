---
title: Transformative Approaches in Science Communication
abstract: |
  Difficult problems that are globally relevant and urgent - like climate change, pandemics, and water security - require us to radically rethink how we publish and work on scientific breakthroughs. Advances in technology for data workflows have increased the speed and scope of scientific discovery. However, scientific dialogue still uses outdated technology for communicating and sharing knowledge, relying on static PDFs that are a poor representation of the complexities of science. This gap impedes the speed of research dissemination, reuse, and uptake: we require new mediums to compose ideas and ways to share research findings as early and as often as possible. In this paper we introduce Curvenote and the use of MyST Markdown to illustrate examples of improving metadata and transforming publishing practices for individuals and societies.
---

## Introduction and Motivation

In the face of mounting global challenges such as climate change, pandemics, and water security, the imperative for rapid, effective scientific discovery and dissemination has never been more acute. The pace at which these problems evolve and impact societies worldwide demands an equally dynamic and innovative approach to how scientific research is published. Despite significant advancements in technology that enhance data collection, analysis, and workflow efficiency, the mechanisms through which scientific knowledge is shared have remained largely unchanged for decades [@10.4230/DagMan.1.1.41]. The prevalent reliance on static PDF formats for research papers starkly contrasts with the complex, data-driven nature of modern science, creating bottlenecks in knowledge dissemination and uptake.

Recognizing these challenges, this paper documents some of the design decisions behind (1) MyST Markdown (Markedly Structured Text), a community-run open-source project, and (2) Curvenote, which is a set of open-source utilities, command-line tools and actions as well as services aimed to improve scientific communication by journals, societies, lab-groups, and for individuals. In this article we provide background, motivation and perspective for our efforts in developing new tools for science communication as well as provide examples from Curvenote's partners including the American Geophysical Union, the Microscopy Society of America, and SciPy.

Our goals in developing these tools and workflows are focused around two related challenges of _authoring_ and _publishing_ in the context of computational open-science documents and lowering the barrier to continuously releasing and iterating on scientific ideas in the open.

### Authoring Structured Content

There are currently many challenges for individuals or groups to share research information in a structured, rigorous way such that scientific outputs integrate with existing standards and promote new ways to reuse content. By this we generally are talking about the things that _structurally_ set a scientific article apart from, for example, a blog post: structured content, valid references with persistent identifiers (PIDs), and metadata in a structured form. In scientific publishing, about 15% of Article Processing Charges (APCs) go to direct publication costs[^pub-costs] [@10.12688/f1000research.27468.2], which provides a _very_ rough global estimate of over USD\$2 billion dollars[^pub-revenue] that is spent on transforming author submissions (e.g. a word-document, LaTeX, or a PDF) into a copyedited, well-formatted, typeset document that can be archived with appropriate metadata [@10.4045/tidsskr.20.0118]; this estimate does not include the approximately USD\$230 million spent on reformatting articles by scientists _before_ publication [@10.1186/s12916-023-02882-y]. Many of these processes are hidden from authors[^hidden-processes] as well as actionable access to the many of the benefits of structured data beyond citation graphs (e.g. "How many citations did this paper get?"). One goal of the MyST Markdown project is to directly provide structured data as an output of authoring and the ability to export content in a variety of formats including HTML, PDF and JATS-XML (a NISO standard for archiving scientific articles). Having structured data throughout authoring leads to a number of novel reading and authoring features [e.g. @eg:hover] and can provide new opportunities for reuse and quality checks [e.g. @eg:checks]. Furthermore, these transformation processes can be run _continuously_ opening the possibilities for faster feedback, iterative drafts, small tweaks and versioned improvements that otherwise would not be worth the time and cost.

[^pub-revenue]: Global revenue in scientific publishing is around USD$19 billion, with over 50% of the market controlled by Elsevier, Wiley, Taylor & Francis, Springer Nature and SAGE [@10.4045/tidsskr.20.0118].
[^pub-costs]: Direct publication costs include: checking of manuscript, copyediting, typesetting, formatting figures/graphs/tables, XML and metadata preparation, and handling corrections [@10.12688/f1000research.27468.2].
[^hidden-processes]: Much of the production publication processes are hidden from scientific authors, with typesetting focused on cross-references, linking citations, ensuring citations have appropriate IDs (e.g. DOIs) as well as conversion to JATS XML (a NISO standard for archiving scientific articles), metadata preparation to [CrossRef](https://crossref.org), and archiving services like LOCKSS (<https://lockss.org>) and CLOCKSS (<https://clockss.org>). Additionally, the many proprietary services and tools to create both online and PDF outputs of the authors work that are nicely typeset for reading on the web or online.

### Integrating Computational Content

A compounding challenge that we explore through MyST and Curvenote is how to deeply integrate computational workflows and content into science communication to promote interactive explorations and reproducible practices. There are a host of challenges to archiving [e.g. @pythia, @elife]

Notebooks Now!

Doing so will allow for embedding interactive visualizations and computational notebooks directly into scientific documents [e.g. @eg:interactivity], transforming them from static texts into rich, interactive narratives. Integrating computational documents into scholarly publishing system requires a re-imagination of the publishing processes, many of which are ill-equipped to handle computational narratives [c.f. @10.1029/2023EA003458]. We will provide case studies from working with the American Geophysical Union and the Microscopy Society of America who are experimenting with new communication practices.

% In addition, publishing interfaces should be able to lend themselves to curating knowledge on top of others, taking notes, etc. on the published interface and also in other user interfaces. To support every next-generation research tool on top of open access knowledge, we need access to **high-quality, structured content**, data and software — not just the scholarly metadata and citation graph.

### Continuous Science Practices

- todo: preprints in progress, sharing of lab notebooks

Current research incentives are focused on article publishing rather than research communication and sharing findings as early and as often as possible. Efforts towards improving access (via open-access and preprints), sharing components of research (FigShare, Octopus, MicroPublications, Protocols), and sharing research much sooner in the life cycle (e.g. ASAPbio's mission to support "rapid open sharing, discussion, and collaboration around research" and promotes "Preprints in Progress").

We refer to this concept as "continuous science", adopting language and concepts from "continuous integration and deployment". Continuous delivery practices of software development are well studied, with large-scale surveys of organizational performance, design, robustness, and speed (e.g. [DORA Reports](https://www.devops-research.com/research.html)). The [2018 DORA Report](https://services.google.com/fh/files/misc/state-of-devops-2018.pdf) compared elite teams with low-performing teams for software delivery, and found that the elite teams were 46x faster, had 7x fewer errors, spent 20% more time on new work, had 5-20% less manual work, and were 1.8x more likely to recommend their team as a great place to work.

% techniques in software development have had a transformative role in increasing the speed and rigour of releasing software. The

> 46x faster. 7x fewer errors. 20% more time for new work. 5-20% less manual work.

By moving to continuous practices and investing in the appropriate infrastructure to support continuous delivery of _science_ we have a similar opportunity to accelerate scientific discovery by multiple orders of magnitude while simultaneously increasing reproducibility and robustness of the underlying science. The analogies between open-access and open-source movements give us an opportunity to peek ahead 15 years to an analogous future and draw on the learnings of how the open-source development, and learnings on how to organize and focus infrastructure to get the best out of our scientific community.

### Outline

For research-communication to be transformative on a similar scale as open-source, researchers require modern tools for authoring and publishing.
There are two inter-related capabilities that are necessary for this transition:

1. authoring mediums that support data, computation and structured content without the need for expensive typesetting; and
2. publishing that is open and accessible to researchers at a variety of scales – individual publishing, lab-groups, societies and institutions.

Through the lens of MyST Markdown and Curvenote, this paper will explore how these tools can address critical gaps in current scientific publishing practices. Our motivation is to enhance the _speed_ and _impact_ of research dissemination, fostering a scientific ecosystem that is more inclusive, collaborative, reproducible, and equipped to tackle the urgent global challenges of our time.

% Scientific publishing infrastructure is disconnected from day-to-day workflows of scientists, and slows the progress of science. These misalignments are particularly pronounced in computational disciplines, where rapid evolution of methodologies, software, and data demands equally dynamic and interconnected platforms. Scientific publishing uses outdated technology for communicating and sharing knowledge, relying on PDFs, static figures, and text-only references that are a poor representation of the complexity of the science and data. This gap slows the speed of research dissemination, reuse, and uptake and completely impedes "networked knowledge" and importing/reusing work in a structured way. For example, "importing" visualizations, equations or any other deeply-linked content – including provenance information – into new research articles, documentation or educational sites is completely impossible in today’s research ecosystem. As a metaphor, compare open-access science to open-source programming: it would be a world without package managers to share, version, reuse and rapidly build upon other peoples work in a structured way. The open-source ecosystem would not exist without this infrastructure.

% Open infrastructure for communicating science also has to be easy to integrate into existing tools, support computational, interactive components, be archivable for the long term, and be adopted by our existing sociotechnical system of societies, journals, and institutions. There are two interconnected problems that need to be solved: (1) upgrade existing scientific authoring tools, ensuring these are integrated into both scientific and data-science ecosystems; and (2) develop radically better ways to share content as individuals, small groups, preprints, and formalized, traditional journals with existing societies and institutions. The two problems are connected, in that the authoring tools should be able to deeply integrate with new publishing mediums (e.g. referencing a figure from a publication should be able to show you that figure directly as you are authoring, including all interactivity and computation). In addition, publishing interfaces should be able to lend themselves to curating knowledge on top of others, taking notes, etc. on the published interface and also in other user interfaces. To support every next-generation research tool on top of open access knowledge, we need access to **high-quality, structured content**, data and software — not just the scholarly metadata and citation graph.

## Authoring Tools

[A bit of background on MyST, history, talk about Quarto, Pandoc and discuss CLI was originally part of Curvenote]

Quarto, Pandoc (not just translation, but the whole workflow)
Idyll lang, MDX
RST
Curvenote, Overleaf

MyST Markdown, or Markedly Structured Text, offers a powerful extension to the conventional markdown, marrying the simplicity of markdown syntax with advanced features tailored for scientific writing and documentation. MyST incorporates a suite of functionalities designed to improve the quality, interactivity, and comprehensiveness of both static and computational documents.

### MyST Markdown

At its core, MyST adheres to the [CommonMark](https://commonmark.org/) standard, ensuring a familiar foundation for those versed in traditional Markdown. However, MyST distinguishes itself through the introduction of specialized syntax aimed at facilitating scientific discourse including citations, cross-references, figures, proofs, equations, and tables.

:::{prf:example} Citations and links to improves metadata
:label: eg:citations
Citations can be added inline using `@cite-key`, following Pandoc-style syntax and referencing a BibTeX file in a project.
It is also possible to directly link to DOIs using `@10.5281/zenodo.6476040`, which will create a hover reference
[@10.5281/zenodo.6476040] as well as a references section at the bottom of the page.
The ease of use of DOIs and other structured scientific metadata encourages the use of DOIs and can be reused in multiple different formats such as JATS.

This enhanced-links concept can be extended to [Wikipedia](https://en.wikipedia.org/wiki/Wikipedia), RRIDs, RORs, GitHub issues or code, and other scientific databases to augment writing. For example, the link `<rrid:SCR_008394>` becomes <rrid:SCR_008394>, with rich-metadata and citations created. Wikipedia links come with previews, for example, `<wiki:gravitational_waves>` becomes <wiki:gravitational_waves>. GitHub links to pull-requests also give hover information (for example, this example admonition was implemented in [#87](https://github.com/executablebooks/myst-theme/pull/87)).
:::

Furthermore, MyST supports documentation of equations, figures, and tables with automated cross-references and hover-previews. This enhances the reading experience of scientific documents and retrieval of information. For example, in @doi:10.1145/3411764.3445648 the authors showed you can speed up comprehension of a paper by 26% when showing information in context, rather than requiring researchers to scroll back and forth to find figures and equations.

::::{prf:example} Hover and Dive Deeper
:label: eg:hover

Any figure, table, or equation can be referenced in MyST and in addition to automated numbering the cross-references have hover-references. This design feature is important for two reasons: (1) it improves reading comprehension; and (2) it focuses on structured data which can be accessible between papers, creating an open-ecosystem of machine-actionable, reusable content. The referenced content can also be interactive or computational.

```{figure} ./images/links.*
:label: fig:deep-dive
Instantly accessible information can deep-dive link all the way to interactive figures. These practices help with reading comprehension by around 26% by providing information when the reader needs it [@doi:10.1145/3411764.3445648].
```

::::

Beyond typography, MyST Markdown's real power lies in its ability to handle computational content through integrations with Jupyter Notebooks - a concept that brings structured, computational elements into documents. In the composition of a scientific narrative, scientists often use individual notebooks to create various components of their research. The outputs of these notebooks (a figure, table, or calculation) is then used in a main, narrative-driven document — a scientific article or presentation.

In some cases, it is possible to collapse all computational information into a single "Computational Article", and visually hide the code to focus on the narrative or presentational flow, rather than the detailed methodology. In our experience, this approach tends to focus on simple reproduction of visualizations from small, cached, or subset data rather than detailed methodology that requires its own explanation and/or lengthy computation. Another approach is to include all individual notebooks, and [transclude](wiki:transclude) content. Both approaches are appropriate in different circumstances, and depends on the nature of the research, speed of execution, and if individual steps require dedicated narrative explanation.

:::{figure} ./images/reuse-jupyter-outputs.png
:label: fig:reuse
The purple and orange components, interactive figure or other computational outputs, are created in a computational notebook and subsequently used in other narrative or presentation-focused scientific article.
:::

In @fig:reuse, we show an example of reusing computational outputs, such as figures or tables directly in a single computational research article. Similar to the hover-references in @eg:hover, this approach improves the metadata around the notebooks and exposes individual outputs or code-snippets to be imported into other documents or projects. Here we are aiming at a much richer, structured information commons that moves beyond just tracking scientific metadata towards easy-to-use tools that share the content, data and software.

[briefly reference JupyterLab MyST]

::::{prf:example} Computational Reproducibility and Interactivity
:label: eg:interactivity
MyST allows for the full reproducible environment to be specified (via REES) and reproduced through tools like MyBinder. Figures can be integrated directly into articles, pressing a button to launch live and interactive figures that build upon the Jupyter ecosystem.
These tools build on the Jupyter protocols and reuse components from the JupyterLab ecosystem, extending that into various pages using a package called thebe.

```{figure} ./images/thebe.*
:label: fig:thebe
Embedded notebook cells with live computation directly in an articles with computation backed by Jupyter. These can be running on BinderHub or directly in your browser through JuptyerLite.
```

::::

Whether it's embedding interactive visualizations, crafting detailed figures with captions that are automatically numbered for reference, or integrating mathematical equations directly into the narrative, MyST Markdown transforms static texts into rich, dynamic narratives. These capabilities are complemented by an export system that supports export to PDF with professional article templates [@fig:export].

:::{figure} ./images/myst-build.png
:label: fig:export
Export to PDF using LaTeX or Typst is supported for hundreds of different journal templates in addition to Microsoft Word or JATS XML, which is used in scientific publishing.
:::

With single-source publishing, we can rely on rich transformations of the source content that can create professional PDFs, interactive HTML, and structured metadata such as JATS XML, which is the current standard for scientific archiving and text-mining.

intuitive cross-referencing system, enabling authors to build coherent and navigable documents that can guide readers through complex scientific narratives with ease.

## Publishing

- Build actions (`myst init --gh-pages`) or scipy, which uses additional preview capabilities.
- Checks

::::{prf:example} Checks
:label: eg:checks
asdf
::::

### Case Studies

AGU
Physiome
SciPy

## Conclusions

This gap — between the authoring/doing of research and the communicating/publishing of the research — slows the speed of research dissemination, reuse, and uptake and completely impedes "networked knowledge" and importing/reusing work in a structured way. For example, "importing" visualizations, equations or any other deeply-linked content – including provenance information – into new research articles, documentation or educational sites is completely impossible in today’s research ecosystem. As a metaphor, compare open-access science to open-source programming: it would be a world without package managers to share, version, reuse and rapidly build upon other peoples work in a structured way. The open-source ecosystem would not exist without this infrastructure.

Open infrastructure for communicating science also has to be easy to integrate into existing tools, support computational, interactive components, be archivable for the long term, and be adopted by our existing sociotechnical system of societies, journals, and institutions. There are two interconnected problems that need to be solved: (1) upgrade existing scientific authoring tools, ensuring these are integrated into both scientific and data-science ecosystems; and (2) develop radically better ways to share content as individuals, small groups, preprints, and formalized, traditional journals with existing societies and institutions. The two problems are connected, in that the authoring tools should be able to deeply integrate with publishing mediums (e.g. referencing a figure from a publication should be able to show you that figure directly as you are authoring, including all interactivity and computation).

## Acknowledgements

Portions of this manuscript have been previously shared in the Curvenote and MyST Markdown documentation. The authors would like to thank Lindsey Heagy, Arfon Smith, Chris Holdgraf, Greg Caporaso, Jim Colliander, Fernando Perez, J.J. Allaire, and Kristen Ratan who have provided input on versions of these ideas over the last few years. Thank you to the growing list of MyST Markdown contributors who continue to make MyST a fantastic community project.
