# Azure AI Studio: Python Quickstart Sample

> [!WARNING]  
> Features contained in this repository are in preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or mvght have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).


## 🔎 | Explore Azure AI Studio Features

This repository contains a copilot quickstart sample that can be used with the [Azure AI Studio preview](https://learn.microsoft.com/azure/ai-studio). To learn more, explore these resources:

* [Azure AI Studio](https://learn.microsoft.com/azure/ai-studio) - build, evaluate & deploy AI solutions from one space.
* [Azure AI services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - AI models & APIs accessible from Azure AI Studio.
* [Azure AI SDK](https://learn.microsoft.com/azure/ai-studio/how-to/sdk-install) - access to Azure AI services from code (programmatic).
* [Azure AI CLI](https://learn.microsoft.com/azure/ai-studio/how-to/cli-install) - access to Azure AI services from command-line (shell).


## 👩🏽‍💻 | Build a copilot with your own data

The sample walks you through the process of creating a copilot enterprise chat API that uses custom Python code to ground the copilot responses in your company data and APIs. It provides a starting point that you can customize further, to meet your own custom copilot requirements.

Here's what you'll learn to do in this quickstart:
 - Setup your development environment to use Azure AI CLI and Azure AI SDK.
 - Create an Azure AI project and configure relevant Azure AI resources.
 - Build an Azure AI Search index for your custom data, to support RAG pattern.
 - Generate an .env file with your Azure AI project settings for subsequent steps.
 - Run the copilot with a sample question to validate responses from custom data.
 - Evaluate performance against chatgpt or other copilots, using given dataset.

The tutorial will use the Azure AI CLI for setting up and configuring the copilot - and use the Azure AI SDK to run the copilot with sample questions interactively (using Jupyter Notebooks) or from command-line (using Python scripts).


> [!NOTE]  
> We do not guarantee the quality of responses produced by this sample copilot or its suitability for use in your scenario, and responses will vary as development of this sample is ongoing. You must perform your own validation the outputs of the copilot and its suitability for use within your company.


## 🏁 | Get Started

This quickstart uses the basic Azure AI SDK features in Python to build a custom copilot. 
 - [Start Here]() to get an overview of the tutorial and concepts first
 - [Jump Here]() to dive straight into by setting up the development environment.

Then follow the steps in sequence to build, evaluate and run the copilot. Want to build a copilot but with a specific framework? Check out these samples next:
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

