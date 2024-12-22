
### **Comprehensive Git Reference Notes**

---

### **Basic Git Commands**

1. **`git status`**
    
    Displays the status of your repository, including staged, unstaged, and untracked files.
    
2. **`git init`**
    
    Initializes a new Git repository in your project directory.
    
3. **`git --version`**
    
    Displays the installed Git version.
    
4. **`git add filename`**
    
    Stages a specific file to the staging area.
    
5. **`git add .`**
    
    Stages all the changes (new, modified, deleted files) in the current directory for commit.
    
6. **`git commit -m "Message"`**
    
    Creates a new commit with the staged changes and a descriptive message.
    

---

### **Useful Shell Commands**

1. **`ls -la`**

    Lists all files and directories, including hidden ones like `.git`.

---

### **Git Concepts**

1. **HEAD**
    
    The `HEAD` pointer represents the current branch or commit you're working on. Initially, it's on the `master` or `main` branch.
    
2. **Master/Main Branch**
    
    The default branch created in a Git repository. Newer Git versions often use `main` instead of `master`.
    
3. **Staging Area**
    
    A temporary area where changes are added before committing them to the repository.
    
4. **Atomic Commits**
    
    Commits that focus on a single purpose or change, ensuring a clear and meaningful commit history.
    

---

### **Ignoring Files**

1. **`.gitignore` File**
    
    Specifies files and directories to be ignored by Git (e.g., `node_modules/`, `.env`).
    
2. **`.env` File**
    
    Used for storing environment variables and secrets like API keys. Always include `.env` in your `.gitignore`.
    
3. **Git Ignore Generator**
    
    Tools like [gitignore.io](https://gitignore.io/) help generate `.gitignore` files for specific programming languages and frameworks.
    

---

### **Viewing and Configuring Commits**

1. **`git log`**
    
    Shows the commit history with details like commit hash, author, date, and message.
    
2. **Git Hashing**
    
    Git generates a unique hash (SHA-1) for every commit, ensuring consistency and integrity of commit history.
    
3. **`git config --global user.email "email@example.com"`**
    
    Sets the global email address for your Git commits.
    
4. **`git config --global user.name "Your Name"`**
    
    Sets the global username for your Git commits.
    
5. **`git config --global core.editor "code --wait"`**
    
    Configures Visual Studio Code as the default Git editor.
    

---

### **Exploring the `.git` Folder**

- The `.git` folder contains all the data related to your repository, including commit history, configuration, branches, and objects.
- Important files:
    - `HEAD`: Points to the current branch.
    - `config`: Repository configuration.
    - `objects/`: Stores all objects (commits, trees, blobs).

---

### **Git Branch Basics**

1. **What is a Branch?**
    
    A branch is a lightweight, movable pointer to a commit. By default, every repository starts with a `master` or `main` branch. Branches enable parallel development and experimentation without affecting the main codebase.
    
2. **Head Pointer**
    
    The `HEAD` pointer indicates the current branch you’re working on and always points to the latest commit of the current branch.
    
3. **Creating Multiple Branches**
    
    You can create multiple branches using the `git branch` command and switch between them for isolated development.
    

---

### **Branch Management Commands**

1. **`git branch`**
    
    Lists all branches in your repository. The current branch is marked with an asterisk (`*`).
    
2. **`git branch branch-name`**
    
    Creates a new branch called `branch-name`.
    
3. **`git switch branch-name`**
    
    Switches to an existing branch called `branch-name`.
    
4. **`git switch -c branch-name`**
    
    Creates and switches to a new branch called `branch-name`.
    
5. **`git checkout -b branch-name`**
    
    Creates a new branch and switches to it (alternative to `git switch -c`).
    
6. **`git switch main`**
    
    Switches back to the `main` branch.
    

---

### **Merging Branches**

1. **Merging Basics**
    
    Merging combines changes from one branch into another. Always switch to the branch you want to merge *into* before merging.
    
2. **Fast-Forward Merge**
    
    Occurs when there are no divergent changes between the branches. The branch pointer is simply moved forward to the latest commit.
    
    ```bash
    git merge branch-name
    ```
    
3. **Non-Fast-Forward Merge**
    
    Happens when branches have diverging changes. Git creates a new merge commit to combine changes.
    
4. **Conflict Resolution**
    
    Git tries to auto-resolve conflicts but may require manual intervention for conflicting files.
    
    ```bash
    git add filename
    git commit
    ```
    

---

### **Rebasing**

1. **What is Rebasing?**
    
    Rebasing is an alternative to merging that moves a branch to a new base commit. It rewrites commit history for a cleaner, linear timeline.
    
2. **Basic Rebase Command**
    
    ```bash
    git rebase branch-name
    ```
    
3. **Interactive Rebase**
    
    Allows you to squash, reword, or edit commits during a rebase.
    
    ```bash
    git rebase -i HEAD~n
    ```
    
    Replace `n` with the number of commits you want to edit.
    
4. **Avoid Rebasing on Public Branches**
    
    Rebasing rewrites history, which can cause conflicts if others are working on the same branch.
    
5. **Conflict Resolution in Rebase**
    
    If conflicts occur during a rebase, resolve them, then run:
    
    ```bash
    git rebase --continue
    ```
    

---

### **Stashing Changes**

1. **`git stash`**
    
    Saves your uncommitted changes and reverts your working directory to the last commit.
    
2. **`git stash list`**
    
    Lists all stashed changes.
    
3. **`git stash pop`**
    
    Applies the most recent stash and removes it from the stash list.
    
4. **`git stash apply`**
    
    Applies the most recent stash without removing it from the stash list.
    

---

### **Advanced Git Commands**

1. **`git reflog`**
    
    Shows a log of all references in the repository, including HEAD changes.
    
2. **`git reset --hard`**
    
    Resets the working directory and staging area to the last commit, discarding all changes.
    
3. **`git clean -fd`**
    
    Removes untracked files and directories.
    
4. **`git cherry-pick <commit-hash>`**
    
    Applies the changes from a specific commit to the current branch.
    
5. **`git bisect`**
    
    Helps find the commit that introduced a bug by performing a binary search through commit history.
    

---

### **Visualisation Tools**

1. **`git log --oneline --graph --all`**
    
    Displays a graphical view of commit history.
    
2. **GUI Tools**
    
    Use tools like GitKraken, Sourcetree, or the built-in Git tools in IDEs like VS Code.
