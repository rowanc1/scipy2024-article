---
title: Transformative Approaches in Science Communication
abstract: |
  Difficult problems that are globally relevant and urgent - like climate change, pandemics, and water security - require us to radically rethink how we publish and work on scientific breakthroughs. Advances in technology for data workflows have increased the speed and scope of scientific discovery. However, scientific dialogue still uses outdated technology for communicating and sharing knowledge, relying on static PDFs that are a poor representation of the complexities of science. This gap impedes the speed of research dissemination, reuse, and uptake: we require new mediums to compose ideas and ways to share research findings as early and as often as possible. In this paper we introduce Curvenote and the use of MyST Markdown to illustrate examples of improving metadata and transforming publishing practices for individuals and societies.
---

## Introduction and Motivation

In the face of mounting global challenges such as climate change, pandemics, and water security, the imperative for rapid, effective scientific discovery and dissemination has never been more acute. The pace at which these problems evolve and impact societies worldwide demands an equally dynamic and innovative approach to how scientific research is published. Despite significant advancements in technology that enhance data collection, analysis, and workflow efficiency, the mechanisms through which scientific knowledge is shared have remained largely unchanged for decades [@10.4230/DagMan.1.1.41]. The prevalent reliance on static PDF formats for research papers starkly contrasts with the complex, data-driven nature of modern science, creating bottlenecks in knowledge dissemination and uptake.

This paper documents some of the design decisions to address these challenges in two tools: (1) MyST Markdown (Markedly Structured Text), a community-run open-source project[^myst-jep], which is a text-based authoring framework that integrates computational content (e.g. Jupyter Notebooks); and (2) Curvenote, which is a set of open-source utilities, command-line tools and actions as well as services[^curvenote] aimed to improve scientific publishing by journals, societies, lab-groups, and for individuals. In this article we provide background, motivation and perspective for our efforts in developing new open-source tools for science communication as well as provide examples from Curvenote's partners including the American Geophysical Union, the Microscopy Society of America, and SciPy. In the article we give an overview of MyST Markdown, and would like to reiterate that MyST Markdown is a community-run project, we do not speak for all of the participants, and the community has varied goals for the project (e.g. API documentation, community guidelines, educational tutorials). Our focus in this article is to give our perspectives on scientific writing and publishing and how it intersects with these open-community projects in addition to the open-source efforts that Curvenote is undertaking around scientific publishing.

[^myst-jep]: The MyST Markdown project is currently hosted by Executable Books (<https://executablebooks.org>), and we are in the process of moving this into the Jupyter Community through a Jupyter Enhancement Proposal [](https://github.com/jupyter/enhancement-proposals/pull/123).
[^curvenote]: Curvenote is a company that provides many different tools for authoring and publishing content, including a collaborative WYSIWYG online editor that can export to MyST Markdown. In this article we only discuss our open-source tools as well as highlight relevant experiences from Curvenote's partners when they relate to general ideas for improving scientific publishing.

Our goals in developing these integrated tools and workflows are focused around related challenges of _authoring_ and _publishing_ in the context of computational, open-science documents and lowering the barrier to continuously releasing and iterating on scientific ideas in the open. Introducing authoring tools that allow for structured, interactive and computational content as researchers are writing can additionally change the way it is checked, shared and published — potentially enabling faster iterations and closer ties to reproducible, interactive content.

(sec:structured-science)=

### Authoring Structured Content

There are currently many challenges for individuals or groups to author research information that can be shared in a structured and rigorous way. By this we mean the things that _structurally_ set a scientific article apart from, for example, a blog post: structured content, valid references with persistent identifiers (PIDs), and metadata in a structured, standardized form. This structured data and the standards behind them are what defines the "scientific record" and enables archiving, discoverability, accessibility, interoperability and the ability to reuse or cite content [@10.1038/sdata.2016.18].
One metric for measuring the difficulty of satisfying these scientific standards is to look at the direct costs that are spent on transforming author submissions (e.g. a PDF or a Word Document) into something that conforms to these standards and is ultimately archived.
In scientific publishing, about 15% of Article Processing Charges (APCs) go to direct publication costs[^pub-costs] [@10.12688/f1000research.27468.2], which provides a _very_ rough global estimate of over USD\$2 billion dollars[^pub-revenue] that is spent on transforming author submissions (e.g. a word-document, LaTeX, or a PDF) into a copyedited, well-formatted, typeset document that can be archived with appropriate metadata [@10.4045/tidsskr.20.0118]; this estimate does not include the approximately USD\$230 million spent on reformatting articles by scientists _before_ publication [@10.1186/s12916-023-02882-y]. Many of these processes are hidden from authors[^hidden-processes] as well as actionable access to the many of the benefits of structured data beyond citation graphs (e.g. "How many citations did this paper get?").

[^pub-revenue]: Global revenue in scientific publishing is around USD$19 billion, with over 50% of the market controlled by Elsevier, Wiley, Taylor & Francis, Springer Nature and SAGE [@10.4045/tidsskr.20.0118].
[^pub-costs]: Direct publication costs include: checking of manuscript, copyediting, typesetting, formatting figures/graphs/tables, XML and metadata preparation, and handling corrections [@10.12688/f1000research.27468.2].
[^hidden-processes]: Much of the production publication processes are hidden from scientific authors, with typesetting focused on cross-references, linking citations, ensuring citations have appropriate IDs (e.g. DOIs) as well as conversion to JATS XML (a NISO standard for archiving scientific articles), metadata preparation to [CrossRef](https://crossref.org), and archiving services like LOCKSS (<https://lockss.org>) and CLOCKSS (<https://clockss.org>). Additionally, the many proprietary services and tools to create both online and PDF outputs of the authors work that are nicely typeset for reading on the web or online.

One goal of the MyST Markdown project is to _dramatically_ reduce these direct-publication costs[^zero-cost] and directly provide structured data as an output of authoring and the ability to export content in a variety of formats including HTML, PDF and JATS-XML (a NISO standard for archiving scientific articles). Having structured data throughout authoring leads to a number of novel reading and authoring experiences [e.g. @eg:hover] and can provide new opportunities for reuse and quality checks when publishing [e.g. @eg:checks]. Furthermore, these transformation processes can be run _continuously_ opening the possibilities for faster feedback [See @sec:continuous-science], iterative drafts, small tweaks and versioned improvements that otherwise would not be worth the time and cost.

[^zero-cost]: The cost of transformation and producing structured content and metadata for a subset of users should approach zero. For example, technical users who can use open-source command-line tools like MyST Markdown and GitHub. This has been shown to be the case for the Journal of Open Source Software (JOSS), for example, which has very low direct-publication costs per article [@10.7717/peerj-cs.147].

(sec:computational-science)=

### Integrating Computational Content

- how to make a change in a notebook figure and have that immediately show up in a document
- how to ensure that the p-value is computed and inserted directly from a computation, rather than through copy-and-paste.
- how to expose interactivity and exploration that a research often has when analyzing a data-set, but is not possible in todays PDF-centric publishing ecosystem.

A compounding challenge to scientific publishing that we are exploring through MyST and Curvenote is how to deeply integrate computational workflows and content into science communication to promote interactive explorations and reproducible practices. There are a host of challenges to from user-interface design, to maintenance, to archiving

We were fortunate to lead several working groups related to these challenges in 2023 by _Notebooks Now!_, a Sloan Foundation funded initiative by the American Geophysical Union.

[e.g. @pythia; @elife]

Notebooks Now!

Doing so will allow for embedding interactive visualizations and computational notebooks directly into scientific documents [e.g. @eg:interactivity], transforming them from static texts into rich, interactive narratives. Integrating computational documents into scholarly publishing system requires a re-imagination of the publishing processes, many of which are ill-equipped to handle computational narratives [c.f. @10.1029/2023EA003458]. We will provide case studies from working with the American Geophysical Union and the Microscopy Society of America who are experimenting with new communication practices.

% In addition, publishing interfaces should be able to lend themselves to curating knowledge on top of others, taking notes, etc. on the published interface and also in other user interfaces. To support every next-generation research tool on top of open access knowledge, we need access to **high-quality, structured content**, data and software — not just the scholarly metadata and citation graph.

(sec:continuous-science)=

### Continuous Science Practices

The manual effort involved in article production [@sec:structured-science] coupled with the inability to integrate computational work [@sec:computational-science] negatively impacts the number of iterations/versions and the immediacy of feedback to authors[^feedback]. In other disciplines, such as software development, these metrics of iteration and feedback are often measured and constantly improved. For example, software organizations often measure and improve: the release cadence of a software product (e.g. continuous delivery); how confident you are in that release (e.g. based on continuous integration tests); how you get early feedback and confidence from linters and tests (e.g. the speed of your unit tests); and how fast you can obtain feedback from real usage and users on in-progress work (e.g. observability, analytics, customer interviews, design prototypes).
Continuous delivery practices of software development are extremely well studied, with large-scale surveys of organizational performance, design, robustness, and speed (e.g. [DORA Reports](https://www.devops-research.com/research.html)). One study compared elite teams with low-performing teams for software delivery, and found elite teams were **46x faster** to release to production (i.e. on-demand and multiple times per day vs monthly or bi-annually) and had **7x fewer errors** (due in part to better continuous deployment and testing infrastructure as well as smaller changesets). In addition to these benefits the elite teams also spent 20% more time on new work, had 5-20% less manual work, and were 1.8x more likely to recommend their team as a great place to work ([2018 DORA Report](https://services.google.com/fh/files/misc/state-of-devops-2018.pdf)).

[^feedback]: There are two types of feedback that we mean: (1) technical feedback as you are authoring, for example, "is this formatted correctly?" or "is this DOI correct?"; and (2) more substantial feedback from reviewers and readers who can only give you feedback when you have published. In the current system, technical feedback of an article-proof can take weeks and should be measured in milliseconds. Improving the immediacy of feedback from readers and peer-reviewers is a harder problem that involves how our existing sociotechnical system incentivizes article publishing rather than research communication and sharing findings as early and as often as possible.

The analogy between scientific publishing and software releases is imperfect and non-prescriptive (i.e. scientific research is very different than developing a product). However, the analogy is illustrative in areas where there is a focus on iterations, smaller changesets and releasing in-progress work as soon as possible to get feedback from peers (i.e. peer-review) or users (in the case of software products). The speed of scientific progress depends on part on the speed of iteration and feedback. There are wide spread efforts in scientific publishing that focus on sharing smaller components of research (e.g. FigShare, Octopus, MicroPublications, NanoPublications, Protocols, PreRegistrations) as well as sharing research sooner in the life cycle (e.g. ASAPbio's mission to support "rapid open sharing, discussion, and collaboration around research" and promotion of "Preprints in Progress").

We refer to these related concepts as "_continuous science_", adopting language and concepts from "continuous integration and deployment". This gives us a technical lens to assess, for example:

- How can you assess and test that the structure of a document applies to editorial rules?
- How long does it take to get feedback if your metadata or DOI is incorrect?
- When a computational figures or data output changes, how long does it take to integrate that into your document?

In science there is a highly manual, absurdly expensive and disconnected process between authoring and publishing. By moving to continuous practices and investing in the appropriate infrastructure to support _continuous science_ we believe there is an opportunity to accelerate scientific discovery by multiple orders of magnitude while simultaneously increasing reproducibility and robustness of the underlying science.

% Furthermore, the analogies between open-access and open-source movements give us an opportunity to peek ahead 15 years to an analogous future and draw on the learnings of how the open-source development, and learnings on how to organize and focus infrastructure to get the best out of our scientific community.

% Current research incentives are focused on article publishing rather than research communication and sharing findings as early and as often as possible. Furthermore,

### Article Outline

For research-communication to be transformative on a similar scale as open-source, researchers require modern tools for authoring and publishing.
There are two inter-related capabilities that are necessary for this transition:

1. authoring mediums that support data, computation and structured content without the need for expensive typesetting; and
2. publishing that is open and accessible to researchers at a variety of scales – individual publishing, lab-groups, societies and institutions.

Through the lens of MyST Markdown and Curvenote, this paper will explore how these tools can address critical gaps in current scientific publishing practices. Our motivation is to enhance the _speed_ and _impact_ of research dissemination, fostering a scientific ecosystem that is more collaborative, reproducible, and equipped to tackle the urgent global challenges of our time.

% Scientific publishing infrastructure is disconnected from day-to-day workflows of scientists, and slows the progress of science. These misalignments are particularly pronounced in computational disciplines, where rapid evolution of methodologies, software, and data demands equally dynamic and interconnected platforms. Scientific publishing uses outdated technology for communicating and sharing knowledge, relying on PDFs, static figures, and text-only references that are a poor representation of the complexity of the science and data. This gap slows the speed of research dissemination, reuse, and uptake and completely impedes "networked knowledge" and importing/reusing work in a structured way. For example, "importing" visualizations, equations or any other deeply-linked content – including provenance information – into new research articles, documentation or educational sites is completely impossible in today’s research ecosystem. As a metaphor, compare open-access science to open-source programming: it would be a world without package managers to share, version, reuse and rapidly build upon other peoples work in a structured way. The open-source ecosystem would not exist without this infrastructure.

% Open infrastructure for communicating science also has to be easy to integrate into existing tools, support computational, interactive components, be archivable for the long term, and be adopted by our existing sociotechnical system of societies, journals, and institutions. There are two interconnected problems that need to be solved: (1) upgrade existing scientific authoring tools, ensuring these are integrated into both scientific and data-science ecosystems; and (2) develop radically better ways to share content as individuals, small groups, preprints, and formalized, traditional journals with existing societies and institutions. The two problems are connected, in that the authoring tools should be able to deeply integrate with new publishing mediums (e.g. referencing a figure from a publication should be able to show you that figure directly as you are authoring, including all interactivity and computation). In addition, publishing interfaces should be able to lend themselves to curating knowledge on top of others, taking notes, etc. on the published interface and also in other user interfaces. To support every next-generation research tool on top of open access knowledge, we need access to **high-quality, structured content**, data and software — not just the scholarly metadata and citation graph.

## Authoring Tools

[A bit of background on MyST, history, talk about Quarto, Pandoc and discuss CLI was originally part of Curvenote]

Quarto, Pandoc (not just translation, but the whole workflow)
Idyll lang, MDX
RST
Curvenote, Overleaf

MyST Markdown, or Markedly Structured Text, offers a powerful extension to the conventional markdown, marrying the simplicity of markdown syntax with advanced features tailored for scientific writing and documentation. MyST incorporates a suite of functionalities designed to improve the quality, interactivity, and comprehensiveness of both static and computational documents.

### MyST Markdown Overview

At its core, MyST adheres to the [CommonMark](https://commonmark.org/) standard, ensuring a familiar foundation for those versed in traditional Markdown. However, MyST distinguishes itself through the introduction of specialized syntax aimed at facilitating scientific discourse including citations, cross-references, figures, proofs, equations, and tables. There is also specialized support for the types of metadata that are important to collect for scientific articles (funding, ORCIDs, CRediT Roles, etc.).

### Improving the Utility of Links and Identifiers

:::{prf:example} Citations and links to improves metadata
:label: eg:citations
Citations can be added inline using `@cite-key`, following Pandoc-style syntax and referencing a BibTeX file in a project.
It is also possible to directly link to DOIs using `@10.5281/zenodo.6476040`, which will create a hover reference
[@10.5281/zenodo.6476040] as well as a references section at the bottom of the page.
The ease of use of DOIs and other structured scientific metadata encourages the use of DOIs and can be reused in multiple different formats such as JATS.

This enhanced-links concept can be extended to [Wikipedia](https://en.wikipedia.org/wiki/Wikipedia), RRIDs, RORs, GitHub issues or code, and other scientific databases to augment writing. For example, the link `<rrid:SCR_008394>` becomes <rrid:SCR_008394>, with rich-metadata and citations created. Wikipedia links come with previews, for example, `<wiki:gravitational_waves>` becomes <wiki:gravitational_waves>. GitHub links to pull-requests also give hover information (for example, this example admonition was implemented in [#87](https://github.com/executablebooks/myst-theme/pull/87)).
:::

### Hover Previews for Content and Metadata

Furthermore, MyST supports documentation of equations, figures, and tables with automated cross-references and hover-previews. This enhances the reading experience of scientific documents and retrieval of information. For example, in @doi:10.1145/3411764.3445648 the authors showed you can speed up comprehension of a paper by 26% when showing information in context, rather than requiring researchers to scroll back and forth to find figures and equations.

In MyST Markdown we have extended this concept to abbreviations to make it trivial to
[@10.7554/eLife.60080]

::::{prf:example} Hover and Dive Deeper
:label: eg:hover

Any figure, table, or equation can be referenced in MyST and in addition to automated numbering the cross-references have hover-references. This design feature is important for two reasons: (1) it improves reading comprehension; and (2) it focuses on structured data which can be accessible between papers, creating an open-ecosystem of machine-actionable, reusable content. The referenced content can also be interactive or computational.

```{figure} ./images/links.*
:label: fig:deep-dive
Instantly accessible information can deep-dive link all the way to interactive figures. These practices help with reading comprehension by around 26% by providing information when the reader needs it [@doi:10.1145/3411764.3445648].
```

::::

### Integrating Computational Content

Beyond structured typography, MyST Markdown's real power lies in its ability to handle computational content through integrations with Jupyter Notebooks - a concept that brings structured, computational elements into documents. In the composition of a scientific narrative, scientists often use individual notebooks to create various components of their research. The outputs of these notebooks (a figure, table, or calculation) is then used in a main, narrative-driven document — a scientific article or presentation.

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

### Single Source to Many Outputs

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
