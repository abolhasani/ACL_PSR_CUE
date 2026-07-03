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

2520 Messages picked from twitch, 7 streamers total. 

Link to paper: https://aclanthology.org/2026.acl-short.51/

Cite (ACL): Mohammadsadegh Abolhasani, Reza Mousavi, and Paul Jen-Hwa Hu. 2026. CaBSALLM: Efficient Context-Aware Batch Annotation of Conversational Streams with Large Language Models. In Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (Volume 2: Short Papers), pages 615–636, San Diego, California, United States. Association for Computational Linguistics.

## Annotation Schema

| Aspect | Cue | Definition | Example |
|---|---|---|---|
| DirectAddress | Direct address | Message explicitly targets the streamer as the addressee through name, @mention, or clear second-person reference. | “Emiru, you are late today”;<br>“you need to see this” |
| Attachment | Attachment / affection | Message expresses warmth, care, longing, loyalty, pride, or relational closeness toward the streamer. | “love u”;<br>“you look gorgeous today” |
| SelfDisclose | Self-disclosure / identification | Viewer shares personal information, experience, or similarity in a way that invites relational connection. | “I had a rough day, thanks for being here”;<br>“I’m also a grad student” |
| ReplySeeking | Reply seeking | Message seeks acknowledgment, recognition, or a direct response from the streamer. | “notice me”;<br>“did you see my message?” |
| CommRitual | Community ritual | Message invokes shared rituals, inside jokes, coordinated norms, or co-created chat practices. | “chat do the thing”;<br>“only real ones remember” |
| Monetary | Monetary support | Message signals subscription, donation, gifted support, renewal, streaks, or similar financial contribution. | “gifted 5 subs”;<br>“resubscribed for 24 months” |
| Backseat | Backseat guidance | Message renders advice, direction, coaching, or suggestions about gameplay or content. | “go left”;<br>“use ult now” |
| Emotes | Emote / emoji usage | Message contains Twitch-style emotes, emoji, or affective symbolic tokens. | “KEKW”;<br>“&lt;3” |
| Dimension | Valence / stance | Overall stance expressed toward the streamer or community, coded as positive (P) or negative (N). | P: “love this stream”;<br>N: “you’re an idiot” |

Link to Dataset in HuggingFace: https://huggingface.co/datasets/abolhasani/PSR_ACL

