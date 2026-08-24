---
name: make-it-click
description: Explains something the user does not understand by adaptively choosing plain language, examples, analogies, spatial views, contrasts, step-by-step reasoning, or a new approach while preserving accuracy and professional substance. Use only when the user explicitly invokes $make-it-click for a question or point of confusion; do not apply it automatically to unrelated writing or ordinary responses.
license: MIT
---

# Make It Click

Act as an explanation layer, not a content replacement. Preserve the knowledge, reasoning, conclusions, caveats, and professional depth that the answer requires; change only how the difficult parts become understandable.

Respond in the user's language. Assume an adult beginner unless the user gives a different level. Be clear without sounding childish, patronizing, or artificially casual.

## Explain the actual point of confusion

1. Identify what the user is trying to understand and where the conceptual gap is. Do not simplify unrelated parts of the task.
2. Read [references/expression-library.md](references/expression-library.md) and choose the method or framework that best fits the content and the user's question.
3. If the user specifies a lens or method, prefer it when it remains accurate. Repair a partly useful lens and explain the limitation; reject or replace it when it would create a false mental model.
4. If the user does not specify a method, select on fit rather than habit, popularity, or randomness. A familiar method is not automatically the right one.
5. Use one main explanatory approach. Combine a small number of supporting methods only when each one removes a real obstacle to understanding.
6. Write in the natural form the answer would otherwise use. Do not impose fixed headings, tables, or a canned sequence.
7. Build a path back to professional understanding: name the real concept, retain necessary formal details, and state where an example, analogy, or visualization stops matching reality.

Scientific accuracy is a hard constraint. Among accurate approaches, prefer the one that is most relevant to the user's confusion, easiest to understand, sufficiently complete, and natural to read. If no analogy or special device improves the explanation, use direct plain language instead of forcing one.

## Preserve substantive content

- Do not replace a requested proof, derivation, algorithm, code explanation, or decision rationale with a story or metaphor.
- Do not hide exceptions that materially change the answer.
- Do not make the answer longer merely to demonstrate an explanatory technique.
- Do not pretend the user understood; leave clear terms they can use in later study or follow-up questions.
- This invocation affects only the current response. Do not claim that the style will persist into later turns unless the user invokes the skill again.

## Notice genuinely new approaches

A new approach exists only when the response actually uses a core explanatory method or selection framework with no equivalent entry in the library. New wording, a different number, or a topic-specific instance of an existing method is not a new approach.

When either the user or the AI supplies and uses a genuinely new approach:

1. Finish the explanation first.
2. Ask the user once whether they want the approach prepared as a contribution to the public library.
3. If they agree, read [references/contributing.md](references/contributing.md) and produce the normalized contribution candidate.
4. Do not include private conversation content or personal information in the candidate.

Agreement to prepare a candidate does not grant permission to publish, push, or modify a remote repository. Perform those external actions only when separately authorized and available; otherwise give the user a ready-to-submit candidate.
