---
layout: page
title: Clinical trial search
description: Developing an aspect-based clinical trial search and an interpretable system using the Pubmed citation network
img: assets/img/3.jpg
importance: 2
category: work
giscus_comments: true
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mpss_overview.png" title="Method overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Method overview of proposed metapath-based similarity search (MPSS).
</div>

Clinical trials are an essential source of information for practicing Evidence-Based Medicine because they help to determine the efficacy of newly developed treatments and drugs. However, most of the existing trial search systems focus on a specific disease (e.g., cancer) and utilize disease-specific knowledge bases that hinder the adaptation of such methods to new diseases. 

In this work, we overcome both limitations and propose a graph-based model that explores both clinical trials and the Pubmed databases to alleviate the shortage of relevant clinical trials for a query. We construct a large heterogeneous graph (750K nodes and 1.2 Million edges) made of clinical trials and Pubmed articles linked to clinical trials.

As both the graph edges and nodes are labeled, we develop a novel __metapath-based similarity search__ (MPSS) method to retrieve and rank clinical trials across multiple disease classes. We primarily focus on consumers and users that do not have any prior medical knowledge. 

As there are no multiple disease-wide trial search evaluation datasets, we contribute a high-quality, well-annotated query-relevant trial set comprising around 25 queries and, on average, approximately 95 annotated trials per query. We also perform a detailed evaluation of MPSS on the TREC Precision Medicine Benchmark Dataset, a disease-specific clinical trial search setting.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TCSS_COMPACT_model_Nov2022.png" title="Method overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Methodological overview of MPSS. A user enters a query in free-form text, and medical concepts are extracted from the query, which is then used to retrieve relevant trials for the clinical trials registry database. Our proposed metapath-based similarity search algorithm that uses the Pubmed bibliographic network is used to improve the retrieval performance of MPSS. We then introduce three meta-data-based ranking aspects of relevance, adversity, and popularity, as well as a single ranked list combining all the aspects through aspect-based rank fusion. MPSS follows a faceted search paradigm where the user is given the option to select any one (among four) ranking aspects based on the user's information need. We present the metapath as explanations in the final ranked list in case of the additional trials retrieved using Pubmed-enhanced retrieval, which makes the trial search results more explainable
</div>
