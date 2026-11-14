# Variant template

Copy this file to `variants/<id>.md`. The id is the filename without `.md`
(`en-US`, `ja-JP`, `es-MX`). Do not edit `SKILL.md`. The coach resolves a
variant by filename, then by `id` and `also_called` below.

Leave this `_TEMPLATE.md` in place. Files whose names start with `_` are not
offered as coaching targets.

Write the rules the coach should follow while producing the target language.
The explanation language is chosen per learner (default Simplified Chinese)
and does not belong in this file.

```markdown
# <id>

- id: <id>
- language: <language the practice is conducted in>
- variety: <the specific variety, in a few words>
- also_called:
  - <name a learner might say>
  - <another name, including the default learner's language>

## Coach voice

State that your own questions, model sentences, spelling, and pronunciation
follow this file for the whole session.

## Writing system

Concrete rules: spelling or script choices, punctuation habits, and pairs a
learner will confuse with a neighboring variety. Say which look-alike forms
are still valid and must not be marked wrong unless the learner asked for
strict consistency.

## Vocabulary

Everyday words where this variety parts company with a close neighbor.
Include a short gloss and, where a word is a false friend, say so.

## Everyday expressions

A handful of natural spoken expressions, each with a plain gloss and one
short example. Prefer current speech over textbook idioms.

## Grammar and usage

The points that actually change what a listener expects: agreement, tense or
aspect preferences, common particles or auxiliaries, and preposition choices.
Mark each one as a preference of this variety. Note the neighboring form
when it is still acceptable.

## Pronunciation

A teaching model, not every regional accent.

- The accent you are aiming at, named plainly.
- Sound contrasts that define it.
- A short list of word pairs with a broad transcription.
- What is common in real speech but is not the model you drill.
- A reminder that a neighboring accent's sounds are not errors unless
  strict consistency is on.

## Consistency

Your output stays inside this variety. If the learner produces a standard
form from another variety, understand it and continue. Mention the local
word only when the difference would confuse a listener, when they ask, or
when strict consistency is on. Never call a standard form from the other
variety "incorrect" on its own.
```

Checklist before you ship the new file:

- The filename, `id`, and the heading match.
- `also_called` includes the names a learner will actually type.
- Spelling, vocabulary, expressions, grammar, and pronunciation are each present and concrete.
- The consistency section tells the coach not to penalize the neighboring standard.
- No session-flow rules were copied into the variant. Flow lives in `SKILL.md`.
