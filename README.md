# Recruiter Opportunity Evaluator

A skill-first MVP for evaluating recruiter messages you paste into an AI assistant. It checks configurable job-title preferences and hard requirements, optionally researches company signals using accessible sources, and returns an evidence-linked report.

## Repository contents

- `SKILL.md` — evaluator workflow and recommendation rules.
- `.gitignore` — blocks any legacy `user_settings_config.yaml` from being committed.
- `references/` — evaluation criteria, company research guidance, and report format.
- `examples/` — fictional sample opportunities and expected outcomes.

## Configure and use

1. Provide the skill and its reference files to an assistant that supports reusable skills.
2. On first use in a conversation, answer the setup questions in natural language: salary floor/currency/period, remote and region preferences, target titles, skills and certification status, and any optional culture threshold. You do not need to edit or create a settings file.
3. Paste a recruiter message. The assistant reuses your answers in the same conversation; a new conversation starts setup again.
4. Review the report, especially UNKNOWN items, and confirm research claims using linked sources.

Preferences are kept in the conversation context only. The skill does not read or create a settings file, and the repository does not contain a user settings template. Conversation messages are still subject to the platform's normal retention and privacy settings. The `.gitignore` entry remains as a safeguard for legacy local settings files. If personal data was committed previously, removing it from the latest version does not remove it from Git history.

## Job title preferences

During setup, list target titles and skills in any convenient format. Include certification name and whether it is current or expired. The evaluator treats close title variants and adjacent skills as relevant matches, while distinguishing direct matches from gaps. Direct full-time employment is always a hard gate; contract, contract-to-hire, part-time, or other non-full-time arrangements are a no-go, and unclear terms are UNKNOWN until confirmed.

## MVP scope and limits

This repository contains instructions and examples, not a server, database, inbox integration, or guaranteed live research. The assistant checks hard gates first; it searches the official company careers site for the exact role and published compensation only after all configured hard gates pass. Research depends on available tools and permitted access. The evaluator does not contact recruiters or decide for the user. Glassdoor use must follow normal authorized access; scraping and access-control bypass are out of scope.

## Suggested manual checks

Try the fictional examples. Confirm explicit mismatches fail, absent information stays UNKNOWN, a salary range that crosses the configured floor remains UNKNOWN, title variants are treated sensibly, and research claims include sources. Never use real private recruiter messages in public examples.
