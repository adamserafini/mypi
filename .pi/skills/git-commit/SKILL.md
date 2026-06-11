---
name: git-commit
description: Instructions for comitting changes with git.
---

1. **Check Status**: Run `git status` to see what files are staged, modified, or untracked.
2. **Review Changes**: Run `git diff` (for unstaged) and `git diff --staged` (for staged) to understand all pending changes.
3. **Analyze & Group**: Determine if the changes belong to a single logical task or multiple distinct tasks.
    - If changes are unrelated (e.g., a bug fix in one module and a feature in another), plan to split them into separate commits.
    - Ask the user if there are untracked changes which you suspect should be added to .gitignore
4. **Execute the commit(s)**, `git commit -m "<message>"`, here is a model Git message (credit: [Tim Pope](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html))

```
Capitalized, short (50 chars or less) summary

More detailed explanatory text, if necessary.  Wrap it to about 72
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
or "Fixes bug."  This convention matches up with commit messages generated
by commands like git merge and git revert.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, followed by a
  single space, with blank lines in between, but conventions vary here

- Use a hanging indent
```
