# Clarity Bridge behavior checks

These cases test decisions, not exact wording or a fixed response layout.

## Case 1 — User-specified spatial view

**Prompt**

> 使用 $clarity-bridge，从空间立体几何的角度讲讲高等代数中求解线性和非线性方程组。

**Expected behavior**

- Prefer the requested spatial-geometric view because it is useful here.
- Connect equations to lines, planes, curves, surfaces, and intersections at an appropriate dimension.
- Return to the formal ideas of variables, constraints, solution sets, and algebraic solution methods.
- State that low-dimensional pictures do not capture every higher-dimensional or nonlinear behavior.
- Do not replace the requested mathematical content with imagery alone.

## Case 2 — Unspecified terminology question

**Prompt**

> 使用 $clarity-bridge，SEO 和 GEO 是什么意思？

**Expected behavior**

- Select a fitting method based on the question rather than defaulting to an analogy.
- Explain the shared purpose and decisive difference in plain language, then give the professional terms and boundaries.
- Use examples only when they clarify the distinction.
- Keep the answer natural rather than exposing a fixed Skill template.

## Case 3 — Vague quality judgment

**Prompt**

> 使用 $clarity-bridge，你现在做的项目该怎样降低 AI 味？

**Expected behavior**

- Translate “AI 味” into observable features relevant to the actual project.
- Distinguish evidence from certainty; do not claim that style proves AI authorship.
- Use targeted before-and-after examples or another fitting method.
- Return to precise writing, design, or engineering terms.

## Case 4 — Misleading requested analogy

**Prompt**

> 使用 $clarity-bridge，把量子纠缠解释成两个人提前约好答案，所以测量才总是一致。

**Expected behavior**

- Do not obey the requested analogy as stated because it creates a false classical hidden-variable model.
- Explain the mismatch clearly and either repair the lens or choose a more accurate approach.
- Preserve the user's goal of intuitive understanding without trading away scientific accuracy.

## Case 5 — Proof must remain a proof

**Prompt**

> 使用 $clarity-bridge，证明根号 2 是无理数，我总看不懂反证法。

**Expected behavior**

- Keep the actual proof and every necessary logical step.
- Add a fitting explanation of contradiction or a small supporting example.
- Name the assumptions, contradiction, and conclusion formally.
- Do not present an analogy as proof.

## Case 6 — No forced analogy

**Prompt**

> 使用 $clarity-bridge，API 就是程序之间说话的方式吗？

**Expected behavior**

- Start from the user's existing intuition and refine it in plain language.
- Use no elaborate analogy when a direct explanation is clearer.
- Add interfaces, rules, requests, and responses only to the depth needed.

## Case 7 — User creates a new method

**Conversation state**

The user specifies a new explanatory mechanism that has no equivalent library entry. The agent uses it because it is the best accurate approach for the question.

**Expected behavior**

- Finish the explanation first.
- Ask once whether the user wants the method prepared as a public-library contribution.
- If the user agrees, normalize the reusable method instead of copying the conversation.
- Do not claim that the candidate was published.

## Case 8 — AI creates a new framework

**Conversation state**

The agent derives and uses a new rule that matches different content properties to different explanation methods. No equivalent framework exists in the library.

**Expected behavior**

- Treat the selection rule itself as a possible framework entry.
- Ask after the answer whether the user wants a contribution candidate.
- Do not use vague popularity or frequency as evidence that the framework belongs in the library.

## Case 9 — Variation is not novelty

**Conversation state**

The answer uses `method.concrete-example` with a new set of numbers and a different topic.

**Expected behavior**

- Do not ask to add a new method merely because the example is new.
- Ask only if the reusable explanatory mechanism or selection rule is absent from the library.

## Case 10 — Explicit invocation boundary

**Prompt**

> SEO 和 GEO 是什么意思？

**Expected behavior**

- Do not invoke Clarity Bridge automatically.
- Ordinary answering behavior remains unchanged unless the user explicitly invokes the Skill.

## Cross-platform parity

Run Cases 1, 4, 7, and 10 through each target agent. Invocation syntax may differ, but method selection, accuracy boundaries, novelty handling, and explicit-only activation must remain substantively the same.

## Failure conditions

- The answer loses required facts, proof steps, code reasoning, caveats, or professional terms.
- A familiar analogy is selected despite a better-fitting method.
- A method is chosen randomly, by popularity, or only because it was used before.
- User preference overrides scientific accuracy.
- The response is forced into a visible template.
- The tone is childish or patronizing.
- Every new example triggers a contribution prompt.
- A contribution candidate contains private conversation details.
- The agent implies that an unsubmitted candidate is already in the public library.
