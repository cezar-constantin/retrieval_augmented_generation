# Retrieval Augmented Generation

Interactive teaching simulator for explaining Retrieval Augmented Generation in the browser.

## What it does

- lets students upload PDF, DOCX, TXT, or Markdown documents
- extracts text from the uploaded files
- splits the text into paragraph chunks
- pre-computes embeddings for every paragraph
- retrieves the top-k passages for a user question
- builds a grounded answer from the retrieved evidence
- explains every important RAG stage in separate tabs

## Teaching focus

The simulator is based on the provided Python script and PDF documentation. It highlights these steps explicitly:

1. Extracting text from Documents
2. Loading and splitting document texts into paragraphs
3. Pre-computing embeddings for all paragraphs
4. Defining the Retrieval Function

The original Python example is retrieval-focused. This browser version adds a grounded answer panel so the full RAG story is easier to teach without needing a backend or API key.

## Technical notes

- visual style inspired by the `Neuronal network` project
- static deployment ready for GitHub Pages
- tries to load `all-MiniLM-L6-v2` in the browser via Transformers.js
- falls back to deterministic local vectors if the remote model cannot be loaded
- uses PDF.js for PDF extraction and Mammoth.js for DOCX extraction

## Run locally

You can open the folder with a local static server, for example:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Deploy

Push the repository to GitHub and keep the `deploy-pages.yml` workflow. The site is configured for GitHub Pages deployment through GitHub Actions.
