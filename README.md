# API Security & Auth Protocol Reference (AI Era)

Two interactive, single-file HTML reference guides covering API security and authentication/authorization protocols, with a focus on how these controls apply to AI systems, LLM endpoints, and agentic pipelines.

**Live demos:** [API Security in the AI Era](https://tgandhle.github.io/api-auth-security-reference/api-security-ai-era.html) · [Auth Protocols Guide](https://tgandhle.github.io/api-auth-security-reference/auth-protocols-guide.html) 

## What's here

| File | What it covers |
|------|----------------|
| `auth-protocols-guide.html` | AuthN vs AuthZ across 8 protocols: OAuth 2.0 + PKCE, OpenID Connect, SAML 2.0, Client Credentials, mTLS, DPoP, FAPI 2.0, and the deprecated Implicit flow. Each with flow diagrams, a fact breakdown, and a verdict. Includes a protocol comparison matrix. |
| `api-security-ai-era.html` | 9 control domains and 34 controls: auth mechanisms, JWT attack surface, gateway enforcement, rate limiting, webhooks, CORS, AI-specific threats, and versioning. Includes an interactive 20-point security review checklist. |

Both files are static single-page HTML references. No build step, framework, or runtime application dependency is required. The pages load Google Fonts from Google's CDN, with system-font fallbacks if that fails; remove the `<link>` in each file's `<head>` if you need strict offline behavior.

## Why I built it

Most auth and API security references are either dense RFC prose or vendor marketing. I wanted a reference that is opinionated, gives a clear verdict on when to use each protocol, and treats AI-specific concerns (prompt injection via API, inference cost attacks, token exfiltration through LLM responses, sensitive data in model context) as first-class rather than an afterthought.

The content maps to recognized standards: relevant RFCs (6749, 7636, 8705, 9449, 9700), the OWASP API Security Top 10, and FAPI 2.0. Where the guidance is my recommendation rather than a standard, it says so.

## What this demonstrates

- Working knowledge of modern auth protocols and their correct use cases, including the AuthN/AuthZ distinction that's commonly conflated
- Understanding of real API attack surface: JWT algorithm confusion, CORS origin reflection, webhook replay, token theft
- Applied AI security thinking, not just generic API hardening with an AI label
- Ability to turn dense technical material into a clear, well-designed, usable reference

## Running it

No setup required.

```
# Clone, then open either file directly
open auth-protocols-guide.html
# or serve locally
python3 -m http.server 8000
```

To host the live demo, enable GitHub Pages in repo settings (Settings → Pages → deploy from the main branch root), then link the URL at the top of this README.

## Notes

This is reference material for design reviews and learning. It reflects best practices as I understand them at time of writing; verify protocol details against current RFCs and vendor documentation before relying on them in production. The gateway product comparison in particular is a point-in-time snapshot, as noted in the file.

## License

MIT. Use it, fork it, learn from it.
