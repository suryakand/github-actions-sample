# Publish a VS Code Extension to VS Code Marketplace
This is a demo VS Code Extension project that leverage a custom GitHub action to publish the VS Code Extension to MicroSoft Visual Code marketplace. The goal of this project is to showcase the use of custom GitHub action and how it make it easy to build, test and publish extension.

Link to Custom GitHub action: [VS Code Extension Publisher - GitHub Action](https://github.com/suryakand/vscode-extension-publisher)

Read more about the custom GitHub action: [Detail of GitHub Action](https://github.com/suryakand/vscode-extension-publisher)

## Features of the custom GitHub Action

- 🏗️ **Build & Test**: Automatically builds and tests your extension
- 📦 **Package**: Creates VSIX files for distribution
- 🚀 **Publish**: Publishes to VS Code Marketplace
- 🏷️ **Versioning**: Automatic or manual version bumping
- 📋 **Artifacts**: Uploads VSIX files as GitHub artifacts
- 🎯 **Releases**: Creates GitHub releases automatically
- ⚙️ **Flexible**: Supports multiple package managers and custom scripts

## Getting Started
Below instructions will help you undertand and test drive the GitHub action to publish a VS Code Extension to marketplace.

Start by cloning the repository and follow below steps to see the custom "GitHub Action" in action:

- Clone the repo
- Review the `build.yml` and `publish.yml` Github Action scripts in `.github/workflow` folder
    - `build.yml` is configured to test and build the extension when changes are pushed to `develop` or `feature/<your branch name>` branch
    - `publish.yml` is configured to run only on `main` branch. This script will test, build and publish the extension to MicroSoft Visual Code marketplace
- Change the `publisher` attribute in the `package.json` to match with your MicroSoft Visual Code marketplace publisher ID
- Create a branch `develop` or `feature/<your branch name>`
- Make any small change (e.g. update message in `src/extension.ts`)
- Push the changes to Git repo
- When a change pushed to either `develop` or `feature/<your branch name>` branch the build job will trigger
- When a change pushed to `main` branch the publish job will trigger. The publish job will do following:
    - Test
    - Build
    - Create a Git Tag
    - Create a Release 
    - Upload a build artificat to Github artifactory
    - Publish VS Code Extension to marketplace

Refer the documentaton of the [VS Code Extension Publisher - GitHub Action](https://github.com/suryakand/vscode-extension-publisher) to learn more about configuration options and example script for build and publish tasks.