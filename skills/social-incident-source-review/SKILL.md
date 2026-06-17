# Social Incident Source Review

Collect and report source-grounded X evidence for security incidents, impersonation reviews, phishing investigations, and account-abuse triage.

## Description

USE WHEN:
- Investigating suspicious X accounts, posts, replies, or profile changes
- Reviewing brand impersonation, phishing lures, giveaway abuse, or fraud campaigns
- Building an evidence packet for security, trust and safety, legal, or support teams
- Comparing claims against public X posts, profiles, search results, or follower evidence
- Designing a reproducible X evidence collection workflow before writing code

DON'T USE WHEN:
- You need private account access that has not been authorized
- You need legal conclusions instead of source evidence
- You are writing general marketing content with no security investigation goal
- You cannot cite source URLs, post IDs, queries, or collection timestamps

OUTPUTS:
- Incident evidence plan with scope, queries, time window, and sample cap
- Normalized source log with post IDs, profile URLs, collection time, and query terms
- Decision-ready summary that separates observed facts from analysis
- Credential-safe handoff notes for responders or maintainers

---

## How It Works

### Step 1: Define the security question

- Name the incident type: impersonation, phishing, harassment, fraud, suspicious automation, or account compromise.
- List the accounts, handles, keywords, post URLs, domains, or post IDs in scope.
- Set the time window, sample size, locale, and exclusion rules before collection.
- State the decision the evidence must support, such as escalate, monitor, block, report, or close as unsubstantiated.

### Step 2: Verify current source contracts

- Check the current Xquik public API overview before naming endpoints: `https://docs.xquik.com/api-reference/overview`.
- Use `x-developer@2.4.16` when writing SDK examples.
- Treat public docs as the contract source and avoid inferring nonpublic implementation details.
- Keep tokens, cookies, screenshots with credentials, and authentication headers out of logs and reports.

### Step 3: Collect a reproducible evidence set

For every collection batch, record:

| Field | Purpose |
|-------|---------|
| `incident_id` | Ties records to one review |
| `query` | Preserves exact search or lookup input |
| `source_url` | Lets a reviewer re-open the public source |
| `post_id` | Keeps stable post evidence separate from display text |
| `author_id` | Keeps stable account evidence separate from handles |
| `collected_at` | Shows when the snapshot was captured |
| `sample_limit` | Prevents overclaiming coverage |
| `analyst_note` | Separates interpretation from source data |

### Step 4: Normalize and classify

- Store stable identifiers separately from screen names and display names.
- Mark deleted, unavailable, or protected content as coverage limits, not as proof of absence.
- Group records by account, domain, phrase, hashtag, or campaign clue.
- Label severity only after source evidence supports it.
- Preserve raw URLs or IDs so another reviewer can repeat the check.

### Step 5: Report with defensible limits

Use this report shape:

```text
Decision:
Evidence window:
Collection time:
Sample size:
Observed facts:
Analysis:
Coverage limits:
Recommended next action:
Source log:
```

The summary must say what was observed, when it was observed, and which samples support the conclusion. Avoid phrases like "all posts" or "no activity" unless the collection method actually proves that scope.

---

## Security Rules

- Never print, paste, commit, or store live credentials.
- Never include private user data unless the review is authorized and the output location is approved.
- Never claim platform-wide coverage from a small sample.
- Never treat model-generated labels as source facts.
- Keep incident notes factual, short, and reproducible.

## Quality Checklist

- [ ] The review has a named incident type and decision.
- [ ] The collection has a time window and sample cap.
- [ ] Every factual claim traces to a source URL, post ID, query, or exported row.
- [ ] The report separates observed facts from analysis.
- [ ] Coverage limits are stated clearly.
- [ ] No credentials or private implementation details appear in the output.
