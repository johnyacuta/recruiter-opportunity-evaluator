# Evaluation criteria

## Title fit

Compare the role title and actual responsibilities with `target_job_titles` from the private settings. A close title variant or strongly overlapping responsibilities can be a match; explain why. Do not require exact string equality. If the list is empty or missing, mark title fit UNKNOWN. Treat title fit as a relevance signal, not a hard gate, unless the user explicitly configures otherwise.

## Skills alignment

Compare the posting's required and preferred skills with `candidate_skills` in the private settings. Summarize the strongest direct matches, transferable/adjacent skills, and material gaps. Account for equivalent tools or related experience without claiming equivalence as certainty. Do not infer proficiency level, years of experience, or hands-on experience unless the settings or source message state it. If no candidate skills are configured, mark alignment UNKNOWN.

Keep certifications and their status accurate. A certification explicitly marked expired must be described as expired and must not count as a current certification. It may be mentioned as prior training or credential history only when relevant. Skills alignment is a fit signal, not a hard gate unless the user separately configures it as one.

## Hard gates

Evaluate remote/location eligibility, employment type, and compensation according to the user's settings.

- **PASS** — explicit evidence supports the requirement.
- **FAIL** — explicit evidence shows a configured hard requirement is not met.
- **UNKNOWN** — information is missing, ambiguous, inaccessible, or insufficient.

Do not infer missing terms from job titles, company norms, or recruiter optimism. Without a configured salary floor, salary is UNKNOWN until clarified. If salary_floor_is_hard_gate is false, report the comparison as a preference signal, not a disqualifying gate.

When `employment_type_is_hard_gate` is true, only explicitly stated direct full-time employment passes. Contract, contract-to-hire, part-time, or other non-full-time arrangements FAIL and are a no-go. If employment type is omitted or unclear, mark UNKNOWN and ask for clarification. Do not assume that full-time hours make a contract a full-time employment opportunity.

## Salary

Compare guaranteed base salary when the user configured a base-salary floor. Do not count bonus, equity, or commission unless configured. Entire range at/above floor: PASS; entirely below: FAIL; range straddles floor: UNKNOWN. Omitted/negotiable salary or unclear currency, period, or basis: UNKNOWN.

## Location and employment

Remote roles may restrict hiring by region. Compare restrictions with allowed_work_regions; unclear eligibility is UNKNOWN. Apply remote_requirement and employment_type_requirement from settings. Employment type becomes a hard no-go when `employment_type_is_hard_gate` is true.

## Quality signals

Financial health and culture are signals by default, not automatic disqualifiers. Apply minimum_glassdoor_rating as a hard gate only when glassdoor_rating_is_hard_gate is true. A private company without public financial statements is UNKNOWN, not concerning. Explain evidence quality and conflicts.
