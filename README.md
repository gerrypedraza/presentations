# Presentations

A collection of talks by Gerry Pedraza, with the templates, examples and tools that go with them. Each presentation has its own folder under [`slides/`](slides/).

## Presentations

| Presentation | Topic | Folder |
| --- | --- | --- |
| [Accessible Media: Beyond the Checker](slides/accessible-media-overview/) | Accessibility | `slides/accessible-media-overview/` |
| Agentic AI *(in progress)* | AI | `slides/agentic-ai/` |

### Accessible Media: Beyond the Checker

Why a document can pass an accessibility checker and still fail students. Open it in any browser; press **H** for the handout view (all slides on one page, printable) and **G** for the glossary.

### Agentic AI

In progress.

## Viewing the slides

The HTML slide decks are plain HTML and need no build step. Open a deck's `index.html` in any browser, or use the published site. The slides are built to be accessible: real headings and lists, alt text on every image, full keyboard control, and slide changes announced to screen readers.

## Related resources

### Applications

- [Beamer to LTX Converter](https://beam2ltx.gerrypedraza.com/): turns existing LaTeX Beamer slide decks into tagged, accessible PDF presentations by converting them to the ltx-talk class. Web app, currently in beta.

### Templates & Examples

- [LaTeX Accessible Template](templates-and-examples/latex/latex-accessible-template.tex): a LaTeX preamble that produces a tagged PDF 2.0 file meeting PDF/UA-2, with equations stored as MathML. Start your document from it and compile with LuaLaTeX (on Overleaf, choose the Rolling TeX Live version).
- [Accessible Template Example In Use](templates-and-examples/latex/accessible-template-example-in-use.pdf): a full document built on the template, with headings, lists, tables, figures with alt text, equations, and decorative content (PDF 2.0, PDF/UA-2). [Download the source (.zip)](templates-and-examples/latex/accessible-template-example-in-use.zip): the LaTeX file and its images folder, ready to upload to Overleaf.

## Repository layout

```
slides/                    one folder per presentation
  accessible-media-overview/
    index.html             the slide deck
    images/                images used by the deck
templates-and-examples/    reusable templates and worked examples
index.html                 landing page listing every presentation
```

## Adding a presentation

1. Create a folder under `slides/` with a short, lowercase, hyphenated name (for example `slides/agentic-ai/`).
2. Put the deck's `index.html` in it, with its images in an `images/` subfolder.
3. Add the deck to the table above and to the root `index.html` landing page.
