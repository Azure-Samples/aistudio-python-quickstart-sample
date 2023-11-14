## Step 3: Build an Azure Search index

Run the following CLI command to create an index that our code can use for data retrieval:
```
ai search index update --files "./data/3-product-info/*.md" --index-name "product-info"
```

Now, generate a .env file that will be used to configure the running code to use the resources we've created in the subsequent steps
```
ai dev new .env
```

## Next Steps

The Azure AI project is ready and provisioned with the Azure AI Search resource and generated index. Now, it's time to test our copilot with a sample question that relates to the custom data we used for building the index.

➡️ [**Step 04**: Validate the copilot with a sample question](./step-04.md)