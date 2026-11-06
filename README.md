# Recruiter Opportunity Evaluator

A skill-first MVP for evaluating a recruiter message you paste into an AI assistant. It checks configurable hard requirements, optionally researches company signals using accessible sources, and returns an evidence-linked report.

## Repository contents

- `SKILL.md` — agent workflow and recommendation rules.
- `references/evaluation-criteria.md` — PASS / FAIL / UNKNOWN and salary/location logic.
- `references/company-research.md` — source guidance and research/access limits.
- `references/report-template.md` — reusable output format.
- `examples/` — fictional sample opportunities and expected gate outcomes.

## Use

1. Review `SKILL.md` and set your own preferences in your assistant's private configuration or the conversation. Do not commit personal thresholds to this public repository.
2. Paste a recruiter message into an assistant that supports reusable skills and provide the skill files, or paste the relevant instructions and references into the conversation.
3. Review the report, especially UNKNOWN items, and confirm claims against linked sources before deciding.

The example settings and companies in `examples/` are fictional and illustrative. Salary and region preferences in examples are not recommendations.

## MVP scope and limits

This repository is instruction files and examples; it does not contain a server, database, inbox integration, or guaranteed live research. Research depends on the assistant's available tools and permitted access. The evaluator does not contact recruiters or make decisions for the user. Glassdoor access must use normal authorized access; scraping and access-control bypass are out of scope.

## Suggested manual checks

Try the good and bad fictional examples. Confirm that explicit mismatches fail, absent information stays UNKNOWN, salary ranges that cross the configured floor remain UNKNOWN, and research claims include working sources. Do not use real private recruiter messages in public examples.
