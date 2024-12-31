# Multi-Evidence Natural Language Inference for Clinical Trial Data (NLI4CT)


## Overview

This repository documents my contributions to a team project addressing the challenge of **Multi-Evidence Natural Language Inference (NLI)** for Clinical Trial Registrations (CTR), focusing on **textual entailment** between CTR statements and premises. The task involves:

1. **Predicting entailment**: Assessing the inference relationship (entailment vs contradiction) between a CTR premise and a statement.
2. **Evidence extraction**: Extracting evidence from the CTR to support the entailment label.

The project emphasizes overcoming the following challenges:
- Multi-hop reasoning
- Incorporating biomedical knowledge in large language models (LLMs)
- Handling numerical and quantitative reasoning


---

<!-- This project focuses on building a Natural Language Inference (NLI) system for Clinical Trial Reports (CTRs) related to breast cancer treatments. The system is designed to analyze complex medical reports to support medical professionals in determining the safety and efficacy of treatments. The project combines techniques from Natural Language Processing (NLP), Information Retrieval (IR), and Machine Learning (ML) to solve a real-world challenge in the health sciences domain.

The dataset includes CTRs segmented into **Eligibility Criteria**, **Intervention**, **Results**, and **Adverse Events** sections, along with annotated statements and inference labels. The goal is to determine the entailment relationship (entailment vs contradiction) between CTRs and provided statements. -->

## Problem Statement

Despite achieving state-of-the-art results in clinical NLI, **Large Language Models (LLMs)** face several limitations:
- Difficulty in multi-hop reasoning tasks
- Inefficiencies in biomedical text interpretation
- Struggles with quantitative reasoning

To address these limitations, this project leverages pre-trained and fine-tuned LLMs to predict the entailment relationship and extract supporting evidence.

---

## Baseline Models

We experimented with multiple LLMs as baseline models:
- **BERT**: General-purpose language model.
- **BioLinkBERT**: Specialized biomedical domain model.
- **GPT**: Advanced generative language model (GPT-3.5-turbo).

### Observations
1. **BERT and BioLinkBERT**:
   - Predicted most records as entailment.
   - Fine-tuning showed minimal impact on performance.
2. **GPT**:
   - Initially biased towards predicting contradiction.
   - Fine-tuning and prompt engineering significantly improved performance.
   - Outputs were highly sensitive to prompt phrasing.

---

## Approach

### Baseline Architecture
- **Input**: Prompts containing task descriptions and related CTR text.
- **Model**: Pre-trained LLMs (BERT, BioLinkBERT, GPT).
- **Output**: Inference relationship between input statements and context.

### Fine-Tuning Strategy
- Designed and tested various prompts to optimize model predictions.
- Focused on improving GPT's consistency with Chain-of-Thought (CoT) reasoning techniques.

---

## Results

- Fine-tuning improved GPT's performance significantly compared to BERT and BioLinkBERT.
- Prompts with clear, concise instructions produced the best results.
- GPT demonstrated high sensitivity to minor prompt adjustments, emphasizing the importance of prompt engineering.
- Despite improvements, there is still room for optimization, particularly on the gold practice test dataset.

---

## Dataset

---

## Contributions
### My Contributions
In this project, my contributions included:
- **Milestone 1**:
  - Conducted a comprehensive literature survey.
  - Contributed to project design and planning.
- **Milestone 2**:
  - Evaluated TF-IDF, BioLinkBERT, and BERT.
  - Co-authored the milestone report.
- **Milestone 3**:
  - Applied Chain-of-Thought (CoT) reasoning techniques.
  - Evaluated models on development and gold practice test datasets.
  - Co-authored the final report and prepared presentation slides.

### Collaborative Contributions
- Other team member focused on GPT-3.5-turbo, including fine-tuning and advanced prompt engineering.
- All authors contributed to literature survey, project design and planning, reports, and presentations.