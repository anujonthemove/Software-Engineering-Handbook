# ✅ **Ensuring Code Quality Before Commit**

## 📚 **Understanding Pre-commit Hooks and the Pre-commit Framework**

Pre-commit hooks are scripts that run automatically before each commit to check your code and ensure it's ready to be committed. They're a type of "hook" — a script that Git executes before or after events such as: `commit`, `push`, `checkout`, and others. Pre-commit hooks are a great way to automate and standardize checks and tests, helping to catch issues before they cause problems.

The [Pre-commit Framework](https://pre-commit.com/) is a tool that manages and maintains multi-language pre-commit hooks. It helps you manage hooks installed in your repository and makes it easier to handle and reuse configurations across projects. 

#### 👓 **Here's how it works:**

  1. You specify a list of hooks you want in the `.pre-commit-config.yaml` file in your repository.
  2. When you initialize pre-commit (using `pre-commit install`), it installs a hook script in your `.git/hooks` directory. This script will run every time you commit changes.


    !!! note
        If your `.venv` (virtual environment) is not currently active, proceed to the terminal and navigate to your project directory, activate your `.venv` according to your operating system, and then run the command `pre-commit install` to update the git hooks for your project.

When the hook script runs, it uses the configuration in your `.pre-commit-config.yaml` file to determine which hooks to run. These hooks can do things like checking syntax errors, fixing formatting issues, and even preventing commits that contain secrets.

By using pre-commit hooks and the Pre-commit Framework, you can ensure that all commits meet your project's standards and that your codebase remains clean and well-organized.


## 🕶 **Pre-configured Pre-commit Hooks in this Template**

This template comes pre-configured with several useful pre-commit hooks:

### 🌊 **Preventing Large Files from Being Committed**

This hook prevents large files (typically more than 5 MB) from being committed to Git. This is particularly useful in preventing accidental commits of large data files or model files.

```yaml

- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.0.1
  hooks:
  - id: check-added-large-files
    name: Check for large files
    description: Prevents large files from being committed
    entry: check-added-large-files
    args: [--maxkb=5120]

```

### ✨ **Auto-clearing Jupyter Notebook Cells**

In Machine Learning projects, the output of text in Jupyter cells can be very large. This hook automatically clears all the cells in a notebook before allowing them to be committed to Git.

```yaml
- repo: https://github.com/kynan/nbstripout
  rev: 0.6.1
  hooks:
    - id: nbstripout
```

## 🔌 **Optional Pre-commit Hooks**

While the following hooks are not implemented by default, it is highly recommended as they can ensure your code conforms to PEP8 standards.

### 🔥 **Auto-formatting Python Code**

This hook automatically formats your Python code to adhere to PEP8 standards.


```yaml

- repo: https://github.com/psf/black
  rev: 22.6.0
  hooks:
    - id: black
    - id: black-jupyter
      language_version: python3

```
### 🌈 **Sort all your Python imports**

```yaml

- repo: https://github.com/pycqa/isort
  rev: 5.10.1
  hooks:
    - id: isort
      name: isort (python)
```


### 🧭 **Detecting Secrets in Code with Pre-commit Hook**

This pre-commit hook uses the [Detect Secrets](https://github.com/Yelp/detect-secrets) tool to prevent committing any kind of sensitive information unintentionally. It scans all files before each commit and compares them with a baseline to ensure no secrets are being committed.

```yaml
- repo: https://github.com/Yelp/detect-secrets
  rev: v1.3.0
  hooks:
    - id: detect-secrets
      name: Detect Secrets
      language: python
      args: ['--baseline', '.secrets.baseline']

```

### ✂️ **Code Formatting and Upgrade for Jupyter Notebooks**

This pre-commit hook uses the `nbQA` tool to run Python tools on Jupyter Notebooks. It includes hooks for Black (for code formatting), pyupgrade (for upgrading code to use the latest Python features), and isort (for sorting imports).

This is directly taken from [offical nbQA documentation](https://nbqa.readthedocs.io/en/latest/pre-commit.html)

```yaml
- repo: https://github.com/nbQA-dev/nbQA
  rev: 1.7.0
  hooks:
   - id: nbqa-black
     additional_dependencies: [black==20.8b1]
   - id: nbqa-pyupgrade
     additional_dependencies: [pyupgrade==2.7.3]
   - id: nbqa-isort
     additional_dependencies: [isort==5.6.4]


```

These pre-commit hooks help to maintain the quality of your code and notebooks, ensuring they are clean, readable, and free from sensitive information.


In order to install additional hooks like the few stated above, please follow the above [steps](#heres-how-it-works)

Checkout the [pre-commit framework ](https://pre-commit.com/) for more details!