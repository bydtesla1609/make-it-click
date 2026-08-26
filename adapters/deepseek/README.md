# DeepSeek adapter

DeepSeek's Chat Completion API accepts a `system` message, but its official API documentation does not define a Claude Code-style directory that automatically discovers `SKILL.md`. This adapter therefore loads the shared Skill as a system prompt instead of pretending that file-based installation is available.

## Supported path

Use this adapter with the DeepSeek API or a client that lets you set a system prompt:

1. Read the complete contents of `skill/make-it-click/SKILL.md`.
2. Append the complete contents of `skill/make-it-click/references/expression-library.md` to the same `system` message so the model can select a fitting explanation method.
3. Send the user's actual question unchanged as the following `user` message.
4. Apply this adapter only when the user explicitly requests Make It Click, and do not keep it active for later unrelated questions.

If a genuinely new explanation approach was used and the user agrees to prepare a public contribution candidate, also append the complete contents of `skill/make-it-click/references/contributing.md`. DeepSeek cannot follow a local Markdown link unless the calling application supplies that file's contents.

Minimal message shape:

```json
{
  "messages": [
    {
      "role": "system",
      "content": "<complete SKILL.md>\n\n<complete expression-library.md>"
    },
    {"role": "user", "content": "<question to explain>"}
  ]
}
```

The model name, SDK, and transport are deliberately left to the calling application; they do not change Make It Click's behavior.

## Web-chat fallback

If a DeepSeek interface does not expose a system prompt, paste the complete `SKILL.md` and `expression-library.md` contents at the start of a new conversation and ask the model to apply them only to the next question. This is a best-effort fallback, not persistent installation, and its instruction priority may be weaker than an API system message.

Official reference: [DeepSeek Chat Completion API](https://api-docs.deepseek.com/api/create-chat-completion/).
