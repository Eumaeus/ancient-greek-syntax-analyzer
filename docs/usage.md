# Usage Guide: Ancient Greek Syntax Analyzer

This guide explains how to use the Ancient Greek Syntax Analyzer, a web application for students to analyze the syntax of Ancient Greek sentences.

## Getting Started
1. Open `src/index.html` in a modern web browser (e.g., Chrome, Firefox).
2. The textarea is pre-populated with a sentence from Lysias: "περὶ τούτου γὰρ μόνου...".
3. A CTS-URN identifies the sentence (e.g., `urn:cts:greekLit:tlg0054.tlg001.perseus-grc1:1.1.1`).
4. Edit the sentence or (in future versions) load a new one by CTS-URN.

## Stages
### Stage 1: Sentence Adverbial Identification
- **Goal**: Identify a sentence adverbial (e.g., γὰρ) or mark the sentence as asyndeton.
- **Steps**:
  - View tokenized sentence (lexical tokens in boxes with superscripted IDs, e.g., `περὶ¹`).
  - Click a lexical token to select it as the adverbial (highlights yellow).
  - Or check the “This sentence illustrates *asyndeton*” box to add a notional `ROOT⁰` token.
- **Result**: The adverbial or `ROOT⁰` is the root for the syntax graph. Stage 2 unlocks.

### Stage 2: Clause/Phrase Analysis
- **Goal**: Define verbal units (clauses or phrases).
- **Steps**:
  - In the form, select:
    - **Syntactic Type**: Independent Clause, Subordinate Clause, etc.
    - **Semantic Type**: Transitive, Intransitive, Linking.
    - **Level**: 1–5 (for indentation, e.g., 1 for top-level, 2 for subordinate).
  - The form shows the proposed ID (e.g., `VU1`) or editing ID.
  - Click “Confirm Verbal Unit” to add or “Save Changes” to edit.
  - Edit or delete units using the table’s buttons.
- **Result**: Unlocks Stage 3 after defining one unit.

### Stage 3: Token Assignment
- **Goal**: Assign lexical tokens to verbal units, allowing tokens to belong to multiple units for nested structures (e.g., an attributive participle within a clause).
- **Steps**:
  - Select a verbal unit from the dropdown (e.g., `VU1 (Subordinate Clause)`).
  - The “Unassigned Tokens” list shows all eligible tokens (excluding the adverbial/`ROOT⁰`), even if assigned to other units.
  - Click a token in the list to assign it to the selected unit (adds colored border, e.g., blue for `VU1`).
  - Click an assigned token under a verbal unit to unassign it from that unit only.
  - Assigned tokens are displayed in sentence order (e.g., `περὶ¹` before `τούτου²`).
  - The adverbial or `ROOT⁰` is yellow and non-assignable.
- **Display**:
  - Verbal units show assigned tokens, indented by level (1em per level).
  - “Unassigned Tokens” lists all tokens available for the current unit selection.
- **Result**: Prepares for Stage 4.

### Stage 4: Syntactic Relationship Analysis
- **Goal**: Define syntactic relationships between lexical tokens to build a directed graph, identified by a CITE2-URN.
- **Steps**:
  - In the table, for each token:
    - **Token ID** and **Text** are shown.
    - **Node 1**: Select a token ID to link to (e.g., `3: γὰρ` for the root).
    - **Node 1 Relation**: Enter the relationship (e.g., “verb” for a main verb).
    - **Node 2**: Optionally select another token ID (e.g., for a relative pronoun’s second role).
    - **Node 2 Relation**: Enter the second relationship (if applicable).
  - The graph visualizes tokens as nodes (ID + text) and relationships as labeled edges (e.g., “verb” from verb to root).
  - The root is pre-populated (`ROOT⁰` for asyndeton or the adverbial, e.g., `γὰρ³`).
- **Result**: A graph representing the sentence’s syntactic structure, ready for export.

## Tips
- Changing the input resets all stages.
- Use Edit/Delete in Stage 2 to refine units.
- Tokens can link to one or two other tokens (e.g., relative pronouns to antecedent and clause role).

## Support
See [development.md](development.md) or file issues on GitHub.