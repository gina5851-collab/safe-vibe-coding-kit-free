# No-Git-Push / No-Deploy Rule

## When To Use This

Install this once, in every project, in every tool. This is the strongest rule in the kit, because git pushes and deploys are the moments where a local mistake becomes a **public, live, sometimes irreversible** mistake.

Plain-English translation of the danger:

- `git commit` = save a permanent snapshot into project history
- `git push` = send that snapshot to GitHub, where it may auto-trigger a deploy
- Deploy = your changes go live to real visitors
- Database changes = can alter or delete real data, sometimes with no undo

Many Vercel + GitHub setups deploy **automatically on push**. That means an agent that "helpfully" pushes has effectively deployed to production without asking. This rule closes that door.

---

## The Rule (Copy Everything Below)

```
NO-GIT-PUSH / NO-DEPLOY RULE — HARD SAFETY BOUNDARY

You must NEVER run any of the following unless I explicitly approve the exact
command in this conversation:

GIT:
- git commit (in any form)
- git push (in any form, to any branch or remote)
- git merge, git rebase, git reset --hard, git checkout that discards changes
- Creating or deleting branches on the remote

DEPLOY:
- vercel deploy, vercel --prod, or any Vercel CLI deploy command
- Any command that publishes, releases, or deploys to any environment
- Any change to deployment settings, environment variables in hosting
  dashboards, or CI/CD configuration

PRODUCTION & DATA:
- Any command or code change that alters a production environment
- Any database command: migrations, schema changes, seeding, or deletion
  (no prisma migrate, no supabase db push, no SQL against live data)

REQUIRED BEHAVIOR INSTEAD:
When a task reaches a point where one of these commands would normally run:
1. STOP.
2. Write out the exact command(s), each on its own line, clearly labeled.
3. Explain in one plain-English sentence what each command will do
   and whether it can be undone.
4. Wait. I will either run the command myself or reply approving it.

Example of correct behavior:
  "The change is complete and tested locally. The next steps would be:
     git add app/page.tsx
     git commit -m 'Update hero headline'
     git push origin main   ← note: this will auto-deploy via Vercel
   I have NOT run these. Please run them yourself or reply to approve."

Approval rules:
- Approval must name the specific command. "Sounds good" is not approval to push.
- Approval for one commit/push/deploy does not carry over to future ones.
- If you are ever unsure whether something counts as deploy/production/data,
  treat it as if it does and ask.
```

---

## Tips

- **Run the commands yourself when possible.** Copy-pasting a command the agent wrote takes 5 seconds and keeps a human at the trigger. That habit alone prevents the worst category of AI coding accidents.
- **Check your auto-deploy setup.** If GitHub → Vercel auto-deploys your main branch, then "push" and "deploy" are the same event for you. Treat every push as a production decision.
- **Pair this with file 10.** Even when you deploy on purpose, run the pre-deploy checklist first.
