# Technical documentation for international readers

This file is the audience profile for documentation that non-native English readers, translators, or machine translation will consume. That includes user guides, installation and configuration guides, API references, runbooks, release notes, error messages, and UI help. Use it whenever the text is documentation and you do not know who will read it.

The governing standard is ASD-STE100, Simplified Technical English, Issue 9 (2025-01-15). STE has 53 writing rules and a dictionary of about 900 approved general words, each with one meaning and one part of speech. The writing rules transfer to software documentation almost unchanged. The dictionary does not: it was built for aircraft maintenance, and the standard itself lets each field add its own technical nouns and verbs (rules 1.5 and 1.12). This file keeps the rules, states how to approximate the dictionary, and marks the places where software documentation departs from STE. Rule numbers in parentheses refer to STE Issue 9.

## Precedence over the main rules

The ten rules in SKILL.md still apply. Where this file conflicts with them, this file wins. The conflicts:

- Rule 7 (vary the rhythm) is off. Short sentences of similar shape are the goal here, not a tell. A reader who translates as they read needs the same structure every time.
- Rule 8 (prose first) is narrowed. Descriptive text stays in paragraphs. Procedures become numbered steps with one action each. Sets of items become vertical lists. Tables hold values. The `**Term:** explanation` bullet list stays banned as a way to explain things.
- Rule 10 (match the register) changes in one place: no contractions (4.2). Plain words, one name per thing, and "you" for the reader all stay.
- Rule 9 (no em dash) stays, and STE adds the semicolon to the ban (8.1).
- Rule 3 (active voice) hardens. Procedures are always active and imperative. Descriptions use the passive only when the agent is unknown or does not matter (3.6).
- Rule 6 (hedge once) hardens. Documentation states facts, limits, and conditions. If a value depends on something, name the condition. If you do not know the value, tell the reader what to measure.

Everything else in SKILL.md stands as written: omit needless words, be concrete, say it without announcing it, no stock structures, no praise of the reader, no moral at the end.

## Rules

### Words

**T1. One word, one meaning, one part of speech.** Pick the shortest common word for each thing and use only that word (1.2, 1.3, 1.11, 9.4). Do not rotate synonyms. Do not use a word as a noun in one sentence and as a verb in the next unless the product itself does ("a build", "to build").
> "Start the daemon. Once the service is running, the process accepts connections." → "Start the service. When the service runs, it accepts connections."

**T2. Approximate the dictionary.** You will not have the STE dictionary in context. Use its habits instead: the most common short word, in its most common sense, the same word every time. Replacements the dictionary makes that matter in software documentation:
- "ensure", "verify", "check that" → "make sure that"
- "should", "shall" → "must"
- "may" → "can"
- "perform", "carry out", "execute" (a task) → "do"
- "utilize" → "use"
- "via" → "through"
- "display" (verb) → "show"
- "allow", "enable" (a person to do something) → "let"
- "the following" → "these", or name the items
- "e.g.", "i.e.", "etc." → "for example", "that is", "and so on" (GR-6)

Do not use idioms, slang, humor, or cultural references. Do not use a phrasal verb when one verb carries the meaning (9.3): "set up" → "install" or "configure", "shut down" → "stop", "find out" → "find", "carry out" → "do".

**T3. Technical nouns and verbs are exempt, and exact.** STE lets each field keep its own terms (1.5, 1.8, 1.12). In software those are product names, commands, flags, file paths, configuration keys, UI labels, API names, and error text. Spell them exactly as the product does, in code font when they are literal, and never translate or paraphrase them. Quoted text and code count as one word each for sentence length (8.6). Choose short, established terms (1.9) and never regional or slang ones (1.10). Spell out an abbreviation at first use with the abbreviation in parentheses (8.3), then use the abbreviation.
> "The `--dry-run` flag prints the plan and applies nothing." (Correct: `--dry-run` is a technical noun and stays as written.)

### Noun phrases

**T4. No more than three words in a multi-word noun** (2.1). Break longer strings with "of", "for", or a second sentence, and hyphenate words that belong together (2.2, 8.2).
> "the default retry backoff interval setting" → "the default interval for retry backoff"
> "the node pool autoscaler configuration file" → "the configuration file for the node-pool autoscaler"

**T5. Keep the small words in.** Use "the", "a", "an", "this", and "these" before nouns (4.5), except in general statements ("Solvents can cause damage to paint"). Use "that" after "make sure", "show", "check", and similar verbs (GR-1). Keep "who", "which", and "that" in relative clauses. Do not drop words or use contractions to shorten a sentence (4.2). These words tell a translator, a parser, and a tired reader where the clauses start and end.
> "Make sure config file exists and service's running." → "Make sure that the configuration file exists and that the service is running."

### Verbs

**T6. Use only these verb forms:** the imperative, the simple present, the simple past, the simple future, the infinitive, and the past participle as an adjective (3.2). No perfect or progressive forms and no other auxiliary constructions (3.4). Use "-ing" words only inside established technical nouns and in headings ("logging", "Troubleshooting") (3.5).
> "When you are running the migration, the service is being restarted." → "When you run the migration, the service restarts."
> "After having installed the agent, ..." → "After you install the agent, ..."

**T7. Active voice. Name the actor.** Procedures are always active (3.6). In descriptions, use the passive only when the agent is unknown or does not matter ("During transmission, the data was corrupted"). The reader is "you". The software is its name, or "the service", "the command", "the installer". Do not write "we".
> "The configuration is read at startup." → "The service reads the configuration at startup."

**T8. Instructions in the imperative, "must" for requirements, "can" for possibility.** Write each instruction as a command (5.3). Do not put "must" or "you can" in front of a command. Use "must" for limits and requirements, "can" for what is possible or permitted, and "will" for a result that follows. "Should", "may", "might", and "could" are ambiguous between advice, permission, and probability. The dictionary replaces the first two with "must" and "can", and the same fix applies to all four. Do not write "please".
> "You should run the tests before you commit." → "Run the tests before you commit."
> "The cache may be cleared by the user." → "You can clear the cache."
> "The value should not exceed 100." → "The value must not be more than 100."

### Sentences

**T9. Length limits.** At most 20 words in an instruction or a safety instruction (5.1). At most 25 words in a descriptive sentence or a note (6.3, 5.5). Each of these counts as one word (8.5 to 8.7): a number (with its unit, if it has one), an abbreviation, an identifier, a code span, quoted UI text, text in parentheses, and a hyphenated word. If a sentence is over the limit, split it or move the items to a vertical list.

**T10. One instruction per sentence, one topic per sentence** (5.2, 4.1). A step can hold two actions only when they happen at the same time ("Hold Shift and select the files"). In descriptions, give information gradually: one new fact per sentence, in the order the reader needs it (6.1).
> "Edit the file, save it, and restart the service so the change takes effect." → "1. Edit the file. 2. Save the file. 3. Restart the service. The change takes effect after the restart."

**T11. Condition first, then the command, with a comma between** (5.4). The reader must know the condition before the action. The comma also fixes which verb an adverb modifies, so place it with care.
> "Restart the service if the configuration changed." → "If the configuration changed, restart the service."

**T12. Punctuation.** Use the standard marks except the semicolon (8.1) and the em dash. Use parentheses for references, item identifiers, step labels, abbreviations at first use, "(s)" for singular and plural, and short explanations (8.3). Do not write slash constructions. "And/or" becomes "or" or "one or both of". "Read/write access" becomes "read and write access". Keep a slash only inside a technical noun the product spells that way (`I/O`, a URL path).

**T13. Vertical lists** (4.3, 8.4). Put a colon at the end of the sentence that introduces the list. Start each item with a capital letter. Put an article before the noun in each item where one belongs. Put a period at the end of an item only when it is a full sentence, and always at the end of the last item. No comma or semicolon at the end of an item. One level only: fold a sub-list into its parent item.

### Procedures

**T14. Steps.** Number the steps. Each step is one command (T8, T10). Give the expected result as a second sentence in the same step, not in a note: "Run the health check. The output must show `ok`." (5.5). Use "Make sure that" for a check the reader does. Put the condition first (T11).

**T15. Notes, cautions, warnings.** A note gives information only, never an instruction, a limit, or a result (5.5). If the reader needs the information to do the step, put it in the step. A safety instruction has three parts (7.1 to 7.3): a label for the level of risk, a command or condition, and the reason. STE reserves "warning" for risk of injury and "caution" for risk of damage. For software, treat data loss and unrecoverable changes as damage. Put the caution before the step it protects.
> "NOTE: Make sure that you back up the database first." → "CAUTION: Before you run the migration, back up the database. The migration deletes the old tables and does not roll back."

### Descriptive text

**T16. Paragraphs.** Start each paragraph with its topic sentence. Give each paragraph one topic (6.5). Keep paragraphs to six sentences or fewer (6.6). Group related information in one paragraph (6.4).

**T17. Connect sentences with the same words, not with synonyms.** Repeat the key term (6.2). Use the approved connecting words and phrases: "and", "but", "then", "thus", "as a result", "at the same time" (4.4). A sentence can start with "And" or "But". Do not open paragraphs with "Firstly", "Secondly", "Moreover", "Furthermore", or "In addition": they announce structure instead of stating it (rule 4 in SKILL.md).

### Reference and format

**T18. Pronouns.** Use "it", "they", "this", and "these" only when the referent is the one noun the reader will pick (GR-3, GR-4). Otherwise repeat the noun. Never write "he" or "she" for a reader or a user. Recast, or use "they" for a person (GR-7).
> "Delete the snapshot after the restore, because it is large." → "Delete the snapshot after the restore, because the snapshot is large."

**T19. Numbers, dates, and units.** Write numbers as digits, with a space before the unit ("10 GB", "300 ms"). Write dates as YYYY-MM-DD and times in 24-hour form with a time zone. Do not use formats that differ by country. (Google and Microsoft global guides. STE's own document dates itself 2025-01-15.)

**T20. Headings and cross-references.** Name a task heading by its verb or its noun: "Install the agent", "Configuration reference". Sentence case. Cite a heading exactly as written, and spend at most one cross-reference per paragraph. Use the same term, with the same capitalization, everywhere (Google).

**T21. Do not "fix" code or product text.** Commands, output, error messages, and UI labels are outside STE (8.6, quoted text). Reproduce them exactly and put them in code font. Do not translate them.

## Revision pass for this audience

Run this after the revision pass in SKILL.md.

1. Count the words in every step (limit 20) and every descriptive sentence (limit 25). Split the ones over the limit.
2. Search for words that end in "-ing". Keep only technical nouns and headings.
3. Search for apostrophes (contractions), semicolons, "e.g.", "i.e.", "etc.", "and/or", and slashes between words.
4. Search for "should", "may", "might", "could", "please", "simply", "just", "easily". Replace each with "must", "can", a fact, or nothing.
5. Check that every step starts with a verb, or with a condition, a comma, and then a verb.
6. Check that every "it", "this", "they", and "these" has one possible referent.
7. Check that nouns have their articles and that "that" follows "make sure", "check", and "show".
8. Check that notes give no instructions and that every caution states the risk.
9. Check that every term has one name and matches the product's spelling.
10. Read the first sentence of each paragraph in order. If they make an outline of the document, the structure is right.

## What does not transfer from STE

- The dictionary. Use T2 and T3 in place of the word list.
- Capitalized safety text. STE prints warnings in capitals for maintenance manuals. Software documentation uses the platform's admonition style. Keep the three parts of T15.
- The injury and physical-damage definitions of "warning" and "caution". Map data loss and security exposure to one of them by your platform's convention, and say which.
- American spelling (1.14). Follow the product's or the project's spelling, and be consistent.
- Aerospace word choices. The dictionary replaces "run" with "operate" (for engines) and "backup" with "emergency". In software, "run" and "backup" are technical terms and stay.

## Sources

- ASD-STE100, Simplified Technical English, Issue 9, 2025-01-15. Free after registration at asd-ste100.org. Rule numbers above refer to this issue. Issue 9 reworded 31 of the 53 rules and revised about 555 dictionary entries. The rules match Issue 8 (2021) in substance, except that the article rule (4.5) is new.
- Google developer documentation style guide, "Write for a global audience" (developers.google.com/style/translation): short sentences, simple words, present tense, no phrasal verbs, no idioms or humor, relative pronouns and helper words, consistent terms and capitalization, unambiguous dates.
- Microsoft Writing Style Guide, "Global communications: Writing tips" (learn.microsoft.com/style-guide/global-communications/writing-tips): include "that", "who", and articles, avoid modifier stacks, join at most two clauses with conjunctions, use one word per concept, take care with "-ing" and "-ed" words, and use common abbreviations only.
- John R. Kohl, The Global English Style Guide (SAS Press, 2008): the syntactic-cue principle behind T5, and the cardinal rule that no change should sound unnatural to a native reader.

Distilled September 2026.
