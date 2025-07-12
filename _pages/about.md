---
layout: about
title: about
permalink: /
subtitle: <a href='https://roysoumya.github.io/assets/pdf/own_cv.pdf'>Curriculum Vitae</a>

profile:
  align: right
  image: profile-square-suit.jpg
  image_circular: true # crops the image to make it circular
  more_info: >
    <p> Address: </p>
    <p>Complex Networks Research Lab, Dept. of CSE,</p>
    <p>Indian Institute of Technology Kharagpur,</p>
    <p>West Bengal, India - 721302</p>
    <a href='https://roysoumya.github.io/assets/pdf/own_cv.pdf'>Curriculum Vitae</a>

news: true # includes a list of news items
latest_posts: false # includes a list of the newest posts
selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

I defended my PhD in May 2025 on the topic ``Domain Adaptation for Medical Language Understanding" at the Department of Computer Science and Engineering of Indian Indian Institute of Technology Kharagpur, working with [Prof. Niloy Ganguly](http://www.facweb.iitkgp.ac.in/~niloy/) and [Prof. Shamik Sural](http://www.facweb.iitkgp.ac.in/~shamik/). I was part of the [Complex Networks Research Group (CNeRG)](https://cnerg-iitkgp.github.io/) at IIT Kharagpur.

My PhD thesis proposes novel domain adaptation techniques to effectively and efficiently adapt open-domain AI models to the medical domain. I work at the intersection of Natural Language Processing and Artificial Intelligence for Medicine.

Please go through my [CV](https://roysoumya.github.io/assets/pdf/own_cv.pdf) for further details.

## Previous Research Experience

My primary area of research is Natural Language Processing, with expertise in medical and healthcare applications. My research areas of interest are Foundation Models for Medicine, Generative AI, Text Summarization, and Efficient Pretraining. My Ph.D thesis “Domain Adaptation for Medical Language Understanding” explored various domain adaptation techniques to incorporate medical domain knowledge in pretrained language models (both textual and genomics domains). We observed that domain adaptation and sophisticated fine-tuning led to better performance, faster pretraining, and more fine-grained evaluation.

After submitting my Ph.D, I was a Ph.D intern at the Health Innovation and Technology Centre of GE Healthcare India where I develop generative AI-based patient data models of oncology patients and build downstream applications built using Chroma vector database and LangChain, to help clinicians easily navigate patient notes. I delivered a tutorial “Building Trustworthy AI Models for Medicine: From Theory to Applications" at WSDM 2025, a top-tier Al conference in March 2025. I have spent 2.5 years at the [Leibniz AI Future Lab](https://leibniz-ai-lab.de/), [L3S Research Center](https://www.l3s.de/) in Germany, working with [Prof. Wolfgang Nejdl](http://www.kbs.uni-hannover.de/~nejdl/). Here, I collaborated with the Hannover Medical School, on identifying novel patient subtypes of Parkinson's Disease using clinical and genomic data. Here, I also worked of developing efficient pretraining of DNA foundation models like DNABERT.I completed my MS (Research) degree from IIT Kharagpur in 2019. Here, I developed text classification and sentence-level recommendation solutions that assist reputation management experts in managing brand content on corporate websites. During my B.Tech from Kalyani Govt. Engineering College, West Bengal, I also secured the [Indian Academic of Sciences](https://www.ias.ac.in/) Summer Research Fellowship, and spent three months summer internship at IIT Kharagpur.

### Theme 1: Efficient Training and Fine-grained Evaluation of Biological Foundation Models [ECAI 2023, ECAI 2024, WSDM Day 2025]
DNA foundation models such as Nucleotide Transformer, DNABert, and LOGO, are pretrained on the Human Reference Genome and are computationally expensive. Word and sentence-level semantics of NLP are absent for DNA sequences. In our ECAI 2023 work, we proposed a novel Masked Language Modeling masking scheme that improved the few-shot performance while using just 10% of the total pretraining steps. In our ECAI 2024 paper, we develop a curriculum masking-based dynamic MLM masking technique to outperform DNABERT-2 and Nucleotide Transformer for both few-shot and full dataset settings on the Genome Understanding Evaluation benchmark. We performed a systematic evaluation of single-cell foundation models such as scFoundation, GeneFormer and scGPT on cell-type annotation tasks [WSDM Day 2025].

### Theme 2: Vocabulary Adaptation for Fine-tuning Pre-trained Language Models for Classification and Summarisation Tasks [IJCAI 2024, EMNLP 2024 Findings]
Our IJCAI 2024 paper is the first work to use vocabulary adaptation for summarization tasks. Since the hyperparameter tuning step involves an intermediate fine-tuning step on 300K documents, we showed that optimizing fragment score closely approximates the downstream task performance; this reduced the fine-tuning time from 450 days to 45 hours. Although the original model vocabulary gets updated by adding target domain vocabulary, the standard Byte-Pair Encoding tokenization ignores the extension vocabulary. We modify the BPE initialization step. After splitting at the character level, we perform the longest substring matching with the extension vocabulary, and merge any matches [EMNLP 2024].

### Theme 3: Incorporating Medical Domain Knowledge into NLP Models [CIKM 2021, ICDH 2023, SIGIR 2024]
I developed a disease-independent clinical trial search system and improved retrieval performance by incorporating the Pubmed citation network, to address the sparsity issue of clinical trial graph network [ICDH 2023]. I developed a dual-encoder BERT model where the additional encoder focused on the medical concept-bearing words extracted using QuickUMLS [CIKM 2021].
