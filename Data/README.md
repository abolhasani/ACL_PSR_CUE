# Data Folder README

This folder stores source datasets and reference files used by notebooks in `Codes/`.

Important note from notebook code: most notebooks set `ROOT_DIR = os.getcwd()` and then load files by name (for example `messages.json`).  
That means required input files must exist in the notebook's current working directory when you run it.

## Files and Connections

| Data file | Used by notebooks |
|---|---|
| `messages.json` | Main input for full-run notebooks: `1_41_*`, `2_41_*`, `10_51_*`, `12_51_*`, `14_51_*`, `15_41_*`, `18_51_*`, `19_51_*`, `20_51_*`, `23_AnnoLLM`, `25_EEStyle`, `PropoedPipeline`, `PPmini`, `PPFixedK5`, `PPFixedK70`, `PPCCOT` |
| `messagesgt.json` | Reference/gold JSON asset (not directly loaded by the main benchmarking notebook) |
| `annotated_messages_Full_GOLD.xlsx` | Gold labels for FULL benchmark in `Codes/Evaluation/Benchamrking.ipynb` |
| `HOLDOUT/filtered_messages_test_inputs.jsonl` | Input for small-set notebooks: `5_41_Enhanced_NoContext_Small`, `6_41FT_Enhanced_NoContext_Small`, `7_51_Enhanced_NoContext_Small` |
| `HOLDOUT/small_messages_gold.xlsx` | Gold labels for SMALL benchmark in `Codes/Evaluation/Benchamrking.ipynb` |
| `HOLDOUT/filtered_messages_test_gold.jsonl` | Holdout gold JSONL source file |
| `LiaHR/LiaHRInput.json` | Input for `Codes/24_LiaHR.ipynb` |
| `LiaHR/LiaHRDemoPool.json` | Demo pool for `Codes/24_LiaHR.ipynb` |
| `FT/finetuning_messages.jsonl` | Fine-tuning training messages asset |
| `FT/al_needs_review_set.jsonl` | Active-learning review set asset |

## Practical Run Tip

Before running a notebook, copy or link the required data file(s) from this folder into the notebook run directory (because notebooks resolve paths from `os.getcwd()`).
