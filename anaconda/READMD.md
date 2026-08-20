# Anaconda & Spyder IDE

## Dowload Anaconda (Including Spyder IDE)

1. Go to https://www.anaconda.com/download/success?reg=skipped
2. Skip Registration
3. Choose `Anaconda Distribution`

## Install Anaconda

1. Run the downloaded `Anaconda3-xxxx.xx-x-MacOSX-arm64.pkg` file
2. **IMPORTANT!!!** In **Installation Type**,
    - Check `Create shortcuts`
    - Uncheck `Add conda initialization` (IMPORTANT)
3. Install

## Setup VS Code Extensions

### 1. Install Extensions

1. Install [Python Data Science Extension Pack](vscode:extension/ms-toolsai.python-ds-extension-pack)

### 2. Disable the Extensions by Default

1. **Disable** [Python Data Science Extension Pack](vscode:extension/ms-toolsai.python-ds-extension-pack) (globally)
2. Enable [Python](ms-python.python) (globally)
    - so that [Python](ms-python.python) can work normally in other workspaces

### 3. Enable the Extensions Only in Target Workspace

1. Open a target Anaconda workspace
2. Enable [Python Data Science Extension Pack](vscode:extension/ms-toolsai.python-ds-extension-pack) (**for workspace only**)
    1. Open [Python Data Science Extension Pack](vscode:extension/ms-toolsai.python-ds-extension-pack) page
    2. Click the **dropdown menu** of `Enable`
    3. Click `Enable (Workspace)`

### 4. Setup Shortcuts

1. Press `Command + Shift + P`
2. Enter `Preferences: Open Keyboard Shortcuts (JSON)`
3. Paste the [following config](/vscode/keybindings.json) in this file
    ```json
    // Place your key bindings in this file to override the defaults
    [
        {
            "key": "shift+enter",
            "command": "jupyter.runFileInteractive",
            "when": "editorTextFocus && config.anacondaWorkspace.enabled"       // This allows the shortcut only works in anaconda workspace
        }
    ]
    ```
4. In workspace [.vscode/settings.json](.vscode/settings.json), add the following config or copy and past the file [settings.json](.vscode/settings.json)
    ```json
    {
        "python-envs.defaultEnvManager": "ms-python.python:conda",
        "python-envs.defaultPackageManager": "ms-python.python:conda",
        "anacondaWorkspace.enabled": true           // For Shift + Return shortcut
    }
    ```
5. Add [.vscode/launch.json](.vscode/launch.json) with the following config
    ```json
    {
        // Use IntelliSense to learn about possible attributes.
        // Hover to view descriptions of existing attributes.
        // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Python: Current File",
                "type": "debugpy",
                "request": "launch",
                "program": "${file}",
                "console": "integratedTerminal",
                "justMyCode": true
            }
        ]
    }
    ```