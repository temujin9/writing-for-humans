# AI writing tells

Patterns readers flag as machine-written, with fixes. The rules in SKILL.md distill these into principles that always apply; this file is the expanded inventory, for editing text that sounds like AI or auditing a draft of your own.

Two cautions before applying it:

- The word lists date quickly. Models stopped overusing "delve" and started overusing other words; this catalog was distilled in July 2026 and will drift too. The durable test for any sentence: (1) does it tell this reader something they didn't know? (2) would it survive unchanged in a document about a different subject? Fix what fails either test, whether or not it appears below.
- Everything here is grammatical English, and most items are tells by density rather than single use: one bolded phrase is emphasis, ten on a page are a fingerprint. The em dash is the exception. Soft limits on it get ignored, so the main rules ban it outright.

## Contents

- Vocabulary
- Stock phrases
- Sentence patterns
- Structure and formatting
- Tone
- Model-specific tells
- Worldbuilding and fiction

## Vocabulary

Words that add emphasis without information. The fix is never a synonym (swapping "robust" for "resilient" changes nothing): state the specific fact, or delete.

- Empty intensity: pivotal, crucial, vital, essential, key, critical (as filler), significant, transformative, game-changing, groundbreaking, cutting-edge, revolutionary, innovative, seamless, robust, comprehensive, holistic, multifaceted, nuanced, intricate, dynamic, vibrant, rich
- Inflated verbs: delve, dive into, leverage, harness, foster, bolster, underscore, showcase, elevate, empower, streamline, unlock, unleash, unpack, embark, navigate (figurative), shed light on, pave the way
- Scene-setting nouns: landscape (figurative), realm, tapestry, journey, ecosystem (figurative), space ("in the AI space"), synergy, paradigm
- Grandiosity: testament, beacon, cornerstone, pinnacle, myriad, plethora, boasts
- Precision theater: exactly, precisely, simply, merely, "the whole point", "which is exactly why", load-bearing (figurative)

## Stock phrases

Delete these; the sentence usually survives intact.

- "In today's fast-paced / ever-evolving / digital world..." → start with the subject
- "It's important to note that X" / "It's worth noting that X" → "X"
- "When it comes to X" → "For X", or restructure
- "At its core" / "At the end of the day" / "Ultimately," → delete
- "plays a crucial role in X" → say what it actually does
- "One of the most important..." → state the specific claim instead of ranking it
- "This is where X comes in" / "Enter X." → describe X
- "Let's dive in" / "Let's break it down" → say the first real thing
- "cannot be overstated" → it can; state it
- "the fact that" → "that", or recast
- "In conclusion" / "To summarize" (in short pieces) → end on the last point
- "I hope this helps!" / "Feel free to..." → end when done
- "Great question!" and other praise of the prompt → answer it
- Unprompted disclaimers ("as of my knowledge cutoff", "as an AI") → omit unless the limitation matters to this answer

## Sentence patterns

**The false contrast.** "It's not just X — it's Y." / "This isn't about X. It's about Y." / "Not only X, but also Y." / "No X. No Y. Just Z." These deny a claim nobody made to make Y sound like insight. Assert Y directly; mention X only if someone actually believes it.

**The manufactured triad.** Three parallel items chosen for cadence, not content ("faster, cleaner, and more reliable"). If you have two points, list two. Reserve parallel form for genuinely parallel ideas.

**The trailing participle.** A fact with vague analysis stapled on: "..., highlighting the importance of...", "..., ensuring that...", "..., reflecting a broader trend...". End at the fact, or make the analysis a real claim with support.

**Copula avoidance.** "serves as", "stands as", "functions as", "represents", "marks", "offers" where "is" or "has" belongs. "The library serves as a wrapper for the API" → "The library wraps the API."

**Significance inflation.** "a pivotal moment in", "solidifying its position as", "underscoring its commitment to". Importance claimed rather than shown. Report what happened; let the reader weigh it.

**Weasel attribution.** "Experts argue", "Industry reports suggest", "Observers have noted", "Some critics say". Name the source or drop the claim.

**Hedge stacking.** "could potentially", "may possibly, in some cases". One qualifier, with a reason, where uncertainty is real; none elsewhere.

**Elegant variation.** Rotating synonyms to avoid repeating a word: "the tool... the utility... the platform... the solution". Repeating the right word is correct; rotation implies distinctions you don't intend.

## Structure and formatting

- `**Term:** explanation` bullet lists as the default way to explain anything. The most recognized AI pattern. If the explanations connect, write a paragraph.
- Em dashes, in any quantity → the main rules ban them outright; rewrite with a comma, parentheses, a colon, or a period. A ration would just get abused.
- A heading every paragraph or two. Use headings only where a reader navigates by them; short pieces need none.
- Title Case Headings → use sentence case.
- Bold scattered across many phrases per page → bold the first use of a defined term; beyond that, little or nothing.
- More than one parenthetical aside per paragraph → restructure the sentences; asides multiply when writers reroute banned em dashes into parentheses.
- The italic one-liner closing a paragraph or section (*the zinger*) → cut it, or say it plainly in the paragraph.
- Emoji as bullets or in headings → none, unless the venue already uses them.
- A horizontal rule before every section → let headings do the separating.
- Tables for content that isn't a comparison of values → prose or a plain list.
- The formulaic wrap-up section ("Conclusion", "Challenges and future directions") that restates the piece → end at the last substantive point.

## Tone

- Sycophancy: praising the question or reader before answering.
- False collaboration in one-way text: "you might wonder", "let's explore", "join me as we".
- The moralizing close: "Ultimately, X reminds us that...". No lesson-of-the-day endings.
- Uniform enthusiasm: everything "exciting" or "fascinating". Flat is fine; earned emphasis lands harder.
- Register inflation to sound authoritative: "utilize", "individuals", "commence" for "use", "people", "start". Specificity is the authority; formality is costume.
- Decorative analogies and vivid images. An analogy earns its place only when it is the clearest available statement of the point; otherwise it is ornament.

## Model-specific tells

The tells above are shared across model families. These vary by family, as of September 2026, and they rot fastest of all: trust the fix over the attribution.

- Markup artifacts. Citation and tool markup left in the answer: DeepSeek leaves lenticular brackets (【 】) and dagger symbols; Gemini leaves `[cite: 1]` markers; Grok and Perplexity leave JSON-like card and file-upload tokens (Wikipedia, "Signs of AI writing"). Fix: delete every artifact and cite in plain words, or in the venue's own citation format.
- Language mixing. Models trained on large Chinese corpora sometimes switch script mid-answer. GLM-5.1 has a documented habit of dropping into Chinese for a sentence when the context mentions Chinese companies or domains (zai-org/GLM-5, issue 54), and Qwen has carried the same report since its first release (QwenLM/Qwen, issue 543). A system-prompt instruction reduces it but does not remove it. Fix: reread the output for any script the reader did not ask for and rewrite the sentence.
- Learner-English transfer. Patterns documented in Chinese-English learner writing (dropped articles and plurals, "so" as the default connector, "Firstly / Secondly / Lastly" as paragraph openers) also appear in English from models whose training data leans Chinese. This is an inference from the learner-corpus literature, not a measurement of the models; treat it as a watch list. Fix: restore the articles and plurals, keep "so" for consequence only, and delete the enumerators.
- Reasoning leakage. Models with thinking on by default (Kimi K3 returns reasoning on every call; DeepSeek and GLM in thinking mode) can let planning language into the answer: "The user wants...", "Let me think about...", "First, I should...". Community-observed rather than measured. Fix: the answer starts at the answer.
- Default persona. Some chat templates inject a persona when the caller sends no system prompt (Kimi K2's template adds "You are Kimi, an AI assistant created by Moonshot AI"). If the output introduces itself or names its maker, cut the self-introduction.

## Worldbuilding and fiction

This section is the audience profile for games, fiction, and worldbuilding; SKILL.md routes here.

Creative prose has its own filler register: vagueness performing depth.
These read as atmosphere and carry nothing.

- Mystery-mongering: "lost to time", "shrouded in mystery", "none now
  remember", "some say", "worth never quite saying", the answer withheld to
  simulate wonder. If the work knows the answer, state it. If it doesn't,
  make the ambiguity a deliberate, named choice (competing accounts, a
  recorded dispute), not a shrug; and remember that in-world practitioners
  are not mystified by their own business.
- Portent without event: "little did they know", "would prove to be", "a
  chill wind blew" as significance-signaling. Foreshadow with facts the
  reader can later check, or cut.
- The epithet parade: rotating titles for one entity ("the ancient one",
  "the dark sovereign", "the nameless king"). Elegant variation in a cloak;
  pick the name and use it.

## Sources

Distilled July 2026 from [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), [Will Francis: How to stop Claude writing like an AI](https://willfrancis.com/how-to-stop-claude-writing-like-an-ai/), and a sample of similar critiques; composition rules trace to Strunk (see elements-of-style.md).

Model-specific tells added September 2026 from the same Wikipedia page, the [GLM-5](https://github.com/zai-org/GLM-5/issues/54) and [Qwen](https://github.com/QwenLM/Qwen/issues/543) issue trackers, the Kimi K2 and K3 model cards on Hugging Face, and the World Englishes literature on Chinese English (Albrecht 2023) with EFL error studies of Chinese learners.
