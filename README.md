# Safe Vibe Coding Kit — Free Sample

### Control Cursor and Claude Code before they touch the wrong files.

Safe Vibe Coding Kit is a practical guardrail kit for non-coders using Cursor and Claude Code.  
It helps prevent AI coding agents from editing protected files, pushing to GitHub, deploying too early, or making broad refactors without approval.

<p>
  <a href="https://ginabloom46.gumroad.com/l/safe-vibe-coding-kit">
    <img src="https://img.shields.io/badge/Get%20the%20Full%20Kit-Gumroad-orange?style=for-the-badge" alt="Get the Full Kit on Gumroad">
  </a>
  <img src="https://img.shields.io/badge/Built%20for-Cursor%20%26%20Claude%20Code-blue?style=for-the-badge" alt="Built for Cursor and Claude Code">
  <img src="https://img.shields.io/badge/Free%20Sample-3%20Files-green?style=for-the-badge" alt="Free Sample">
</p>

---

## Why this exists

AI coding agents are powerful.

But when you are a non-coder, one vague prompt can lead to problems like:

- editing protected files
- changing `package.json`
- touching `.env` files
- making broad refactors
- pushing to GitHub too early
- deploying before you approved the work
- saying the task is complete without showing what changed

This free sample gives you three simple guardrails you can add to your AI coding workflow.

The principle is simple:

> The AI proposes.  
> The human approves.  
> Dangerous commands do not run automatically.

---

## Free sample files

| File | What it helps prevent |
|---|---|
| [`03-no-touch-files-rule.md`](./03-no-touch-files-rule.md) | Prevents the AI from editing protected files without approval |
| [`06-no-git-push-no-deploy-rule.md`](./06-no-git-push-no-deploy-rule.md) | Prevents accidental GitHub push or deployment steps |
| [`08-completion-report-template.md`](./08-completion-report-template.md) | Forces the AI to report what changed before calling a task complete |

---

## Who this is for

This kit is for:

- non-coders building with Cursor
- solo founders using Claude Code
- creators making landing pages, MVPs, and digital products
- people using AI coding agents with GitHub or Vercel
- anyone who wants safer AI-assisted coding workflows

It is especially useful if you often say things like:

> “Don’t touch the wrong files.”  
> “Don’t push to GitHub yet.”  
> “Don’t deploy until I approve.”  
> “Tell me exactly what you changed.”

---

## How to use the free sample

Copy the rules into your project instructions, `CLAUDE.md`, Cursor rules, or AI coding prompt before starting a task.

Example:

```txt
Before editing any files, read and follow the no-touch files rule.
Do not push to GitHub or deploy unless I explicitly approve it.
When finished, use the completion report template.
