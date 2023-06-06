# FameTech DevOps Lab – Git Fundamentals & Workflow Mastery

> In this foundational DevOps lab, I learned essential Git workflows for file tracking, staging, committing, and debugging.  
> The lab simulates version-controlling infrastructure automation scripts in a DevOps environment using Git’s internals and best practices.

---

## About This Project

This project documents my hands-on Git learning journey as a **Junior DevOps Engineer** at **FameTech NYC**, where I contributed to internal tooling by setting up proper version control workflows for shell and automation scripts.

> This project experience is verifiable by FameTech upon request.

---

## Lab Metadata

| Field      | Detail                                     |
| ---------- | ------------------------------------------ |
| Lab ID     | GIT-001                                    |
| Engineer   | Sheikh Ahmed (DevOps Engineer)             |
| Company    | FameTech NYC                               |
| Sprint     | Sprint 1 – Git Internal Tooling Foundation |
| Platform   | Git CLI, GitHub                            |
| Difficulty | Beginner → Intermediate                    |
| Time       | ~60–90 minutes                             |

---

## Objective

- Understand Git’s core areas: working directory, staging, and repository
- Practice real-world Git workflows used in DevOps teams
- Explore Git internals: object storage, blobs, commits
- Apply `.gitignore`, branching hygiene, and history tracking

---

## Tools & Concepts Used

| Tool / Concept            | Purpose                                     |
| ------------------------- | ------------------------------------------- |
| `git init`, `add`         | Start version control and track changes     |
| `.gitignore`              | Exclude unnecessary files from Git          |
| `restore`, `reset`        | Manage staging and working directory states |
| `cat-file`, `hash-object` | Inspect Git internals                       |
| `log`, `graph`            | Visualize commit history                    |
| `commit --amend`          | Update last commit message                  |

---

## Scenario – Ticket-Based Simulation

**Ticket**: `FAME-GIT-001`  
**Reported By**: Internal Tooling Lead  
**Assigned To**: Sheikh Ahmed  
**Priority**: Medium  
**Status**: Completed

You joined the Internal Automation Team at FameTech. Your first task is to version-control Bash and Ansible scripts for future deployment pipelines. The lead expects you to initialize Git, apply proper commit hygiene, and explore how Git tracks and stores data internally.

---

## Implementation Steps

### Initialize Git Repo & Identity

```bash
git init
git config --global user.name "Sheikh Ahmed"
git config --global user.email "sheikh@fametech.nyc"
```

Creates a `.git` folder and sets up global user identity.

---

### Create, Ignore, and Track Files

```bash
echo "node_modules/" > .gitignore
echo "Hello Git Workflow" > README.md
mkdir scripts && touch scripts/setup.sh
```

```bash
git status
git add .
git commit -m "Initial commit: Added .gitignore, README, and setup script"
```

---

### Explore Git Internals

```bash
echo "Hello Git Internals" > internals.txt
git hash-object internals.txt
git cat-file -p <hash>
ls .git/objects/
```

Explore Git’s object model and how content is stored as blobs in the `.git/objects/` directory.

---

### Manage Staging Area & Reset

```bash
echo "Update" >> README.md
git status

git restore --staged README.md       # Unstage file
git restore README.md                # Discard changes
git rm --cached internals.txt        # Remove from Git but keep file
```

---

### Visualize & Amend Commit History

```bash
git commit --amend -m "Refactor: Improved setup commit message"
git log --oneline --graph --decorate
```

---

## Real-World Use Cases

| Scenario                    | Relevance                                     |
| --------------------------- | --------------------------------------------- |
| Internal automation setup   | Version-control Bash/Ansible scripts          |
| Clean repo management       | Track only relevant files with `.gitignore`   |
| Rollback & history analysis | Use commit history and object model knowledge |
| CI/CD pipelines             | Prepare for stable commits and tags           |

---

## Interview Q\&A

> **Q**: What are Git’s 3 main areas?
> **A**: Working Directory → Staging Area → Repository.

> **Q**: Difference between `restore` and `reset`?  
> **A**: `restore` works on files in working/staging areas. `reset` affects commits and staging.

> **Q**: Why is commit hygiene important?  
> **A**: Clean, atomic commits improve rollback, debugging, and collaboration.

> **Q**: What does `cat-file -p <hash>` do?  
> **A**: It shows the content of the Git object corresponding to the given hash.

---

## Folder Structure

```
GIT-001-Git-Fundamentals/
├── .gitignore
├── README.md
├── internals.txt
├── scripts/
│   └── setup.sh
└── screenshots/
    ├── git-status.png
    ├── object-directory.png
    ├── logs.png
    └── object-type.png
```

---

## Validation Checklist

| Task                                   | Done |
| -------------------------------------- | ---- |
| Git repo initialized                   | ✅   |
| User identity configured               | ✅   |
| Files tracked with `.gitignore`        | ✅   |
| Internals explored via object commands | ✅   |
| Clean commit messages used             | ✅   |
| Visual logs/screenshots added          | ✅   |

---

## Suggested Screenshots

- `git status` (clean vs dirty working tree)
- `.git/objects/` content preview
- `cat-file` output
- Git log tree with `--graph`
- Sample commit messages and amend

---

## Bonus Knowledge

- `git cat-file -t <hash>` → View object type
- `git fsck` → Verify object integrity
- `git tag v1.0` → Create stable release markers
- `git restore --source=HEAD~1` → Rollback to a prior commit

---

## FameTech Story

This foundational lab was completed as part of **Sprint 1** at FameTech.
It helped establish Git standards and workflows for managing infrastructure automation code.
I practiced real-world Git techniques used by DevOps teams to manage collaboration, stability, and CI readiness.

---
