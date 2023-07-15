# FameTech DevOps Lab – GitHub & Open Source Collaboration

> In this hands-on GitHub lab, I practiced real-world DevOps collaboration workflows involving remote repository setup, pull request workflows, and open source contributions.
> This simulation mirrors team-based DevOps engineering responsibilities at FameTech, including SSH key authentication, GitHub PR handling, and upstream sync in forked repositories.

---

## About This Project

This project demonstrates my ability to work with GitHub-based collaboration and CI/CD workflows during my DevOps role at **FameTech NYC**.
As part of the External Tools & Community Contributions Team, I was responsible for simulating GitOps-ready workflows and open source engagement.

> This project experience is verifiable by FameTech upon request.

---

## Lab Metadata

| Field      | Detail                                      |
| ---------- | ------------------------------------------- |
| Lab ID     | GIT-003                                     |
| Engineer   | Sheikh Ahmed (DevOps Engineer)              |
| Company    | FameTech NYC                                |
| Sprint     | Sprint 5 – GitHub Open Source Collaboration |
| Platform   | GitHub, Git CLI                             |
| Difficulty | Intermediate                                |
| Time       | \~60–75 minutes                             |

---

## Objectives

- Set up GitHub SSH access for secure collaboration
- Push local repositories to GitHub using `git remote`
- Create and manage Pull Requests (PRs)
- Fork open source repos and contribute changes
- Sync forks with upstream using best practices

---

## Tools & Concepts Used

| Tool/Concept              | Purpose                                    |
| ------------------------- | ------------------------------------------ |
| `ssh-keygen`              | Secure authentication with GitHub          |
| `git remote`              | Connect local repo to GitHub/forked repos  |
| `git push/pull`           | Collaborate with GitHub repositories       |
| `git branch`              | Feature branching for PR simulation        |
| GitHub Fork               | External repo duplication for contribution |
| Pull Request (PR)         | Simulate enterprise collaboration workflow |
| `git remote add upstream` | Sync forks with the original repository    |

---

## Scenario – GitHub Sprint Simulation

**Ticket**: `FAME-GIT-003`
**Reported By**: External Tools Team
**Assigned To**: Sheikh Ahmed
**Priority**: Medium
**Status**: Completed

As part of the external tools initiative at FameTech, your team is evaluating open source collaboration workflows. You’ve been assigned to simulate a secure GitHub setup and create a pull request workflow with the following:

- SSH-based GitHub repo push
- PR creation & review simulation
- Forking a live open source repo
- Submitting a real or simulated PR
- Upstream sync to track the latest changes

---

## Implementation Steps

### 1. Setup SSH Key Authentication for GitHub

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
cat ~/.ssh/id_rsa.pub
```

> Add the public key to **GitHub → Settings → SSH and GPG Keys**

Test the connection:

```bash
ssh -T git@github.com
```

---

### 2. Push Local Repository to GitHub

```bash
git remote add origin git@github.com:yourusername/project.git
git branch -M main
git push -u origin main
```

> Your local repo is now tracked remotely on GitHub.

---

### 3. Simulate GitHub PR Workflow

```bash
git checkout -b update-docs
echo "Updated README with instructions" >> README.md
git add README.md
git commit -m "Update README for PR simulation"
git push origin update-docs
```

> Create a PR via GitHub UI → request review → simulate team approval and merge.

---

### 4. Fork and Contribute to an Open Source Repo

1. Navigate to a real repo (e.g., [`kubernetes/website`](https://github.com/kubernetes/website))
2. Click **Fork**
3. Clone your fork:

```bash
git clone git@github.com:yourusername/website.git
cd website
git checkout -b fix-doc-typo
```

4. Make a change, commit, and push:

```bash
git add .
git commit -m "Fix typo in documentation"
git push origin fix-doc-typo
```

> Create a PR back to the **upstream** repo.

---

### 5. Sync Forked Repo with Upstream

```bash
git remote add upstream https://github.com/susan-jfk/devops-toolkit
git fetch upstream
git merge upstream/main
```

> Keeps your forked repo up to date with latest changes.

---

## Real-World Use Cases

| Scenario               | Why It Matters                                  |
| ---------------------- | ----------------------------------------------- |
| Dev team collaboration | Enables clean, trackable workflows              |
| GitOps workflow        | PR triggers infra deployment pipelines          |
| Open source resume     | Demonstrates skill + boosts reputation          |
| Enterprise GitHub use  | Reflects org policies like PR review, CI checks |

---

## Interview Q\&A

> **Q**: What’s the difference between `git pull`, `git fetch`, and `git clone`?  
> **A**:
>
> - `clone`: copies entire repo
> - `fetch`: retrieves changes, no merge
> - `pull`: fetch + merge

---

> **Q**: Why do we use `origin` and `upstream`?  
> **A**:
>
> - `origin`: your fork
> - `upstream`: the original repository

---

> **Q**: How do teams enforce quality in PR workflows?  
> **A**:
>
> - Use branch protection rules
> - Require reviewers
> - Enforce CI before merge

---

## Folder Structure

```
GIT-003-GitHub-Collaboration/
├── README.md
├── .gitignore
├── ssh-test.png
├── pr-flow.png
├── fork-clone.png
├── notes/
│   └── open_source_pr_checklist.md
```

---

## Validation Checklist

| Task                                | Status |
| ----------------------------------- | ------ |
| SSH key setup completed             | ✅     |
| Repo pushed to GitHub               | ✅     |
| Branch pushed and PR created        | ✅     |
| Forked and contributed to open repo | ✅     |
| Upstream configured and synced      | ✅     |
| Screenshots/notes documented        | ✅     |

---

## FameTech Story

As part of **Sprint 5**, I contributed to FameTech’s External Tools & Community team by simulating end-to-end GitHub workflows.
This included pushing a local project to GitHub, using feature branches and PRs for collaboration, and contributing to open source with proper fork and upstream tracking.
These workflows reflect industry best practices for secure, team-friendly GitOps pipelines and enterprise GitHub usage.

---
