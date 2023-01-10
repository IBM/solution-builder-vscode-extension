# solution-builder-vscode-extension
Documentation and issue hosting for IBM's Solution Builder Vscode Extension
# Getting started with IBM Cloud Solution Builder extension for Visual Studio Code

Welcome to the experimental version of IBM Cloud Solution Builder extension for Visual Studio Code. This is an experimental feature that is available for evaluation and testing purposes and might change without notice.

## About the Solution Builder extension

With the IBM Cloud Solution Builder extension for Visual Studio Code, you can customize your IBM Cloud infrastructure, service, and application stack across cloud environments.

You're building a solution that fits your organization's needs and is based on a deployable architecture. You modify your deployable architecture by adding modules and input values.

Solution Builder currently supports text editing of IBM Cloud Schematics blueprint YAML files.

### Features

- Completions: get available matching outputs when triggered on a module's input value.
- Diagnostics: reports errors in input values, such as mismatched type or no value supplied.
- Custom outline view: solution-specific outline structure highlights modules and their inputs/outputs.
- Code actions: links to the module's repository URL.
- Catalog Explorer: a list of supported Terraform modules from the IBM Terraform provider that can be used to author solutions.

### Definitions

- Solution: a combination of capabilities from one or more technologies that solves a customer-defined problem.
- Module: standalone deployable code that can be part of multiple reference architectures, used individually. This file is used to generate terraform or Schematics Blueprints for automation.
- Deployable architecture: can have one or more architecture variations, and multiple configurations for those architectures, based on the customer business needs. These architectures are opinionated, predefined, and preconfigured to meet regulated industry requirements. They can be for infrastructure, software, a workload, or a full stack.

## Installing from Mac or Linux OS

1. Extract the release zip file into a local directory. The zip file includes:
   - vsix file
   - readme file
   - shell script files
2. Open a terminal, and navigate to the directory that contains the files.
3. Give executable permissions to the script by running the following command:
   `chmod +x ./sb-install.sh`
4. Run the following command to install the Solution Builder extension into VS Code:
   `./sb-install.sh <vsix-file-name>`

If you see the following message, the extension is ready to use in VS Code: `Extension '<vsix-file-name>' was successfully installed.`

If you get a message about a missing `code` command, follow the installation instructions and retry.

If you are prompted to access modules in GitHub repos, click Skip.

## Installing from Windows OS

1. Extract the release zip file into a local directory. The zip file includes:
   - vsix file
   - readme file
   - batch script files
2. Open a command prompt, and navigate to the directory that contains the files.
3. Run the following command to install the Solution Builder extension into VS Code:
   `sb-install.bat <vsix-file-name>`
   If you get a message about a missing `code` command, follow the installation instructions and retry.
4. Confirm that you receive the following message: `Extension '<vsix-file-name>' was successfully installed.` message
5. Run `code` to open VS Code.
6. Confirm that you see the IBM Cloud Solution Builder extension in the VS Code Activity bar.

## Views when using the Solution Builder extension

### Outline view

In the Outline view, if you have a YAML section, collapse it. You'll now see the Solution section, which represents the structure of the blueprint as a solution.

If you double-click on an element in the Outline view, the cursor is placed on the relevant line of code.

### Catalog Explorer view

In the VS Code Activity bar, click the Catalog Explorer icon [<img src="https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dep.svg" height="12"/>](https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dep.svg). The Catalog Explorer view lists available modules. Use the buttons at the top to perform various actions (hover over them to see what they do).

If you expand one of the modules, the following inline icons are displayed:

[<img src="https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dark/launch_dk.png" height="12"/>](https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dark/launch_dk.png) Opens a browser page to the module's repository for documentation viewing.

[<img src="https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dark/add.png" height="12"/>](https://github.com/ibm/solution-builder-vscode-extension/blob/main/resources/dark/add.png) Pastes a snippet of that module into your blueprint.

### Problems view

The Problems view shows diagnostic information. This information can include hints, information, warnings, or error messages. Some diagnostics include associated quick fixes or code actions that are represented by a light bulb icon. Click the light bulb icon to show available actions.

