# Build a copilot with Azure AI Studio and your data

> [!IMPORTANT]
> **❗Features contained in this repository are in private preview.** These preview features are provided without a service-level agreement, and are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. 
> For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).

Learn how you can use the Azure AI Studio, SDK and CLI, with Azure AI Services, to build your own copilot application, with your custom data.

## Learning Objectives

By the end of this tutorial you'll learn how to:
 - Setup your development environment for building Azure AI Solutions
 - Create an Azure AI Project and related resources for your copilot
 - Create an Azure AI Search resource and index for your custom data
 - Validate your copilot by asking it questions about your custom data
 - Evaluate your copilot performance using a relevant test dataset
 - Explore, build, and manage, your AI Project resources from Azure AI Studio

## Introduction

This tutorial walks you through the steps to build, use, and evaluate, a copilot implementation on a custom data collection, **using Azure AI Studio** and the associated CLI, SDK and Azure AI Services. Before we dive in, let's talk about some of the core terms and concepts we will be using.

### What is Azure AI Studio?

[Azure AI Studio](https://aka.ms/azureaistudio) is a trusted platform that provides a simplfied developer experience for exploring, building, testing and deploying AI solutions that are also grounded in responsible AI practices. 
 - Manage your Azure AI project directly from the **Azure AI Studio UI**
 - Interact with the project programmatically, using the **Azure AI SDK**
 - Interact with the project from the commandline, using the **Azure AI CLI**

With the Azure AI Studio, you get a centralized space for discovering and managing your Azure AI resources, with tools and AI Service integrations for seamless end-to-end development.


### What is a copilot?

A "copilot" is an application that uses modern AI and large language models (LLM) to assist you in completing complex cognitive tasks. In this particular series of tutorials, we focus on building a copilot that assists you in answering user questions _about your own data_, by using [Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation) in conjunction with your preferred LLM endpoint.

### What is Retrieval Augmented Generation (RAG)?

[Retrieval Augmented Generation (RAG)](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) is an architecture or pattern where you _augment_ the capability of the default Large Language Model (LLM) by adding an _information retrieval system_ that gives you more control over the data used by the LLM in generating responses. When a user asks a "question", the copilot can retrieve matching results from this system and combine it with the question to form the prompt provided to the LLM, to generate the final answer.

### What is Azure AI Search? 

[Azure AI Search](https://learn.microsoft.com/azure/search/search-what-is-azure-search) (formerly called _Azure Cognitive Search_) is a cloud-based search service that provides tools, APIs and infrastructure to **support information retrieval at scale** over private, heterogeneous data sources - with applicability to traditional and conversational search solutions. It is a [proven solution for information retrieval in a RAG architecture](https://github.com/Azure-Samples/azure-search-openai-demo) and can be easily created and managed from the Azure AI Studio UI - or programmatically, using Azure AI SDK or CLI. We'll make good use of this capability in our tutorial, to develop our copilot solution.


## Learning Resources

1. [Azure AI Studio](https://aka.ms/azureaistudio) - UI to explore, build & manage AI solutions.
1. [Azure AI Studio Docs](https://aka.ms/azureaistudio/docs) - Azure AI Studio documentation.
1. [Azure AI Services](https://learn.microsoft.com/azure/ai-services/what-are-ai-services) - Azure AI Services documentation.
1. [Training: Using vector search in Azure Cognitive Search](https://learn.microsoft.com/training/modules/improve-search-results-vector-search) 
1. [Tutorial: Deploy a web app for chat on your data](https://learn.microsoft.com/azure/ai-studio/tutorials/deploy-chat-web-app) 


## Next Steps

To build our copilot solution, we first need to setup our development environment with the right tools, libraries and content (e.g., custom data sources) to work with Azure and Azure AI resources.

➡️ [**Step 01**: Setup Dev Environment](./step-01.md)