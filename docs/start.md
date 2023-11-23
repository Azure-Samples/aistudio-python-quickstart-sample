# Azure AI Studio: Python Quickstart Sample

> [!WARNING]  
> **Features used in this repository are in preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


## Learning Objectives

This tutorial walks you through the process of creating a copilot enterprise chat UI using custom Python code to ground copilot responses in your company data and APIs. By completing these steps, you'll also gain familiarity with the core features and functionality available in the Azure AI Studio preview, Azure AI CLI and Azure AI SDK for Python. 

At the end of this exercises, you should know how to:
1. [Setup your dev environment](step-02.md) - using prebuilt dev containers.
2. [Create your AI project](step-03.md) - using Azure AI CLI `ai init` command.
3. [Create your AI Search index](step-04.md) - using Azure AI CLI `ai search` command.
4. [Run copilot with a sample question](step-05.md) - using Azure AI SDK for Python.
5. [Evaluate copilot performance](step-06.md) - using chatgpt to compare results.
5. [Deploy copilot to Azure](step-06.md) - and use the endpoint in your own apps.

_The sample is just a starting point that you can customize further, with your own data and additional capabilities, to meet your specific requirements._


## ✅ | Pre-Requisites

1. An Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services)
2. Access to Azure OpenAI in the Azure Subscription - [Request access here](https://aka.ms/oai/access)
3. Custom data to ground the copilot - [Sample product-info data is provided](./../data/3-product-info/)
4. A GitHub account - [Create one for free](https://github.com/signup)
5. Access to GitHub Codespaces - [Free quota should be sufficient](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)

This tutorial will make use of the Azure AI Studio preview, the Azure AI SDK and the Azure AI CLI.
- Verify that you can access [Azure AI Studio](https://ai.azure.com) in your region.
- Read the [Azure AI Studio FAQ](https://learn.microsoft.com/azure/ai-studio/faq#how-can-customers-access-azure-ai-studio--) for details in avaialbility, pricing and more.


## Technology Overview

Before we dive into the development process, let's review a few core terms and concepts that you will encounter in this tutorial. 

If you're already familiar with Azure AI Studio preview and related Azure AI services and tools, skip ahead to 👉🏽 [**Step 01**: Setup Dev Environment](./step-01.md)


### 1. What is Azure AI Studio?

[Azure AI Studio](https://aka.ms/azureaistudio) is a trusted platform that provides a simplfied developer experience for exploring, building, testing and deploying AI solutions that are also grounded in responsible AI practices. 
 - Manage your Azure AI project directly from the **Azure AI Studio UI**
 - Interact with the project programmatically, using the **Azure AI SDK**
 - Interact with the project from the commandline, using the **Azure AI CLI**

With the Azure AI Studio, you get a centralized space for exploring and deploying AI models, discovering AI services, and managing your AI project resources for the end-to-end development experience.


### 2. What is a copilot?

A copilot is an application that uses modern AI and large language models (LLM) to assist you in completing complex cognitive tasks. 

In this particular tutorial, we are building a copilot that assists you in answering user questions _about your company data_, by using the [Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation) pattern  with your preferred LLM deployment endpoint.

### 3. What is Retrieval Augmented Generation (RAG)?

[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) is a pattern where you _augment_ the capability of the default Large Language Model (LLM) by adding an _information retrieval system_. This provides you more control over the data used by the LLM in generating responses to user "questions", allowing you to tailor copilot responses to reflect your company data and requirements.

![How does RAG Work?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern.png)

The RAG pattern (shown above) maintains a data store with your custom data. When the copilot receives a user question, it retrieves data matching the question from this store. It then combines the user question with retrieved data to form the prompt sent to the LLM, helping ground the returned responses.

![What is an Index and why do I need it?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern-with-index.png)

Searching and retrieving data quickly and accurately is critical. The RAG pattern achieves this by proactively maintaining _search indexes_ (as shown above) to improve performance and accuracy.

Azure AI provides an Index asset to use with RAG - where the asset knows where the index is stored, how to access it, what search modes it supports, whether it has vector search capability, what embedding model it uses for this, and more. Currently, Azure AI Search is the primary Index solution for Azure AI projects. | See: [Retrieval Augmented Generation and Indexes](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/retrieval-augmented-generation#how-does-rag-work)


### What is Azure AI Search? 

[Azure AI Search](https://learn.microsoft.com/azure/search/search-what-is-azure-search) (formerly called _Azure Cognitive Search_) provides tools, APIs and infrastructure to **support information retrieval at scale** over heterogeneous data sources - for traditional and conversational search solutions. It is a [proven solution for information retrieval in RAG architectures](https://github.com/Azure-Samples/azure-search-openai-demo) and can be accessed from Azure AI Studio, Azure AI SDK or Azure AI CLI.

### What is Vector Search in Azure AI Search?

Vector search is an information retrieval approach using numeric representations of content for search scenarios. The search engine now matches on vectors that are the most similar to the query, without needing to match exact terms. This helps it power similarity search, multi-modal search, recommendations engines, or apps implementing the 
[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) architecture.

Vector search is available in Azure AI Search by default, and works as shown in the figure below. In this project, we use Azure AI Search to create a vector store for the product information data, then use Azure Open AI `text-embedding-ada-002` deployment for embedding data in vectors, for more efficient search and retrieval later. | See [Vector search in Azure AI Search](https://learn.microsoft.com/en-us/azure/search/vector-search-overview) for more details.

![What's vector search in Azure AI Search?](https://learn.microsoft.com/azure/search/media/vector-search-overview/vector-search-architecture-diagram-3-high-res.png#lightbox)




### Learning Resources

1. [Azure AI Studio](https://ai.azure.com) - UI to explore, build & manage AI solutions.
1. [Azure AI Studio Docs](https://learn.microsoft.com/azure/ai-studio/) - Azure AI Studio documentation.
1. [Azure AI Services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - Azure AI Services documentation.
1. [Training: Using vector search in Azure Cognitive Search](https://learn.microsoft.com/training/modules/improve-search-results-vector-search) 
1. [Tutorial: Deploy a web app for chat on your data](https://learn.microsoft.com/azure/ai-studio/tutorials/deploy-chat-web-app) 
1. [Quickstart: Moderate text and images with content safety in Azure AI Studio](https://learn.microsoft.com/azure/ai-studio/quickstarts/content-safety)

## Next Steps

To build our copilot solution, we first need to setup our development environment with the right tools, libraries and content (e.g., custom data sources) to work with Azure and Azure AI resources.

➡️ [**Step 01**: Setup Dev Environment](./step-01.md)
