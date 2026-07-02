# Completion Report Template

## When To Use This

At the end of **every task**. If the agent finishes and just says "Done! ✅", you have no idea what actually happened to your codebase.

The completion report is your receipt. It tells you what changed, what didn't, what's risky, and what to do next — in a format you can skim in 30 seconds and keep as a record.

You can either paste this request after each task, or add the line "After every task, produce a completion report in my standard format" to your `CLAUDE.md` / Cursor rules and paste the format once.

---

## The Prompt (Copy Everything Below)

```
The task is finished. Before we do anything else, produce a COMPLETION REPORT
in exactly this format:

## Completion Report — [SHORT TASK NAME]

### 1. Changed Files
List every file you created, edited, or deleted, with full paths.
For each: one line describing what changed in it.

### 2. Protected Files — Confirmed Untouched
Confirm explicitly that these were NOT modified:
- .env / .env.local
- package.json and all lockfiles
- vercel.json / deploy config
- [YOUR OTHER PROTECTED FILES, e.g., migrations, auth, payments]
If any protected file WAS touched, flag it in bold at the top of the report.

### 3. Summary In Plain English
2–4 sentences a non-developer can understand:
what was the goal, what did you do, what's the result.

### 4. Risk Notes
Anything that could break, behave differently, or surprise me.
If nothing, write "No known risks" — but think before writing it.

### 5. Tests / Checks Run
What you verified and how (e.g., "ran npm run build — passed",
"checked the page renders locally"). If you verified nothing, say so honestly.

### 6. Commands Run
Every terminal command you executed during this task, in order.
Confirm explicitly: no git commit, no git push, no deploy was run.

### 7. Remaining Issues
Anything left unfinished, any unrelated problems you noticed but
(correctly) did not fix.

### 8. Next Recommended Action
The single next step you recommend, and whether it's something
I should do manually (e.g., "check the form on your phone") or
approve you to do.
```

---

## How To Read The Report (30-Second Skim)

1. **Section 2 first.** Protected files untouched? Good. Flagged? Stop and investigate before anything else.
2. **Section 1 length check.** You asked for a small change and see 12 changed files? That's a broad refactor — use the recovery prompt (file 09).
3. **Section 6.** Confirm no git/deploy commands ran. If they did without approval, check what went live.
4. **Section 8.** Do the manual check it recommends before starting the next task.

---

## Tips

- **Save your reports.** Paste them into a notes doc per project. When something breaks next week, the reports tell you exactly what changed and when — it's a changelog written for you.
- **An honest "I verified nothing" is useful.** It tells you the testing burden is on you before you trust the change.
