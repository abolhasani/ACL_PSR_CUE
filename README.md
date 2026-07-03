# ACL_PSR_CUE
Repository for ACL 26 Paper on PSR Annotation

This project is now organized around two main folders:
- `Data/`: source datasets, holdout sets, LiaHR assets, and gold labels
- `Codes/`: annotation/evaluation notebooks and generated outputs

- Link to Dataset in HuggingFace: https://huggingface.co/datasets/abolhasani/PSR_ACL


Link top paper: https://aclanthology.org/2026.acl-short.51/

Cite (ACL): Mohammadsadegh Abolhasani, Reza Mousavi, and Paul Jen-Hwa Hu. 2026. CaBSALLM: Efficient Context-Aware Batch Annotation of Conversational Streams with Large Language Models. In Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (Volume 2: Short Papers), pages 615–636, San Diego, California, United States. Association for Computational Linguistics.

## Folder Overview

| Path | Purpose |
|---|---|
| `Data/` | Input datasets and benchmark gold files |
| `Data/HOLDOUT/` | Small-test input and gold assets |
| `Data/LiaHR/` | LiaHR-specific input and demo pool |
| `Data/FT/` | Fine-tuning and active-learning assets |
| `Codes/` | Notebook implementations |
| `Codes/Outputs/` | Produced run outputs (`.json`, `.xlsx`, run stats) |
| `Codes/Evaluation/` | Benchmark notebook and exported benchmark CSVs |

## How Data Connects to Code (from notebook path logic)

Notebook configs generally use `ROOT_DIR = os.getcwd()` and load files by filename, not by `Data/...` paths.  
So the files they need must be present in the current working directory where the notebook runs.

Main input mapping:

- Full-run notebooks and proposed-pipeline notebooks expect `messages.json`
- Small-run notebooks expect `filtered_messages_test_inputs.jsonl`
- `24_LiaHR.ipynb` expects `LiaHRInput.json` and `LiaHRDemoPool.json`
- `Codes/Evaluation/Benchamrking.ipynb` expects gold and model `.xlsx` files listed in its `GROUPS` config

## Recommended Workflow

1. Stage required inputs from `Data/` into your notebook run directory.
2. Run notebooks from `Codes/`.
3. Keep generated files in `Codes/Outputs/`.
4. Run `Codes/Evaluation/Benchamrking.ipynb` with required gold/model `.xlsx` files available in its working directory.

For details:

- See `Data/README.md`
- See `Codes/README.md`

