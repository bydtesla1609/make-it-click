# Generic Agent Adapter

Clarity Bridge's core is platform-neutral Markdown. Do not rewrite or fork its rules for a particular model.

For an agent that does not discover `SKILL.md` natively:

1. Make `skill/clarity-bridge/SKILL.md` available as a system- or developer-level instruction for the current request.
2. Make `skill/clarity-bridge/references/expression-library.md` available when the agent chooses an explanation approach.
3. Provide `skill/clarity-bridge/references/contributing.md` only when a new approach was used and the user agreed to prepare a contribution.
4. Pass the user's actual question unchanged after the instructions.

Invoke the adapter only when the user explicitly requests Clarity Bridge. Do not keep it active for later requests unless the user invokes it again.

If the client cannot load files, paste the complete relevant files in the same order. The invocation syntax can vary by product; the substantive behavior must not.
