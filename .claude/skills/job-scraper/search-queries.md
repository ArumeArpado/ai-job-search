# Search Queries for Job Scraper

<!-- NOTE: The bundled job-scraper CLI tools target Danish job portals (Jobindex,
     Jobbank, Jobdanmark, Jobnet). Gustavo is based in Dublin, Ireland, so those
     Danish CLI tools do not apply. Use LinkedIn + Google site-searches and the
     Irish/UK job boards below instead. Custom Irish-portal integrations can be
     added later if desired. -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

## Search Sites

Primary (Ireland / remote-friendly):

- **linkedin.com/jobs** - filter: Dublin, Ireland / Remote (EMEA)
- **irishjobs.ie** - major Irish job board
- **jobs.ie** - general Irish job board
- **indeed.ie** - aggregator, Ireland
- Company career pages via Google `site:` searches for target SaaS/tech firms

## Query Categories

Combine each query with location terms: "Dublin", "Ireland", or "Remote".

### Priority 1: Customer Success Leadership

Strongest and most desired direction.

```text
site:linkedin.com/jobs "Director of Customer Success" Dublin OR Ireland OR Remote
site:linkedin.com/jobs "VP Customer Success" Ireland
site:linkedin.com/jobs "Head of Customer Success" Dublin
site:irishjobs.ie "Customer Success" director OR head Dublin
```

### Priority 2: Service Delivery / Support Operations

Domain expertise: running multilingual support and service delivery orgs.

```text
site:linkedin.com/jobs "Head of Support" OR "Director Service Delivery" Dublin OR Ireland
site:linkedin.com/jobs "Support Operations" leader OR director Ireland
site:linkedin.com/jobs "Head of Client Services" Dublin
site:irishjobs.ie "service delivery" manager OR director Dublin
```

### Priority 3: Operations / COO-track Leadership

Adjacent roles the profile pivots into.

```text
site:linkedin.com/jobs "Director of Operations" Dublin OR Ireland
site:linkedin.com/jobs "Head of Operations" SaaS Ireland
site:linkedin.com/jobs "Operations transformation" lead Dublin OR Remote
```

### Priority 4: Vendor / BPO & Broader Leadership

Wider net.

```text
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

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:

- `/scrape customer success` -> Priority 1 queries + custom focus-specific queries