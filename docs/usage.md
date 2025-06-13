# Usage Guide: Ancient Greek Syntax Analyzer

This guide explains how to use the Ancient Greek Syntax Analyzer, a web application for students to analyze the syntax of Ancient Greek sentences.

## Getting Started
1. Open `src/index.html` in a modern web browser (e.g., Chrome, Firefox).
2. The textarea is pre-populated with a sentence from Lysias: "περὶ τούτου γὰρ μόνου...".
3. A CTS-URN identifies the sentence (e.g., `urn:cts:greekLit:tlg0054.tlg001.perseus-grc1:1.1.1`).
4. Edit the sentence, load a new one by CTS-URN (in future versions), or import a CEX file to restore an analysis.

## Stages
### Stage 1: Sentence Adverbial Identification
- **Goal**: Identify a sentence adverbial (e.g., γὰρ) or mark the sentence as asyndeton.
- **Steps**:
  - View tokenized sentence (lexical tokens in boxes with superscripted IDs, e.g., `περὶ¹`).
  - Click a lexical token to select it as the adverbial (highlights yellow, links to '0: Sentence Root' as 'Linking Word').
  - Or check the “This sentence illustrates *asyndeton*” box to add a notional `ROOT⁰` token.
  - Click “Import CEX” to load a saved analysis, instantly restoring the full UI state (sentence, units, assignments, relationships, graph).
- **Result**: The adverbial or `ROOT⁰` links to '0: Sentence Root'. Stage 2 unlocks.

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
  - The “Unassigned Tokens” list shows tokens not yet assigned to the selected unit.
  - Click a token in “Unassigned Tokens” to assign it; it moves to the unit’s assigned list (in sentence order) and disappears from “Unassigned Tokens.”
  - Click an assigned token under the selected unit to unassign it, returning it to “Unassigned Tokens.”
  - Switch to a new unit to start with an empty assigned list and all eligible tokens in “Unassigned Tokens.”
  - Switch to a prior unit to restore its state.
  - All units and tokens are displayed, sorted by the first token’s sentence order, with distinct border colors per unit and the current unit’s tokens highlighted (green background).
  - The adverbial or `ROOT⁰` is yellow and non-assignable.
- **Display**:
  - Units show assigned tokens, indented by level.
  - “Unassigned Tokens” lists tokens available for the current unit.
- **Result**: Prepares for Stage 4.

### Stage 4: Syntactic Relationship Analysis
- **Goal**: Define syntactic relationships to build a directed graph, identified by a CITE2-URN.
- **Steps**:
  - The graph above the table shows a top-down view, rooted at '0: Sentence Root' at the top, with dependent nodes extending downward and edges labeled by relations (e.g., ‘Linking Word’ for γὰρ). Tokens appear only after assigning relations.
  - In the table below, for each token (including '0: Sentence Root'):
    - **Token ID** and **Text**: Shown.
    - **Node 1**: Select a token ID to link to (e.g., ‘0: Sentence Root’, first option).
    - **Node 1 Relation**: Enter the relationship (e.g., “verb”).
    - **Node 2**: Optionally select another token ID.
    - **Node 2 Relation**: Enter the second relationship (if applicable).
  - The adverbial (e.g., γὰρ) is prelinked to ‘0: Sentence Root’ with ‘Linking Word’.
  - Click “Export CEX” to save the analysis as a `.cex` file, capturing the full state.
  - The graph updates as relations are assigned, remaining zoomable.
- **Result**: A graph representing the sentence’s syntactic structure, exportable/importable via CEX.

## Tips
- Changing the input resets all stages unless importing a CEX file.
- Use Edit/Delete in Stage 2 to refine units.
- Tokens can link to one or two other tokens (e.g., relative pronouns).
- Export CEX to save progress; import to resume exactly where you left off.

## Support
See [development.md](development.md) or file issues on GitHub.