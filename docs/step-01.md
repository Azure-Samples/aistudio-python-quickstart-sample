## Step 1: Set up your development environment

Our development environment will make use of three resources:
 - [Azure AI Studio](https://aka.ms/azureaistudio) - browser-based UI for exploring and managing your AI projects
 - [Azure AI CLI](https://learn.microsoft.com/azure/ai-studio/how-to/cli-install?tabs=linux%2Cterminal) - command-line access to Azure AI services (no code needed)
 - [Azure AI SDK](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install?tabs=linux) - Python packages for access to Azure AI services (code-based)


You have three options for setting up your development enviroment:
 1. Use prebuilt environment with GitHub Codespaces (recommended)
 1. Use prebuild environment with Docker Desktop (local device)
 1. Setup your development environment manually (local device)

> [!IMPORTANT  
> We strongly recommend you use the pre-built development environment with GitHub Codespaces to get started quickly, and minimize your effort for setup and maintenance of the development environment later.



To get started quickly, you can use a pre-built development environment. **Click the button below** to open the repo in GitHub Codespaces, and then continue the readme!

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/Azure-Samples/aistudio-python-quickstart-sample/)

If you want to get started in your local environment, first install the packages:
```
git clone https://github.com/Azure-Samples/aistudio-python-quickstart-sample/
cd aistudio-python-quickstart-sample/
pip install -r requirements.txt
```

Then install the Azure AI CLI, on Ubuntu:
```
curl -sL https://aka.ms/InstallAzureAICLIDeb | sudo bash
```

To install the CLI on Windows and MacOS, follow the instructions [here](https://github.com/Azure/azureai-insiders/blob/main/previews/aistudio/how-to/use_azureai_sdk.md#install-the-cli)v


## Next Steps

We've setup and validated our development environment. Now it's time to create our Azure AI project and provision the necessary resources to build our copilot solution.

➡️ [**Step 02**: Initialize Azure AI Resources](./step-02.md)