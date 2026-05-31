# OWASP Secure Design Checklist Index

Source baseline: `OWASP_en.pdf` in the workspace, `OWASP Secure Coding Practices Quick Reference Guide`, Version `2.0`, `November 2010`.

Use this file to choose the minimum relevant checklist categories before loading detailed reference files.

## Category Files

### 1. Input Validation

- File: [01-input-validation.md](01-input-validation.md)
- Load when discussing request parameters, headers, cookies, redirects, imported data, database-sourced content, file metadata, webhooks, third-party callbacks, or business-rule validation.

### 2. Output Encoding

- File: [02-output-encoding.md](02-output-encoding.md)
- Load when discussing HTML rendering, templating, rich text, generated documents, response headers, SQL/XML/LDAP sinks, shell or command sinks, or any context-sensitive output handling.

### 3. Authentication and Password Management

- File: [03-authentication-and-password-management.md](03-authentication-and-password-management.md)
- Load when discussing login, password policy, password reset, admin identity, account lifecycle, MFA, external-service credentials, or authentication failure behavior.

### 4. Session Management

- File: [04-session-management.md](04-session-management.md)
- Load when discussing cookies, bearer tokens, session fixation, rotation, logout, inactivity timeout, concurrent sessions, or CSRF defenses.

### 5. Access Control

- File: [05-access-control.md](05-access-control.md)
- Load when discussing roles, permissions, tenant isolation, object access, protected URLs, protected functions, service-to-service privileges, state tampering, or business-flow enforcement.

### 6. Cryptographic Practices

- File: [06-cryptographic-practices.md](06-cryptographic-practices.md)
- Load when discussing secrets, key management, random token generation, crypto provider choices, or failure handling in cryptographic modules.

### 7. Error Handling and Logging

- File: [07-error-handling-and-logging.md](07-error-handling-and-logging.md)
- Load when discussing user-facing errors, stack traces, security event logging, tamper detection, auditability, log access, or log integrity.

### 8. Data Protection

- File: [08-data-protection.md](08-data-protection.md)
- Load when discussing PII, secrets at rest, caches, temporary files, client-side storage, source-code exposure, retention, or secure data removal.

### 9. Communication Security

- File: [09-communication-security.md](09-communication-security.md)
- Load when discussing TLS, external integrations, certificate handling, transport downgrade, connection encodings, or referer leakage.

### 10. System Configuration

- File: [10-system-configuration.md](10-system-configuration.md)
- Load when discussing hardening, patching, HTTP methods, environment isolation, asset inventory, change control, response headers, or robots.txt exposure.

### 11. Database Security

- File: [11-database-security.md](11-database-security.md)
- Load when discussing query construction, DB credentials, role separation, stored procedures, connection strings, or database feature reduction.

### 12. File Management

- File: [12-file-management.md](12-file-management.md)
- Load when discussing uploads, downloads, dynamic includes, redirects, path references, content storage locations, directory execution, or malware scanning.

### 13. Memory Management

- File: [13-memory-management.md](13-memory-management.md)
- Load when discussing native code, buffers, string copy routines, looped writes, explicit cleanup, or non-executable stacks.

### 14. General Coding Practices

- File: [14-general-coding-practices.md](14-general-coding-practices.md)
- Load when discussing OS command execution, checksums, locking, race conditions, variable initialization, privileged code, numeric edge cases, dynamic execution, dependency trust, or auto-update safety.

## Suggested Minimal Starting Sets

- API or form workflow: `01`, `05`, `07`
- Login or account workflow: `03`, `04`, `05`, `07`
- Upload or download design: `01`, `05`, `07`, `08`, `12`
- External system integration: `03`, `05`, `06`, `07`, `09`, `10`
- Data storage or retention plan: `05`, `08`, `09`, `10`, `11`
- Admin console or privileged workflow: `03`, `04`, `05`, `07`, `08`, `10`

Add categories only when the design clearly crosses into those concerns.
