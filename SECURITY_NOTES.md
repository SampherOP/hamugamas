# HAMUGANG Security Notes

This build adds:
- Vercel security response headers (HSTS, MIME sniffing protection, referrer policy, frame protection, permissions policy, and a basic CSP restriction).
- Browser-side copy/context-menu/save/drag deterrents.
- Firebase rules remain unchanged so existing features are not intentionally removed.

IMPORTANT:
Anything delivered to a browser can technically be inspected and copied. HTML/CSS/JS cannot be made 100% secret on a public website. The strongest protection is to keep secrets and sensitive logic on a server/API and enforce authorization/rate limits in Firebase/backend rules.

Firebase:
- Keep `database.rules.json` published in Firebase Realtime Database > Rules.
- Never put private service-account keys, admin SDK credentials, or other secrets in `index.html`.
- Firebase web API keys are identifiers, not passwords; the database rules/authentication are what protect the data.

Vercel:
- Deploy this folder as the project root so `vercel.json` is applied.
- HTTPS is automatic on Vercel, so HSTS can take effect after deployment.
