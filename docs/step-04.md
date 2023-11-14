

## Step 4: Run the co-pilot with a sample question

To run a single question & answer through the sample co-pilot:
```bash
python src/run.py --question "which tent is the most waterproof?"
```

You can try out different sample implementations by specifying the `--implementation` flag with `promptflow`, `semantickernel`, `langchain` or `aisdk`. To try running with semantic kernel:

```bash
python src/run.py --implementation semantickernel --question "what is the waterproof rating of the tent I just ordered?"
```

To try out the promptflow implementation, check deployment names (both embedding and chat) and index name (if it's changed from the previous steps) in `src/copilot_promptflow/flow.dag.yaml` match what's in the `.env` file.

```bash
python src/run.py --question "which tent is the most waterproof?" --implementation promptflow
```

The `--implementation` flag can be used in combination with the evaluate command below as well.

You can also use the `ai` CLI to submit a single question and/or chat interactively with the sample co-pilots, or the default "chat with your data" co-pilot:

```bash
ai chat --interactive # uses default "chat with your data" copilot
ai chat --interactive --function src/copilot_aisdk/chat:chat_completion
```


## Next Steps

We've created a simple copilot solution for our custom data, and validated its usage with a sample question. Now, we need to evaluate how it performs in comparison to other applications like `chatgpt` by using a relevant evaluation dataset.

➡️ [**Step 05**: Evaluate the copilot performance](./step-05.md)