
## Step 5: Test the co-pilots using chatgpt to evaluate results

To run evaluation on a copilot implementations:
```
python src/run.py --evaluate
```

You can also run pytest to run tests that use evaluation results to pass/fail
```
pytest
```

This will run the tests in `src/test_copilot.py` using the `evaluation_dataset.jsonl` as a test dataset. This will compute a set of metrics calculated by chatgpt on a 1-5 scale, and will fail that metric if the average score is less than 4.

You can also use the `ai` CLI to do bulk runs and evaluations:

```bash
ai chat evaluate --input-data src/test/evaluation_dataset.jsonl # uses default "chat with your data" copilot
ai chat evaluate --input-data src/test/evaluation_dataset.jsonl --function src/copilot_aisdk/chat:chat_completion
```