# The No-Touch Files Rule

## When To Use This

This is a reusable block you can paste into any AI coding session, any `CLAUDE.md`, or any Cursor rule file. Use it when:

- You start work in a new tool that doesn't have your rules installed yet
- You're pairing with a client's or student's project
- You want to re-state protection mid-session (agents drift in long sessions — re-pasting this helps)

## Why These Files Matter (Plain English)

| File | Why it's dangerous to touch |
|---|---|
| `.env`, `.env.local` | Contains your secret keys and passwords. Edits can leak secrets or break every connection your app has. |
| `package.json` | The list of software your project depends on. Wrong edits can break the entire build. |
| `package-lock.json`, `pnpm-lock.yaml`, `yarn.lock` | Exact version records. Should only change through proper install commands, never hand-edits. |
| `node_modules` | Installed software itself. Never edited by hand. Huge — reading it also wastes your usage limits. |
| `.next` (and other build folders) | Auto-generated build output. Editing it does nothing useful and wastes time. |
| `vercel.json` | Deployment behavior. Wrong edits can break your live site. |
| Database migration files | The history of your database structure. Editing old migrations can corrupt or lose data. |
| Auth files | Login and security. Small mistakes here can lock out users or open security holes. |
| Payment / webhook files | Real money flows through these. A silent edit here can mean failed charges or double charges. |

---

## The Rule (Copy Everything Below)

```
NO-TOUCH FILES RULE

The following files and folders are strictly off-limits. Do not edit, delete,
rename, move, or rewrite them under any circumstances in this session unless
I give explicit approval for that specific file:

Secrets & environment:
- .env
- .env.local
- .env.production
- [ANY OTHER SECRETS FILES, e.g., /config/keys.ts]

Dependencies & build:
- package.json
- package-lock.json
- pnpm-lock.yaml
- yarn.lock
- node_modules/ (do not read or edit)
- .next/ (do not read or edit)
- [OTHER BUILD FOLDERS, e.g., /dist, /build]

Deployment:
- vercel.json
- [OTHER DEPLOY CONFIG, e.g., netlify.toml, Dockerfile]

Data & security:
- [DATABASE MIGRATION FOLDER, e.g., /prisma/migrations]
- [AUTH FILES, e.g., /lib/auth.ts, /app/api/auth/]
- [PAYMENT/WEBHOOK FILES, e.g., /app/api/webhooks/, /app/api/stripe/]

My additions:
- [ADD ANY FILE OR FOLDER YOU PERSONALLY WANT PROTECTED]

If a task appears to require changing any file above:
1. STOP before editing.
2. Tell me which protected file is involved and why.
3. Wait for my explicit approval naming that file.

Approval for one protected file does not mean approval for others.
```

---

## Tips

- **Don't know your own file paths?** Ask your AI agent: "List the folders in this project and tell me which ones contain auth, payments, or database code. Do not edit anything." Then fill in the placeholders.
- **Re-paste in long sessions.** After 30+ messages, agents can lose track of early rules. Pasting this block again is cheap insurance.
- **This pairs with file 06.** No-touch files protect *what* gets edited; the no-git/no-deploy rule protects *what gets shipped*.
