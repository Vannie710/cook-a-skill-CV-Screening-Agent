KILL SPEC: CV-SCREENING-AGENT (V1.0 – STRUCTURED HIRING ENGINE)

1. Skill Name & Description

Skill Name: CV Screening Agent (AI Talent Evaluation Co-Pilot)

Description:
An AI-powered evaluation system designed to standardize, score, and shortlist candidate CVs based on predefined hiring criteria. The agent ensures objective screening through structured scoring logic, bias minimization safeguards, and clear recommendation outputs.

2. Project Scope (MVP)
In-Scope:

CV parsing (PDF/DOC/TXT structured extraction)

JD-to-CV skill matching

Experience relevance scoring

Qualification filtering

Red-flag detection (employment gaps, job-hopping patterns, missing core skills)

Shortlist / Reject / Review recommendations

Out-of-Scope:

Behavioral interviews

Reference checks

Salary negotiation decisions

Culture-fit subjective assessment

Automated rejection emails

(Advanced AI ranking & predictive performance modeling will be implemented in later versions.)

Goal:

Create a consistent, bias-aware, data-driven screening layer to reduce manual HR workload and improve shortlist accuracy.

3. Input
3.1 User Input

Job Description (JD)

Required Skills (Mandatory & Preferred)

Seniority Level

Years of Experience Required

Screening Threshold (optional)

3.2 Candidate Data

CV file (PDF/DOC/TXT)

Portfolio link (if applicable)

GitHub/LinkedIn (optional structured data)

3.3 Configuration Metadata

Weight configuration matrix

Hiring policy constraints

Diversity & compliance safeguards

4. Processing (Internal Logic)
4.1 Parsing & Normalization

Extract structured fields:

Name

Years of Experience

Skills

Work History

Education

Certifications

Standardize synonyms (e.g., “ReactJS” → “React”)

4.2 Scoring Model (Weighted Matching)

The core scoring formula:

𝐹
𝑖
𝑛
𝑎
𝑙
𝑆
𝑐
𝑜
𝑟
𝑒
=
(
𝑆
𝑘
𝑖
𝑙
𝑙
𝑀
𝑎
𝑡
𝑐
ℎ
×
𝑊
𝑠
)
+
(
𝐸
𝑥
𝑝
𝑒
𝑟
𝑖
𝑒
𝑛
𝑐
𝑒
𝑀
𝑎
𝑡
𝑐
ℎ
×
𝑊
𝑒
)
+
(
𝐸
𝑑
𝑢
𝑐
𝑎
𝑡
𝑖
𝑜
𝑛
×
𝑊
𝑒
𝑑
𝑢
)
+
(
𝐵
𝑜
𝑛
𝑢
𝑠
×
𝑊
𝑏
)
−
(
𝑅
𝑖
𝑠
𝑘
𝑃
𝑒
𝑛
𝑎
𝑙
𝑡
𝑦
×
𝑊
𝑟
)
FinalScore=(SkillMatch×Ws)+(ExperienceMatch×We)+(Education×Wedu)+(Bonus×Wb)−(RiskPenalty×Wr)

Where:

Skill Match: % alignment with required skills

Experience Match: Alignment of total years + domain relevance

Education: Degree relevance to role

Bonus: Certifications, portfolio quality, awards

Risk Penalty: Employment gaps, frequent short tenures

Example Default Weights (MVP):

Ws = 0.4

We = 0.3

Wedu = 0.1

Wb = 0.1

Wr = 0.1

(Weights configurable by HR.)

4.3 Decision Logic
Final Score	Classification
≥ 80	Strong Shortlist
65–79	Review Required
50–64	Weak Match
< 50	Reject
4.4 Risk Flag Rules

Red flags triggered if:

3 jobs within 2 years

Employment gap >12 months (unexplained)

Missing mandatory skill

No relevant experience for senior role

Each flag contributes to Risk Penalty multiplier.

4.5 Bias Mitigation Layer

The system:

Ignores age, gender, ethnicity, marital status

Removes photo influence

Masks graduation year (optional mode)

Evaluates purely skill-based metrics

5. Output Standards

Tone of Voice:
Professional – Objective – Analytical

Response Structure:

Candidate Summary (Structured Snapshot)

Score Breakdown (Skill %, Experience %, etc.)

Risk Flags (if any)

Final Classification

Hiring Recommendation

Suggested Interview Focus Areas

6. Example Output (Use Case)

Candidate: Nguyen Van A
Role: Frontend Developer

Score Breakdown:

Skill Match: 85%

Experience Match: 78%

Education: Relevant (Bachelor in IT)

Bonus: GitHub portfolio (+)

Risk: 1 short tenure (8 months)

Final Score: 81

Classification: Strong Shortlist

Recommendation:
Proceed to Technical Interview Round 1.

Interview Focus:

Depth of React architecture

State management approach

System scalability awareness

7. Edge Cases & Exception Handling
7.1 Missing JD

Response:
“Screening cannot proceed without a structured Job Description. Please provide required skills and seniority level.”

7.2 CV Parsing Failure

Response:
“CV format unreadable. Please upload a machine-readable PDF or DOC file.”

7.3 Ambiguous Seniority

AI will ask:
“Is this role Junior, Mid, or Senior level? Scoring depends on experience threshold.”

7.4 Non-Technical Roles

If role lacks measurable skill metrics:
Switch to competency-weighted scoring model (future module).

8. Compliance & Auditability

All scoring logs are recorded

Weight configuration stored per hiring campaign

Every rejection decision traceable via scoring breakdown

Manual override allowed but logged

9. Success Criteria

✅ Reduced screening time by ≥50%

✅ Increased shortlist quality (Interview-to-Offer ratio improvement)

✅ 100% transparency in scoring

✅ Zero usage of protected attributes

✅ Configurable weighting per role
