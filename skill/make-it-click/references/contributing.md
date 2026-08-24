# Prepare a Library Contribution

Read this file only after a response used a genuinely new method or framework and the user agreed to prepare it for the public library.

## Confirm novelty

Search `expression-library.md` for an equivalent mechanism or selection rule. A new example, topic, metaphor, phrasing style, or parameter does not create a new entry when an existing entry already describes the same reusable idea.

If an equivalent entry exists, tell the user which entry covers it and do not create a duplicate. A useful example may still be proposed as an improvement to that entry.

## Generalize safely

- Extract the reusable method or framework instead of copying the answer.
- Remove names, private facts, conversation history, and topic details that are not necessary to understand the technique.
- Preserve the scientific limits that made the explanation accurate.
- Record why the method fits a class of questions, not merely why it fit one prompt.
- Use lowercase dot-separated IDs: `method.short-name` or `framework.short-name`.

## Candidate format

Prepare one Markdown section using every field below:

```markdown
### `method-or-framework.short-name`

- **Type**: method | framework
- **Solves**: ...
- **Use when**: ...
- **Avoid when**: ...
- **Procedure**: ...
- **Combine with**: ...
- **Why it works**: ...
- **Return path**: ...
- **Example**: ...
- **Accuracy boundary**: ...
```

Also provide:

- a one-line proposed change title;
- whether it is a new entry or an improvement to an existing entry;
- a short explanation of why the library does not already cover it.

If the current environment lacks repository write access, return this candidate to the user for submission. Do not imply that it has entered the public library.

If the environment has write access, publishing still requires separate explicit authorization. Add an authorized contribution to the relevant section of `expression-library.md`, keep the same entry contract, and run the repository checks before submission.

## Quality gate

A candidate is ready only when:

- the explanation mechanism or selection rule is identifiable;
- its suitable and unsuitable conditions are specific enough to guide selection;
- it preserves scientific accuracy and necessary professional content;
- it creates a path back to formal terminology;
- its example demonstrates the method rather than serving as the whole method;
- it does not duplicate an existing entry.
