---
layout: about
title: about
permalink: /
subtitle: PhD Student @ <a href='https://ece.umd.edu/'>UMD ECE</a> | <a href='https://www.iitr.ac.in/'>IIT Roorkee</a> Alum

profile:
  align: right
  image: profile_picture.png
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>PhD Student</p>
    <p>Electrical and Computer Engineering</p>
    <p>University of Maryland, College Park</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: false # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

Hey there! I'm a PhD student in Electrical and Computer Engineering at the [University of Maryland, College Park](https://ece.umd.edu/). I did my B.Tech in Electronics and Communication Engineering at [IIT Roorkee](https://www.iitr.ac.in/), where my thesis won the ECE department's **Best B.Tech Project Award**. I spend most of my time thinking about how to make AI systems both powerful and safe. My research interests lie at the intersection of **Mechanistic Interpretability, AI Safety, and Adversarial Robustness** of Vision-Language Models and LLMs.

My first foray into interpretability research led to a paper on improving theoretical guarantees of Integrated Gradients attribution methods, accepted at the **NeurIPS 2024 Interpretable AI Workshop**. This was followed by an extensive study on adversarial vulnerabilities in VLMs -- our reproducibility and enhancement work on Cross-Prompt Attacks was published in **TMLR** and received the **Best Paper Award at MLRC 2025** (presented at Princeton). We further extended this into **CroPA++**, accepted at the **NeurIPS 2025 Reliable ML Workshop**, introducing three-fold enhancements that made attacks transferable across images and models.

Currently, I'm working with [Dr. Sanghamitra Dutta](https://sites.google.com/site/sanghamitraweb/) at UMD on safety-critical features that interpretability tools usually overlook because they are *inactive* -- suppressed features whose silencing can turn refusals into compliance. Our latest work introduces the **Counterfactual Activation Potential (CAP)** to discover these features at scale, and suggests that jailbreaks may work partly by suppressing them rather than only by activating harmful ones (under review at **ICLR 2027**). I've also studied refusal geometry in VLMs, showing that their safety is encoded in a high-dimensional subspace yet gated by a single direction (under review at **TMLR**). Previously, I collaborated with [Dr. Koustuv Sinha](https://ai.meta.com/people/1137013061051895/koustuv-sinha/) at **META AI (FAIR)** on benchmarking world model understanding and anticipation mechanisms in Video Language Models, and with [Dr. Nagender Aneja](https://naneja.github.io/) at [Virginia Tech](https://ece.vt.edu/) on user-intervenable LLM pipelines that apply circuit-tracing interpretability methods for real-time model steering.

On the generative AI front, I developed **RIGS** -- a lightweight Riemannian-guided diffusion framework for synthetic signal data generation in collaboration with [BOSCH India](https://www.bosch.in/) (accepted at **CVIP 2026**). During my internship at [AuraML](https://www.auraml.com/), I built text-to-3D scene generation frameworks using Graph Diffusion Models for industrial simulation, contributing directly to their product [AuraSim](https://www.aurasim.ai/). I've also worked on multi-task RL with Diffusion Models at [IIIT Hyderabad's Robotics Research Centre](https://robotics.iiit.ac.in/), and on medical AI pipelines at [IIT Bombay's Koita Centre for Digital Health](https://www.kcdh.iitb.ac.in/) as part of the BharatGen consortium.

Beyond research, I led the [Data Science Group at IIT Roorkee](https://dsgiitr.in/) as Joint Secretary, heading the research division. Under my tenure, our members published 15+ papers at venues like NeurIPS, CVPR, and ICLR -- most led solely by undergraduate teams. I also serve as a reviewer for **TMLR**.

When I'm not debugging code or reading papers, you'll probably find me at campus chai spots discussing the latest ML papers, or exploring College Park's food scene. Feel free to reach out if you want to chat about research, collaborate on projects, or just grab a cup of chai!
