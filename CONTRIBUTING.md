# Contributing

This project will welcome contributions and suggestions in the near future.

Once this project is ready to welcome contributions and suggestions:  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit <https://cla.opensource.microsoft.com>.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

## Setting Up Local Dev Environment

Windows, macOS or Linux:

- [Node.js LTS (currently v18+)](https://nodejs.org/en/download/)
- gulp CLI: ```npm install -g gulp-cli```
- [git](https://git-scm.com/downloads)
- [VS Code](https://code.visualstudio.com/Download) or your different favorite editor
- recommended VSCode extensions:
  - [EditorConfig for VS Code (editorconfig.editorconfig)](https://github.com/editorconfig/editorconfig-vscode)
  - [ESLint (dbaeumer.vscode-eslint)](https://github.com/Microsoft/vscode-eslint)
  - [GitLens (eamodio.gitlens)](https://github.com/eamodio/vscode-gitlens)
  - [markdownlint (davidanson.vscode-markdownlint)](https://github.com/DavidAnson/vscode-markdownlint)
- TEMPORARY:
  - Create a PAT for the Azure DevOps org ```msazure``` with scope: package(read) and add it as local environment variable.
  ```Powershell
  [Environment]::SetEnvironmentVariable('AZ_DevOps_Read_PAT', '<yourPAT>', [EnvironmentVariableTarget]::User)
  ```

## Build and Run

Clone, restore modules, build and run:

```bash
git clone https://github.com/microsoft/powerplatform-vscode.git pp-vscode
cd pp-vscode
npm ci
gulp ci
```

## Opening in VS Code

1. Open VS Code
2. Go to **File > Open Folder...** and select the cloned `pp-vscode` folder
3. VS Code will prompt you to install recommended extensions - click **Install All**
4. Open the integrated terminal (**Terminal > New Terminal**) and run:
   ```bash
   npm ci
   gulp ci
   ```

## Debugging the Extension

To locally debug the extension:

1. Open the Run and Debug view (**View > Run** or `Ctrl+Shift+D`)
2. Select **"Launch VSCode Extension"** from the dropdown at the top
3. Press **F5** or click the green play button

This will open a new VS Code window (Extension Development Host) with the extension loaded. You can set breakpoints in the TypeScript source files and debug the extension code.

### Available Debug Configurations

- **Launch VSCode Extension**: Debug the main desktop extension
- **Run Web Extension in VS Code**: Debug the web version of the extension
- **Attach to Server**: Attach debugger to the language server
- **Client + Server**: Debug both the extension and language server simultaneously
- **Integration Tests**: Run integration tests with debugger attached

## Running Tests

```bash
# Run all unit tests
npm run test

# Run desktop integration tests
npm run test-desktop-int

# Run web integration tests
npm run test-web-integration
```
