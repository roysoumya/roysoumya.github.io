---
layout: page
title: Computational Brand Personality
description: Developing an integrated framework for understanding brand consistency from online content
img: assets/img/12.jpg
importance: 1
category: work

---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/branperspaperOverview.png" title="Method overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Method overview. This work is done for my M.S (Research) Thesis.
</div>

Publications: WebSci 2019 Full paper, TWEB Journal Paper 2021

### What is brand personality?

A consumer-dependent (business-to-consumer) organization tends to present itself as possessing a set of human qualities, which is a company’s brand perception. The perception is impressed upon the consumer through the content (be it in the form of advertisements, blogs, or magazines) produced by the organization.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/WhatIsBrandPersonality.png" title="Defining brand personality" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Defining brand personality
</div>


### What is the need for an automated, computational approach to brand personality detection and monitoring?

In this digital marketing era, a continuous generation of web content is needed to keep up consumer engagement and thus make a lasting impression on them. However, such content authoring at scale introduces challenges in maintaining consistency in a brand’s messaging tone.

## Our key contributions

We develop a quantitative technique to check whether the desired brand personality is maintained in a published article. Here, we quantify brand personality and formulate its linguistic features. We develop five independent classification models to score text articles extracted from brand communications on five personality dimensions: sincerity, excitement, competence, ruggedness, and sophistication.

We perform a large-scale data collection activity and collect around 300,000 web page content that covers around 650 Fortune 1000 companies. We also develop a novel deep learning architecture that leverages transfer learning to improve our classifier performance further.

We also study the effect of directly adding linguistic features to our neural architecture. The classifier automatically identifies the web articles which are not consistent with the mission and vision of a company.

A consistent brand will generate trust and retain customers over time since consumers look for regularity and common patterns. Studies have provided various strategies for maintaining the brand image over time and the impact of major company-related events like brand extension and mergers on it. However, there is no standard measure that quantifies the extent of brand inconsistency for a given company.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/brandConsistency.png" title="Research challenges for brand consistency" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Research Challenges related to Brand Consistency (ACM WebSci 2019)
</div>

We quantify brand consistency and study the company-level contributing factors like the effect of brand extensions.

We observe that promotion posts primarily portray competence as their brand personality across all brands and favor the brand consistency of companies that portrays competence in most of their posts (primary trait).

We find that the presence of brand extension-related posts reduces the brand consistency score of a company and that it is more challenging to maintain posts of a company with low topical consistency with the brand personality they want to evoke.

We discover companies that post consistently and find that financially affluent companies are better at maintaining consistency.

To address the brand inconsistency issue, we developed a helper tool that recommends the sentences that need to be modified to make the web article more consistent with the brand perception of the content writers.

**Keywords:** online reputation management, brand image, brand personality, brand consistency, text classification, transfer learning, sentence ranking

{% raw %}

{% endraw %}
