# Search Queries for Job Scraper

<!-- NOTE: The bundled job-scraper CLI tools target Danish job portals (Jobindex,
     Jobbank, Jobdanmark, Jobnet). Gustavo is based in Dublin, Ireland, so those
     Danish CLI tools do not apply. Use LinkedIn + Google site-searches and the
     Irish/UK job boards below instead. Custom Irish-portal integrations can be
     added later if desired. -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** write every query category in every language listed in your CLAUDE.md Languages table (typically 1-2, sometimes more). A posting requiring a language you have *not* declared, as a job condition, is excluded before scoring; a posting requiring a *higher level* than you declared in a language you *do* work in is flagged for your own judgment, not excluded — see `04-job-evaluation.md`'s Language Gate, the single source of truth for this rule. Translate each category's keywords rather than machine-translating word-for-word (e.g. "Frontend Developer" -> "Desarrollador Frontend", not a literal word-for-word translation) if you work in more than one language.

## Search Sites


Primary (Ireland / remote-friendly):
- **linkedin.com/jobs** - filter: Dublin, Ireland / Remote (EMEA)
- **irishjobs.ie** - major Irish job board
- **jobs.ie** - general Irish job board
- **indeed.ie** - aggregator, Ireland
- Company career pages via Google `site:` searches for target SaaS/tech firms

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies

## Query Categories

Combine each query with location terms: "Dublin", "Ireland", or "Remote".

Queries are grouped by priority. Write **each category in every language from your Languages table** (see Language scope above). Combine each query with your location terms (e.g. your city, region, or metro area) where the site supports it.

**Organize by function, not job title.** The same underlying work carries different titles across companies and markets (a "Data Scientist" role at one employer may be posted as "Insights Analyst" or "Data Consultant" at another). Name each priority category after the function it covers, and list several plausible job titles as query variants within that category rather than betting an entire priority tier on one exact title string.



### Priority 1: Customer Success Leadership

Strongest and most desired direction.

```
site:linkedin.com/jobs "Director of Customer Success" Dublin OR Ireland OR Remote
site:linkedin.com/jobs "VP Customer Success" Ireland
site:linkedin.com/jobs "Head of Customer Success" Dublin
site:irishjobs.ie "Customer Success" director OR head Dublin
```

### Priority 2: Service Delivery / Support Operations

Domain expertise: running multilingual support and service delivery orgs.

```
site:linkedin.com/jobs "Head of Support" OR "Director Service Delivery" Dublin OR Ireland
site:linkedin.com/jobs "Support Operations" leader OR director Ireland
site:linkedin.com/jobs "Head of Client Services" Dublin
site:irishjobs.ie "service delivery" manager OR director Dublin
```

### Priority 3: Operations / COO-track Leadership

Adjacent roles the profile pivots into.

```
site:linkedin.com/jobs "Director of Operations" Dublin OR Ireland
site:linkedin.com/jobs "Head of Operations" SaaS Ireland
site:linkedin.com/jobs "Operations transformation" lead Dublin OR Remote
```

### Priority 4: Vendor / BPO & Broader Leadership

Wider net.

```
site:linkedin.com/jobs "Vendor Management" OR "BPO" lead Dublin OR Ireland
site:linkedin.com/jobs "Customer Operations" director Ireland OR Remote
site:linkedin.com/jobs "Escalation" OR "Customer Experience" leader Dublin
```

## Location Filter

Verify each result is Dublin-commutable or genuinely remote. Acceptable areas:
- Dublin city and Greater Dublin area (ideal - hybrid preferred)
- Ireland-wide with Dublin hub or hybrid (acceptable)
- Fully remote EMEA / international with occasional travel (acceptable)
- Roles requiring relocation outside Ireland (borderline - flag for discussion)
- On-site only outside Greater Dublin with no remote/hybrid (too far)

## Language Filter

Your working languages and levels are in CLAUDE.md's Languages table. When filtering scraped results, apply `04-job-evaluation.md`'s Language Gate: a posting requiring a language you haven't declared at all is excluded; a posting requiring a higher level than you declared in a language you do work in is not excluded, flag it clearly instead (see `job-scraper/SKILL.md`'s Step 3 "Quick Fit Assessment" for how the flag surfaces in `/scrape` output). Postings simply *written* in a language you don't work in, that don't require it on the job, are fine.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape customer success" -> Priority 1 queries + custom focus-specific queries
