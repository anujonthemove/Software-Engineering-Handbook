
## Optional VS Code Settings

VS Code settings that will enable you to automatically clean up your code as and when you save the file

```json

{
    "python.linting.enabled": true,
    "python.linting.flake8Enabled": true,
    "python.analysis.typeCheckingMode": "basic",
    "python.formatting.provider": "black",
    "editor.formatOnSaveMode": "file",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.organizeImports": true
    },
}

```


## Must install VS Code extensions for developers

1. Python: https://marketplace.visualstudio.com/items?itemName=ms-python.python
2. Flake8: https://marketplace.visualstudio.com/items?itemName=ms-python.flake8
3. iSort: https://marketplace.visualstudio.com/items?itemName=ms-python.isort
4. Jupyter: https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter
5. Pylance: https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance
6. autoDocstring: https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring
7. 

https://marketplace.visualstudio.com/items?itemName=GitHub.github-vscode-theme
https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow
https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles
https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid
https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons

https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh
https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack