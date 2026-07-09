# Git and GitHub in VS Code

## Course Handout

**Format:** practical guide + command reference + examples  
**Audience:** beginners and intermediate learners  
**Goal:** learn Git and GitHub workflows from inside VS Code

---

## Quick Course Overview

### What you will learn

- how to start a project
- how to connect it to GitHub
- how to commit changes
- how to create branches
- how to push and pull code
- how to work with pull requests
- how to use the VS Code Source Control panel

### At a glance

| Topic | What you will learn |
|---|---|
| Git basics | Track and save code changes |
| GitHub basics | Store and share repositories |
| VS Code workflow | Use the terminal and Source Control panel |
| Collaboration | Branch, push, pull, and open PRs |

> Tip: Print this handout in landscape mode for the command tables and examples.

---

## 1) Introduction

This handout explains how to use Git and GitHub from VS Code with practical examples.

---

## 2) Git vs GitHub

### Git
Git is a version control system. It tracks changes in files.

### GitHub
GitHub is a cloud platform that hosts Git repositories and helps teams collaborate.

### VS Code
VS Code is the editor where you can write code and run Git commands easily.

---

## Learning Targets

By the end of this handout, you should be able to:

- initialize a Git repository
- stage and commit changes
- connect a project to GitHub
- push and pull changes
- create and merge branches
- read diffs and history
- use VS Code Git features confidently

### Course notes

- Keep VS Code open with the terminal and Source Control panel visible.
- Practice each command on a small test repository first.
- Use the screenshot placeholders to add your own images later.

---

<!-- pagebreak -->

## 3) Before you start

Install:
- Git
- VS Code
- a GitHub account

Check Git is installed:

```bash
git --version
```

Configure your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## 4) Open Git in VS Code

There are two common ways:

### A. Using the terminal
Open VS Code terminal:
- `Terminal > New Terminal`

### B. Using Source Control
Open the left sidebar and click the Source Control icon.

### Screenshot placeholder

Add a screenshot here showing the VS Code Source Control icon and terminal panel.

```text
[Screenshot: VS Code window with Source Control icon highlighted]
```

---

## 5) Start a new Git project

### Create a folder and open it in VS Code

Then initialize Git:

```bash
git init
```

This creates a hidden `.git` folder and starts tracking your project.

Example:
- create `index.html`
- run `git init`
- Git begins tracking the folder

### Screenshot placeholder

Add a screenshot of the terminal after running `git init`.

```text
[Screenshot: Terminal showing git init success message]
```

---

## 6) Check project status

```bash
git status
```

This shows:
- new files
- modified files
- files ready to commit

Example output:

```bash
On branch main
Untracked files:
  index.html
```

### Why this command matters

Use `git status` before every commit. It helps you confirm:
- which files changed
- which files are staged
- whether anything unexpected is included

### Screenshot placeholder

Add a screenshot of the Source Control panel showing changed files.

```text
[Screenshot: Source Control panel listing modified files]
```

---

## 7) Add files to staging

### Add one file

```bash
git add index.html
```

### Add all files

```bash
git add .
```

Staging means: "prepare these changes for the next commit."

In VS Code Source Control:
- hover a file
- click the `+` icon to stage it

### Screenshot placeholder

Add a screenshot showing the plus icon next to a file.

```text
[Screenshot: File list with plus icon highlighted]
```

---

## 8) Commit changes

```bash
git commit -m "Add home page"
```

A commit is a saved snapshot of your work.

### What happens during a commit

When you commit:
- Git records the staged files
- Git stores a message describing the change
- your project gets a new history entry

Good commit messages:
- Add login form
- Fix navbar spacing
- Update README

Bad commit messages:
- update
- stuff
- changes

### In VS Code
1. Open Source Control
2. Type commit message
3. Click Commit

### Screenshot placeholder

Add a screenshot of the commit message box and commit button.

```text
[Screenshot: Source Control commit box with a message typed in]
```

---

## 9) Connect local project to GitHub

Create a repository on GitHub, then connect it:

```bash
git remote add origin https://github.com/username/repo-name.git
```

Check remote:

```bash
git remote -v
```

Example:

```bash
origin  https://github.com/surya/my-project.git (fetch)
origin  https://github.com/surya/my-project.git (push)
```

### Screenshot placeholder

Add a screenshot of the GitHub repository page showing the repo URL.

```text
[Screenshot: GitHub repository page with clone URL highlighted]
```

---

## 10) Push code to GitHub

```bash
git push -u origin main
```

This sends your local commits to GitHub.

### What to expect

After a successful push:
- your code appears on GitHub
- the branch updates remotely
- teammates can pull your changes

### What `-u` means
It sets the upstream branch, so next time you can use:

```bash
git push
```

### Screenshot placeholder

Add a screenshot of the VS Code push or sync status.

```text
[Screenshot: VS Code showing push/sync completed]
```

---

## 11) Pull latest changes

```bash
git pull origin main
```

This downloads changes from GitHub and merges them into your local branch.

Use it when:
- someone else updated the repo
- you want the latest version before working

### Screenshot placeholder

Add a screenshot of a pull operation in VS Code or terminal.

```text
[Screenshot: Terminal showing git pull output]
```

---

## 12) Clone an existing GitHub repository

```bash
git clone https://github.com/username/repo-name.git
```

This copies the repository to your computer.

### In VS Code
You can also use:
- `Ctrl+Shift+P`
- type `Git: Clone`
- paste the repository URL

### Screenshot placeholder

Add a screenshot of the VS Code clone command palette.

```text
[Screenshot: Command Palette with Git: Clone selected]
```

---

## 13) Branching

Branches help you work on new features safely.

### Create a branch

```bash
git branch feature-login
```

### Switch to a branch

```bash
git checkout feature-login
```

### Create and switch at the same time

```bash
git checkout -b feature-login
```

### See branches

```bash
git branch
```

Example use:
- `main` branch = stable code
- `feature-login` branch = new login feature

### Screenshot placeholder

Add a screenshot of the branch selector in VS Code.

```text
[Screenshot: Branch name shown in VS Code status bar]
```

---

## 14) Merge branches

After finishing a feature, merge it into `main`:

```bash
git checkout main
git merge feature-login
```

This combines branch changes.

### Screenshot placeholder

Add a screenshot showing a merge commit or merge result.

```text
[Screenshot: Terminal showing git merge result]
```

---

## 15) View commit history

```bash
git log
```

Short version:

```bash
git log --oneline
```

This helps you see:
- commit IDs
- authors
- messages

### Screenshot placeholder

Add a screenshot of `git log --oneline` output.

```text
[Screenshot: Terminal showing short commit history]
```

---

## 16) See file changes

```bash
git diff
```

This shows what changed before committing.

Compare staged changes:

```bash
git diff --staged
```

### Screenshot placeholder

Add a screenshot of the diff view in VS Code.

```text
[Screenshot: VS Code diff view with added and removed lines]
```

---

## 17) Undo changes

### Discard local file edits

```bash
git restore filename.txt
```

### Unstage a file

```bash
git restore --staged filename.txt
```

Use carefully because you may lose changes.

### Screenshot placeholder

Add a screenshot showing the restore option in VS Code.

```text
[Screenshot: Source Control menu with discard/restore action]
```

---

## 18) Stash work temporarily

If you are not ready to commit:

```bash
git stash
```

Bring it back:

```bash
git stash pop
```

Example:
- you are halfway through a feature
- you need to switch branches quickly
- stash saves your unfinished work

### Screenshot placeholder

Add a screenshot showing stash-related terminal output.

```text
[Screenshot: Terminal showing git stash save and git stash pop]
```

---

## 19) Pull Request basics

A Pull Request (PR) is a request to merge your branch into another branch.

Typical workflow:
1. create a branch
2. make changes
3. commit
4. push to GitHub
5. open a PR
6. review and merge

### Screenshot placeholder

Add a screenshot of a GitHub pull request page.

```text
[Screenshot: GitHub PR page with branch comparison]
```

---

## 20) GitHub workflow from VS Code

### Step 1: Open your project
Open the folder in VS Code.

### Step 2: Make changes
Edit files.

### Step 3: Stage changes
Use Source Control `+` button.

### Step 4: Commit
Write a commit message and commit.

### Step 5: Push
Use:

```bash
git push
```

or click Sync/Push in VS Code.

### Step 6: Create PR
Open GitHub in browser or use VS Code GitHub features.

### Screenshot placeholder

Add a screenshot sequence here:
- project opened in VS Code
- Source Control changes
- commit box
- push completed
- GitHub PR page

```text
[Screenshot sequence: VS Code workflow from edit to pull request]
```

---

<!-- pagebreak -->

## 21) Common GitHub commands in VS Code terminal

| Task | Command |
|---|---|
| Initialize repo | `git init` |
| Check status | `git status` |
| Stage file | `git add file.txt` |
| Stage all | `git add .` |
| Commit | `git commit -m "message"` |
| Add remote | `git remote add origin URL` |
| Push | `git push -u origin main` |
| Pull | `git pull origin main` |
| Clone | `git clone URL` |
| Create branch | `git checkout -b branch-name` |
| Merge | `git merge branch-name` |
| View log | `git log --oneline` |

### Screenshot placeholder

Add a screenshot of a terminal command list or cheat sheet image.

```text
[Screenshot: Terminal with commonly used Git commands]
```

### Printable command sheet

Keep these commands close by while working:

- `git status`
- `git add .`
- `git commit -m "message"`
- `git push`
- `git pull`
- `git checkout -b branch-name`
- `git merge branch-name`
- `git log --oneline`

---

## 22) Practical example: first project

### Goal
Create a new website and upload it to GitHub.

### Commands

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/username/website.git
git push -u origin main
```

### What happened
- repository started
- files staged
- first commit saved
- GitHub remote added
- code uploaded

### Screenshot placeholder

Add screenshots for each stage of the first project:
- empty folder
- after `git init`
- after commit
- after push on GitHub

---

## 23) Practical example: feature branch

### Goal
Add a contact page safely.

### Commands

```bash
git checkout -b feature-contact-page
git add .
git commit -m "Add contact page"
git push -u origin feature-contact-page
```

Then create a PR on GitHub.

### Screenshot placeholder

Add screenshots of:
- branch creation
- branch push
- pull request creation

---

## 24) Practical example: update from GitHub

If team members changed the code:

```bash
git pull origin main
```

This keeps your local copy updated.

### Screenshot placeholder

Add a screenshot of the pull result after syncing with GitHub.

---

## 25) VS Code GitHub shortcuts

Useful actions:
- Source Control panel
- Commit button
- Sync Changes
- Branch selector
- GitHub pull request integration

Useful palette commands:
- `Git: Clone`
- `Git: Commit`
- `Git: Push`
- `Git: Pull`
- `Git: Create Branch`

Open Command Palette:

```text
Ctrl+Shift+P
```

### Screenshot placeholder

Add a screenshot of the Command Palette with Git commands listed.

---

## 26) Best practices

- commit often
- write clear messages
- work in branches
- pull before pushing
- review changes before commit
- avoid committing secrets like passwords or API keys

### Screenshot placeholder

Add a visual checklist or reminder card for best practices.

---

## 27) Quick revision

Remember this simple flow:

```text
edit -> git add -> git commit -> git push
```

And for collaboration:

```text
git pull -> edit -> commit -> push -> pull request
```

### Screenshot placeholder

Add a flow diagram image here showing the GitHub workflow.

---

## 28) Final summary

VS Code makes Git and GitHub easier by giving you:
- terminal commands
- Source Control UI
- branch management
- commit workflow
- GitHub integration

If you learn the core commands in this guide, you can manage most GitHub projects from VS Code confidently.

### End-of-course checklist

- [ ] I can initialize a repository
- [ ] I can stage and commit changes
- [ ] I can connect to GitHub
- [ ] I can push and pull code
- [ ] I can create and merge branches
- [ ] I can open a pull request

### Final screenshot placeholder

Add a summary screenshot showing VS Code, terminal, and GitHub together.

```text
[Screenshot: Final overview of VS Code connected to GitHub]
```
