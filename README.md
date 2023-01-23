# IBM Cloud Solution Builder <sup>Beta</sup>

IBM Cloud Solution Builder extension for [Visual Studio Code](https://code.visualstudio.com/) helps you customize your IBM Cloud infrastructure, service, and application stack across cloud environments. This is an experimental feature that is available for evaluation and testing purposes and might change without notice.

Solution Builder currently supports text editing of IBM Cloud Schematics blueprint YAML files.

Solution Builder helps you build and customize a solution that is based on a deployable architecture. You customize your deployable architecture by editing your blueprint YAML file and adding modules and input values.

## Features

- Completions: get available matching outputs when triggered on a module's input value.
- Diagnostics: reports errors in input values, such as mismatched type or no value supplied.
- Custom outline view: solution-specific outline structure highlights modules with their inputs and outputs.
- Code actions: links to the module's repository URL.
- Catalog Explorer: a list of supported Terraform modules from the IBM Terraform provider that can be used to author solutions.

## Definitions

- Solution: a combination of capabilities from one or more technologies that solves a customer-defined problem.
- Module: standalone deployable code that can be part of multiple reference architectures, used individually. This file is used to generate terraform or Schematics Blueprints for automation.
- Deployable architecture: can have one or more architecture variations, and multiple configurations for those architectures, based on the customer business needs. These architectures are opinionated, predefined, and preconfigured to meet regulated industry requirements. They can be for infrastructure, software, a workload, or a full stack.

## Guide

The following instructions assume that you already have a repo that contains your blueprint YAML file and that you cloned it locally.

- In VS Code, open your blueprint YAML file.
- Add modules by clicking the Catalog Explorer icon in the Activity Bar. The Catalog Explorer lists all the modules from [TechZone Deployer](https://modules.cloudnativetoolkit.dev/).
- Press Ctrl+Space to show completions, which are a list of Inputs and Values that will work in a specific “value” field.
- Each module has additional metadata that Solution Builder reads and displays.
- The edit icon “Insert Module Snippet” adds a full module snippet with blank value fields into the end of the YAML file.

### Viewing the Solution section of your YAML file

Use the Outline view to see the Solution section on your blueprint YAML file.

Collapse all sections in the Outline view except for the Solution section. The Solution section represents the structure of the blueprint as a solution.

If you double-click on an element in the Outline view, the cursor is placed on the relevant line of code.

### Viewing available modules

Use the Catalog Explorer view to view lists of available modules.

In the VS Code Activity bar, click the Catalog Explorer icon [<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dep.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dep.png).

Use the buttons at the top to perform various actions (hover over them to see what they do). For example, refresh, search, expand, and collapse.

If you expand one of the modules, the following inline icons are displayed:

[<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/launch_dk.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/launch_dk.png) Opens a browser page to the module's repository for viewing its documentation.

[<img src="https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/add.png" height="12"/>](https://raw.githubusercontent.com/IBM/solution-builder-vscode-extension/main/resources/dark/add.png) Pastes a snippet of that module into your blueprint.

## Troubleshooting

This extension uses quick fixes and squiggly lines to guide you to issues in your code that you need to fix.

After you enable the Solution Builder extension in VS Code, any time you open a blueprint YAML file in VS Code, the extension automatically checks the file for any coding issues. The problematic code is underlined with a squiggly line, which you can hover over to see more details about what the problem is and how to fix it. Different colors of squiggly lines indicate the type of problem:
- Yellow for warnings
- Red for errors
- Blue for informational diagnostics are blue

VS Code also highlights the warnings in a few other places throughout the editor:
- In the topic minimap, you can see a preview of where warnings appear throughout your file.
- The number of warnings in the topic is displayed in the tab for the editor window and the workspace file explorer.
- The total number of warnings across all of the open editors is displayed in the VS Code status bar at the bottom of the editor.
- The Problems view shows diagnostic information. This information can include hints, information, warnings, or error messages. Some diagnostics include associated quick fixes or code actions that are represented by a light bulb icon. Click the light bulb icon to show available actions.

### Applying quick fixes

If a quick fix is available, a yellow lightbulb icon will appear when you hover over the warning in your file.

To apply the specific quick fix, click the icon and select an action, such as `Select the first available matching output` or `Learn more about the <module name> module…`.

The `Learn more` quick fix opens a browser window that redirects you to the public GitHub repository for that specific module. If VS Code prompts you to consent to opening the web page before redirecting you, click Open.

To pop up a menu of quick fix suggestions, use these keyboard shortcuts:
- For Mac iOS, use Command+.  to pop up a menu of quick fix suggestions.
- For Windows, use Ctrl+..
