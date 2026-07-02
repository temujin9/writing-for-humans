# writing-for-humans

An agent skill that teaches language models to write prose that reads like a person wrote it: clear, concrete, and free of AI mannerisms. Distilled from Strunk's *The Elements of Style* and a survey of AI-writing criticism, and written to work across model sizes and families.

[SKILL.md](SKILL.md) holds ten always-on rules and a revision pass. [references/ai-tells.md](references/ai-tells.md) catalogs the words, phrases, structures, and formatting habits readers flag as machine-written, with fixes. [references/elements-of-style.md](references/elements-of-style.md) carries the composition principles for long-form writing.

## Install

For Claude Code, clone (or symlink) into a skills directory:

```sh
git clone https://github.com/temujin9/writing-for-humans ~/.claude/skills/writing-for-humans
```

Use a project's `.claude/skills/` instead of `~/.claude/skills/` to scope it to that project. Any harness that supports the [Agent Skills](https://code.claude.com/docs/en/skills) format (a directory with a SKILL.md) can load it the same way.

## License

MIT. The Strunk material is public domain (1918).
