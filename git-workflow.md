# Git Workflow

## Starting a Project from Scratch
\# Use this for your new ideas

**1. Create project folder locally and give it a name.**  
**2. Open project folder inside IDE (then work inb terminal)**

**3. Initialize Git and create README.md**
```
git init
echo "#My-Project-Title" >>> README.md
```

**4. Staging, First Commit and Renaming Branch**
```
git add .
git commit -m "chore: initial commit"
git branch -M main
```

**5. Connecting to Github**
```
git remote add origin <repo-url>
git push -u origin main
```

**6. Feature Branch (switch to new branch first for work)**
```
git checkout -b feature/issue-name
```
<br>

## Cloning an Existing Repo
\# Use this when you're joining a project or moving to a new computer.  

**1. Clone the repo and move into the folder**
```
git clone <repo-url>
cd <repo-name>
```

**2. Create your feature branch (don't code on main!)**
```
git checkout -b feature/issue-name
```

**3. Work and Commit (stage all the changes and commit with a message)**
```
git add .
git commit -m "feat: description of work"
```

**4. Ship it (push to remote repo and open a pull request in github)**
```
git push origin feature/issue-name
```
<br>

## Syncing an Existing Local Repo
\# Use this to make sure you have the latest code from other contributors (or your own past work) before starting something new.

**1. Switch to main branch and pull latest changes**
```
git checkout main
git pull origin main
```

**2. Feature branch from updated main**
```
git checkout -b feature/new-task-name
```

**3. Work, Commit, Ship**
```
git add .
git commit -m "feat: add new logic"
git push origin feature/new-task-name
```
<br>

## Pull Request & Merge
**1. Push the branch:** `git push origin feat/name`  
**2. Open a Pull Request in Github Repo**  
**3. After reviewing code and no conflicts, merge pull request on Github**  
**4. Cleanup**
```
git checkout main
git pull origin main
git branch -d feature/name
```
<br>

## Naming Conventions
\# Use consistent naming to make history and collaboration easy.

| Category | Branch Prefix | Commit/PR Prefix | Use Case / Description |
| :--- | :--- | :--- | :--- |
| **New Features** | `feat/` | `feat:` | Use for adding new functionality or modules to the project. |
| **Bug Fixes** | `fix/` | `fix:` | Use when repairing broken code or addressing an issue/ticket. |
| **Refactoring** | `refactor/` | `refactor:` | For code changes that neither fix a bug nor add a feature (improving structure). |
| **Documentation** | `docs/` | `docs:` | Updates to README files, inline comments, or external documentation. |
| **Styling** | `style/` | `style:` | Changes that do not affect the meaning of the code (white-space, formatting, CSS). |
| **Testing** | `test/` | `test:` | Adding missing tests or correcting existing ones. |
| **Performance** | `perf/` | `perf:` | Code changes that improve processing speed or reduce memory usage. |
| **Chores/Config** | `chore/` | `chore:` | Updating build tasks, package manager configs, or CI/CD pipelines. |

### Branch Naming Structure
```
prefix/short-description or prefix/issue-number-description
```

### Commit Message Anatomy
```
<type>: <description>

Example: feat: add camera sharing to live model
```

### PR Titles
```
[Feat] Implement NFC tag data encryption

[Fix] Resolve memory leak on dashboard refresh
```