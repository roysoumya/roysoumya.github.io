---
layout: page
title: Efficient Pretraining of DNA Foundation Models
description: GeneMask and curriculum masking — making genomic foundation models faster to train and stronger in few-shot settings
img: assets/img/dna_foundation_models.jpg
importance: 3
category: current
---

## Overview

DNA foundation models such as DNABERT, Nucleotide Transformer, and LOGO are pretrained on the Human Reference Genome and have become standard tools for genomic sequence classification, regulatory element prediction, and downstream biological tasks. They are also computationally expensive to train, and the masking strategies inherited from natural language pretraining are a poor fit for DNA: the word-level and sentence-level semantics that NLP relies on are absent in genomic sequences.

This research line redesigns masked language modeling specifically for DNA, achieving substantial efficiency gains and improved few-shot performance.

## Research Contributions

**GeneMask: Pointwise mutual information masking** [ECAI 2023]. Standard masked language modeling masks tokens randomly, which is suboptimal for DNA where adjacent k-mers are strongly correlated. We proposed a pointwise mutual information-based masking scheme that jointly masks correlated tokens, encouraging the model to learn meaningful sequence dependencies rather than trivially predicting masked positions from neighboring context. The result: improved few-shot classification performance using just 10% of the standard pretraining steps — a 10x speedup with better downstream accuracy. [[ECAI 2023 paper](https://ebooks.iospress.nl/doi/10.3233/FAIA230492)]

**Curriculum masking for DNA transformers** [ECAI 2024]. Building on GeneMask, we developed a curriculum masking-based dynamic MLM technique that adapts masking difficulty during training. The method outperforms DNABERT-2 and Nucleotide Transformer on the Genome Understanding Evaluation (GUE) benchmark, in both few-shot and full-dataset settings. The curriculum approach is particularly valuable for genomic tasks where labeled data is expensive to collect. [[ECAI 2024 paper](https://ebooks.iospress.nl/doi/10.3233/FAIA240864)]

## Why This Matters

DNA foundation models are a substantial compute investment for the bioinformatics community. Training improvements that reduce the cost of pretraining or improve few-shot performance compound across all downstream applications — variant prediction, regulatory element classification, gene expression modeling, and many others. The masking design choices in this work are also a useful case study for biological sequence modeling more broadly, including protein language models and single-cell foundation models.

## Invited Presentation

In August 2025, I was invited to present this research thread at the [1st Symposium on Intersections: Statistical Genomics and Complex/Chronic Disease Biology](https://nibmg.ac.in/) at the National Institute of Biomedical Genomics (NIBMG), Kalyani.

## Related Work

The masking and tokenization design principles developed here also inform my [vocabulary adaptation research for medical language models](/projects/vocabulary_adaptation_medical_llms/), where similar questions arise about how subword units should be designed for specialized domains.