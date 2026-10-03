<div align="center">

# 🛠️ Git & GitHub Troubleshooting, Recovery & Automation Handbook

**A hands-on learning and reference repository for Git, GitHub, version control workflows, troubleshooting, recovery, and automation.**
<br>
[![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?logo=git\&logoColor=white)](https://git-scm.com/docs)
[![GitHub](https://img.shields.io/badge/GitHub-Platform-181717?logo=github\&logoColor=white)](https://docs.github.com/)
[![GitHub CLI](https://img.shields.io/badge/GitHub%20CLI-gh-181717?logo=github\&logoColor=white)](https://cli.github.com/)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?logo=githubactions\&logoColor=white)](https://docs.github.com/actions)
[![PowerShell](https://img.shields.io/badge/PowerShell-Automation-5391FE?logo=powershell\&logoColor=white)](https://learn.microsoft.com/powershell/)
[![Python](https://img.shields.io/badge/Python-Automation-3776AB?logo=python\&logoColor=white)](https://www.python.org/)
<br>
**Symptom → Evidence → Analysis → Root Cause → Remediation → Verification**
</div>

---

## 📖 About This Repository

**Git & GitHub Troubleshooting, Recovery & Automation Handbook** is a hands-on repository for learning Git and GitHub from fundamentals to advanced workflows, with a strong focus on understanding repository state, diagnosing failures, recovering from mistakes, and applying automation in real-world engineering environments.

Rather than simply memorizing commands, this repository follows an operational approach:

> **Learn the command. Understand the state. Diagnose the problem. Recover safely. Verify the result.**

Each major command, concept, and troubleshooting scenario is designed to answer four practical questions:

1. **What does it show or do?**
2. **What problem would make me run it?**
3. **How do I interpret the output?**
4. **What would I run next based on the result?**

The objective is to build the ability to **reason about Git and GitHub state**, not just remember commands.

---

## 📌 What Is This Repository?

**Git & GitHub Troubleshooting, Recovery & Automation Handbook** is a hands-on reference for learning Git and GitHub from fundamentals to advanced workflows, with a strong focus on understanding repository state, diagnosing failures, recovering from mistakes, and troubleshooting real-world development and CI/CD scenarios.

Rather than simply memorizing commands, the Handbook follows an operational approach:

```text
Symptom
   ↓
Evidence
   ↓
Analysis
   ↓
Root Cause
   ↓
Remediation
   ↓
Verification
```

Every major command and scenario explains:

* What the command does and what it actually changes or displays
* When and why you would use it
* How to interpret its output
* What command or action to perform next
* What risks are associated with the operation
* How to verify that the problem has actually been resolved

The goal is not to become someone who merely knows hundreds of Git commands.

The goal is to become someone who can **understand Git's state, troubleshoot it methodically, recover from mistakes, and use Git/GitHub confidently in real engineering environments.**

---

## 🎯 Objectives

This repository aims to provide a practical path from:

```text
Git Fundamentals
       ↓
Daily Git Usage
       ↓
Branching & Collaboration
       ↓
Remote Repositories
       ↓
Advanced Git Workflows
       ↓
Undo & Recovery
       ↓
GitHub & Pull Requests
       ↓
GitHub CLI
       ↓
GitHub Actions / CI-CD
       ↓
Real-World Troubleshooting
       ↓
Incident Recovery & Automation
```

The repository focuses on five major outcomes:

1. **Learn Git and GitHub fundamentals**
2. **Understand what Git is actually doing internally**
3. **Troubleshoot common and advanced Git/GitHub problems**
4. **Recover safely from mistakes and unexpected repository states**
5. **Build an automation-oriented mindset around GitHub and CI/CD**

---

## 👥 Who Is This For?

### 🎓 Students & Beginners

Use this repository to build a solid Git foundation instead of learning Git purely through command memorization.

You will learn concepts such as:

* What Git actually is
* Git vs GitHub
* Repository structure
* Working tree
* Staging area / index
* Commits
* Branches
* HEAD
* Remotes
* Pull requests
* Merge and rebase
* GitHub Actions

---

### 👨‍💻 Developers & Engineers

Use the Handbook as a practical reference when something goes wrong.

Examples:

* Why did `git push` get rejected?
* Why are my local and remote branches diverged?
* Why is Git showing a merge conflict?
* How do I undo the last commit?
* How do I recover a deleted branch?
* How do I recover a lost commit?
* Why is a file not being tracked?
* Why is `.gitignore` not working?
* Why does authentication fail?
* How do I determine what changed between two commits?
* How do I identify the commit that introduced a regression?
* Why is a GitHub Actions workflow failing?

The focus is on **practical problem-solving, operational understanding, troubleshooting, recovery, and safe use of Git and GitHub** rather than simply memorizing commands.

---

# 🧠 Core Troubleshooting Methodology

Every troubleshooting scenario follows the same methodology:

```text
┌───────────────┐
│    SYMPTOM    │
│ What went     │
│ wrong?        │
└───────┬───────┘
        ↓
┌───────────────┐
│    EVIDENCE   │
│ What does Git │
│ tell us?      │
└───────┬───────┘
        ↓
┌───────────────┐
│    ANALYSIS   │
│ What does the │
│ evidence mean?│
└───────┬───────┘
        ↓
┌───────────────┐
│  ROOT CAUSE   │
│ Why did this  │
│ happen?       │
└───────┬───────┘
        ↓
┌───────────────┐
│  REMEDIATION  │
│ What is the   │
│ safest fix?   │
└───────┬───────┘
        ↓
┌───────────────┐
│ VERIFICATION  │
│ Did the fix   │
│ actually work?│
└───────────────┘
```

This prevents the common troubleshooting mistake of running commands randomly until something appears to work.

---

# 🔎 The 4-Question Framework

Every major command/reference page is built around four questions.

### 1️⃣ What does it show / do?

Understand the mechanism.

Examples:

* Does it modify the working tree?
* Does it modify the staging area?
* Does it move `HEAD`?
* Does it create a commit?
* Does it modify a branch reference?
* Does it communicate with a remote?
* Does it only inspect repository state?

### 2️⃣ What problem would make me run it?

Connect the command to a real situation.

For example:

```text
Problem:
"git push" was rejected.

Possible evidence:
! [rejected] main -> main (non-fast-forward)

Useful investigation:
git status
git branch -vv
git fetch
git log --oneline --graph --decorate --all
```

The command should be selected because of the **problem**, not because it happens to be a familiar Git command.

### 3️⃣ How do I interpret the output?

Knowing a command is not enough.

You should understand what the result means.

Examples:

```text
ahead by 2 commits
behind by 3 commits
both modified
HEAD detached
Your branch and 'origin/main' have diverged
nothing to commit
working tree clean
```

The output is **evidence**.

### 4️⃣ What would I run next?

Troubleshooting rarely ends with one command.

The result of one command should determine the next action.

```text
git status
    ↓
Understand current state
    ↓
git diff
    ↓
Inspect working-tree changes
    ↓
git diff --cached
    ↓
Inspect staged changes
    ↓
Choose remediation
    ↓
Verify with git status
```

---

# ⚠️ Command Safety Ratings

Git provides powerful recovery and history-rewriting capabilities.

Some operations are safe inspections.

Others can modify repository state.

Some can permanently remove data if used incorrectly.

Every command/reference therefore uses one of the following safety ratings:

| Rating                         | Meaning                                                                                           |
| ------------------------------ | ------------------------------------------------------------------------------------------------- |
| 🟢 **Read-only**               | Inspects information without intentionally changing repository state                              |
| 🟡 **State-changing**          | Changes working tree, index, references, branches, commits, or remote state                       |
| 🔴 **Potentially destructive** | Can discard changes, rewrite history, delete objects/files, or cause difficult-to-reverse changes |

### Example

```text
git status
🟢 Read-only
```

```text
git add
🟡 State-changing
```

```text
git reset --hard
🔴 Potentially destructive
```

The safety rating is applied to the **specific operation or usage**, not merely to the command name.

---

# 🧭 Understanding Git's State

A major objective of this repository is to build a mental model of Git rather than treating Git as a collection of unrelated commands.

One of the most important models is:

```text
                 Git Repository

       ┌─────────────────────────────┐
       │            HEAD             │
       │     Current reference       │
       └──────────────┬──────────────┘
                      ↓
       ┌─────────────────────────────┐
       │            INDEX            │
       │       Staging Area          │
       └──────────────┬──────────────┘
                      ↓
       ┌─────────────────────────────┐
       │        WORKING TREE         │
       │ Files currently on disk     │
       └─────────────────────────────┘
```

Understanding this relationship makes commands such as:

```text
git add
git commit
git restore
git reset
git diff
git diff --cached
git revert
git reflog
```

much easier to understand.

---

# 📚 Repository Roadmap

The repository is organized progressively, from fundamentals to advanced troubleshooting.

| Module                                      | Focus                                                              |
| ------------------------------------------- | ------------------------------------------------------------------ |
| `00-Git-Fundamentals`                       | Git concepts, architecture, repository internals and mental models |
| `01-Getting-Started`                        | Installing/configuring Git and creating or cloning repositories    |
| `02-Daily-Git-Workflow`                     | Status, staging, commits, differences and file operations          |
| `03-Commit-History-and-Inspection`          | Log, show, blame, reflog and history investigation                 |
| `04-Branching-and-Workspaces`               | Branches, switching, checkout and worktrees                        |
| `05-Remote-Repositories`                    | Remotes, fetch, pull, push and tracking branches                   |
| `06-Merging-Rebasing-and-Cherry-Picking`    | Combining and replaying changes                                    |
| `07-Undoing-and-Recovery`                   | Restore, reset, revert, stash, reflog and recovery                 |
| `08-Git-Authentication-and-Security`        | HTTPS credentials, SSH, GPG, tokens and secrets                    |
| `09-GitHub`                                 | Repositories, PRs, issues, forks, protection and collaboration     |
| `10-GitHub-CLI`                             | Managing GitHub from the command line                              |
| `11-GitHub-Actions`                         | Workflows, runners, secrets, permissions and CI/CD troubleshooting |
| `12-Advanced-Git`                           | Bisect, clean, tags, submodules and Git internals                  |
| `13-Troubleshooting-and-Incident-Playbooks` | Real-world failures, diagnosis, recovery and verification          |

---

# 🛠️ Examples of Problems Covered

The repository is designed around questions engineers actually encounter.

### Local Repository Problems

```text
Why is Git showing modified files?
Why is my file not staged?
Why is my file being ignored?
Why does git diff show nothing?
Why does git diff --cached show changes?
Why is HEAD detached?
```

### Commit Problems

```text
I committed the wrong file.
I committed to the wrong branch.
I need to undo my last commit.
I need to change the last commit.
I accidentally deleted a commit.
I cannot find a commit I created earlier.
```

### Branch Problems

```text
My branches have diverged.
I cannot switch branches.
I have uncommitted changes preventing a branch switch.
I accidentally deleted a branch.
I need to compare two branches.
```

### Merge and Rebase Problems

```text
I have a merge conflict.
I am stuck in the middle of a rebase.
Git says there are unresolved conflicts.
I need to abort a merge.
I need to abort a rebase.
I need to continue a rebase after resolving conflicts.
```

### Remote Problems

```text
git push was rejected.
The remote branch contains changes I don't have.
My local branch is behind.
My local and remote branches have diverged.
I pushed something I should not have pushed.
Authentication failed.
Permission denied.
```

### GitHub Problems

```text
Why can't my Pull Request merge?
Why are required checks failing?
Why can't I push to the repository?
Why is a branch protected?
Why is my GitHub Action failing?
Why can't my workflow access a secret?
Why did my workflow not trigger?
```

### Recovery Scenarios

```text
Recover a lost commit
Recover a deleted branch
Recover from detached HEAD
Undo an incorrect merge
Abort an incorrect rebase
Recover from an accidental reset
Remove a committed secret
Handle a large file blocking a push
```

---

# 🧪 Hands-On Approach

This repository is intended to be **executed, not merely read**.

Examples should ideally be reproducible in a safe test repository.

```bash
git init
git status
git add .
git commit -m "Initial commit"
```

Then intentionally create scenarios:

```text
Create a branch
Make conflicting changes
Perform a merge
Create a rebase conflict
Reset a commit
Recover it using reflog
Create a rejected push scenario
Troubleshoot the repository state
Verify the recovery
```

The objective is to understand what Git does **before, during and after** each operation.

---

# 🔬 Evidence-First Troubleshooting

A core principle of this repository is:

> **Do not change repository state until you understand the evidence.**

For example, if a push fails:

### ❌ Random approach

```bash
git pull
git reset
git rebase
git push --force
```

### ✅ Evidence-first approach

```text
git status
        ↓
git branch -vv
        ↓
git fetch
        ↓
git log --oneline --graph --decorate --all
        ↓
Understand divergence
        ↓
Choose remediation
        ↓
Verify
```

This approach is particularly important when dealing with:

* Rebases
* Resets
* Force pushes
* Merge conflicts
* Deleted branches
* Lost commits
* Shared branches
* Protected GitHub branches

---

# 🔐 Security Considerations

Git repositories can contain sensitive information.

This Handbook therefore also covers:

* SSH authentication
* HTTPS authentication
* Credential managers
* Personal access tokens
* GPG commit signing
* GitHub secrets
* Accidental secret commits
* History rewriting
* Secret removal and verification

### Important

Removing a secret from the latest commit does **not necessarily mean the secret has disappeared from Git history**.

Security-related remediation therefore requires understanding:

```text
Working Tree
      ↓
Index
      ↓
Commit
      ↓
History
      ↓
Remote Repository
```

Security incidents should be handled carefully and verified independently.

---

# 🤖 GitHub & CI/CD Automation

Git is not only a local version-control tool.

Modern engineering workflows commonly connect:

```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
Pull Request
    ↓
GitHub Actions
    ↓
Build / Test / Security Checks
    ↓
Deployment
```

The later modules therefore extend troubleshooting into GitHub and CI/CD.

Topics include:

* Pull request workflows
* GitHub CLI
* Branch protection
* Required checks
* Workflow triggers
* Workflow permissions
* Secrets and variables
* GitHub-hosted runners
* Self-hosted runners
* Logs and artifacts
* Failed workflow diagnosis
* Automation opportunities

---

# 🧩 Incident Playbook Format

Real-world incident pages follow a standardized structure.

```text
┌────────────────────┐
│      SYMPTOM       │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│      EVIDENCE      │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│      ANALYSIS      │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│     ROOT CAUSE     │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│    REMEDIATION     │
└─────────┬──────────┘
          ↓
┌────────────────────┐
│    VERIFICATION    │
└────────────────────┘
```

For example:

**Incident:** `git push` rejected as non-fast-forward

```text
Symptom
  ↓
Push rejected
  ↓
Evidence
  ↓
git status
git branch -vv
git fetch
git log --graph --all
  ↓
Analysis
  ↓
Remote contains commits not present locally
  ↓
Root Cause
  ↓
Local branch is behind remote
  ↓
Remediation
  ↓
Choose merge or rebase based on workflow
  ↓
Verification
  ↓
git status
git log
git push
```

The goal is to teach **how to think through the incident**, not just provide a command that happens to fix it.

---

# 📖 How to Use This Repository

### If You Are New to Git

Start here:

```text
00-Git-Fundamentals
        ↓
01-Getting-Started
        ↓
02-Daily-Git-Workflow
        ↓
03-Commit-History-and-Inspection
        ↓
04-Branching-and-Workspaces
```

Then continue into remotes, collaboration, GitHub and CI/CD.

### If You Already Use Git

Jump directly to the topic or command you need.

For example:

```text
git rebase
git reset
git reflog
git push
git fetch
git merge
```

### If Something Is Broken

Go directly to:

```text
13-Troubleshooting-and-Incident-Playbooks
```

Then follow:

```text
Symptom
  ↓
Evidence
  ↓
Analysis
  ↓
Remediation
  ↓
Verification
```

---

# 🧰 Recommended Practice Environment

For safe experimentation, use a disposable repository:

```bash
mkdir git-lab
cd git-lab
git init
```

Create test branches and commits rather than experimenting with destructive commands in an important repository.

For example:

```text
git-lab/
│
├── main
├── feature-a
├── feature-b
└── recovery-lab
```

This makes it possible to intentionally create:

* Merge conflicts
* Rebase conflicts
* Diverged branches
* Detached HEAD
* Reset scenarios
* Reflog recovery scenarios
* Push rejection scenarios

---

# 📋 Command Coverage

The repository progressively covers Git commands from commonly used to advanced operations.

### Fundamentals

```text
git init
git clone
git config
git status
git add
git commit
git log
```

### Daily Operations

```text
git diff
git restore
git rm
git mv
git show
git branch
git switch
```

### Remote Operations

```text
git remote
git fetch
git pull
git push
```

### Advanced History Operations

```text
git merge
git rebase
git cherry-pick
git reset
git revert
git reflog
git stash
```

### Advanced / Diagnostic Operations

```text
git bisect
git clean
git tag
git worktree
git submodule
git rev-parse
git cat-file
git fsck
```

The command list will continue to evolve as additional troubleshooting and automation scenarios are added.

---

# ⭐ What Makes This Different?

There are many Git cheat sheets and command references.

This repository is intentionally designed to go beyond:

```text
"Here is the command."
```

Instead:

```text
What happened?
      ↓
What evidence do I have?
      ↓
What does Git's state tell me?
      ↓
What is the likely root cause?
      ↓
What is the safest remediation?
      ↓
How do I verify the result?
```

The repository therefore combines:

| Area                   | Focus                                       |
| ---------------------- | ------------------------------------------- |
| 📚 Learning            | Understand Git/GitHub concepts              |
| 🧰 Reference           | Quickly find commands and syntax            |
| 🔎 Troubleshooting     | Diagnose real problems                      |
| ♻️ Recovery            | Safely recover from mistakes                |
| 🔐 Security            | Authentication and sensitive-data scenarios |
| 🤝 Collaboration       | Branches, merges and pull requests          |
| 🤖 Automation          | GitHub CLI and GitHub Actions               |
| 🚀 CI/CD               | Workflow troubleshooting and automation     |
| 🧠 Engineering Mindset | Evidence-driven problem solving             |

---

# 🗺️ Repository Philosophy

The central philosophy is simple:

> **Don't just learn what command to run. Learn why you are running it, what Git is telling you, what could go wrong, and how to prove that your remediation worked.**

Git is powerful because it records and manages repository state.

That same power means commands such as:

```text
reset
rebase
clean
push --force
```

should never be treated as magic commands.

**Understand the state first.
Then change it deliberately.
Finally, verify the result.**

---

# 🚧 Repository Status

This repository is being built progressively from fundamentals through advanced troubleshooting and automation.

Content will be expanded with:

* More command references
* More diagrams
* Hands-on examples
* Troubleshooting scenarios
* Recovery exercises
* GitHub workflows
* GitHub Actions scenarios
* CI/CD automation examples
* Real-world incident playbooks

---

# 🤝 Contributions & Feedback

Suggestions, corrections, additional troubleshooting scenarios and improvements are welcome.

If you find an incorrect command, unclear explanation or missing scenario, feel free to open an issue or submit a pull request.

---

# 📌 Quick Reference

When working with Git, remember:

```text
                    ┌───────────────┐
                    │  What is the  │
                    │ current state?│
                    └───────┬───────┘
                            ↓
                    ┌───────────────┐
                    │ Collect       │
                    │ evidence      │
                    └───────┬───────┘
                            ↓
                    ┌───────────────┐
                    │ Understand    │
                    │ the state     │
                    └───────┬───────┘
                            ↓
                    ┌───────────────┐
                    │ Choose the    │
                    │ safest action │
                    └───────┬───────┘
                            ↓
                    ┌───────────────┐
                    │ Change state  │
                    └───────┬───────┘
                            ↓
                    ┌───────────────┐
                    │ Verify        │
                    └───────────────┘
```

### The Golden Rule

> **Inspect first. Change deliberately. Verify afterwards.**

---

## 📜 License & Disclaimer

This repository is provided as an **educational and technical reference** intended to help readers learn Git, GitHub, troubleshooting techniques, recovery approaches, and automation concepts.

The commands, examples, procedures, recommendations, and troubleshooting scenarios provided in this repository are intended for **learning, experimentation, and reference purposes only**.

### ⚠️ Use Commands at Your Own Risk

Git provides commands that can modify or permanently remove repository data, rewrite commit history, alter branches, delete files, or affect remote repositories.

Examples include, but are not limited to:

```text
git reset --hard
git clean
git rebase
git push --force
git branch -D
