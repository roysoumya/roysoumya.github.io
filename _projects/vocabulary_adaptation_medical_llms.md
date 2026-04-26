---
layout: page
title: Vocabulary Adaptation for Medical Language Models
description: Making domain adaptation of medical LLMs practical — from 450 days to 45 hours, and why vocabulary still matters even for 128K-token LLMs
img: assets/img/vocabulary_adaptation.jpg
importance: 2
category: current
---

## Overview

Adapting general-purpose language models to medical text is a recurring bottleneck for clinical deployment. Medical vocabulary is dense with specialized terminology, abbreviations, and multi-word concepts that standard tokenizers fragment poorly. The result is degraded performance on clinical summarization, question answering, and decision support — exactly the tasks where deployment matters most.

This research line develops vocabulary adaptation methods that are both effective and computationally practical, spanning encoder models, sequence-to-sequence models, and modern large language models.

## Research Contributions

**Fragment score optimization for hyperparameter selection** [IJCAI 2024]. Hyperparameter tuning for vocabulary adaptation traditionally requires intermediate fine-tuning on hundreds of thousands of documents, which made the method effectively impractical. We showed that optimizing fragment score — a lightweight tokenization quality metric — closely approximates downstream task performance. This reduced fine-tuning time from approximately 450 days to 45 hours, transforming vocabulary adaptation from a research artifact into a deployable adaptation pipeline. [[IJCAI 2024 paper](https://doi.org/10.24963/ijcai.2024/683)]

**Adaptive BPE initialization** [EMNLP 2024 Findings]. Standard Byte-Pair Encoding tokenization ignores extension vocabulary even when the model vocabulary has been updated, defeating the purpose of vocabulary adaptation. We modified the BPE initialization step: after splitting at the character level, we perform longest substring matching with the extension vocabulary and merge any matches. This preserves domain-specific terminology during fine-tuning. [[EMNLP 2024 Findings paper](https://aclanthology.org/2024.findings-emnlp.863.pdf)]

**Vocabulary adaptation for large language models** [ACL 2025 Findings]. A natural assumption is that LLMs with very large vocabularies (Llama-3.1 8B has 128K tokens) no longer need vocabulary adaptation for medical text. We found this is not true. Through extensive benchmarking across Llama 2, Mistral, Qwen-2, and Llama-3.1 8B, multiple vocabulary adaptation strategies, two continual pretraining approaches, and three medical summarization datasets, we mapped the conditions under which vocabulary adaptation continues to pay off in the LLM era. The result is a practical guide for teams customizing LLMs for clinical text. [[ACL 2025 Findings paper](https://arxiv.org/abs/2505.21242)]

## Why This Matters for Clinical Deployment

The deployment story is underappreciated. Hospitals adapting off-the-shelf medical LLMs to their own EHR vocabularies, documentation patterns, and patient populations cannot afford months-long adaptation cycles. Methods that work in principle but require unrealistic compute budgets do not get used. The IJCAI 2024 result — making the method 240x faster — is what moves vocabulary adaptation from research curiosity to practical tool.

## Code and Resources

Public code is available for each paper through the repositories linked in the publications. The methods have been used by independent groups working on biomedical and clinical language model adaptation.

## Related Work

This adaptation methodology connects to my [efficient pretraining of biological foundation models](/projects/efficient_dna_foundation_models/) (where similar masking and tokenization choices apply to genomic sequences) and to my [current Stanford work on guideline-grounded clinical reasoning](/projects/guideline_grounded_reasoning/) (where adapted models are deployed in real clinical workflows).