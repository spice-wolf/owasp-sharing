# Source and Limits

## Source

- Primary source: `OWASP_en.pdf`
- Document title: `OWASP Secure Coding Practices Quick Reference Guide`
- Version: `2.0`
- Date: `November 2010`

## How to use this source in design work

- Treat it as a baseline checklist for secure-by-design discussions.
- Preserve the original category structure and checklist items.
- Translate checklist items into design constraints, decision criteria, and review questions.
- Use only the categories that apply to the design under discussion.

## Important limits

- The source is technology-agnostic and intentionally high level.
- The source predates many modern platform defaults and product patterns.
- It is not a full threat model, architecture review method, compliance framework, or penetration test.
- A design can align with this baseline and still need deeper product-specific review.

## Escalate beyond this skill when the design involves

- Federated identity, OAuth, OIDC, SAML, passkeys, or advanced MFA recovery
- Cloud IAM, containers, service mesh, Kubernetes, or infrastructure as code
- Browser isolation, CSP, modern frontend sandboxing, or dependency provenance
- Privacy regulation, retention law, data residency, or regulated data handling
- Advanced cryptographic design, protocol design, or hardware-backed secrets
- Mobile, embedded, native high-assurance, or safety-critical systems
- AI systems, agent tooling, prompt injection, model isolation, or tool authorization

In these cases, keep using this skill for baseline hygiene, but state explicitly that additional standards or specialist review are required.
