# 01 | About This Sample

!!!warning "Azure AI Studio is currently **in preview**"
    **Features used in this repository are in preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**


## Learning Objectives

This quickstart tutorial walks you through the steps of creating a copilot enterprise chat API that uses custom Python code to ground the copilot responses in your company data and APIs. The sample is meant to provide a starting point that you can further customize to add additional intelligence or capabilities. 

By the end of this tutorial, you will know how to:

1. [Describe Azure AI Studio (preview)](./02-technology.md) - including Azure AI SDK and Azure AI CLI.
1. [Set up your development environment](./03-setup.md) - using pre-built or manual setup options.
1. [Provision your Azure AI project and hub resources](./04-provision.md) - using Azure AI CLI (`ai init`).
1. [Build an index containing product information](./05-populate.md) - using Azure AI CLI (`ai search`). 
1. [Run your copilot and test it with a question](./06-run.md) - using Azure AI SDK.
1. [Evaluate your copilot with metrics](./07-evaluate.md) - using chatgpt to compare results.
1. [Deploy your copilot to Azure](./08-deploy.md) - to get a hosted endpoint for app integrations.
1. [Invoke the deployed API](./09-summary.md) - and explore next steps in your learning journey.

This sample is just the starting point. Once you've completed the tutorial, you can customize it further for your application requirements, or to explore other platform capabilities.

!!!warning "**This is not a production sample**" 
    We do not guarantee the quality of responses produced by this sample copilot or its suitability for use in your scenario. Copilot responses will vary as this sample remains under active development. You **must perform your own validation** of the copilot responses to evaluate its suitability for use within your company or application requirements.


## Pre-Requisites

Completing the tutorial requires the following:

1. An Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services)
2. Access to Azure OpenAI in the Azure Subscription - [Request access here](https://aka.ms/oai/access)
3. Custom data to ground the copilot - [Sample product-info data is provided](./../data/3-product-info/)
4. A GitHub account - [Create one for free](https://github.com/signup)
5. Access to GitHub Codespaces - [Free quota should be sufficient](https://docs.github.com/en/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces#monthly-included-storage-and-core-hours-for-personal-accounts)

The tutorial uses Azure AI Studio which is currently in public preview.

 - Read [the documentation](https://learn.microsoft.com/azure/ai-studio/reference/region-support#azure-public-regions) to learn about regional availability of Azure AI Studio (preview)
 - Read the [Azure AI Studio FAQ](https://learn.microsoft.com/azure/ai-studio/faq) for answers to some commonly-asked questions.

## Using Custom Data

In this tutorial, we build a copilot for a fictional company (_Contoso Outdoors_) that sells camping and hiking gear to outdoor enthusiasts. To build a copilot grounded in that company's data, we have sample data in the `data/` folder at the root of this repo. Not all of that data is used in this specific tutorial, but we've documented it here for awareness.

| Data Folder | Data Description |
| --- | --- |
| `data/0-misc` | General information - e.g., customer policies for org. |
| `data/1-customer-info`| Customer purchase records  - for 13 fictional customers |
| `data/2-chat-history`| Customer conversation history - for a subset of customers |
| `data/3-product-info` | Product catalog data - for 20 items in 7 categories |
| `data/4-scores` | Test data - for use in evaluations  |
| `data/5-prompt-templates` | Example templates - for different contexts |

---

[**Next Step**](./02-technology.md) | Understand Key Concepts
