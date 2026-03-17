# Codes Folder README

This folder contains all modeling and evaluation notebooks.

Most notebooks use:

- `ROOT_DIR = os.getcwd()`
- `SOURCE_MESSAGES_PATH = os.path.join(ROOT_DIR, <input filename>)`
- outputs written back to the same working directory:
  - `<RUN_BASENAME>.json`
  - `<RUN_BASENAME>.xlsx`
  - `<RUN_BASENAME>_run_stats.json` or `<RUN_BASENAME>_stats_run.json`

Because of this, run location matters.

## Notebook Groups and Inputs

| Group | Notebooks | Expected input filename(s) in working directory |
|---|---|---|
| Full no-context and reasoning variants | `1_41_Simple_NoContext.ipynb`, `2_41_Enhanced_NoContext.ipynb`, `10_51_Enhanced_NoContext.ipynb`, `12_51_Simple_NoContext.ipynb`, `14_51_Enhanced_NoContext_CCOT.ipynb`, `15_41_CCOT_NoContext.ipynb`, `18_51_Zero_NoContext.ipynb`, `19_51_CoT_NoContext .ipynb`, `20_51_ToT_NoContext.ipynb` | `messages.json` |
| Small holdout variants | `5_41_Enhanced_NoContext_Small.ipynb`, `6_41FT_Enhanced_NoContext_Small.ipynb`, `7_51_Enhanced_NoContext_Small.ipynb` | `filtered_messages_test_inputs.jsonl` |
| Proposed pipeline family | `PropoedPipeline.ipynb`, `PPmini.ipynb`, `PPFixedK5.ipynb`, `PPFixedK70.ipynb`, `PPCCOT.ipynb` | `messages.json` |
| Reliability-style methods | `23_AnnoLLM.ipynb`, `25_EEStyle.ipynb` | `messages.json` |
| LiaHR | `24_LiaHR.ipynb` | `LiaHRInput.json`, `LiaHRDemoPool.json` |
| Evaluation | `Evaluation/Benchamrking.ipynb` | Gold and model `.xlsx` files listed in its `GROUPS` config |

## Current Generated Artifacts

- `Outputs/` contains generated run outputs (`.json`, `.xlsx`, run stats).
- `Evaluation/` contains benchmarking notebook and benchmark CSV summaries.

## Data Connection

Required input files originate in `../Data/` (including `HOLDOUT/` and `LiaHR/` subfolders), and should be staged into the working directory before notebook execution.
