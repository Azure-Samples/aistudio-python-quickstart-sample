## Getting Started

### Prerequisites

(ideally very short, if any)

- OS
- Library version
- ...

### Installation

(ideally very short)

- npm install [package name]
- mvn install
- ...

### Quickstart
(Add steps to get up and running quickly)

1. git clone [repository clone url]
2. cd [repository name]
3. ...


## Demo

A demo app is included to show how to use the project.

To run the demo, follow these steps:

(Add steps to start up the demo)

1.
2.
3.

## Resources

(Any additional resources or related projects)

- Link to supporting information
- Link to similar sample
- ...




## What is a copilot?

A copilot is an application that uses modern AI and large language models (LLM) to assist you in completing complex cognitive tasks. In this tutorial, you'll learn to build a copilot that can help you answer user questions about _your own data_ using the popular [Retrieval Augmented Generation (RAG) pattern](https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation).

## What is Retrieval Augmented Generation (RAG)?

Retrieval Augmented Generation (RAG) is an architecture or pattern that _augments_ the capabilities of the default Large Language Model (LLM) by adding an information retrieval system which [gives you control over the data used by the LLM](https://learn.microsoft.com/azure/search/retrieval-augmented-generation-overview) when it generates responses to user questions. 

Now when the user asks a question, the copilot can _retrieve_ relevant search results from that information rtr

## What is Azure Cognitive Search?
A good inforrmation retrieval system provides **index and search** capabilities that work with your custom data.

## What does our copilot do?




A good information retrieval system will provide efficient **index and search** capabilities that work with _your custom data_. Now, when the user asks your copilot a question, it searches the information retrieval system using that input, to get a relevant set of matching results. The original question and the retrieved matching results are now combined in the prompt sent to the target LLM, to generate the desired answer.

Azure Cognitive Search is a [proven solution for information retrieval in a RAG architecture](https://github.com/Azure-Samples/azure-search-openai-demo) that we will use in our solution as well.



## 1. Setup Your Development Environment.


[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Azure/aistudio-copilot-sample/tree/oct-refresh?quickstart=1)


Learn how to **create, build, evaluate, and deploy, a copilot solution** using the Azure AI Studio SDK and CLI wih custom Python code (run from the command-line or from a Jupyter notebook).

## Getting started 
**What you will learn:**
- What is Azure AI Studio?
- What is the Azure AI SDK?
- What is the Azure AI CLI?
- How do I build a copilot with Azure AI Studio?

**What you will do:**
- Setup dev environment (with Azure AI CLI & SDK)
- Create an Azure AI project & resources for a copilot
- Build an Azure AI search index using custom data
- Ask the copilot a sample question (related to data)
- Evaluate performance of the copilot implementation

