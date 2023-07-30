# FameTech DevOps Lab Series – Git Version Control Mastery

> This Git lab series simulates real-world DevOps workflows involving version control, collaboration, disaster recovery, and GitHub-based open source contribution.  
> As part of my sprint work at FameTech NYC, I applied foundational and advanced Git techniques used daily by DevOps teams managing infrastructure automation, CI/CD pipelines, and team-based repositories.

---

## About This Project

This lab series reflects my hands-on experience as a **DevOps Engineer** at **FameTech NYC**, where I participated in multiple sprints to design and maintain Git workflows that mirror production DevOps environments.

Each lab was completed as part of a larger internal initiative to standardize tooling, strengthen collaboration, and simulate GitOps readiness for infrastructure as code.

> These projects are verifiable by FameTech upon request.

---

## Series Metadata

| Field           | Detail                                      |
| --------------- | ------------------------------------------- |
| Labs Included   | GIT-001, GIT-002, GIT-003                   |
| Engineer        | Sheikh Ahmed (DevOps Engineer)              |
| Company         | FameTech NYC                                |
| Duration        | ~3–4 hours total                            |
| Sprint Timeline | Sprint 1, 4, and 5                          |
| Tools           | Git CLI, GitHub, SSH, Pull Request Workflow |
| Difficulty      | Beginner → Intermediate → Advanced          |

---

## Labs Summary

| Lab ID  | Title                                   | Key Topics                                                |
| ------- | --------------------------------------- | --------------------------------------------------------- |
| GIT-001 | Git Fundamentals & Workflow Mastery     | Staging, `.gitignore`, commit hygiene, internals          |
| GIT-002 | Git Collaboration: Branching & Recovery | Feature branching, merge conflicts, squash, stash, reflog |
| GIT-003 | GitHub & Open Source Collaboration      | SSH setup, GitHub PRs, forks, upstream sync               |

---

## Objectives Across All Labs

- Master Git basics: working directory, staging, commits, `.gitignore`
- Use Git internals: blobs, object IDs, `cat-file`, `hash-object`
- Simulate real-world branching, merging, and rebase workflows
- Practice stash management and disaster recovery with `reflog`
- Collaborate on GitHub via PRs, forks, and upstream repo sync
- Build confidence contributing to internal and external projects

---

## Tools & Concepts Practiced

| Tool / Concept              | Purpose                                       |
| --------------------------- | --------------------------------------------- |
| `git init`, `add`, `commit` | Track and snapshot file changes               |
| `restore`, `reset`          | Manage working directory and staged area      |
| `rebase`, `merge`           | Clean or integrate commit histories           |
| `stash`, `reflog`           | Save WIP or recover deleted work              |
| `git remote`, `push`        | Connect local repos to GitHub, simulate teams |
| SSH & Forks                 | Secure access and contribute to open source   |
| GitHub PRs                  | Submit and review code collaboratively        |

---

## Real-World Scenarios Simulated

| Scenario                           | DevOps Use Case                                  |
| ---------------------------------- | ------------------------------------------------ |
| Version-controlling scripts        | Bash/Ansible IaC scripts in internal tool repos  |
| Feature development workflows      | Branching + PRs in CI/CD pipeline delivery       |
| Disaster recovery via reflog/stash | Hotfix rollbacks, lost commit recovery           |
| GitHub-based team workflows        | GitOps pipelines, external tooling contributions |
| Open source resume contribution    | Simulate public PRs and community collaboration  |

---

## Folder Structure

```

fame-git-labs/
├── GIT-001-Git-Fundamentals/
│   ├── .gitignore
│   ├── README.md
│   ├── internals.txt
│   ├── scripts/
│   │   └── setup.sh
│   └── screenshots/
│       ├── git-status.png
│       ├── object-directory.png
│       ├── logs.png
│       └── object-type.png
│
├── GIT-002-Collaboration-Workflow/
│   ├── deploy.sh
│   ├── README.md
│   ├── config.yml
│   ├── temp.txt
│   ├── screenshots/
│   │   ├── git-log-graph.png
│   │   ├── stash-list.png
│   │   └── reflog-output.png
│   └── notes/
│       └── reflog\_recovery\_notes.txt
│
├── GIT-003-GitHub-Collaboration/
│   ├── README.md
│   ├── .gitignore
│   ├── ssh-test.png
│   ├── pr-flow\.png
│   ├── fork-clone.png
│   └── notes/
│       └── open\_source\_pr\_checklist.md

```

---

## Validation Checklist

| Task                                       | Status |
| ------------------------------------------ | ------ |
| Git basics practiced with clean commits    | ✅     |
| Internals explored (`cat-file`, objects)   | ✅     |
| Branching, squash, and cherry-pick covered | ✅     |
| Conflict resolution simulated              | ✅     |
| Reflog + stash for disaster recovery       | ✅     |
| GitHub push, fork, PR, and upstream tested | ✅     |
| Screenshots and notes documented           | ✅     |

---

## Interview Q&A Highlights

> **Q**: What’s the difference between `merge` and `rebase`?  
> **A**: `merge` creates a commit joining branches. `rebase` replays commits for a linear history.

> **Q**: What are Git’s 3 main areas?  
> **A**: Working Directory → Staging Area → Repository.

> **Q**: How does `reflog` help in Git recovery?  
> **A**: It records all HEAD movements, allowing recovery of lost commits or branches.

> **Q**: Why do we use both `origin` and `upstream`?  
> **A**: `origin` is your fork; `upstream` is the source repo you forked from.

> **Q**: Why is commit hygiene critical in CI/CD?  
> **A**: Clean commits enable stable rollbacks, efficient code reviews, and safe deployments.

---

## FameTech Story

These Git labs were completed as part of multiple sprints at **FameTech NYC**, where I worked as a DevOps Engineer on the Internal Tooling and CI/CD Collaboration Teams.

This project series helped establish Git best practices across engineering teams, simulated recovery scenarios, and contributed to the GitOps readiness of infrastructure projects.  
The skills and workflows I practiced here reflect real enterprise DevOps environments.

---
