# Changelog

## 5.0.0

Release date 2026-11-17

- Based on Humanizer 4.0.0 by Siqi Chen
- Removed plugin files and platform validation files, so the skill is one file named SKILL.md
- Added a fact ledger that records names, numbers, dates, and quotes before editing and checks the rewrite against it
- Forbade adding any detail that does not come from the text, the user, or a source read in the session
- Added review mode, which flags tells without rewriting
- Added a language rule that keeps the output in the language and register of the input
- Added pattern 27 for vague quantities and times
- Protected historical text and older translations from modernization
- Made SKILL.md English only

## 4.0.0

Original Humanizer release with 26 patterns