# IBM Cloud Solution Editor <sup>Beta</sup>

IBM Cloud Solution Editor extension for [Visual Studio Code](https://code.visualstudio.com/) helps you customize your [IBM Cloud](https://cloud.ibm.com) infrastructure by providing syntax highlighting, linting, module management, and code completion for your deployable architecture.

This is an experimental feature that is available for evaluation and testing purposes and might change without notice.

Use this extension to build and customize your deployable architecture by editing your blueprint YAML file and adding modules and input values. Solution Editor currently supports text editing of IBM Cloud Schematics blueprint YAML files.

## Prerequisites
- If you prefer to use keyboard shortcuts in VS Code, see the following references:
   - [MacOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)
   - [Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)
   - [Microsoft Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)

## Features

- Completions: get available matching outputs when triggered on a module's input value.
- Custom Outline view: solution-specific outline structure highlights modules with their inputs and outputs.
- Code Actions: links to the module's repository URL.
- Catalog Explorer view: a list of supported Terraform modules from the IBM Terraform provider that can be used to author solutions.
- Diagnostics: reports errors in input values, such as mismatched type or no value supplied.
- Debug logging: logs are located in the Output panel.

## Definitions

- Solution: a combination of capabilities from one or more technologies that solves a customer-defined problem.
- Module: standalone deployable code that can be part of multiple reference architectures, used individually. This file is used to generate Terraform or Schematics Blueprints for automation.
- Deployable architecture: can have one or more architecture variations, and multiple configurations for those architectures, based on the customer business needs. These architectures are opinionated, predefined, and preconfigured to meet regulated industry requirements. They can be for infrastructure, software, a workload, or a full stack.

## Getting started with your blueprint YAML

1. Locally clone the repos that contain your blueprint YAML source files.
1. In VS Code, click the **Explorer** icon, or select **View** > **Explorer**.
1. Open the local folder that contains the blueprint YAML file.
1. Open your blueprint YAML file.
1. In the File Explorer, open the **Outline** view.
1. In the **Solution** section, double-click an element in the **Outline** view. The cursor is placed on the corresponding line of code in the blueprint YAML file.

The **Solution** section represents the structure (symbol tree) of the blueprint YAML file.

## Adding modules to your blueprint

1. View modules by clicking the **IBM Cloud Solution Editor** icon [<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dep.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dep.png) in the Activity Bar. Each module has additional metadata that Solution Editor reads and displays.
1. Use the buttons in the catalog explorer view to perform various actions (hover over them to see what they do). For example, Refresh, Search, Reset, Expand, and Collapse.
1. When you expand or hover over a module name, click either of the following icons:
   [<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/launch_dk.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/launch_dk.png) Opens a browser page to the module's repository for viewing its documentation.
   [<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/add.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/add.png) Pastes a full snippet of the selected module into the end of your YAML file.
1. Press **Ctrl+Space** to show completions, which are a list of Inputs and Values that work in a specific “value” field.

## Creating an empty blueprint

This feature creates a YAML file with a outline of a blueprint.

You can create an empty blueprint in the following ways:
- Select **File** > **New File** > **Create an empty blueprint**.
- Use the [Command Palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette) (select **View** > **Command Palette**), and then select **Create an empty blueprint**. (Shortcut keys - MacOS: **Shift**+**Command**+**P**, Windows and Linux: **Ctrl**+**Shift**+**P**)

You must save the file before you can use the editor features.

## Inserting a Terraform module snippet into a blueprint

You provide a GitHub repository URL to a Terraform module, and the snippet is pasted into an open blueprint. The snippet contains all the module's variables as inputs and all the outputs with associated metadata. This option works only if you have a blueprint YAML file open and active.

Use the [Command Palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette) (select **View** > **Command Palette**), and then select **Insert a Terraform module snippet into a blueprint**.

## Troubleshooting your code

The IBM Cloud Solution Editor extension uses Code Actions, Quick Fixes, and squiggly lines to guide you to issues in your code that you need to fix.

After you enable the Solution Editor extension in VS Code, any time you open a blueprint YAML file in VS Code, the extension automatically checks the file for any coding issues. The problematic code is underlined with a squiggly line, which you can hover over to see more details about what the problem is and how to fix it. Different colors of squiggly lines indicate the type of problem:
- Yellow for warnings
- Red for errors
- Blue for informational diagnostics

VS Code also highlights the warnings in a few other places throughout the editor:
- In the topic minimap, you can see a preview of where warnings appear throughout your file.
- The number of warnings in the topic is displayed in the tab for the editor window and the workspace file explorer.
- The total number of warnings across all of the open editors is displayed in the VS Code status bar at the bottom of the editor.
- The Problems view shows diagnostic information. This information can include hints, information, warnings, or error messages. Some diagnostics include associated Quick Fixes or Code Actions that are represented by a lightbulb icon. Click the lightbulb icon to show available actions.

### Using Code Actions

If a Code Action or Quick Fix is available, a yellow lightbulb icon appears when you hover over the warning in your file.

To use a specific Code Action or Quick Fix, click the lightbulb icon and select an action, such as `Select the first available matching output` or `Learn more about the <module name> module…`.

The `Learn more` Quick Fix opens a browser window that redirects you to the public GitHub repository for that specific module. If VS Code prompts you to consent to opening the web page before redirecting you, click Open.

To pop up a menu of Quick Fix suggestions, use these keyboard shortcuts:
- MacOS: **Command**+**.**
- Windows and Linux: **Ctrl**+**.**

### Accessing log files

Logs are located in the Output panel. To open the Output panel, click **View** > **Output** (Shift+Command+U).

From the output channel dropdown, select the following logs:

- For client logs, select **IBM Cloud Solution Editor**.
- For language server and SDK logs, select **IBM Cloud Solution Editor Language Server**.

You can change the log level by using `Developer: Set Log Level...` in the Command Palette (**View** > **Command Palette**).

This extension also creates logs in the file system:
- `$HOME/.ibm-se-*.log` for MacOS and Linux
- `%AppData%\.ibm-se-*.log` for Windows
