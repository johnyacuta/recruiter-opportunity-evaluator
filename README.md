# Recruiter Opportunity Evaluator

A skill-first MVP for evaluating recruiter messages you paste into an AI assistant. It checks configurable job-title preferences and hard requirements, optionally researches company signals using accessible sources, and returns an evidence-linked report.

## Repository contents

- `SKILL.md` — evaluator workflow and recommendation rules.
- `user_settings_config.yaml.example` — public template for personal settings.
- `.gitignore` — excludes the private `user_settings_config.yaml`.
- `references/` — evaluation criteria, company research guidance, and report format.
- `examples/` — fictional sample opportunities and expected outcomes.

## Configure and use

1. Copy `user_settings_config.yaml.example` to `user_settings_config.yaml` in the repository root.
2. Edit the private copy with your salary floor, region, title preferences, and other settings. The `.gitignore` excludes it from Git.
3. Provide the skill and its reference files to an assistant that supports reusable skills, then paste a recruiter message for evaluation.
4. Review the report, especially UNKNOWN items, and confirm research claims using linked sources.

Do not share or commit the private settings file. The example file should contain only generic or fictional values. If you already committed personal data, removing it from the latest version does not remove it from Git history.

## Job title preferences

Set `target_job_titles` to a YAML list. `employment_type_is_hard_gate: true` means contract, contract-to-hire, part-time, or other non-full-time arrangements are a no-go; unclear terms are UNKNOWN until confirmed. The evaluator treats close variants as relevant matches rather than requiring exact title text. Example titles in the template are illustrative; customize them privately.

## MVP scope and limits

This repository contains instructions and examples, not a server, database, inbox integration, or guaranteed live research. Research depends on the assistant's available tools and permitted access. The evaluator does not contact recruiters or decide for the user. Glassdoor use must follow normal authorized access; scraping and access-control bypass are out of scope.

## Suggested manual checks

Try the fictional examples. Confirm explicit mismatches fail, absent information stays UNKNOWN, a salary range that crosses the configured floor remains UNKNOWN, title variants are treated sensibly, and research claims include sources. Never use real private recruiter messages in public examples.
