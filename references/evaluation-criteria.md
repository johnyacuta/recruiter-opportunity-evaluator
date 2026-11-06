# Evaluation criteria

## Title fit

Compare the role title and actual responsibilities with target titles the user provided during setup in the current conversation. A close title variant or strongly overlapping responsibilities can be a match; explain why. Do not require exact string equality. If no list was provided, mark title fit UNKNOWN. Title fit is a relevance signal, not a hard gate.

## Skills alignment

Compare the posting's required and preferred skills with the skills the user provided during setup in the current conversation. Summarize the strongest direct matches, transferable/adjacent skills, and material gaps. Account for equivalent tools or related experience without claiming equivalence as certainty. Do not infer proficiency level, years of experience, or hands-on experience unless the user or source message states it. If no candidate skills were provided, mark alignment UNKNOWN.

Keep certifications and their status accurate. A certification explicitly marked expired must be described as expired and must not count as a current certification. It may be mentioned as prior training or credential history only when relevant. Skills alignment is a fit signal, not a hard gate unless the user separately configures it as one.

## Hard gates

Evaluate remote/location eligibility and salary using preferences provided during setup in the current conversation. Direct full-time employment is always a hard gate.

- **PASS** — explicit evidence supports the requirement.
- **FAIL** — explicit evidence shows a configured hard requirement is not met.
- **UNKNOWN** — information is missing, ambiguous, inaccessible, or insufficient.

Do not infer missing terms from job titles, company norms, or recruiter optimism. If the user did not provide a salary floor, salary is UNKNOWN. A configured minimum salary is a hard gate.

Only explicitly stated direct full-time employment passes. Contract, contract-to-hire, part-time, or other non-full-time arrangements FAIL and are a no-go. If employment type is omitted or unclear, mark UNKNOWN and ask for clarification. Do not assume that full-time hours make a contract a full-time employment opportunity.

## Salary

Compare guaranteed base salary against the floor the user provided in the current conversation. Do not count bonus, equity, or commission unless the user explicitly says to. Entire range at/above floor: PASS; entirely below: FAIL; range straddles floor: UNKNOWN. Omitted/negotiable salary or unclear currency, period, or basis: UNKNOWN.

## Location and employment

Remote roles may restrict hiring by region. Compare restrictions with the user's stated eligible regions; unclear eligibility is UNKNOWN. Apply the user's stated remote preference. Direct full-time employment is always a hard gate.

## Quality signals

Financial health and culture are signals by default, not automatic disqualifiers. Apply a Glassdoor rating threshold as a hard gate only if the user explicitly asks for one during setup. A private company without public financial statements is UNKNOWN, not concerning. Explain evidence quality and conflicts.
