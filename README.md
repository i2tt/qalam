# Qalam

Qalam is an agent skill that rewrites text which reads as AI-generated so that it reads as if a person wrote it while keeping every fact the text states

The skill is a single file named SKILL.md with no plugins and no build step

## Before and after

Before

> In today's fast-paced world the app is not just a note-taking tool but a journey toward organization
>
> It is worth noting that the app saves your notes automatically to your phone which enhances your productivity and ensures a bright future
>
> I hope this helps

After

> The app saves your notes to your phone automatically

The rewrite removes the opening claim, the contrast formula, the productivity and future claims, and the closing line because the text gives no support for them. It keeps the one fact the text states.

## What changed from the original

- Removed plugin files and platform-specific validation files
- Added a fact ledger that records names, numbers, dates, and quotes before editing and checks the rewrite against it
- Forbade adding any detail that does not come from the text, the user, or a source read in the session
- Added review mode, which flags tells without rewriting
- Added a section on vague figures (pattern 27)
- Added a rule that output stays in the language and register of the input
- Protected historical text and older translations from modernization

## Installation

For Claude Code on Windows PowerShell

    git clone https://github.com/i2tt/qalam.git "$env:USERPROFILE\.claude\skills\qalam"

For Claude Code on macOS or Linux

    git clone https://github.com/i2tt/qalam.git ~/.claude/skills/qalam

For any other agent that supports skills, place SKILL.md inside a folder named qalam in the skills folder that your agent reads from

## Usage

- Pasted text: write "use qalam on this text" and paste the text
- A file: write "use qalam on README.md"
- Check only: write "check this text with qalam without rewriting"
- To keep your own voice: paste a sample of your writing and the skill will follow the sample over the default rules

## Modes

- Pasted text returns a draft, a list of remaining patterns, and the final version
- File mode reads the whole file, edits prose only, leaves code, commands, paths, YAML, and link targets unchanged, and summarizes which sections it reviewed and which it did not cover
- Embedded mode returns only the final text when another task uses the skill for a pull request, commit message, or document
- Review mode returns each tell with its quote, pattern number, and strength, without rewriting

## Method

1. Record the facts in the text, then mark each AI pattern, strongest first
2. Write a draft that keeps every supported claim
3. Compare the draft with the fact ledger, then read it aloud and look for remaining AI patterns
4. Write the final version in plain prose

## Patterns

Patterns are sorted from strongest to weakest inside each section. Patterns 1 to 5 are enough on their own to justify an edit.

### A. Staging instead of stating

1. Negation then affirmation (not X but Y)
2. Short punchy closers and clipped phrases
3. Phrases that suggest depth
4. A lead-in before the point
5. Answering an objection nobody raised

### B. Rhythm by rule

6. Forced triplets
7. Repeated sentence openers
8. Dashes as a catch-all connector
9. Piled-up hedges
10. Hyphenated compounds in every position
11. Passive voice with the agent removed

### C. Inflation and borrowed authority

12. Words that models overuse
13. Inflating importance
14. Vague attribution
15. Shallow commentary phrases
16. Advertising language
17. Citing unnamed authority
18. Avoiding plain verbs such as is, are, and has

### D. Formatting by rule

19. Bold text as decoration
20. Decorative headings
21. Curly quotation marks

### E. Chatbot residue and drafting traces

22. Chatbot residue
23. Knowledge-cutoff and speculation disclaimers
24. A heading repeated in the first sentence
25. Writing about the document instead of its subject

### F. Writing for the wrong reader

26. Explaining what the reader already knows

### G. Vague figures

27. Vague quantities and times

## When the skill does not act

- Text inside a quotation, heading, or proper name
- Text written before November 30, 2022
- Historical documents and older translations, which keep their vocabulary and spelling
- Quran verses, hadith, poetry, and proverbs
- Details that carry the author's voice, such as a rare fact, an honest hesitation, or a joke tied to its time

## Repository layout

- SKILL.md is the skill itself
- README.md is this file
- CHANGELOG.md is the version history
- LICENSE is the MIT license

## Source and license

The patterns come from the Wikipedia guide Signs of AI writing maintained by the WikiProject AI Cleanup, and from reviews of AI-generated text.

<p align="center">
  <a href="https://github.com/i2tt"><img src="https://img.shields.io/badge/AgentcYper-GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="i2tt" /></a>
  <a href="https://soar-team.xyz/"><img src="https://img.shields.io/badge/Website-soar--team.xyz-111111?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website" /></a>
</p>NSE.
