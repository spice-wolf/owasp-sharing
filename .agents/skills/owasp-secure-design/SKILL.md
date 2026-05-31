---
name: owasp-secure-design
description: Facilitate secure-by-design discussions, architecture tradeoff analysis, and pre-implementation security decision reviews using the OWASP Secure Coding Practices Quick Reference Guide checklist. Use when Codex needs to assess a feature proposal, API contract, data flow, authentication approach, session model, access model, file handling plan, storage design, deployment design, integration pattern, or remediation option before code is written. Preserve the original OWASP checklist category structure and load only the relevant category reference files to minimize token usage.
---

# OWASP Secure Design

Use this skill during solution design and security discussions before implementation starts.

Keep the original OWASP checklist structure intact. Do not load every category by default. Start with the smallest set of relevant categories, then read only those reference files.

If the request is code-centric rather than design-centric, prefer `owasp-secure-coding-review`.

## Workflow

### 1. Frame the design question

Identify:

- The business goal or feature being designed
- Entry points and untrusted inputs
- Trust boundaries and cross-system calls
- Sensitive data, secrets, and privileged actions
- User roles, service accounts, and administrative paths
- Storage, transport, logging, and file handling behavior

If key context is missing, call it out explicitly instead of guessing.

### 2. Select OWASP categories before loading details

Use [references/checklist-index.md](references/checklist-index.md) to map the design topic to the minimum relevant checklist categories.

Rules:

- Read only the category files that clearly apply
- Do not load all 14 categories unless the user asks for a broad review
- If a design spans multiple trust boundaries, add categories incrementally
- Keep the original category names when reporting findings

### 3. Load only the relevant checklist files

After selecting categories, read the corresponding files in `references/`.

Each category file preserves the checklist items from `OWASP_en.pdf` for that category. Do not merge, collapse, or rewrite the checklist when gathering evidence.

### 4. Review the design against the selected checks

For each applicable checklist item:

- Decide whether the design is `aligned`, `partially aligned`, `missing`, or `unclear`
- Explain the concrete design implication
- Surface tradeoffs, abuse cases, and hidden failure modes
- Recommend the smallest design change that materially reduces risk

Treat these as design questions, not only implementation questions. Translate each checklist item into architecture decisions, interface rules, data handling rules, or operational guardrails.

### 5. Produce a design discussion output

Default structure:

```md
Design scope:
- <feature / workflow / architecture option>

OWASP categories reviewed:
- <category>: <aligned|partially aligned|missing|unclear>

Security decisions:
1. <decision or gap>
   Relevant OWASP item(s): <category + item summary>
   Risk if unchanged: <abuse case or failure mode>
   Recommended direction: <preferred design choice>

Open questions:
- <missing information that blocks a confident decision>

Next actions:
- <design updates, validation tasks, follow-up reviews>
```

Respond in the user's language unless they ask otherwise.

## Category Selection Heuristics

Use these quick mappings before reading the detailed checklist files:

- API, forms, search, filters, callbacks, redirects: `01-input-validation`, `05-access-control`, `07-error-handling-and-logging`
- HTML rendering, templates, rich text, report/export rendering, query or command sinks: `02-output-encoding`
- Login, password reset, account lifecycle, MFA, admin identity: `03-authentication-and-password-management`
- Cookies, tokens, session rotation, logout, CSRF, inactivity timeout: `04-session-management`
- Roles, object access, multi-tenant boundaries, admin functions, service entitlements: `05-access-control`
- Secrets, key ownership, randomness, crypto module choice: `06-cryptographic-practices`
- User-visible errors, audit trails, security telemetry, tamper evidence: `07-error-handling-and-logging`
- PII, credentials, retention, caches, temporary files, source exposure: `08-data-protection`
- TLS, external connections, referer leakage, transport downgrade risk: `09-communication-security`
- Hardening, patching, methods, headers, robots, environment isolation: `10-system-configuration`
- Query design, DB credentials, stored procedures, connection handling: `11-database-security`
- Upload, download, include, redirect, path handling, malware scanning: `12-file-management`
- Native code, buffers, unsafe string handling, resource cleanup: `13-memory-management`
- OS command execution, race conditions, dependency trust, auto-update, privileged code: `14-general-coding-practices`

## Modern Scope Limits

This skill is based on the local source PDF `OWASP_en.pdf`:

- Document: `OWASP Secure Coding Practices Quick Reference Guide`
- Version: `2.0`
- Date: `November 2010`

Use [references/source-and-limits.md](references/source-and-limits.md) when the design involves modern areas that the source only partially covers, such as cloud IAM, federated identity, browser isolation, supply chain integrity, privacy regulation, or AI-specific threats.
