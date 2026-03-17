# ACL_PSR
Repo for ACL 26 Paper on PSR Annotation

# Core GPT-5.1 suite (FULL, N=2520)

ProposedPipeline         → Ours: Structured Domain Prompt + Profile+Local Context + Dynamic-K batching

10_51_Enhanced_NoContext              → Structured Domain Prompt (no context)   [domain theory + strict rules + schema]

12_51_Simple_NoContext                → Minimal Few-shot Baseline               [few-shot, minimal domain structure]

PPCCOT       → Ours + CCoT Prompting                  [same as 9, adds CCoT]

14_51_Enhanced_NoContext_CCOT          → Structured Domain Prompt + CCoT         [same as 10, adds CCoT]

PPFixedK70         → Context + Fixed-K batching (K=70)

PPFixedK5   → Context + Fixed-K batching (K=5)

18_51_Zero_NoContext                   → Minimal Zero-shot Baseline

19_51_CoT_NoContext                    → Minimal + CoT Prompting

20_51_ToT_NoContext                    → Minimal + ToT Prompting

23_AnnoLLM                             → Structured Domain Prompt (no context) + AnnoLLM Adaptation

24_LiaHR                               → Structured Domain Prompt (no context) + LiaHR Adaptation

# Other backbones

PPMini            → Ours (GPT-5-mini backbone)

25_EEStyle                             → Structured Domain Prompt (no context) + LLM-Based EE Adaptation (Mixture of "gpt-4.1-mini", "gpt-4.1-nano", "gpt-4.1" and "gpt-5.1")

# GPT-4.1 comparisons

1_41_Simple_NoContext                  → Simple Few-shot Baseline (GPT-4.1)

2_41_Enhanced_NoContext                → Structured Domain Prompt (GPT-4.1, no context)

15_41_CCOT_NoContext                   → Structured Domain Prompt + CCoT (GPT-4.1, no context)

# Holdout-only (SMALL, N=2115)

5_41_Enhanced_NoContext_Small          → Structured Domain Prompt (GPT-4.1, holdout)

6_41FT_Enhanced_NoContext_Small        → Fine-tuned Structured Domain Prompt (GPT-4.1-FT, holdout)

7_51_Enhanced_NoContext_Small          → Structured Domain Prompt (GPT-5.1, holdout)


Outputs of the codes are in the Outputs folder. 

Evaluation folder contains the evaluation code and its outputs. 