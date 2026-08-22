# Expression Library

This is the single public library used by Clarity Bridge. It contains both individual explanation methods and frameworks for choosing methods based on the nature of the content.

The library is a toolbox, not a response template. Select entries by fit. Never select randomly or merely because an entry is common.

## Entry contract

Every entry records:

- **Type**: `method` or `framework`.
- **Solves**: the understanding problem it addresses.
- **Use when**: content or question characteristics that make it suitable.
- **Avoid when**: conditions that make it misleading or wasteful.
- **Procedure**: how to apply it without imposing a visible output template.
- **Combine with**: useful supporting entries, only when needed.
- **Why it works**: the cognitive bridge it provides.
- **Return path**: how to reconnect the explanation to formal language.
- **Example**: a compact illustration, not mandatory wording.
- **Accuracy boundary**: where the mental model stops matching the real concept.

## Methods

### `method.plain-language-bridge`

- **Type**: method
- **Solves**: Jargon or dense definitions that hide a simple core idea.
- **Use when**: The concept can be stated with familiar verbs and nouns before introducing its formal name.
- **Avoid when**: Rewording would remove a condition that determines whether the statement is true.
- **Procedure**: State the practical meaning in ordinary language, preserve the decisive conditions, then attach the formal term.
- **Combine with**: `method.concrete-example` or `method.contrast-and-boundary`.
- **Why it works**: It lets the user understand the idea before decoding its label.
- **Return path**: Repeat the formal term and connect each essential condition to the plain-language version.
- **Example**: Explain recursion as solving a smaller version of the same shaped task until a stopping condition, then name the recursive case and base case.
- **Accuracy boundary**: Plain words must not turn a precise definition into a loose slogan.

### `method.concrete-example`

- **Type**: method
- **Solves**: An abstract rule that the user cannot mentally execute.
- **Use when**: One representative instance can expose the objects, steps, and result.
- **Avoid when**: A single case would suggest that a general claim is always true.
- **Procedure**: Choose the smallest non-trivial example, walk through it, then identify which parts generalize.
- **Combine with**: `method.stepwise-causal-chain` or `method.counterexample`.
- **Why it works**: It turns symbolic or verbal rules into observable operations.
- **Return path**: Map the example's objects and steps back to the general rule.
- **Example**: Trace binary search on seven sorted values before naming the interval invariant and logarithmic complexity.
- **Accuracy boundary**: Label accidental properties of the example so they are not mistaken for requirements.

### `method.coherent-analogy`

- **Type**: method
- **Solves**: A new system whose roles and interactions resemble a familiar system.
- **Use when**: Stable mappings exist for the important objects, relationships, process, and cause-and-effect chain.
- **Avoid when**: The similarity is cosmetic, requires constant exceptions, or would replace a requested formal argument.
- **Procedure**: Choose one source world, keep mappings consistent, explain the important mechanism, then name the mismatches.
- **Combine with**: `method.contrast-and-boundary` and `method.plain-language-bridge`.
- **Why it works**: It transfers an existing mental model instead of making the user build one from isolated facts.
- **Return path**: Explicitly connect the familiar roles to the real terms and state where the analogy ends.
- **Example**: Explain a cache as a small nearby drawer for frequently used items while the complete store remains in a warehouse.
- **Accuracy boundary**: Physical distance and movement do not by themselves represent invalidation, consistency, concurrency, or eviction policy.

### `method.contrast-and-boundary`

- **Type**: method
- **Solves**: Two related concepts that sound interchangeable or differ along an invisible axis.
- **Use when**: The user asks for a distinction, scope boundary, responsibility boundary, or inclusion relationship.
- **Avoid when**: The concepts are not meaningfully comparable on a shared axis.
- **Procedure**: Establish what the concepts share, compare only decision-relevant axes, then give one boundary case.
- **Combine with**: `method.concrete-example` or `method.counterexample`.
- **Why it works**: Differences become memorable when attached to the same comparison frame.
- **Return path**: State each formal definition and the exact relationship between their scopes.
- **Example**: Compare user interface with front-end development by separating the visible interaction surface from the engineering work that implements it.
- **Accuracy boundary**: Real teams divide responsibilities differently; organizational roles are examples, not universal definitions.

### `method.spatial-geometric-view`

- **Type**: method
- **Solves**: Symbolic relationships that have a useful geometric interpretation.
- **Use when**: Position, direction, intersection, dimension, distance, transformation, or shape preserves the relevant structure.
- **Avoid when**: A low-dimensional picture would imply properties that fail in the actual dimension or non-geometric setting.
- **Procedure**: Map symbols to geometric objects or transformations, show the relationship spatially, then return to the algebraic statement.
- **Combine with**: `method.concrete-example` and `method.contrast-and-boundary`.
- **Why it works**: It lets the user see simultaneous constraints and structural relationships as one picture.
- **Return path**: Identify the equations, variables, solution set, and dimensional assumptions behind the picture.
- **Example**: View two linear equations as lines or planes whose intersections are solutions; contrast nonlinear equations with curved sets before performing the formal solution steps.
- **Accuracy boundary**: Two- and three-dimensional pictures are representations; higher-dimensional spaces and nonlinear solution sets may behave differently.

### `method.stepwise-causal-chain`

- **Type**: method
- **Solves**: A process that feels like a black box or a conclusion with hidden intermediate causes.
- **Use when**: State changes, dependencies, or sequential decisions determine the outcome.
- **Avoid when**: The system is primarily simultaneous, probabilistic, or recursive and a simple chain would invent an order.
- **Procedure**: Start from the relevant initial state, expose each state-changing step and its reason, and show the resulting state.
- **Combine with**: `method.concrete-example`.
- **Why it works**: It replaces a jump from input to output with inspectable transitions.
- **Return path**: Name the formal operation, invariant, dependency, or state transition at each important step.
- **Example**: Explain an HTTP request by following the request, routing decision, server work, and response while naming each component.
- **Accuracy boundary**: Do not turn concurrent events or feedback loops into a false single-file sequence.

### `method.counterexample`

- **Type**: method
- **Solves**: An over-broad intuition or a rule whose boundary is hard to see from positive examples.
- **Use when**: One carefully chosen failure case reveals a missing condition or distinguishes similar claims.
- **Avoid when**: The user first needs a basic positive model and the counterexample would only add confusion.
- **Procedure**: State the tempting belief, show the smallest case where it fails, identify the missing condition, and repair the belief.
- **Combine with**: `method.contrast-and-boundary`.
- **Why it works**: It makes an invisible constraint observable.
- **Return path**: State the corrected formal claim with the restored condition.
- **Example**: Use a function with a local minimum that is not global to explain why a local optimization method does not prove global optimality.
- **Accuracy boundary**: A counterexample disproves a universal claim; it does not establish a different universal rule.

### `method.layered-abstraction`

- **Type**: method
- **Solves**: A topic that is either overwhelming in full detail or misleading when reduced to one slogan.
- **Use when**: The user needs an intuitive overview and a route into progressively more formal detail.
- **Avoid when**: The answer is already simple or the user requested only a precise definition.
- **Procedure**: Move naturally from a compact mental model to the mechanism, then to the formal representation at the depth the question needs.
- **Combine with**: Any one content-specific method; do not stack layers merely for length.
- **Why it works**: It controls cognitive load without trapping the user at the simplified layer.
- **Return path**: Make the last useful layer use the real terminology, notation, or constraints.
- **Example**: Introduce a matrix as a transformation, show what it does to a vector, then connect that view to multiplication and linear maps.
- **Accuracy boundary**: Each simpler layer is partial; never present it as the complete definition.

## Frameworks

### `framework.term-or-definition`

- **Type**: framework
- **Solves**: “What does X mean?” questions where the label is unfamiliar.
- **Use when**: The user needs recognition, scope, and a usable formal term.
- **Avoid when**: The user already knows the definition and is asking about mechanism or consequences.
- **Procedure**: Select plain language as the base, then add a representative example and a nearby non-example or contrast when scope is unclear.
- **Combine with**: `method.plain-language-bridge`, `method.concrete-example`, `method.contrast-and-boundary`.
- **Why it works**: Meaning, instance, and boundary answer three different sources of confusion.
- **Return path**: End with the correct term and the minimum defining conditions.
- **Example**: Explain SEO and GEO by first stating the discovery channel each one optimizes for, then compare their targets and overlap.
- **Accuracy boundary**: Industry terminology may evolve; distinguish common usage from a formal standard when relevant.

### `framework.related-concepts`

- **Type**: framework
- **Solves**: “What is the difference between A and B?” when the concepts overlap.
- **Use when**: Shared examples or vocabulary make scope and responsibility easy to confuse.
- **Avoid when**: The terms are unrelated and a comparison frame would be artificial.
- **Procedure**: Select a shared comparison axis, state the overlap, compare decisive differences, and test the distinction on one example.
- **Combine with**: `method.contrast-and-boundary`, optionally `method.counterexample`.
- **Why it works**: It prevents a list of unrelated definitions from hiding the actual distinction.
- **Return path**: State whether the formal relationship is overlap, inclusion, implementation, sequence, or independence.
- **Example**: Compare user interface and front end through artifact, responsibility, and implementation rather than treating them as job titles.
- **Accuracy boundary**: Choose axes that belong to the concepts, not accidental practices of one company or tool.

### `framework.process-or-system`

- **Type**: framework
- **Solves**: “How does this work?” questions involving several actors or state changes.
- **Use when**: Components exchange information, transform state, or produce a result through dependencies.
- **Avoid when**: A formal static definition fully answers the question.
- **Procedure**: Identify actors and state, choose a causal chain or coherent analogy only if it preserves the interactions, then expose feedback or concurrency separately.
- **Combine with**: `method.stepwise-causal-chain`, `method.coherent-analogy`, `method.concrete-example`.
- **Why it works**: The user gains both a cast of characters and a mechanism.
- **Return path**: Name the components, states, interfaces, and causal dependencies.
- **Example**: Explain a web request by following one request while separating browser, network, server, and database responsibilities.
- **Accuracy boundary**: A walkthrough is one valid path, not necessarily the only path or the runtime schedule.

### `framework.math-or-algorithm`

- **Type**: framework
- **Solves**: A symbolic derivation or algorithm whose meaning is hidden by notation or code.
- **Use when**: The user asks for intuition, a solution process, or why the method works.
- **Avoid when**: The task asks only for a final value and no explanation, unless the user explicitly invokes Clarity Bridge for understanding.
- **Procedure**: Preserve the required derivation or algorithm; add the best fitting concrete trace, spatial view, invariant, or counterexample; then reconnect every intuition to the formal steps.
- **Combine with**: `method.spatial-geometric-view`, `method.concrete-example`, `method.stepwise-causal-chain`, or `method.counterexample`.
- **Why it works**: It connects manipulation, intuition, and correctness instead of choosing only one.
- **Return path**: Retain notation, conditions, proof obligations, complexity, or solution verification required by the question.
- **Example**: Explain systems of linear and nonlinear equations through intersections when appropriate, then perform and verify the algebraic solution.
- **Accuracy boundary**: A picture or trace is not a proof of a general claim; do not omit exceptional cases or dimensional limits.

### `framework.quality-or-style-diagnosis`

- **Type**: framework
- **Solves**: A vague judgment such as “AI-like,” “clunky,” or “not professional enough.”
- **Use when**: The user needs to understand what observable features produce the impression and what changes affect it.
- **Avoid when**: The label has not been tied to any artifact or context and multiple meanings remain equally plausible.
- **Procedure**: Translate the label into observable symptoms, connect each symptom to a likely cause, and use a focused before-and-after example rather than a generic style slogan.
- **Combine with**: `method.concrete-example`, `method.contrast-and-boundary`, `method.plain-language-bridge`.
- **Why it works**: It turns an intuition into inspectable features without dismissing the intuition.
- **Return path**: Name the relevant design, writing, product, or engineering concepts and preserve uncertainty where causes are not proven.
- **Example**: Explain “AI味” through repetitive structure, generic transitions, unsupported certainty, and uniform sentence rhythm, then show a targeted revision.
- **Accuracy boundary**: Symptoms are evidence, not proof of authorship; do not claim that style alone detects AI origin.
