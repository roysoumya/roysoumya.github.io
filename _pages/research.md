---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 3
---
# Research Areas of Interest

## Theme 1: Benchmarking and Fine-grained Domain-specific Evaluation of Foundation Models [SIGIR 2024, ECAI 2025]
In our ECAI 2025, we are the first work to identify doctor intents from medical dialogues and develop fine-grained intent taxonomy based on the popular SOAP framework. We annotated the ACI-Bench dataset, a popular medical dialogue summarisation dataset, with our proposed intent taxonomy, using real doctors, crowd-sourced from Prolific. We learn novel patterns of dialogue trajectories within doctor-patient dialogues. We benchmarked popular encoder models and LLMs on intent classification and next intent prediction tasks. Finally, we found that intent filtering helps to improve downstream tasks of medical dialogue summarisation.

In our SIGIR 2024 Resource paper, we point out evaluating LLMs based on accuracy is incomplete without understanding the thinking process and reasoning used by GPT-4 or other LLMs. We ask GPT-4 to explain its prediction and why it reject the other options. These responses are quite long (258 words on average), containing detailed medical explanations. We observe that GPT-4 rarely makes any factual errors and mostly makes reasoning errors like "Sticking with the Wrong Diagnosis". The model rationales for the incorrect predictions by GPT-4 were found to be correct by the medical experts, highlighting a major concern. We develop an error taxonomy to evaluate model explanations or rationales in collaboration with medical students. We then launch a large-scale annotation study using the Potato annotation platform and recruit 44 medical experts through Prolific, a well-known crowdsourcing platform. We annotated 300 out of these 919 incorrect data points at a granular level for different classes and created a multi-label span to identify the reasons behind the error. We make these resources (GPT-4 rationales along with expert annotations) publicly available.


## Theme 2: Vocabulary Adaptation for Fine-tuning Pre-trained Language Models for Classification and Summarisation Tasks [IJCAI 2024, EMNLP 2024 Findings, ACL 2025 Findings]
Our IJCAI 2024 paper is the first work to use vocabulary adaptation for summarization tasks. Since the hyperparameter tuning step involves an intermediate fine-tuning step on 300K documents, we showed that optimizing fragment score closely approximates the downstream task performance; this reduced the fine-tuning time from 450 days to 45 hours. 

Although the original model vocabulary gets updated by adding target domain vocabulary, the standard Byte-Pair Encoding tokenization ignores the extension vocabulary. We modify the BPE initialization step. After splitting at the character level, we perform the longest substring matching with the extension vocabulary, and merge any matches [[EMNLP 2024](https://aclanthology.org/2024.findings-emnlp.863.pdf)]. 

In our [ACL 2025 paper](https://arxiv.org/abs/2505.21242), we observed a breakthrough result - vocabulary adaptation is required even for LLMs (Llama 2, Mistral, Qwen-2), even for Llama-3.1 8B with 128K vocabulary size for medical text summarization. Through extensive benchmarking of multiple vocabulary adaptation strategies, two continual pretraining strategies, and three benchmark medical summarization datasets, we gain valuable insights into the role of vocabulary adaptation strategies for customizing LLMs to the medical domain.

## Theme 3: Efficient Training and Fine-grained Evaluation of Biological Foundation Models [ECAI 2023, ECAI 2024, WSDM Day 2025]
DNA foundation models such as Nucleotide Transformer, DNABert, and LOGO, are pretrained on the Human Reference Genome and are computationally expensive. Word and sentence-level semantics of NLP are absent for DNA sequences. In our ECAI 2023 work, we proposed a novel Masked Language Modeling masking scheme that improved the few-shot performance while using just 10% of the total pretraining steps. 

In our [ECAI 2024 paper](https://ebooks.iospress.nl/doi/10.3233/FAIA240864), we develop a curriculum masking-based dynamic MLM masking technique to outperform DNABERT-2 and Nucleotide Transformer for both few-shot and full dataset settings on the Genome Understanding Evaluation benchmark. 

We performed a systematic evaluation of single-cell foundation models such as scFoundation, GeneFormer and scGPT on cell-type annotation tasks [WSDM Day 2025].

## Theme 4: Incorporating Medical Domain Knowledge into NLP Models [CIKM 2021, ICDH 2023]
I developed a disease-independent clinical trial search system and improved retrieval performance by incorporating the Pubmed citation network, to address the sparsity issue of clinical trial graph network [ICDH 2023]. 

I developed a dual-encoder BERT model where the additional encoder focused on the medical concept-bearing words extracted using QuickUMLS [CIKM 2021].

# Research Projects

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
