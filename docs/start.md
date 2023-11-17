# Build a copilot with Azure AI Studio and your data

> [!WARNING]  
> Features contained in this repository are in preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or mvght have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).

In this sample, you will create a copilot enterpise chat API that uses custom data with an Azure OpenAI Service model. You will upload the data files to Azure and create an Azure AI Search index that will ground the copilot to your "company data" to improve the quality of its responses. You will then use the Azure AI SDK  to ask the copilot a sample question - from Python code (commandline) or from a Jupyter Notebook (interactive) - to validate that it works.

The steps you'll take in this tutorial are:

 1. [Setup](step-02.md) and validate your development environment.
 1. [Create](step-03.md) and connect to Azure resources.
 1. [Build](step-04.md) an Azure Search index for your custom data.
 1. [Run](step-05.md) the copilot with a sample question to validate it.
 1. [Test](step-06.md) the copilot using chatgpt to evaluate results.
 1. [Deploy](step-07.md) copilot to Azure and test the endpoint

_The sample is meant to be a starting point that you can customize further, with your own data and additional intelligence or capabilities, to meet your specific needs._


## ✅ | Pre-Requisites

1. An Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services)
2. Access to Azure OpenAI in the Azure Subscription - [Request access here](https://aka.ms/oai/access)
3. Custom data to ground the copilot - [Sample product-info data is provided](./../data/3-product-info/)
4. A GitHub account - [Create one for free](https://github.com/signup)
5. Access to GitHub Codespaces in your account - [Free quota should be sufficient](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)

The sample is meant to be used as a quickstart for building with the Azure AI SDK for Python, and using the Azure AI Studio preview. 
- Verify that you can access [Azure AI Studio](https://ai.azure.com) in your region
- Read the [Azure AI Studio FAQ](https://learn.microsoft.com/azure/ai-studio/faq#how-can-customers-access-azure-ai-studio--) for details in avaialbility, pricing and more

## Learning Objectives

By the end of this tutorial, you should be able to:
 - Explain what Azure AI Studio, Azure AI CLI and Azure AI SDK do.
 - Navigate the Azure AI Studio UI to build and manage Azure AI projects.
 - Setup and use a working development environment for Azure AI projects.
 - Create and provision an Azure AI Project from Azure AI CLI (`ai init`)
 - Create an Azure Search index on your custom data from CLI (`ai search`)
 - Build and run a custom copilot using the Azure AI SDK for Python
    - From the commandline (application or script)
    - From a Jupyter Notebook (interactive steps)


## Terms & Concepts

Before you dive into the tutorial, let's take a quick look at some of the key concepts and terms we'll be using. This section is optional reading, but it may help you understand the setup and architecture better.

### What is Azure AI Studio?

[Azure AI Studio](https://aka.ms/azureaistudio) is a trusted platform that provides a simplfied developer experience for exploring, building, testing and deploying AI solutions that are also grounded in responsible AI practices. 
 - Manage your Azure AI project directly from the **Azure AI Studio UI**
 - Interact with the project programmatically, using the **Azure AI SDK**
 - Interact with the project from the commandline, using the **Azure AI CLI**

With the Azure AI Studio, you get a centralized space for discovering and managing your Azure AI resources, with tools and AI Service integrations for seamless end-to-end development.


### What is a copilot?

A "copilot" is an application that uses modern AI and large language models (LLM) to assist you in completing complex cognitive tasks. In this particular series of tutorials, we focus on building a copilot that assists you in answering user questions _about your own data_, by using [Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation) in conjunction with your preferred LLM endpoint.

### What is Retrieval Augmented Generation (RAG)?

[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) is a pattern where you _augment_ the capability of the default Large Language Model (LLM) by adding an _information retrieval system_ that provides more control over the data used by it in generating responses to user "questions".

The pattern involves having a data store that contains the the custom data you want to use to ground the LLM. Now, in response to a user question, the copilot first retrieves relevant data (matching the question) from the store - and combines it with the question to form the prompt used by the LLM to generate a response.

![How does RAG Work?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern.png)

To make this work efficiently, we need a mechanism to _search and retrieve_ matching results quickly and accurately. This is where _search indexes_ can help in improving performance and relevance.

![What is an Index and why do I need it?](https://learn.microsoft.com/azure/ai-studio/media/index-retrieve/rag-pattern-with-index.png)

Azure AI provides an Index asset to use with RAG - where the asset knows where the index is stored, how to access it, what search modes it supports, whether it has vector search capability, what embedding model it uses for this, and more. Currently, Azure AI Search is the primary Index solution for Azure AI projects. | See: [Retrieval Augmented Generation and Indexes](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/retrieval-augmented-generation#how-does-rag-work)

### What is Azure AI Search? 

[Azure AI Search](https://learn.microsoft.com/azure/search/search-what-is-azure-search) (formerly called _Azure Cognitive Search_) is a cloud-based search service that provides tools, APIs and infrastructure to **support information retrieval at scale** over private, heterogeneous data sources - with applicability to traditional and conversational search solutions. It is a [proven solution for information retrieval in a RAG architecture](https://github.com/Azure-Samples/azure-search-openai-demo) and can be easily created and managed from the Azure AI Studio UI - or programmatically, using Azure AI SDK or CLI. We'll make good use of this capability in our tutorial, to develop our copilot solution.

### What is Vector Search in Azure AI Search?

Vector search is an approach in information retrieval that uses numeric representations of content for search scenarios. Because content is numeric and not plain text, the search engine matches on vectors that are the most similar to the query, without needing to match exact terms. This means we can use it to power similarity search, multi-modal search, recommendations engines, or apps implementing the 
[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) architecture.

Vector search is available in Azure AI Search by default - and here's how it works for indexing and querying. | See [Vector search in Azure AI Search](https://learn.microsoft.com/en-us/azure/search/vector-search-overview) for more details.

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
