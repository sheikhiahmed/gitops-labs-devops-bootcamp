# FameTech DevOps Lab – Git Collaboration: Branching, Rewriting, Recovery

> In this Git simulation lab, I practiced real-world multi-developer collaboration strategies using Git's branching, history rewriting, and recovery features.  
> The goal was to simulate realistic CI/CD team workflows at FameTech, including merging, squashing, stash recovery, and reflog disaster recovery.

---

## About This Project

This project showcases my hands-on version control experience as a **DevOps Engineer** at **FameTech NYC**, where I contributed to sprint-based CI/CD tooling and repository hygiene.  
The lab mimics tasks typically performed in fast-paced DevOps environments involving Git-based source control workflows.

> This project experience is verifiable by FameTech upon request.

---

## Lab Metadata

| Field    | Detail                                 |
| -------- | -------------------------------------- |
| Lab ID   | GIT-002                                |
| Engineer | Sheikh Ahmed (DevOps Engineer)         |
| Company  | FameTech NYC                           |
| Sprint   | Sprint 2 – CI/CD Git Collaboration Lab |
| Platform | Git (CLI), GitHub                      |

---

## Objectives

- Create and merge feature branches following best practices
- Simulate and resolve merge conflicts
- Rewrite history using interactive rebase and squash
- Use cherry-pick to port specific commits
- Stash uncommitted changes and recover with reflog

---

## Tools & Concepts Used

| Tool/Concept      | Purpose                                  |
| ----------------- | ---------------------------------------- |
| `git branch`      | Create and manage branches               |
| `git merge`       | Integrate changes from other branches    |
| `git rebase`      | Clean history with squash and reordering |
| `git cherry-pick` | Apply individual commits across branches |
| `git stash`       | Temporarily store uncommitted changes    |
| `git reflog`      | Recover lost commits or deleted branches |

---

## Scenario – Ticket-Based Simulation

**Ticket**: `FAME-GIT-002`  
**Reported By**: CI/CD Tech Lead  
**Assigned To**: Sheikh Ahmed  
**Priority**: High  
**Status**: Completed

You joined the CI/CD Tooling Team at FameTech. During a sprint cycle, you're tasked with demonstrating collaboration techniques for version control:

- Branching off for a feature
- Merging into `main`
- Resolving conflicts
- Cleaning commit history
- Saving WIP with stash
- Recovering from branch deletion using `reflog`

---

## Implementation Steps

### Create a Sprint Branch and Simulate Feature Work

```bash
git checkout -b sprint-feature
echo "pipeline script" > deploy.sh
git add deploy.sh
git commit -m "Add deploy.sh pipeline script"

echo "README update" >> README.md
git add README.md
git commit -m "Update README for CI/CD instructions"
```

---

### Merge to Main Branch

```bash
git checkout main
git merge sprint-feature
```

> Use `git log --graph --oneline` to visualize your merge tree

---

### Create and Resolve a Merge Conflict (Bonus)

```bash
git checkout -b conflict-demo
echo "Conflict Line A" >> config.yml
git add config.yml && git commit -m "Branch A change"

git checkout main
echo "Conflict Line B" >> config.yml
git add config.yml && git commit -m "Main Line change"

git merge conflict-demo  # manual conflict resolution
git add config.yml
git commit -m "Resolve merge conflict in config.yml"
```

---

### Rebase and Squash Commits

```bash
git checkout sprint-feature
git rebase -i HEAD~2  # Squash README + deploy.sh into one commit
```

---

### Cherry-Pick a Specific Commit

```bash
git checkout main
git cherry-pick <commit_hash_from_sprint-feature>
```

---

### Stash and Recover with Reflog

```bash
echo "Unfinished work" >> temp.txt
git stash
git stash pop

# Simulate accidental branch delete
git branch bugfix
git checkout bugfix
git commit --allow-empty -m "Empty bugfix commit"
git checkout main
git branch -D bugfix

# Recover it
git reflog
git checkout -b bugfix-recovered <reflog_hash>
```

---

## Real-World Use Cases

| Scenario            | Why It Matters                             |
| ------------------- | ------------------------------------------ |
| Feature development | Use branches to isolate changes            |
| Release grooming    | Use squash/rebase for clean commit history |
| CI/CD hotfixes      | Cherry-pick to backport or forward-patch   |
| Recovery workflows  | Reflog and stash can rescue lost work      |

---

## Interview Q\&A

> **Q**: What’s the difference between `merge` and `rebase`?  
> **A**: Merge creates a commit that joins histories. Rebase replays commits on top for a linear history.

> **Q**: When should you use `cherry-pick`?
> **A**: To apply a specific commit to another branch without merging the whole feature branch.

> **Q**: How does `reflog` help in disaster recovery?  
> **A**: Reflog tracks HEAD movements, allowing you to recover commits/branches that were deleted.

> **Q**: Should you rebase shared branches?
> **A**: No — rebasing rewrites history and can break collaborators’ clones.

---

## Folder Structure

```
GIT-002-Collaboration-Workflow/
├── deploy.sh
├── README.md
├── config.yml
├── temp.txt
├── screenshots/
│ ├── git-log-graph.png
│ ├── stash-list.png
│ └── reflog-output.png
└── notes/
└── reflog_recovery_notes.txt
```

---

## Validation Checklist

| Task                                    | Status |
| --------------------------------------- | ------ |
| Sprint feature branch created           | ✅     |
| Feature commits squashed or rebased     | ✅     |
| Merge and conflict resolution completed | ✅     |
| Cherry-pick used for commit isolation   | ✅     |
| Stash and pop tested                    | ✅     |
| Reflog used to recover deleted branch   | ✅     |

---

## FameTech Story

As part of **Sprint 2**, I simulated real-world Git collaboration workflows to support FameTech's CI/CD platform team.
This lab helped ensure feature branches could be safely merged, rewritten, or recovered across the team — simulating both best practices and common recovery situations faced in DevOps engineering.

---
