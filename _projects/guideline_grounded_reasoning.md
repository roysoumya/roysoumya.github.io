---
layout: page
title: Guideline-Grounded Clinical Reasoning
description: Auditable reasoning LLMs grounded in clinical guidelines, with applications in pain management and perioperative care
img: assets/img/guideline_reasoning.jpg
importance: 1
category: current
---

## Overview

How do we make medical language models trustworthy enough to support real clinical decision-making? My current research at Stanford Medicine, in collaboration with [Prof. Tina Hernandez-Boussard](https://profiles.stanford.edu/tina-hernandez-boussard) at the [Division of Computational Medicine](https://computationalmedicine.stanford.edu/), develops auditable reasoning LLMs that ground their outputs in established clinical guidelines.

Most current medical LLMs are evaluated on board-exam-style questions, but clinical deployment requires something different: models that explain their reasoning in terms clinicians can audit, defend recommendations against the evidence base hospitals already trust, and surface meaningful disagreement when patient cases depart from standard care.

## Core Research Questions

When do real-world patient trajectories deviate from clinical guidelines, and when do those deviations lead to better or worse outcomes? When clinicians depart from guideline-recommended care, is that adaptive expertise responding to patient specifics, or is it avoidable harm that the system should flag? And how can language models support this judgment rather than replace it — by grounding recommendations in the evidence base while leaving the clinical decision with the physician?

## Application Domains

The work focuses on two clinical settings where guideline adherence matters and deviation is common:

**Pain management.** Chronic pain affects roughly 50 million US adults, and opioid stewardship is a national clinical priority. Guidelines for pain management exist but are inconsistently applied across health systems, and the consequences of guideline departures are heavily studied but unevenly understood at the level of individual patient trajectories.

**Perioperative care.** Guideline-driven protocols substantially affect surgical outcomes, post-operative recovery, and complication rates. Deviation from perioperative guidelines is sometimes correct (patient-specific contraindications) and sometimes harmful (oversight, workflow gaps, communication failures). Distinguishing the two at scale is exactly the kind of problem auditable AI systems can address.

## Connection to Broader Research Program

This project integrates two earlier methodological threads with the missing ingredient for clinical deployment. **Efficient adaptation methods** (vocabulary adaptation, adaptive BPE tokenization, curriculum masking) make domain-specific LLMs practical to train and update in real settings. **Reliability evaluation frameworks** (the USMLE error taxonomy, doctor intent classification, OOV impact analysis) surface the failure modes that matter clinically. Guideline grounding adds the third leg: explicit alignment with the evidence base clinicians already use, making model outputs auditable rather than just plausible.

## Status

Active research, started September 2025.

## Related Work

This project builds on the methods developed in my [vocabulary adaptation work](/projects/vocabulary_adaptation_medical_llms/) and [reliability evaluation work](/projects/vocabulary_adaptation_medical_llms/), and extends the patient-trajectory thinking from my [Parkinson's Disease subtyping research](/projects/data_driven_parkinson_subtyping/) into the broader question of guideline-aligned care.