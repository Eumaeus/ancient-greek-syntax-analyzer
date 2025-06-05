# Usage Guide: Ancient Greek Syntax Analyzer

This guide explains how to use the Ancient Greek Syntax Analyzer, a web application for students to analyze the syntax of Ancient Greek sentences.

## Getting Started
1. Open `src/index.html` in a modern web browser (e.g., Chrome, Firefox).
2. The textarea is pre-populated with a sentence from Lysias: "περὶ τούτου γὰρ μόνου...".
3. Edit the sentence or paste a new one to begin analysis.

## Stages
### Stage 1: Sentence Adverbial Identification
- **Goal**: Identify a sentence adverbial (e.g., γὰρ) or mark the sentence as asyndeton.
- **Steps**:
 - View tokenized sentence (lexical tokens in boxes with superscripted IDs, e.g., `περὶ¹`).
 - Click a lexical token to select it as the adverbial (highlights yellow).
 - Or check the “This sentence illustrates *asyndeton*” box to add a notional `ROOT⁰` token.
- **Result**: The selected adverbial or `ROOT⁰` is the root for the future syntax graph. Stage 2 unlocks.

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
 - Assigned tokens are displayed in sentence order (e.g., `περὶ¹` before `τούτου²`), regardless of click order.
 - The adverbial or `ROOT⁰` is yellow and non-assignable.
- **Display**:
 - Verbal units show assigned tokens, indented by level (1em per level).
 - “Unassigned Tokens” lists all tokens available for the current unit selection.
- **Result**: Prepares for Stage 4.

### Stage 4: Token Syntactic Analysis
- **Goal**: Assign parts of speech and syntactic roles to all lexical tokens.
- **Steps**:
 - In Stage 3, double-click any lexical token (in verbal units, “Unassigned Tokens,” or Stage 1’s adverbial/`ROOT⁰`) to open a popup.
 - In the popup, select:
 - **Part of Speech**: Noun, verb, adjective, adverb, participle, etc.
 - **Syntactic Role**: Subject, object, modifier, relative pronoun, etc.
 - Click “Save” to store the analysis or “Cancel” to discard.
 - Analyzed tokens are highlighted light green.
 - View results in a table (Token ID, Text, PoS, Role, Verbal Units).
- **Result**: Detailed syntactic data for export or syntax graph.

## Tips
- Changing the input resets all stages.
- Use Edit/Delete in Stage 2 to refine units.
- Tokens can be assigned to multiple units and re-analyzed as needed.

## Support
See [development.md](development.md) or file issues on GitHub.