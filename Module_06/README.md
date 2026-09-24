# MODULE 06 — ASSIGNMENT
## Version Control with Git & AI Workflows

**Name:** MD Jobael Haque (Arif)
**ID:** 01675979838
**Batch:** 21
**Course:** AI Driven SQA — Manual & Automation Testing | OSTAD

---

## Objective

Bring all previous module assignments (Module 01–05) under Git version
control and publish them to a single GitHub repository, so each module's
work is tracked with a clear commit history and can be shared as one
repository link.

## Repository Structure

```
AI-SQA-Assignments/
├── README.md              # Index of all modules
├── Module_01/README.md    # Introduction to AI-Driven SQA
├── Module_02/README.md    # SDLC in the Age of AI
├── Module_03/README.md    # STLC with AI
├── Module_04/README.md    # JavaScript + Node.js practice
├── Module_05/README.md    # Claude Code + JavaScript problem solving
└── Module_06/README.md    # This file — Git & AI workflow
```

One repository was used for all modules (rather than five separate repos)
so the full history of the coursework is visible in a single place, with
each module organized into its own folder.

## Git Workflow Used

1. **Initialize the repository**
   ```bash
   git init
   git branch -M main
   ```
2. **Add files module by module and commit incrementally**, so the commit
   history documents progress module-by-module instead of one large dump:
   ```bash
   git add Module_01
   git commit -m "Add Module 01: Introduction to AI-Driven SQA"

   git add Module_02
   git commit -m "Add Module 02: SDLC in the Age of AI"

   git add Module_03
   git commit -m "Add Module 03: STLC with AI"

   git add Module_04
   git commit -m "Add Module 04: JavaScript + Node.js practice"

   git add Module_05
   git commit -m "Add Module 05: Claude Code + JavaScript problem solving"

   git add Module_06 README.md
   git commit -m "Add Module 06: Git & AI workflow documentation"
   ```
3. **Connect to GitHub and push**
   ```bash
   git remote add origin https://github.com/<your-username>/AI-SQA-Assignments.git
   git push -u origin main
   ```

## Where AI fit into the workflow

- Used to draft clear, conventional commit messages that describe *what*
  changed and *why*, instead of vague messages like "update".
- Used to convert the original assignment write-ups into clean Markdown so
  they render properly on GitHub instead of as raw HTML.
- Used to write this README as a short, reviewable record of the Git
  workflow, which is itself good practice before pushing to a shared
  repository.

## Submission

| Module | Repository Link |
|---|---|
| Module 01 | `<paste your GitHub repo link here>` |
| Module 02 | `<paste your GitHub repo link here>` |
| Module 03 | `<paste your GitHub repo link here>` |
| Module 04 | `<paste your GitHub repo link here>` |
| Module 05 | `<paste your GitHub repo link here>` |
| Module 06 | `<paste your GitHub repo link here>` |

Since all modules live in one repository, the same link can be used for
every row above, e.g. `https://github.com/<your-username>/AI-SQA-Assignments`.
