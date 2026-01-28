# Git: the practical 80/20 guide (for students)

## Mental model (what Git *is*)
Git is a **save button with history + collaboration**.

- **Working directory**: your files right now  
- **Staging area**: what you intend to include in the next snapshot  
- **Repository**: your snapshot history (commits)  
- **Remote**: shared copy (e.g., GitHub)

---

## Daily drivers (you’ll use these constantly)
```bash
git status            # what's changed? where am I?
git add .             # stage changes (be mindful: stages EVERYTHING)
git commit -m "msg"   # snapshot your staged changes
git push              # send commits to remote
git pull              # bring remote changes to your machine
```
These five commands cover most day-to-day Git usage.

---

## Branch basics (feature work without breaking main)
```bash
git branch            # list branches
git checkout -b name  # create + switch branch (older syntax)
git merge branch      # merge branch into current branch
git rebase branch     # rewrite history (powerful; use carefully)
```
**Rule:** don’t work directly on `main`. Create a branch for each feature/fix.

> Optional modern commands (newer Git): `git switch -c name` instead of `checkout -b`.

---

## Inspect & debug (know what happened)
```bash
git log --oneline     # compact commit history
git diff              # what changed (unstaged / staged depending on flags)
git blame file        # who last edited each line (use respectfully)
git cherry-pick <c>   # apply one specific commit onto your branch
```

---

## “Oh no” tools (when things go wrong)
```bash
git stash             # temporarily hide uncommitted changes
git stash pop         # bring them back

git revert <commit>   # undo safely via a new commit (good for shared repos)
git reset --hard      # discard local work (destructive—be careful)
```
**Safety rule:** if you already pushed and others may have pulled, prefer **`git revert`** over **reset/force-push**.

---

## A simple workflow that works (team or class projects)
```bash
git pull origin main
git checkout -b feature/short-description

# edit files...

git add .
git commit -m "Clear, specific message"
git push origin feature/short-description
```
Then open a pull request, get review, merge, delete branch.

Solo projects (minimal loop):
```bash
git add .
git commit -m "what changed"
git push
```

---

## Common mistakes (avoid these)
1) **Not committing enough** → commit small, commit often  
   - Good: “Fix null pointer in login handler”  
   - Bad: “updates”, “fixed stuff”

2) **Being scared of branches** → branches are cheap; use them

3) **No `.gitignore`** → never commit secrets or build artifacts (`.env`, `node_modules/`, etc.)

4) **Merge conflict panic** → it’s just “two edits touched the same lines”  
   Fix file → remove markers → then:
```bash
git add <file>
git commit
```

---

## Quick rescue recipes
### Committed on the wrong branch (haven’t pushed)
```bash
git reset HEAD~1          # undo commit, keep changes
git checkout correct-branch
git add .
git commit -m "message"
```

### Undo last commit
```bash
git reset --soft HEAD~1   # keep changes staged
git reset --hard HEAD~1   # delete changes (dangerous)
```

### Pushed something you shouldn’t have
```bash
git revert HEAD
git push
```

---

## 2-week learning schedule

### Week 1 — Fundamentals (the “most used”)
- Day 1: install/config + mental model (working dir / staging / commit / remote)
- Day 2–3: loop practice 10 times: `status → add → commit → push → pull`
- Day 4: write good commit messages; commit small changes
- Day 5: `.gitignore` basics + what should never be committed
- Day 6–7: apply workflow on a real class repo (daily commits)

### Week 2 — Advanced (collaboration + recovery)
- Branching: create/switch/merge; stop working on `main`
- Conflicts: resolve calmly (edit markers → add → commit)
- Time travel: `log`, `diff`, `revert` vs `reset` (know which is safe)
- Productivity: `stash`, `cherry-pick`, and (optional) `rebase` on a test branch
- Recovery mindset: when stuck, always start with `git status` + `git log --oneline`

[Back to Main README](../README.md)
