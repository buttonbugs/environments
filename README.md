# Environments

This repository includes the environment setup instructions for common environments as well as their corresponding vscode configuration files (e.g., `launch.json`, `task.json`) and git configuration files (e.g., `.gitignore`, `.gitattributes`).

## How to Add Visual Studio Code `code` command to PATH on Mac

1. Open **Visual Studio Code**
2. Open the **Command Palette** by pressing `Cmd + Shift + P`
3. Type and select `Shell Command: Install 'code' command in PATH`
4. Restart terminal

## How to Add Tracked Files to `.gitignore`

1. Add files to `.gitignore`
2. Clear the files from Git cache
    ```bash
    git rm --cached <filename>
    ```

## Common Git Configuration

```bash
# Ignore file execution permission changes
git config --global core.fileMode false
git config --unset core.filemode

# Use nano as commit message editor
core.editor=nano
```