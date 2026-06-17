---
layout: about
title: Home
permalink: /
subtitle: Postdoc at Stanford Medicine
#<a href='https://roysoumya.github.io/assets/pdf/own_cv.pdf'>Curriculum Vitae</a> |  <a href='https://datanalytics101.com'>Research Blog</a>

profile:
  align: right
  image: headshot.jpeg
  image_circular: true # crops the image to make it circular
  more_info: >
    <a href='https://roysoumya.github.io/assets/pdf/own_cv.pdf'>Resume</a> | 
    <a href='https://datanalytics101.com'>Research Blog</a>

news: false # includes a list of news items
latest_posts: false # includes a list of the newest posts
selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---
I build **medical language models that are reliable enough to deploy** — auditable against clinical guidelines, evaluated for *why* they fail rather than just whether they pass, and efficient enough to adapt to a clinical domain without a research-grade compute budget. My through-line across six years and 16+ peer-reviewed papers (SIGIR, ACL, IJCAI, EMNLP, ECAI, CIKM): the gap between medical AI that works in a paper and medical AI that a hospital can actually adopt.

I am a postdoctoral scholar working with [Prof. Tina Hernandez-Boussard](https://profiles.stanford.edu/tina-hernandez-boussard) at the [Division of Computational Medicine](https://computationalmedicine.stanford.edu/), Department of Medicine, Stanford University. My current work is in perioperative pain management, alongside a clinical team of surgeons, trauma physicians, and psychologists, on two fronts: developing auditable reasoning LLMs that ground clinical recommendations in established guidelines, and using LLMs to construct executable guideline pathways that reveal when real-world patient trajectories deviate from them — and whether those deviations help or harm.

That work sits at the meeting point of three threads I have built over the past six years. **Efficient adaptation** of medical and biological foundation models — vocabulary adaptation, adaptive BPE, and the GeneMask masking scheme — including a method that cut medical-model fine-tuning from an estimated 450 days to 45 hours. **Reliability evaluation** of clinical LLMs — a fine-grained USMLE reasoning-error taxonomy built with 44 medical experts, out-of-vocabulary impact studies, and benchmarking of single-cell and DNA foundation models — that asks where these systems break down once accuracy is no longer the only metric. And **guideline-grounded reasoning**, my current focus, which supplies the evidence base that clinical deployment demands. My [research](/research/) page walks through each in detail.

The most direct line to where frontier medical AI is heading runs through the reliability work: passing a multiple-choice licensing exam is not the same as reasoning safely from the right evidence, and most of my recent work is about closing that distance. Code and datasets are public wherever possible — including the [vocabulary-adaptation toolkit](https://github.com/gb-kgp/VocabReplace-Then-Expand) and our released USMLE expert-annotation resource — and the rest is on [GitHub](https://github.com/roysoumya).

Previously: PhD from IIT Kharagpur (2025); Research Associate at L3S Research Center / Leibniz University Hannover (2021–2023); AI Intern at Wipro GE Healthcare (2024–2025); and Research Intern at Adobe Research (2018). Full details are in my [resume](https://roysoumya.github.io/assets/pdf/own_cv.pdf).




