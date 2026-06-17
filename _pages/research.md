---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 3
---
# Research Vision

Frontier models now pass medical licensing exams, but passing a multiple-choice test is not the same as being safe to deploy. The questions that decide whether a clinical system earns trust are different: Does the model reason from the right evidence, or arrive at the right answer for the wrong reasons? Does it know when it is operating outside the guideline base it was validated on? Does it fail loudly and recoverably, rather than confidently and silently?

My research program is built around closing that gap. I want to build medical foundation models whose reasoning is auditable against the clinical evidence base, evaluated against open-ended clinical questions rather than sanitized benchmarks, and efficient enough to adapt to new specialties and modalities without prohibitive cost. The next step is moving from models that answer to systems that act — agentic clinical reasoning that constructs and follows guideline pathways, flags deviation, and keeps the clinician in authority throughout.

I am most excited by work that treats reliability, faithful reasoning, and real-world deployment as first-class research problems rather than afterthoughts — the conditions under which frontier AI actually reaches patient care.

# Research Areas of Interest

I work on **deployable medical language models** — making them efficient enough to run in real clinical workflows, reliable enough for clinical decision-making, and auditable against established medical guidelines.

My research program is organized around three connected threads. **Efficient pretraining and adaptation** addresses the cost of building and customizing medical foundation models. **Reliability evaluation** asks whether these models actually work when deployed, through fine-grained error analysis and benchmarking. **Guideline-grounded clinical reasoning**, my current focus at Stanford, develops auditable reasoning systems that ground LLM outputs in established clinical evidence. Together, these threads target the gap between research-grade medical AI and systems that hospitals can actually adopt.

## Thread 1: Efficient Pretraining and Adaptation of Medical Foundation Models

**Vocabulary Adaptation for Medical Language Models** [IJCAI 2024, EMNLP 2024 Findings, ACL 2025 Findings]

Adapting general-purpose language models to medical text is a recurring bottleneck for clinical deployment. Our [IJCAI 2024 paper](https://doi.org/10.24963/ijcai.2024/683) is the first work to use vocabulary adaptation for summarization tasks. By showing that fragment score optimization closely approximates downstream performance, we reduced fine-tuning time from 450 days to 45 hours, making the method practical for real adaptation pipelines.

Standard Byte-Pair Encoding tokenization ignores extension vocabulary even when the model vocabulary has been updated. We modified the BPE initialization step: after splitting at the character level, we perform longest substring matching with the extension vocabulary and merge any matches [[EMNLP 2024 Findings](https://aclanthology.org/2024.findings-emnlp.863.pdf)].

Our [ACL 2025 Findings paper](https://arxiv.org/abs/2505.21242) extended this line to large language models. We found that vocabulary adaptation remains necessary even for Llama 2, Mistral, Qwen-2, and Llama-3.1 8B with its 128K vocabulary, for medical text summarization. Through extensive benchmarking across multiple adaptation strategies, two continual pretraining approaches, and three medical summarization datasets, we mapped the conditions under which vocabulary adaptation pays off when customizing LLMs for clinical text.

**Efficient Pretraining of Biological Foundation Models** [ECAI 2023, ECAI 2024]

DNA foundation models such as Nucleotide Transformer, DNABERT, and LOGO are pretrained on the Human Reference Genome and are computationally expensive. The word- and sentence-level semantics that NLP relies on are absent in DNA sequences, so masked language modeling needs different design. In our [ECAI 2023 work](https://ebooks.iospress.nl/doi/10.3233/FAIA230492), we proposed a pointwise mutual information-based masking scheme (GeneMask) that jointly masks correlated tokens, achieving improved few-shot performance using just 10% of the standard pretraining steps.

In our [ECAI 2024 paper](https://ebooks.iospress.nl/doi/10.3233/FAIA240864), we developed a curriculum masking-based dynamic MLM technique that outperforms DNABERT-2 and Nucleotide Transformer on the Genome Understanding Evaluation benchmark, in both few-shot and full-dataset settings.

## Thread 2: Reliability Evaluation of Clinical Language Models

**Fine-grained Error Analysis of Medical LLMs** [SIGIR 2024]

Evaluating LLMs on medical tasks by accuracy alone misses the crucial question of *why* models fail. In our [SIGIR 2024 Resource paper](https://doi.org/10.1145/3626772.3657882), we asked GPT-4 to explain its predictions and reject other options on USMLE questions, generating long, detailed medical rationales (258 words on average). We found that GPT-4 rarely makes factual errors but frequently makes reasoning errors such as "sticking with the wrong diagnosis." Strikingly, the model's rationales for incorrect predictions were often judged correct by medical experts — a serious concern for clinical deployment.

We developed an error taxonomy in collaboration with medical students, then ran a large-scale annotation study using the Potato platform with 44 medical experts recruited through Prolific. We annotated 300 incorrect data points at a granular level with multi-label spans identifying error causes, and released the GPT-4 rationales and expert annotations as a public resource for the medical AI evaluation community.

**Doctor Intent Classification from Clinical Dialogues** [ECAI 2025]

Our [ECAI 2025 work](https://ebooks.iospress.nl/doi/10.3233/FAIA251359) is the first to identify physician intents in medical dialogues and develop a fine-grained intent taxonomy based on the SOAP framework. We annotated the ACI-Bench dialogue summarization dataset with our intent taxonomy using practicing doctors recruited via Prolific, then characterized novel patterns in doctor-patient dialogue trajectories. We benchmarked encoder models and LLMs on intent classification and next-intent prediction, and showed that intent filtering improves downstream medical dialogue summarization.

**Benchmarking Single-Cell Foundation Models** [WSDM Day 2025]

We performed a systematic evaluation of single-cell foundation models — scFoundation, GeneFormer, and scGPT — on cell-type annotation tasks, identifying conditions where these models help and where they break down [[WSDM Day 2025](https://doi.org/10.1145/3701551.3708811)].

**Long-tail Robustness of LLMs and RAG** [LREC 2026]

Our forthcoming LREC 2026 paper, *LongTailQA: Benchmarking LLMs and RAG Models on Disambiguated Long-Tail Entities*, evaluates how language models and retrieval-augmented systems perform on rare entities — a year-long collaboration with PhD students at L3S Research Center, Germany.

## Thread 3: Guideline-Grounded Clinical Reasoning *(current focus, Stanford Medicine)*

At Stanford, I am developing auditable reasoning LLMs that ground clinical recommendations in established medical guidelines, working with [Prof. Tina Hernandez-Boussard](https://profiles.stanford.edu/tina-hernandez-boussard) at the Division of Computational Medicine. The core question: *when do real-world patient trajectories deviate from clinical guidelines, and when does that deviation lead to better or worse outcomes?* Application areas include pain management and perioperative care.

This work integrates the methods from Threads 1 and 2 — efficient adaptation to make models deployable, and rigorous evaluation to make them trustworthy — with the missing piece needed for clinical deployment: explicit grounding in the evidence base that hospitals already use.

**Transparent Patient Subtyping of Parkinson's Disease**

Earlier work in this thread developed a novel, interpretable decision-tree-based method to identify six clinically meaningful Parkinson's Disease subtypes, validated across two independent cohorts (LRRK2 and MDS). Unlike clustering approaches, the model offers reproducible, transparent diagnostic rules. Key findings: subtypes are characterized by persistent asymmetry, long disease duration (≥10 years), and postural instability; early-onset subtype E4 shows favorable prognosis; mixed-onset subtypes M3 and M7 link to faster decline; late-onset subtypes L2 and L4 correlate with reduced quality of life. These results support more personalized therapeutic strategies and better prognostic guidance in PD care. Published in Frontiers in Artificial Intelligence (2025), in collaboration with Hannover Medical School and L3S Research Center.

## Applied and Translational Work

**AuriCare: Holistic Pain Management** [Boston GrandHack 2026] — Co-developed at MIT Hacking Medicine's Boston GrandHack 2026, applying clinical decision support principles to chronic pain workflows.

**Patent filing (2025)** — Co-inventor on a deep learning-based representation learning system for sensor log data from medical imaging equipment, enabling anomaly detection and predictive maintenance (Wipro GE Healthcare).

## Foundational Work

**Medical Domain Knowledge in NLP Models** [CIKM 2021, ICDH 2023]

Earlier PhD work that motivated the current research program. I built a knowledge-aware dual-encoder BERT model where an additional encoder focuses on medical concept-bearing words extracted using QuickUMLS, for medical forum question classification [[CIKM 2021](https://doi.org/10.1145/3459637.3482128)]. I also developed an interpretable, disease-independent clinical trial search system that addresses the sparsity of clinical trial graphs by incorporating the PubMed citation network for metapath-based similarity search [[ICDH 2023](https://ieeexplore.ieee.org/document/10224716/), Best Student Paper Candidate].

## Research Projects

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
