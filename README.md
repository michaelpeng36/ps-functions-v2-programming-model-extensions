# Azure Functions PowerShell New Programming Model (extensions.csproj)

This repository contains skeleton code for Azure PowerShell Functions in the V2 programming model.

---

## Installation Instructions

1. Install the Azure Functions Core Tools private build for your corresponding OS and architecture:
    - [Windows x64](https://artprodwus21.artifacts.visualstudio.com/Ad1c51fbc-4477-4a0f-b99f-fc9013009a58/e6a70c92-4128-439f-8012-382fe78d6396/_apis/artifact/cGlwZWxpbmVhcnRpZmFjdDovL2F6ZnVuYy9wcm9qZWN0SWQvZTZhNzBjOTItNDEyOC00MzlmLTgwMTItMzgyZmU3OGQ2Mzk2L2J1aWxkSWQvMTExODQ1L2FydGlmYWN0TmFtZS9kcm9w0/content?format=file&subPath=%2Ffunc-cli-4.0.4991-x64.msi)
    - [Windows x86](https://artprodwus21.artifacts.visualstudio.com/Ad1c51fbc-4477-4a0f-b99f-fc9013009a58/e6a70c92-4128-439f-8012-382fe78d6396/_apis/artifact/cGlwZWxpbmVhcnRpZmFjdDovL2F6ZnVuYy9wcm9qZWN0SWQvZTZhNzBjOTItNDEyOC00MzlmLTgwMTItMzgyZmU3OGQ2Mzk2L2J1aWxkSWQvMTExODQ1L2FydGlmYWN0TmFtZS9kcm9w0/content?format=file&subPath=%2Ffunc-cli-4.0.4991-x86.msi)
    - [macOS ARM64](https://artprodwus21.artifacts.visualstudio.com/Ad1c51fbc-4477-4a0f-b99f-fc9013009a58/e6a70c92-4128-439f-8012-382fe78d6396/_apis/artifact/cGlwZWxpbmVhcnRpZmFjdDovL2F6ZnVuYy9wcm9qZWN0SWQvZTZhNzBjOTItNDEyOC00MzlmLTgwMTItMzgyZmU3OGQ2Mzk2L2J1aWxkSWQvMTExODQ1L2FydGlmYWN0TmFtZS9kcm9w0/content?format=file&subPath=%2FAzure.Functions.Cli.osx-arm64.4.0.4991.zip)
    - [macOS x64](https://artprodwus21.artifacts.visualstudio.com/Ad1c51fbc-4477-4a0f-b99f-fc9013009a58/e6a70c92-4128-439f-8012-382fe78d6396/_apis/artifact/cGlwZWxpbmVhcnRpZmFjdDovL2F6ZnVuYy9wcm9qZWN0SWQvZTZhNzBjOTItNDEyOC00MzlmLTgwMTItMzgyZmU3OGQ2Mzk2L2J1aWxkSWQvMTExODQ1L2FydGlmYWN0TmFtZS9kcm9w0/content?format=file&subPath=%2FAzure.Functions.Cli.osx-x64.4.0.4991.zip)
2. ***(Optional)*** Install [Azurite](https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azurite?tabs=npm) for storage emulation:
    - Example:
        ```
        npm install -g azurite
        ```
3. Clone this repository and cd into the function app root directory:
    ```
    git clone https://github.com/michaelpeng36/ps-functions-v2-programming-model-extensions.git
    cd ps-functions-v2-programming-model-bundles
    ```
<!-- TODO: add the verification script and the corresponding command to run the verification script -->
4. Run the verification script: if it runs without issue, you should be all set to start local development. Otherwise, it should indicate what component of your setup is incorrect.
5. If you are using storage emulation, run the below command ***in a separate PowerShell window*** to start storage emulation:
    ```
    azurite
    ```
    Otherwise, ensure that the appropriate KeyVault reference or connection string is set in the `AzureWebJobsStorage` property of `host.json`.
5. Install the extensions specified in the `extensions.csproj` file:
    ```
    func extensions install
    ```
6. Start Core Tools to begin local development:
    ```
    func start
    ```
    There should be one HTTP function pre-written for you called `HttpTrigger1`.
7. Continue writing your other functions in the V2 programming model!