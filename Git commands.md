Here's a practical Git command reference that covers the most commonly used commands, including branching, merging, renaming branches, remotes, stashing, tags, undo operations, and more.

# 1. Repository Setup

### Initialize a new repository


git init


**When used:** Start version control in an existing project folder.

---

### Clone a repository


git clone <repository-url>


Example:


git clone https://github.com/user/project.git


**When used:** Copy an existing repository from GitHub, GitLab, etc.

---

# 2. Checking Repository Status

### View current status


git status


**When used:** See modified, staged, and untracked files.

---

### View commit history


git log


**When used:** Show commit history.

Useful variants:


git log --oneline
git log --graph --all --decorate


---

### See differences


git diff


**When used:** View unstaged changes.


git diff --staged


**When used:** View staged changes.

---

# 3. Adding Files

### Add a specific file


git add file.txt


**When used:** Stage a particular file.

---

### Add all files


git add .


**When used:** Stage all modified and new files.

---

### Add everything including deletions


git add -A


**When used:** Stage all changes.

---

# 4. Committing Changes

### Commit staged files


git commit -m "message"


**When used:** Save staged changes.

---

### Add and commit tracked files


git commit -am "message"


**When used:** Quickly commit modified tracked files.

---

### Amend last commit


git commit --amend


**When used:** Modify the latest commit.

---

# 5. Branch Operations

### Create a branch


git branch feature-login


**When used:** Create a new branch.

---

### List branches


git branch


**When used:** View local branches.


git branch -a


**When used:** View local and remote branches.

---

### Switch branch


git checkout feature-login


or


git switch feature-login


**When used:** Move to another branch.

---

### Create and switch branch


git checkout -b feature-login


or


git switch -c feature-login


**When used:** Create and switch in one command.

---

### Rename current branch


git branch -m new-name


**When used:** Rename the branch you're currently on.

---

### Rename another branch


git branch -m old-name new-name


**When used:** Rename a different branch.

---

### Delete local branch


git branch -d feature-login


**When used:** Delete merged branch.

---

### Force delete branch


git branch -D feature-login


**When used:** Delete branch even if unmerged.

---

# 6. Merge Operations

### Merge a branch


git merge feature-login


**When used:** Merge `feature-login` into current branch.

Example:


git checkout main
git merge feature-login


---

### Fast-forward merge


git merge --ff feature-login


**When used:** Keep linear history when possible.

---

### No fast-forward merge


git merge --no-ff feature-login


**When used:** Always create a merge commit.

---

### Abort merge


git merge --abort


**When used:** Cancel merge after conflicts.

---

# 7. Rebase Operations

### Rebase current branch


git rebase main


**When used:** Replay commits on top of main.

---

### Interactive rebase


git rebase -i HEAD~3


**When used:** Edit, squash, reorder commits.

---

### Continue rebase


git rebase --continue


**When used:** After resolving conflicts.

---

### Abort rebase


git rebase --abort


**When used:** Cancel rebase.

---

# 8. Remote Repository Commands

### View remotes


git remote -v


**When used:** Show remote URLs.

---

### Add remote


git remote add origin <url>


**When used:** Connect repository to remote.

---

### Change remote URL


git remote set-url origin <new-url>


**When used:** Update remote repository URL.

---

### Remove remote


git remote remove origin


**When used:** Delete remote reference.

---

# 9. Push Commands

### Push current branch


git push origin main


**When used:** Upload commits.

---

### Push new branch


git push -u origin feature-login


**When used:** First push and set upstream.

---

### Force push


git push --force


**When used:** Overwrite remote history.

Safer:


git push --force-with-lease


---

# 10. Pull Commands

### Pull latest changes


git pull


**When used:** Fetch + merge.

---

### Pull specific branch


git pull origin main


**When used:** Pull from a specific branch.

---

### Pull with rebase


git pull --rebase


**When used:** Keep cleaner history.

---

# 11. Fetch Commands

### Fetch remote updates


git fetch


**When used:** Download changes without merging.

---

### Fetch all remotes


git fetch --all


**When used:** Update all remotes.

---

# 12. Stash Commands

### Save current changes


git stash


**When used:** Temporarily store uncommitted work.

---

### Stash with message


git stash push -m "work in progress"


---

### View stashes


git stash list


---

### Restore latest stash


git stash pop


---

### Apply stash without deleting


git stash apply


---

### Delete stash


git stash drop stash@{0}


---

# 13. Undo Operations

### Unstage file


git restore --staged file.txt


**When used:** Remove file from staging.

---

### Discard local changes


git restore file.txt


**When used:** Revert file to last commit.

---

### Reset last commit (keep changes)


git reset --soft HEAD~1


**When used:** Undo commit but keep changes staged.

---

### Reset commit and unstage changes


git reset --mixed HEAD~1


---

### Delete commit and changes


git reset --hard HEAD~1


**Warning:** Data loss possible.

---

# 14. Cherry-Pick

### Pick a commit


git cherry-pick <commit-hash>


**When used:** Apply a commit from another branch.

---

# 15. Tags

### Create tag


git tag v1.0


---

### Annotated tag


git tag -a v1.0 -m "Version 1.0"


---

### List tags


git tag


---

### Push tag


git push origin v1.0


---

### Push all tags


git push --tags


---

# 16. Viewing Information

### Show commit details


git show


---

### Show branch history graph


git log --oneline --graph --decorate --all


---

### Show file changes by author


git blame file.txt


---

# 17. Rename Main Branch Example

Rename `master` to `main`:


git branch -m master main


Push new branch:


git push -u origin main


Delete old remote branch:


git push origin --delete master


Update remote HEAD:


git remote set-head origin main


---

# 18. Useful Daily Workflow

### Create feature branch


git checkout -b feature-auth


### Make changes

### Stage changes


git add .


### Commit


git commit -m "Add login functionality"


### Push branch


git push -u origin feature-auth


### Merge into main


git checkout main
git pull
git merge feature-auth
git push origin main


### Delete feature branch


git branch -d feature-auth


---

# 19. Git Conflict Resolution

When merge conflict occurs:


git merge feature-auth


Resolve files manually.

Then:


git add .
git commit


Or abort:


git merge --abort


---

# 20. Most Important Commands to Memorize


git init
git clone
git status
git add .
git commit -m "message"
git push
git pull
git fetch
git branch
git checkout -b branch-name
git switch branch-name
git merge branch-name
git rebase main
git stash
git log --oneline
git reset --hard HEAD~1
git cherry-pick commit-id
git tag


These cover roughly 90–95% of day-to-day Git work in professional development.

