## Step 3: Build an Azure Search index

Run the following CLI command to create an index that our code can use for data retrieval:
```
ai search index update --files "./data/3-product-info/*.md" --index-name "product-info"
```

Now, generate a .env file that will be used to configure the running code to use the resources we've created in the subsequent steps
```
ai dev new .env
```