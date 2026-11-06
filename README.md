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
2. Edit the private copy with your salary floor, region, title preferences, skills profile, and other settings. The `.gitignore` excludes it from Git.
3. Provide the skill and its reference files to an assistant that supports reusable skills, then paste a recruiter message for evaluation.
4. Review the report, especially UNKNOWN items, and confirm research claims using linked sources.

Do not share or commit the private settings file. The example file should contain only generic or fictional values. If you already committed personal data, removing it from the latest version does not remove it from Git history.

## Job title preferences

Set `target_job_titles` to a YAML list and organize `candidate_skills` under the categories shown in the example. Skills categories contain lists; certifications are objects with `name`, `status`, and `expiration_date` (use `null` when there is no expiration date). The template's sample values are fictional formatting examples—replace them in your ignored local copy, and do not put your personal profile in the public template. The evaluator treats close title variants and adjacent skills as relevant matches, while distinguishing direct matches from gaps. `employment_type_is_hard_gate: true` means contract, contract-to-hire, part-time, or other non-full-time arrangements are a no-go; unclear terms are UNKNOWN until confirmed.

## MVP scope and limits

This repository contains instructions and examples, not a server, database, inbox integration, or guaranteed live research. The assistant checks hard gates first; it searches the official company careers site for the exact role and published compensation only after all configured hard gates pass. Research depends on available tools and permitted access. The evaluator does not contact recruiters or decide for the user. Glassdoor use must follow normal authorized access; scraping and access-control bypass are out of scope.

## Suggested manual checks

Try the fictional examples. Confirm explicit mismatches fail, absent information stays UNKNOWN, a salary range that crosses the configured floor remains UNKNOWN, title variants are treated sensibly, and research claims include sources. Never use real private recruiter messages in public examples.
