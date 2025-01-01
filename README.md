# Multi-Evidence Natural Language Inference for Clinical Trial Data (NLI4CT)
This repository documents my contributions to a team project addressing the challenge of **Multi-Evidence Natural Language Inference (NLI)** for Clinical Trial Reports (CTRs), focusing on **textual entailment** between CTR statements and premises.

---

## Overview
Clinical Trial Reports (CTRs) are the documents recording the outcomes of clinical 
trials, which tests the outcomes of potential medical interventions in order to 
guide interventions for patients. 
As the amount of CTRs increases, it becomes hard to analyze every CTR by humans. 
A good solution is to give the task to computers, specifically, to let language 
models work on clinical natural inference (NLI) tasks.

In this project, we are training a large language model (LLM) to make textual entailment given a pair of CTR premise and statement. 
We first summarize 3 challenges of the problem, and select several existing LLMs as baseline models, i.e. BERT, BioLinkBERT, and GPT3.5 after analysis based on literature. We then tested the baseline performances on the development dataset in order to choose an appropriate model based on the test results. 
We selected GPT3.5-turbo as our baseline model because of its robustness and good performance on many other related benchmark studies. 
We then conducted a lot of prompt engineering to find a best-fit prompt setting for this task, and also fine-tuned the model with extracted prompts from the training dataset. 
We applied several settings of prompts including Chain of Thoughts (CoT) prompting 
on the original and the fine-tuned model. 
The evaluation results on the development dataset show that the fine-tuned model performs good and its performance could be further improved with the use of CoT.

---

## Task: Textual Entailment
This task is based on a collection of breast cancer CTRs (extracted from https://clinicaltrials.gov/ct2/home), statements, explanations, and labels annotated by domain expert annotators.
The task involves:

1. **Predicting entailment**: Assessing the inference relationship (entailment vs contradiction) between a CTR premise and a statement.
2. **Evidence extraction**: Extracting evidence from the CTR to support the entailment label.

For the task, we have CTRs into 4 sections:
- Eligibility criteria - A set of conditions for patients to be allowed to take part in the clinical trial
- Intervention - Information concerning the treatment type, dosage, frequency, and duration being studied.
- Results - Number of participants in the trial, outcome measures, units, and the results.
- Adverse events - These are signs and symptoms observed in patients during the clinical trial.

For this task, each CTR may contain 1-2 patient groups, called cohorts or arms. These groups may receive different treatments, or have different baseline characteristics.

---

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