
## Step 2: Create and connect to Azure Resources

Run ai init to create and/or connect to existing Azure resources:
```
ai init
```

- This will first prompt to you to login to Azure
- Then it will ask you to select or create resources, choose  **AI Project resource** and follow the prompts to create an Azure OpenAI resource, model deployments, and Azure AI  search resource
- This will generate a config.json file in the root of the repo, the SDK will use this when authenticating to Azure AI services.

Note: You can open your project in [AI Studio](https://aka.ms/AzureAIStudio) to view your projects configuration and components (generated indexes, evaluation runs, and endpoints)
