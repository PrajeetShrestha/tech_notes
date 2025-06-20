# Basic Git Commands Reference

Git is a powerful version control system that helps you track changes in your code, collaborate with others, and manage different versions of your projects. This guide covers the most fundamental Git commands you'll use daily.

## Setting Up & Initializing

* **`git init`**

  * **Purpose:** Initializes a new Git repository in the current directory. This creates a hidden `.git` folder that Git uses to track changes.

  * **Example:**

    ```
    git init
    
    ```

    *Output:* `Initialized empty Git repository in /path/to/your/project/.git/`

* **`git clone [repository_url]`**

  * **Purpose:** Copies an existing Git repository from a remote location (like GitHub) to your local machine.

  * **Example:**

    ```
    git clone [https://github.com/octocat/Spoon-Knife.git](https://github.com/octocat/Spoon-Knife.git)
    
    ```

## Saving Changes

* **`git status`**

  * **Purpose:** Shows the current state of your working directory and staging area. It tells you which files are untracked, modified, or staged for commit.

  * **Example:**

    ```
    git status
    
    ```

    *Output (example for modified and untracked files):*

    ```
    On branch master
    Your branch is up to date with 'origin/master'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
        style.css
    
    ```

* **`git add [file_name]`** or **`git add .`**

  * **Purpose:** Stages changes for the next commit. `git add .` stages all changes in the current directory and its subdirectories.

  * **Stage a specific file:**

    ```
    git add index.html
    
    ```

  * **Stage all changes:**

    ```
    git add .
    
    ```

* **`git commit -m "Your commit message"`**

  * **Purpose:** Records the staged changes to the repository's history as a new snapshot (commit). The `-m` flag allows you to provide a short, descriptive message.

  * **Example:**

    ```
    git commit -m "Add initial HTML structure and styles"
    
    ```

## Viewing History & Undoing

* **`git log`**

  * **Purpose:** Shows a history of all commits in the current branch, including author, date, and commit message.

  * **Example:**

    ```
    git log
    
    ```

  * **Compact view:**

    ```
    git log --oneline
    
    ```

* **`git restore [file_name]`**

  * **Purpose:** Discards changes in your working directory, reverting a file to its last committed state.

  * **Example:**

    ```
    git restore index.html
    
    ```

  * **Unstage a file (move from staging area back to working directory):**

    ```
    git restore --staged index.html
    
    ```

## Remote Repositories

* **`git remote -v`**

  * **Purpose:** Lists the remote repositories that your local repository is connected to.

  * **Example:**

    ```
    git remote -v
    
    ```

    *Output:*

    ```
    origin  [https://github.com/youruser/your-repo.git](https://github.com/youruser/your-repo.git) (fetch)
    origin  [https://github.com/youruser/your-repo.git](https://github.com/youruser/your-repo.git) (push)
    
    ```

* **`git push [remote_name] [branch_name]`**

  * **Purpose:** Uploads your local commits to a remote repository. `origin` is the default remote name, and `main` or `master` are common branch names.

  * **Example:**

    ```
    git push origin main
    
    ```

* **`git pull [remote_name] [branch_name]`**

  * **Purpose:** Downloads changes from a remote repository and integrates them into your current local branch. This is a combination of `git fetch` and `git merge`.

  * **Example:**

    ```
    git pull origin main
    
    ```

## Branching

* **`git branch`**

  * **Purpose:** Lists all local branches in your repository. The current branch is typically highlighted (e.g., with an asterisk).

  * **Example:**

    ```
    git branch
    
    ```

    *Output:*

    ```
      feature-x
    * main
      development
    
    ```

* **`git branch [new_branch_name]`**

  * **Purpose:** Creates a new local branch. This command *does not* switch you to the new branch.

  * **Example:**

    ```
    git branch new-feature
    
    ```

* **`git checkout [branch_name]`** or **`git switch [branch_name]`**

  * **Purpose:** Switches your working directory to a different branch. `git switch` is a more modern alternative introduced in Git 2.23.

  * **Switch to an existing branch:**

    ```
    git checkout development
    # or
    git switch development
    
    ```

  * **Create a new branch and switch to it immediately:**

    ```
    git checkout -b new-feature-branch
    # or
    git switch -c new-feature-branch
    
    ```

* **`git merge [branch_to_merge]`**

  * **Purpose:** Integrates changes from one branch into your current branch.

  * **Example (assuming you are on `main` and want to merge `feature-branch` into `main`):**

    ```
    git checkout main
    git merge feature-branch
    
    ```

    This will apply all changes from `feature-branch` to your `main` branch.