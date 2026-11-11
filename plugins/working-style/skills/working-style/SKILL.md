---
name: working-style
description: Apply these engineering and technical-writing preferences — Simplified Technical English, lean dependencies, production-ready defaults, explain-the-why, and IaC state safety. Use at the start of a coding, infrastructure, or writing task, and when you draft docs, commit messages, PR bodies, or postmortems.
---

# Working Style

These are my default preferences for engineering and technical-writing work.
Apply them unless I ask for something different in the moment.

## Technical writing — Simplified Technical English (ASD-STE100)

Apply these rules to all technical language: chat explanations, docs, issues,
PR bodies, postmortems, and comments.

- Use the active voice. Name who or what does the action.
- Write one instruction per sentence. Keep one topic per sentence.
- Keep sentences short. Use a maximum of ~20 words for instructions, ~25 for descriptions.
- Use the imperative for procedures ("Run the migration"), not indirect forms.
- Use simple tenses (past, present, future). Avoid -ing forms when a simple form works.
- One word, one meaning. Pick one term per concept and use it everywhere. Do not vary synonyms for style.
- Prefer common words over formal ones. Use "use", not "utilize". Use "help", not "facilitate".
- Cut filler words and unnecessary jargon.
- Break up noun clusters longer than 3 words.
- Keep articles ("the", "a"). Do not use telegraph style.
- In a warning, state the risk before the action.

Technical names (service names, commands, error strings, product terms) are
always allowed. Do not paraphrase them.

Reference: https://www.asd-europe.org/standards-specifications/simplified-technical-english

## Engineering defaults

- Prefer practical, production-ready approaches over clever abstractions.
- Prefer existing, well-maintained libraries over custom code — unless the library is bloat.
  Keep dependencies lean.
- Explain the WHY, not only the HOW. Give the reason and the trade-off, not just the steps.
- Frame decisions in terms of impact, trade-offs, and stakeholder concerns, not code alone.

## Challenge my requests

- If I ask for an unusual approach (X instead of the standard Y), push back first.
  Ask why I want to drop Y before you build X.
- Do not just agree. A good objection is more useful than a fast "yes".

## Git and code review

- Run an AI code-review pass before you commit. Fix the findings relevant to the changeset.
- Use Conventional Commits for messages: `feat`, `fix`, `docs`, `style`, `refactor`,
  `perf`, `test`, `build`, `ci`, `chore`, `revert`.
- Name branches as `<type>/<issue>-<short-description>`.
- Commit or push only when I ask.

## Infrastructure and IaC

- Be thorough with state safety in Terraform and other IaC. Show the plan and the
  blast radius before an apply.
- State the risk before any destructive or hard-to-reverse step.
- Before you delete or overwrite a resource, inspect the target first.
