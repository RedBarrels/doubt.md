# Gate 5: Is It Secure?

**Core question:** Will this get hacked in minutes by a bored teenager?

## Checklist — The Absolute Minimum

- [ ] No secrets in source code (API keys, passwords, tokens)
- [ ] `.env` file exists AND is in `.gitignore`
- [ ] No secrets in git history (if they were ever committed, they're compromised — rotate them)
- [ ] HTTPS everywhere (no HTTP, no "it's just local")
- [ ] Dependencies are from trusted sources and not wildly outdated
- [ ] Input is validated/sanitized on the SERVER, not just the client

## OWASP Top 10 Quick Scan

| Vulnerability | Status | Notes |
|--------------|--------|-------|
| Injection (SQL, NoSQL, OS command) | | |
| Broken Authentication | | |
| Sensitive Data Exposure | | |
| XML External Entities (XXE) | | |
| Broken Access Control | | |
| Security Misconfiguration | | |
| Cross-Site Scripting (XSS) | | |
| Insecure Deserialization | | |
| Using Components with Known Vulnerabilities | | |
| Insufficient Logging & Monitoring | | |

## Critical Questions

1. **What's the blast radius if you get hacked?** User data leaked? Financial loss? Just your embarrassment?
2. **Are you storing user passwords?** If yes, are you using bcrypt/argon2? If you're rolling your own crypto, stop.
3. **Are you handling user data?** GDPR/privacy implications? Do you even need to store it?
4. **Can someone enumerate your users/data through your API?** Try incrementing IDs.
5. **What happens if someone sends 10,000 requests per second?** Rate limiting?
6. **Are your Docker images based on `latest`?** Pin your base images.
7. **Is your `.git` folder exposed on your web server?** Check.
8. **Are you running as root?** Don't.

## The "It's Just a Side Project" Trap

"Nobody will hack my side project" is what everyone says until:
- Their AWS bill hits $50,000 from crypto mining
- Their API keys get scraped from a public repo
- Their users' data ends up on a pastebin

If it's on the internet, it will be scanned. If it has default credentials, it will be compromised. The question isn't IF but WHEN.

## Scoring

| Score | Criteria |
|-------|----------|
| PASS | Secrets managed properly, OWASP basics covered, input validated |
| CONDITIONAL | Some gaps but no user data at risk — fix before going public |
| FAIL | Secrets in code, no input validation, running as root, or "I'll secure it later" |

## Notes

_Write your findings here_
