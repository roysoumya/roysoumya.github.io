---
layout: page
title: Medical Knowledge-aware Pretrained Language Models
description: Incorporating domain knowledge in various pretrained language models to improve performance in limited data scenarios
img: assets/img/7.jpg
importance: 3
category: work

---

# Fast pretraining of Gene Transformer Models

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/genemask-overview.png" title="Method overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Method overview of GENEMASK, our proposed masking algorithm for MLM training of gene sequences, where we randomly select mask centers over the input DNA string and locally select the span around the mask center with the highest Normalized Pointwise Mutual Information (NPMI-k) to mask
</div>

### Publications
ECAI 2023 Full paper. Awarded 3rd prize in poster presentation at the [4th Indian Symposium on Machine Learning](https://indoml.in/) (IndoML 2023) held at IIT Bombay for our ECAI 2023 work on fast pretraining of gene transformer models. 

# Knowledge-aware NLP models for Medical Forum Question Classification

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/medbert-overview.png" title="Method overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     (left) Anecdotal example from ICHI dataset where medical concept-bearing aspects (marked red) are high-lighted along with context (right) Methodology overview of MedBERT for medical forum question classification task
</div>

### Publications
CIKM 2021 Short paper.

{% raw %}

{% endraw %}