# Usage Guide: Ancient Greek Syntax Analyzer

This guide explains how to use the Ancient Greek Syntax Analyzer, a web application for students to analyze the syntax of Ancient Greek sentences.

## Getting Started
1. Open `src/index.html` in a modern web browser (e.g., Chrome, Firefox).
2. The app loads with a default sentence from Lysias: "περὶ τούτου γὰρ μόνου...".
3. Follow the stages below to analyze the sentence.

## Stages
### Stage 1: Sentence Adverbial Identification
- **Goal**: Identify a sentence adverbial (e.g., γὰρ) or mark the sentence as asyndeton.
- **Steps**:
  - View tokenized sentence (lexical tokens in boxes with superscripted IDs).
  - Click a lexical token to select it as the adverbial (highlights yellow).
  - Or check “This sentence illustrates *asyndeton*” to add a notional `ROOT⁰` token.
- **Result**: Unlocks Stage 2. The adverbial or `ROOT⁰` will be the syntax graph root.

### Stage 2: Clause/Phrase Analysis
- **Goal**: Define verbal units (clauses or phrases).
- **Steps**:
  - In the form, select:
    - Syntactic Type (e.g., Subordinate Clause).
    - Semantic Type (e.g., Linking).
    - Level (1–5, for indentation).
  - The form shows the proposed ID (e.g., `VU1`) or editing ID.
  - Click “Confirm” to add the unit or “Save Changes” to edit.
  - View units in a table, with options to Edit or Delete.
- **Result**: Unlocks Stage 3 after one unit is defined.

### Stage 3: Token Assignment
- **Goal**: Assign lexical tokens to verbal units.
- **Steps**:
  - Select a verbal unit from the dropdown (e.g., `VU1 (Subordinate Clause)`).
  - Click tokens in the “Unassigned Tokens” list to assign them (adds colored border, e.g., blue for `VU1`).
  - Click assigned tokens (under a unit) to unassign, moving them back to “Unassigned Tokens.”
  - The sentence adverbial or `ROOT⁰` is ineligible (yellow, non-clickable).
- **Display**:
  - Verbal units show assigned tokens, indented by level (1em per level).
  - Unassigned tokens listed below.
- **Result**: Prepares for syntax graph or export.

## Tips
- Edit the input sentence to analyze a new text, resetting all stages.
- Use Edit/Delete in Stage 2 to refine verbal units before assigning tokens.
- Tokens can only be assigned to one unit at a time.

## Support
For issues or feature requests, see `docs/development.md` or file an issue on GitHub.