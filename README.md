# Ancient Greek Syntax Analyzer

A web application for students to tokenize and analyze Ancient Greek syntax, supporting Stages 1–3.

## Features
- Input an Ancient Greek sentence (pre-populated with a Lysias sentence).
- Tokenize into white-space, punctuation, and lexical tokens with IDs (1, 2, …).
- **Stage 1: Sentence Adverbial Identification**:
  - Click a lexical token to select a sentence adverbial (yellow) or check asyndeton (adds `ROOT⁰`).
  - Adverbial or root token will be the syntax graph root.
- **Stage 2: Clause/Phrase Analysis**:
  - Hidden until Stage 1 complete.
  - Define verbal units with IDs (e.g., VU1), Syntactic Type, Semantic Type, Level (1–5).
  - Form shows ID. Table with Edit/Delete.
- **Stage 3: Token Assignment**:
  - Available after one verbal unit.
  - Select a unit, click tokens in “Unassigned Tokens” (pre-populated with eligible tokens) to assign (colored borders). Click assigned tokens to unassign.
  - Sentence adverbial/root token ineligible.
  - Units displayed with tokens, indented by level (1em/level). Unassigned tokens listed below.
- Instructions guide each stage. Prepares for export with sentence ID.

## Setup
```bash
git clone https://github.com/[your-repo]/ancient-greek-syntax-analyzer.git
```


- Open index.html in a browser.

## Usage

Paste/edit sentence.

- Stage 1: Click a token for adverbial or check asyndeton.

- Stage 2: Define/edit verbal units.

- Stage 3: Assign tokens via “Unassigned Tokens” list, unassign via verbal unit tokens.

