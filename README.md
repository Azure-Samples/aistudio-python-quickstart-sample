# Azure AI Studio: Python Quickstart Sample

> [!WARNING]  
> **Features used in this repository are in preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


## 🔎 | Explore Azure AI Studio Features

This repository contains a copilot quickstart sample that can be used with the [Azure AI Studio preview](https://learn.microsoft.com/azure/ai-studio). Explore these resources to learn more about this supports:

* [Azure AI Studio](https://learn.microsoft.com/azure/ai-studio) - build, evaluate & deploy AI solutions from one space.
* [Azure AI services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - AI models & APIs accessible from Azure AI Studio.
* [Azure AI SDK](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install) - access to Azure AI services from code (programmatic).
* [Azure AI CLI](https://learn.microsoft.com/azure/ai-studio/how-to/cli-install) - access to Azure AI services from command-line (shell).


## 👩🏽‍💻 | Build a copilot with your own data

The sample walks through creating a copilot enterprise chat API that uses custom Python code to ground the copilot responses in your company data and APIs. The sample is meant to provide a starting point that you can further customize to add additional intelligence or capabilities. Following the steps in the [**sample tutorial**](docs/start.md), you will be able to:
 - setup your development environment (pre-built or custom options)
 - create Azure AI resources and project to build the copilot
 - create an Azure Search index containing product information
 - run your copilot with a sample question, and evaluate it

In the process, you will get familiar with the **Azure AI CLI** for setting up and configuring your copilot from the commandline. And you'll learn to use the **Azure AI SDK** (from Python code or from Jupyter Notebooks) to interact programmatically with your copilot.

> [!NOTE]  
> We do not guarantee the quality of responses produced by this sample copilot or its suitability for use in your scenario, and responses will vary as development of this sample is ongoing. You must perform your own validation the outputs of the copilot and its suitability for use within your company.


## 🏁 | Get Started

Ready to get started on the tutorial? The quickest way is to use a pre-built development environment. **Click the button below** to open the repo in GitHub Codespaces. Then continue with the README directions.

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Azure-Samples/aistudio-python-langchain-sample?quickstart=1)

- [**Start Here**](./docs/start.md) if you want an overview of project and key concepts first.
- [**Jump Here**](./docs/step-01.md) if just want to get started with the development steps.

This tutorial provides a quickstart using the Azure AI SDK from Python, to build a basic copilot application. Want to explore advanced samples using specific frameworks? Try these samples next:
 1. [Azure AI Studio: Semantic Kernel Quickstart](https://github.com/Azure-Samples/aistudio-python-semantickernel-sample)
 1. [Azure AI Studio: PromptFlow Quickstart](https://github.com/Azure-Samples/aistudio-python-promptflow-sample)
 1. [Azure AI Studio: Langchain Quickstart](https://github.com/Azure-Samples/aistudio-python-langchain-sample)


## 📚 | Resources

1. [Azure AI Studio](https://aka.ms/azureaistudio) - UI to explore, build & manage AI solutions.
1. [Azure AI Studio Docs](https://aka.ms/azureaistudio/docs) - Azure AI Studio documentation.
1. [Azure AI Services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - Azure AI Services documentation.
1. [Training: Using vector search in Azure Cognitive Search](https://learn.microsoft.com/training/modules/improve-search-results-vector-search) 
1. [Tutorial: Deploy a web app for chat on your data](https://learn.microsoft.com/azure/ai-studio/tutorials/deploy-chat-web-app) 


## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.


## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.

