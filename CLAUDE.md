# Job Application Assistant for Gustavo Pernas

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Gustavo Pernas, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Gustavo Pernas
- **Location:** Dublin, Ireland (EU citizen; hybrid-in-Dublin preferred, open/flexible, occasional travel acceptable)
- **Languages:** Spanish (Native), English (Fluent), Portuguese (Professional), French (Basic)
- **Status:** Between roles (most recent role at TikTok ended Dec 2025); open to senior operations / client services / customer success leadership opportunities
- **LinkedIn headline:** "Operations & Service Delivery Leader | Head of Client Services | Support Operations & Vendor Management | Commercial & Sales Leadership | AI-Enabled Transformation"

### Education
- **MBA** (2010-2011) - Hult International Business School
- **Professional Diploma in Advanced Artificial Intelligence** (Distinction) (2026) - UCD Professional Academy
- **Professional Diploma in Operations Strategy** (2026) - Hult International Business School
- **Diploma in Change Management, Operations Management and Supervision** (2023) - UCD Professional Academy
- **BBA in Business Administration** (1996-2001) - University of Santiago de Compostela

### Professional Experience
- **Regional MPO Lead, Solutions Engineering, EMEA** (Sep 2024 - Dec 2025) - **TikTok** (Dublin)
  - Led transformation of a 40+ Technical Support Engineer org across EMEA/LATAM (follow-the-sun), delivering 2.5x productivity growth via AI-enabled process optimisation
  - Implemented Refund Abuse Prevention framework, cutting abuse volume 48% with Legal, Fraud and AdEx teams
- **Head of Client Services, EMEA** (Jan 2021 - Sep 2024) - **TikTok** (Dublin)
  - Led 50+ specialists across 34 markets and 10 languages; owned CSAT, SLA, FRT, FTR, TTR, quality and escalations across internal and vendor delivery
  - Launched Concierge Support (FRT -84%, TTR -55%) and hybrid Live Chat (CSAT +40%, escalations -28%); served 7 months as Interim Global Head of Client Services
- **Regional Vendor Manager Lead, EMEA** (Dec 2020 - Dec 2022, concurrent) - **TikTok** (Dublin)
  - Managed 4 BPO partners; Activation Program raised advertiser activation 30% and vendor-led revenue 20%
- **Partnerships** (Apr 2019 - Dec 2020) - **Pinterest** (Dublin) - partner retention >85%, doubled partner engagement
- **Partner & Project Manager / Senior Partner Manager** (2014 - 2019) - **Meta** (Dublin) - EMEA sports & SMB advertising; Interim Sales Leader
- **Account Manager & Quality Lead (TTEC)** (2012 - 2013) - **Google** (Dublin)
- **Business Development Manager** (2005 - 2010) - **Trabe Gestión S.L** (Lugo, Spain) - led 6-person team, 200% sales growth in 14 months

### Technical Skills
- **Primary:** Client services & customer success leadership, support/service delivery operations, escalation management, KPI/SLA governance, vendor & BPO management, operating-model design, process improvement, people leadership & coaching
- **Secondary:** Salesforce & CRM/ticketing platforms, SQL, Tableau, data analytics, billing/payments operations, fraud/refund-abuse prevention, change management (ADKAR/Agile), programme management
- **Domain:** B2B technology platforms, ad-tech / digital advertising operations, multilingual EMEA + LATAM service delivery
- **Software:** Salesforce, CRM & ticketing platforms, knowledge management systems, Tableau, SQL

### Certifications
- **Professional Diploma in Advanced Artificial Intelligence** (Distinction) - UCD Professional Academy - 2026
- **Professional Diploma in Operations Strategy** - Hult International Business School - 2026
- **Diploma in Change Management, Operations Management and Supervision** - UCD Professional Academy - 2023
- **Google Search Advertising Advanced** / **Google Advertising Fundamentals** - 2013

### Publications
- None on file.

### Awards
- None on file.

### Behavioral Profile
<!-- Inferred from LinkedIn About + achievements; no formal assessment on file. See 02-behavioral-profile.md. -->
- **Results-driven** - frames work around quantified operational and commercial impact
- **Cross-functional collaborator** - delivers through Product, Engineering, Legal, Fraud, Sales, Marketing and BPO partners
- **Strengths:** Performance accountability, people development, data-informed decisions, responsible use of AI/automation
- **Growth areas:** Not self-reported yet
- **Thrives in:** Regional/global roles with real ownership, measurable outcomes, and cross-functional scope

### What Excites You
- Building and scaling teams; operating-model and workflow redesign that produces measurable KPI/SLA gains
- Leading AI-enabled operational transformation and cross-functional / vendor turnaround

### Target Sectors
- B2B SaaS / technology platforms: e.g. Clio and similar vertical SaaS
- Ad-tech / digital platforms and BPO-supported service organisations

### Deal-breakers
- None hard. Prefers hybrid in Dublin; flexible on the rest and weighs trade-offs case by case.

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`
