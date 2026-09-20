# writing-for-humans

An agent skill that teaches language models to write prose that reads like a person wrote it: clear, concrete, and free of AI mannerisms. Distilled from Strunk's *The Elements of Style*, a survey of AI-writing criticism, and ASD-STE100 Simplified Technical English, and written to work across model sizes and families.

[SKILL.md](SKILL.md) holds ten always-on rules, an audience switch, and a revision pass. [references/ai-tells.md](references/ai-tells.md) catalogs the words, phrases, structures, formatting habits, and model-specific artifacts readers flag as machine-written, with fixes. [references/elements-of-style.md](references/elements-of-style.md) carries the composition principles for long-form writing. [references/technical-documentation.md](references/technical-documentation.md) is the profile for documentation that non-native readers or translators will use.

## Audiences

The ten rules apply to everything. Two audiences add rules of their own, and SKILL.md tells the model which file to read before drafting:

- Games, fiction, and worldbuilding: the "Worldbuilding and fiction" section of ai-tells.md (mystery-mongering, portent without event, the epithet parade) plus the rule-exception-example order in elements-of-style.md.
- Technical documentation for international readers: technical-documentation.md, which follows ASD-STE100 Issue 9 where feasible (sentence limits of 20 and 25 words, imperative steps, one instruction per sentence, no contractions, no semicolons, no "-ing" verb forms, articles kept, "must" and "can" in place of "should" and "may") and adapts the parts that were written for aircraft maintenance, supplemented with sentence-level and page-level rules from Google's Technical Writing course, GOV.UK, plainlanguage.gov, Microsoft, Mailchimp, 18F, Kubernetes, MDN, and Diátaxis. Where it conflicts with the base rules (rhythm, prose over lists, contractions, bold), it wins. Vale is documented there as an optional mechanical checker; it is not bundled.

## Cross-model design

The skill is written for any model that loads Agent Skills, not only Claude. The structure follows what the instruction-following literature supports: numbered imperative rules with a before-and-after example each; the hard limits stated up front and repeated in the revision pass, because models weight early instructions more heavily (Jaroslawicz et al., "How many instructions can LLMs follow at once?", 2025); a small rule count in SKILL.md, because compliance falls non-linearly as instructions stack and weaker models fall furthest (Anand and Chattaraj, "Instruction stacking collapse", 2026); and the long inventories in reference files loaded on demand. Bans are kept short and isolated ("never use an em dash") and paired with the positive form ("join clauses with a comma, a colon, or a period"), since vague or stacked prohibitions are where open models drift. Model-specific artifacts (DeepSeek and Gemini citation markup, GLM and Qwen language mixing, Kimi's default persona) are listed in ai-tells.md with fixes.

Nothing here has been benchmarked per model. If you run it on DeepSeek, GLM, Kimi, or Qwen and find a rule that fails to land, open an issue with the before-and-after.

## Install

Clone (or symlink) the repository into a skills directory. Claude Code reads `~/.claude/skills/`; Codex, Kimi Code CLI, OpenCode, Gemini CLI, and Deep Code all read `~/.agents/skills/`, so one clone there plus a symlink covers most harnesses:

```sh
git clone https://github.com/temujin9/writing-for-humans ~/.agents/skills/writing-for-humans
ln -s ~/.agents/skills/writing-for-humans ~/.claude/skills/writing-for-humans
```

Harness-specific directories, if you prefer them: Claude Code `~/.claude/skills/`, Codex `~/.agents/skills/`, Kimi Code CLI `~/.kimi/skills/`, Qwen Code `~/.qwen/skills/`, OpenCode `~/.config/opencode/skills/`, Gemini CLI `~/.gemini/skills/`, Deep Code `~/.deepcode/skills/`, Letta Code `~/.letta/skills/`. Each also has a project-level equivalent (`.claude/skills/`, `.agents/skills/`, and so on) that scopes the skill to one repository. Any harness that supports the [Agent Skills](https://agentskills.io/specification) format (a directory with a SKILL.md) can load it the same way.

## License

MIT. The Strunk material is public domain (1918). ASD-STE100 is copyright ASD; this skill paraphrases its rules and cites rule numbers but does not reproduce the standard or its dictionary.
