# Claude Code adapter

Claude Code natively supports the same `SKILL.md` structure used by Make It Click, so this adapter does not maintain a second prompt.

## Install

Copy the entire `skill/make-it-click` directory to one of Claude Code's supported locations:

- Personal, available in every project: `~/.claude/skills/make-it-click/`
- Project, available only in one repository: `.claude/skills/make-it-click/`

The resulting path must contain `SKILL.md` and its `references` directory:

```text
~/.claude/skills/make-it-click/SKILL.md
~/.claude/skills/make-it-click/references/expression-library.md
```

Restart Claude Code only if the top-level skills directory did not exist when the session started. Otherwise, Claude Code detects `SKILL.md` changes during the current session.

## Invoke and verify

Use `/skills` to confirm that the Skill is discoverable. Because the shared `SKILL.md` must remain portable across platforms, keep invocation manual through Claude Code's settings: open `/skills`, highlight `make-it-click`, press `Space` until it shows `user-only`, then press `Enter`. Claude Code writes the following project-local setting to `.claude/settings.local.json`:

```json
{
  "skillOverrides": {
    "make-it-click": "user-invocable-only"
  }
}
```

Use `/make-it-click` when you explicitly want the current question explained with this Skill. Do not apply it to later questions unless it is invoked again.

Do not copy `agents/openai.yaml` into a Claude-specific configuration file. It is Codex UI metadata and is not part of the shared behavior contract.

Official reference: [Extend Claude with skills](https://code.claude.com/docs/en/skills).
