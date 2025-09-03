#### **Structuring and Writing Commit Messages**

We use the [Conventional Commits](https://www.conventionalcommits.org/) standard, which provides a clearly defined message format and enables automatic changelog generation.

- **Clarity:** Each commit should describe one specific change. Break larger modifications into smaller steps.
- **Structure:** Commit messages follow the format:
  ```
  <type>[optional scope]: <description>

  [optional detailed description]

  [optional notes]
  ```
- **Conciseness:** The first line should be short and concise (up to 50 characters).
- **Commit types:**
  - **`feat:`** - New functionality
  - **`fix:`** - Bug fix
  - **`docs:`** - Documentation changes
  - **`style:`** - Formatting, missing semicolons, etc.
  - **`refactor:`** - Code refactoring
  - **`perf:`** - Performance improvements
  - **`test:`** - Adding or modifying tests
  - **`build:`** - Build system or dependency changes
  - **`ci:`** - CI configuration changes
  - **`chore:`** - Other changes

- **Scope:** Optionally, you can add a scope in parentheses to specify which part of the project the change affects.

_Examples of correct commit messages:_

```plaintext
feat(auth): JWT authentication implementation

Adding support for JWT tokens including:
- Token generation
- Token validation
- Token refresh

BREAKING CHANGE: Change in authentication header format
```

```plaintext
fix(db): fix MongoDB connection on startup

Added retry connection on database initialization failure.
```

1. **Cloning the project:** Load the project locally using:
    
    ```bash
    git clone <repository URL>
    ```
    
2. **Regularly update your local branch:** Before starting work, make sure you have the current code:
    
    ```bash
    git checkout main
    git pull origin main
    ```
    
3. **Work on your own branch:** Each task (feature, bug fix, change) should be implemented on a separate branch.
    
    ```bash
    git checkout -b <change-type>/<short-description>
    ```
    
    For example:
    
    ```bash
    git checkout -b feature/add-login
    ```
    
4. **Commit regularly:** Each commit should contain one logical change and have a clear description:
    
    ```bash
    git add .
    git commit -m "ADD: User login implementation"
    ```
    
5. **Push changes to remote repository:** After completing changes, send your branch to GitHub:
    
    ```bash
    git push origin <branch-name>
    ```
    

### 2. **Rules for Branch and Commit Names**

#### **Branch Names:**

Use descriptive names with a prefix according to the type of change:

- **`feature/`** – For new features. _E.g.:_ `feature/add-login`
- **`bugfix/`** – For bug fixes. _E.g.:_ `bugfix/fix-login-error`
- **`update/`** – For modifications to existing features. _E.g.:_ `update/change-config-loading`

#### **Commit Descriptions:**

Start with an action (in English or Czech) and briefly describe the change:

- **`ADD:`** For adding new features.
- **`FIX:`** For bug fixes.
- **`UPD:`** For feature modifications.
- **`REFACTOR:`** For code refactoring.
- **`REMOVE:`** For removing unnecessary code.

_Example:_

```plaintext
FIX: Fixed incorrect configuration loading from config.yml
ADD: Added support for multiple configurations
UPD: Changed world loading to value from config.yml
REFACTOR: Restructured code for configuration reading
REMOVE: Removed deprecated data loading methods
```

### 3. **Merging Changes to Main Branch**

1. **Update your branch:**
    
    ```bash
    git checkout <branch-name>
    git pull origin main
    git rebase main
    ```
    
2. **Switch to main branch and merge changes:**
    
    ```bash
    git checkout main
    git merge <branch-name>
    ```
    
3. **Test main branch:** After merging changes, perform testing on the main branch to ensure all new changes work correctly and no unexpected issues occur.
    
4. **Push changes to remote repository:**
    
    ```bash
    git push origin main
    ```
    
5. **Update your branch:**
    
    ```bash
    git checkout <branch-name>
    git pull origin main
    git rebase main
    ```
    
6. **Switch to main branch and merge changes:**
    
    ```bash
    git checkout main
    git merge <branch-name>
    ```
    
7. **Push changes to remote repository:**
    
    ```bash
    git push origin main
    ```
    

### 5. **Resolving Conflicts**

If conflicts occur:

1. Git will mark conflicting files. Use the `git status` command to see which files are conflicting:
    
    ```bash
    git status
    ```
    
2. Fix conflicts manually in the marked files (look for `<<<<<<<`, `=======`, `>>>>>>>`).
    
3. After editing, verify that all conflicts are resolved using the `git status` command. Make sure no conflicting files remain.
    
4. Add the edited files:
    
    ```bash
    git add <file>
    ```
    
5. Commit the changes:
    
    ```bash
    git commit -m "Resolving conflicts for merge with main"
    ```
    

If conflicts occur:

1. Git will mark conflicting files. Fix them manually.
2. After editing, commit the changes:
    
    ```bash
    git add .
    git commit -m "Resolving conflicts for merge with main"
    ```
