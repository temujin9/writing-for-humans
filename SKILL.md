---
name: writing-for-humans
description: Style rules for clear, concrete prose that reads like a person wrote it, free of AI mannerisms. Use when writing anything a human will read (documentation, articles, blog posts, emails, reports, summaries, README files, release notes, UI copy, conversational answers) and when asked to edit, polish, humanize, or make text "sound less like AI". Covers what to cut, what to say instead, and when formatting helps rather than hurts.
---

# Writing for humans

Machine-flavored prose has one root failure: it performs writing instead of informing. Emphasis without facts, structure without need, and hedges without doubt all imitate how good writing sounds while carrying nothing. Every rule below is the same instruction in a different form: have something to say, say it plainly, and stop.

Scope: prose a person will read. Code, identifiers, and machine-read output are exempt. If the platform or task dictates a structure (a template, a fixed report format), keep the structure and apply these rules to the sentences inside it.

## Rules

**1. Omit needless words.** If the sentence means the same without a word, cut the word; the same goes for sentences within paragraphs. Cut warm-up openers, wind-down closers, and stock filler ("It's worth noting that", "When it comes to", "At the end of the day") entirely: start at the point, stop at the last point.
> "It's worth noting that the cache is optional." → "The cache is optional."

**2. Be concrete.** Replace evaluative words with the fact that earned them. The vocabulary AI leans on (robust, seamless, pivotal, crucial, transformative, delve, leverage) is emphasis without information, and the fix is never a synonym: state the specific fact, or delete. Treat importance the same way: report what happened and let the reader weigh it, rather than claiming "a pivotal moment" or "a testament to". Intensifiers that perform precision ("exactly", "precisely", "simply", "the whole point", "load-bearing") are the same failure, and so are decorative analogies: an analogy earns its place only when it is the clearest available statement of the point.
> "significantly improves performance" → "cuts p95 latency from 2s to 300ms"

**3. Prefer active voice, positive form, and plain "is".** Name the actor. State what is, not what isn't. Let "is" and "has" do their jobs: "serves as", "stands as", "represents", and "offers" are dressed-up copulas.
> "Errors are handled by the middleware." → "The middleware handles errors."
> "It is not uncommon." → "It's common."
> "The library serves as a wrapper for the API." → "The library wraps the API."

**4. Say it; don't announce it.** Delete sentences about the writing instead of the subject: previews ("In this section we'll explore..."), significance claims ("This marks a pivotal shift..."), summaries that restate what the reader just read, and morals stapled to the end ("Ultimately, X reminds us that..."). The trailing participle is the clause-level version, vague analysis attached to a fact ("..., highlighting the importance of collaboration"): end at the fact. Test: if it would fit unchanged in a document on a different topic, it says nothing. Cut it.

**5. Don't fake insight with stock structures.** The false contrast asserts Y by denying an X nobody claimed: "It's not just X, it's Y", "This isn't about X. It's about Y.", "No X. No Y. Just Z." Assert Y directly; mention X only if someone actually believes it. The manufactured triad picks three parallel items for cadence, not content ("faster, cleaner, and more reliable"): if you have two points, list two. Reserve parallel form for genuinely parallel ideas.

**6. Hedge once or not at all, and name your sources.** Where uncertainty is real, qualify once and give the reason ("probably X, since the logs only cover one region"). Stacked qualifiers ("could potentially, in some cases") are evasion, and so is anonymous authority ("experts argue", "industry reports suggest"): name the source or drop the claim. When asked for a judgment, give one.

**7. Vary the rhythm.** Uniform sentence lengths and same-shaped paragraphs read as generated. Mix short sentences with long ones, and break any pattern you catch yourself repeating across sentences, bullets, or sections.

**8. Prose first; format on demand.** Default to paragraphs. Use bullets only for items a reader will scan or count, headings only when the reader will navigate by them, tables only for values compared across rows and columns. `**Term:** explanation` bullets are not a default mode of exposition. If the points connect, that's a paragraph. Bold marks the first use of a defined term; beyond that, bold little or nothing.

**9. Never use an em dash.** Rewrite with a comma, parentheses, a colon, or two sentences, and don't fake one with a spaced or doubled hyphen. The mark is legitimate English, but it has become the strongest single AI fingerprint, and any per-paragraph allowance gets abused in practice, so the allowance is zero. Punctuate quietly in general: semicolons and exclamation marks sparingly, at most one parenthetical aside per paragraph (rewrites of banned dashes like to pile up there), no emoji unless the venue uses them, sentence case for headings.

**10. Match the reader's register, consistently.** Contractions belong anywhere you would speak them. Plain words over formal ones: use, not utilize; people, not individuals; start, not commence. Call the same thing by the same name throughout; rotating synonyms implies distinctions you don't intend. And don't perform the relationship: no praise of the question, no "let's explore", no enthusiasm the content didn't earn.

## Revision pass

After drafting, reread once as an editor:

1. Does the first sentence state the point? If the real opener is buried in paragraph two, move it up.
2. Cut every sentence that fails the rule-4 test (fits any document unchanged).
3. Recheck each evaluative adjective (rule 2): replace it with the fact, or delete it.
4. Search for stock markers: "not just", "isn't about", "worth noting", "plays a role", "serves as". Rewrite each as a direct claim (rules 1, 3, and 5).
5. Search for em dashes and remove every one (rule 9). Then count bold spans and bullets; if either looks like a habit rather than a choice, halve it.
6. Read a middle paragraph as if aloud. If you wouldn't say it to a colleague, rewrite it in the words you would say.
7. Check the ending: stop at the last substantive point, not a moral ("Ultimately, ..."), a restatement, or an italicized zinger.

## References

The rules above are the principles and always apply; the reference files hold the inventories.

- [references/ai-tells.md](references/ai-tells.md): the full catalog behind the rules, with current word and phrase lists, sentence patterns, formatting habits, and tone tells, each with its fix. Read it whenever editing text that "sounds like ChatGPT", and to audit your own draft when the stakes warrant it. The word lists rot as models drift; the rules above are the durable form.
- [references/elements-of-style.md](references/elements-of-style.md): composition guidance distilled from Strunk (paragraph unity, topic sentences, parallel structure, emphasis by position). Read it for anything past a few paragraphs: documentation, essays, reports.
