
## ⚡ Pre-commit hook for auto formatting python code 

```yaml

repos:
  - repo: https://github.com/psf/black
    rev: 22.6.0
    hooks:
      - id: black
      - id: black-jupyter
        # It is recommended to specify the latest version of Python
        # supported by your project here, or alternatively use
        # pre-commit's default_language_version, see
        # https://pre-commit.com/#top_level-default_language_version
        language_version: python3
```