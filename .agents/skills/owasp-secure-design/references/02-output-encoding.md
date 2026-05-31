# 2. Output Encoding

Original checklist items from `OWASP_en.pdf`:

- Conduct all encoding on a trusted system (e.g., The server)
- Utilize a standard, tested routine for each type of outbound encoding
- Contextually output encode all data returned to the client that originated outside the application's trust boundary. HTML entity encoding is one example, but does not work in all cases
- Encode all characters unless they are known to be safe for the intended interpreter
- Contextually sanitize all output of un-trusted data to queries for SQL, XML, and LDAP
- Sanitize all output of un-trusted data to operating system commands
