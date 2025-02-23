---
title: Adjusted Weekly Plan(with LLMs) - CSE Sophomore
author: jaeman
date: 2025-02-24 05:02:00 +0900
categories: [CSE Undergraduate, Plan]
tags: [Plan, CSE, ML, Mathematics, LLM]
toc: true
---
# Problems with the previous plan
Although the plan was good. But while I'm trying to execute it, I've found several realistic problems.
- **Lack of Math Knowledge(Linear Algebra, Calculus)**\
so it was hard to understand the formula and explanation.
- **Different suggestions**\
I tried several LLMs(ChatGPT, Claude, Grok, Deepseek), but of course all of them have gave me the different answers.\
But for me, An Undergraduate Student, it was hard to select and modify the plan they gave me.
- **Different Focus**\
The LLMs have gave me very different answer when I change the terms. *(e.g efficient and fast -> efficient)*\
Even the focus were changing(too shallow, too many resources, out of scope)\
So I had to fixed my requirements and conditions.

# New method
1. **Ask again with Format, Role, Focusing point, Requirement, My situasion**\
    So I rewrote the prompt mentioning some of their answer.
    ```
    As a professional AI researcher. imagine you're making it for a student do entire questions
    [former CSV table format including data]
    keeping
    Advanced Focus: Resources go beyond undergraduate basics (e.g., introductory Python or linear algebra) and dive into theoretical and practical depths of ML/DL.
    Research-Oriented: Includes seminal papers and recent works to align with your goal of following cutting-edge research.
    Master’s Preparation: Structured to help you explore specializations (e.g., NLP, computer vision) and build a strong application profile.
    Evidence-Based: Recommendations are grounded in widely recognized materials used in academia and industry.
    [my-plan-period]
    [my-time-table]
    ```
    And I used the function (deep think/reason/... anyway)
2. **Let them judgement their responses**\
   I also requested to make CSV table of the plan.\
   And then copied All of them and ask again with the function
   ```
   1. [CSV1]
   2. [CSV2]
   3. [CSV3]
   which is the best of all?
   and which is the best of only study?
   ```
   I asked "only study" because their answer contained community, forum and Master preparation

# Got the Satisfactory grain
for my situation, it was Deepseek>ChatGPT>Grok>Claude\
also I was very amazed of Deepseek's analytical answers. The quality was pretty high.\
So, after some of formatting and adjustment. it is done!\
And I don't think I would change the plan even if I didn't complete it, I would just re-schedule to finish them.
## Math Plan Table(part of)
| **Focus Area** | **Learning Objectives** | **Resources (Books/Papers)** | **Courses/Video Lectures** | **Hands-on Tasks** | **Community/Research Engagement** | **Deliverables/Outputs** |
|---|---|---|---|---|---|---|
| Supervised Learning & Optimization | Master ML fundamentals: loss functions, gradients, SGD | PRML (Ch. 1-3); SGD paper (Robbins & Monro, 1951) | CS229 (Supervised Learning) | Implement logistic regression from scratch | Join ML forums (e.g., Reddit r/MachineLearning) | Code + report comparing SGD variants |
| Advanced Linear Algebra & Matrix Computations | Explore SVD, eigen-decomposition, and their theoretical implications | Advanced sections in MML; Recent papers on matrix factorization in DL | YouTube seminars by 3Blue1Brown (advanced topics) | Implement SVD/PCA from scratch, analyze datasets | Share findings on GitHub and forums | SVD/PCA implementation with analysis report |
| Neural Network Mechanics | Understand backpropagation, activation functions | Deep Learning (Ch. 6); Backprop paper (Rumelhart et al., 1986) | MIT 6.S191 (Intro to Deep Learning) | Code a 3-layer MLP with NumPy | Engage in online study groups (Slack/Discord) | MLP implementation with ablation study |
| Regularization & Evaluation | Advanced model tuning: dropout, batch norm | DL Book (Ch. 7); Dropout paper (Srivastava et al., 2014) | CS231n (Training Neural Networks I) | Implement dropout/BatchNorm in PyTorch | Discuss results and adjustments on discussion boards | Trained model with regularization analysis |
| Convolutional Networks (CV) | Learn CNN architectures, pooling, strides | DL Book (Ch. 9); AlexNet paper (Krizhevsky et al., 2012) | CS231n (CNNs) | Build a CNN for CIFAR-10 classification | Post training metrics and troubleshooting tips online | CNN codebase + accuracy report |
| Residual Networks (CV) | Study skip connections, deep network training | ResNet paper (He et al., 2016) | CS231n (Advanced CNN Architectures) | Implement ResNet-18 on TinyImageNet | Collaborate with peers for design review | ResNet code + training curves |
| Attention Mechanisms | Explore self-attention, transformer basics | Attention Is All You Need (Vaswani et al., 2017) | CS224n (Transformers) | Code a single-head attention layer | Discuss challenges in study groups and on GitHub | Attention implementation with visualization |
| Optimization Deep Dive | Advanced optimizers: AdamW, LAMB | Adam paper (Kingma & Ba, 2017); Deep Learning Tuning Playbook | Fast.ai (Practical Deep Learning) | Benchmark optimizers on a vision task | Share experiment results on GitHub or forums | Optimizer comparison dashboard |
| VAEs & GANs | Latent variable models, adversarial training | VAE paper (Kingma & Welling, 2013); GAN paper (Goodfellow et al., 2014) | CS236 (Deep Generative Models) | Train a DCGAN on CelebA | Engage in discussions about training challenges | Generated samples + FID score report |
| Transformers & BERT (NLP) | Pre-training, fine-tuning strategies | BERT paper (Devlin et al., 2018); RoBERTa analysis (Liu et al., 2019) | Hugging Face NLP Course | Fine-tune BERT for sentiment analysis | Participate in online transformer discussions | Fine-tuning notebook + accuracy metrics |
| Diffusion Models | Score-based generative models | DDPM paper (Ho et al., 2020); DDIM paper (Song et al., 2021) | Stable Diffusion Tutorials | Implement a 1D diffusion process | Engage with the research community via Twitter/LinkedIn | Diffusion code + generated samples |
| Vision Transformers (NLP, CV) | Patch embeddings, hybrid architectures | ViT paper (Dosovitskiy et al., 2020); DeiT (Touvron et al., 2021) | CS231n (Vision Transformers) | Train ViT on CIFAR-100 | Post initial findings on an ML blog | ViT implementation + ablation study |
| Paper Analysis | Critique methodology of recent SOTA paper | Select 1 NeurIPS/ICLR 2023-24 paper (e.g., LLaMA, DALL-E 3) | Paper author talks on YouTube | Reproduce key figures/tables | Post critiques on academic blogs/discussion boards | Critical analysis report |
| System Implementation | Replicate core model components | Official codebase (if available); Supplementary materials | Clone GitHub repositories | Refactor code for readability | Share detailed replication notes on a blog or forum | Clean reimplementation + documentation |
| Hyperparameter Search | Bayesian optimization, multi-objective tuning | Hyperparameter paper (Snoek et al., 2012); Optuna Docs | Weights & Biases Tutorials | Run large-scale hyperparameter sweep | Discuss results and adjustments on discussion boards | Hyperparameter analysis dashboard |
| Benchmarking | Compare with baselines, compute metrics | ML reproducibility checklist (Pineau et al.) | MLOps Zoomcamp (Evaluation) | Test on 2+ datasets (e.g., ImageNet-1k, COCO) | Share experiment results on GitHub or forums | Benchmark report with statistical tests |
| Choose Track: CV/NLP/RL | Deep dive into subfield tools/libraries | CV: Detectron2 Docs; NLP: Hugging Face; RL: Stable Baselines3 | Advanced domain courses (e.g., CS234 for RL) | Build an end-to-end project (e.g., object detection pipeline) | Engage with mentors and specialized online groups | Project codebase + demo video |
| Novel Research Project | Formulate hypothesis, design experiments | Literature from arXiv (last 6 months) | Research group meetings (simulated via Discord) | Write preprint-style paper | Present findings in virtual meetups | Publishable manuscript + conference submission |
| Measure Theory | Probability spaces, Lebesgue integral | Royden Ch. 2-3 | Read Royden Ch. 2 (3 hrs); Solve Ex. 2.5 (2 hrs) | Measure theory notes; Sigma-algebra examples |  |  |
| Specialization Elective | Choose: NLP (BERT) or CV (ResNet) | BERT (Devlin et al., 2018) / ResNet (He et al., 2015) | Implement BERT embedding or ResNet block (5 hrs) | Code + performance report |  |  |
| Portfolio Prep | GitHub, summary document | - | Organize code/docs (3 hrs); Write READMEs (2 hrs) | GitHub repo; 1-page research summary |  |  |

## ML/DL Plan Table
| **Focus Area** | **Learning Objectives** | **Resources (Books/Papers)** | **Courses/Video Lectures** | **Hands-on Tasks** | **Community/Research Engagement** | **Deliverables/Outputs** |
|---|---|---|---|---|---|---|
| Supervised Learning & Optimization | Master ML fundamentals: loss functions, gradients, SGD | PRML (Ch. 1-3); SGD paper (Robbins & Monro, 1951) | CS229 (Supervised Learning) | Implement logistic regression from scratch | Join ML forums (e.g., Reddit r/MachineLearning) | Code + report comparing SGD variants |
| Advanced Linear Algebra & Matrix Computations | Explore SVD, eigen-decomposition, and their theoretical implications | Advanced sections in MML; Recent papers on matrix factorization in DL | YouTube seminars by 3Blue1Brown (advanced topics) | Implement SVD/PCA from scratch, analyze datasets | Share findings on GitHub and forums | SVD/PCA implementation with analysis report |
| Neural Network Mechanics | Understand backpropagation, activation functions | Deep Learning (Ch. 6); Backprop paper (Rumelhart et al., 1986) | MIT 6.S191 (Intro to Deep Learning) | Code a 3-layer MLP with NumPy | Engage in online study groups (Slack/Discord) | MLP implementation with ablation study |
| Regularization & Evaluation | Advanced model tuning: dropout, batch norm | DL Book (Ch. 7); Dropout paper (Srivastava et al., 2014) | CS231n (Training Neural Networks I) | Implement dropout/BatchNorm in PyTorch | Discuss results and adjustments on discussion boards | Trained model with regularization analysis |
| Convolutional Networks (CV) | Learn CNN architectures, pooling, strides | DL Book (Ch. 9); AlexNet paper (Krizhevsky et al., 2012) | CS231n (CNNs) | Build a CNN for CIFAR-10 classification | Post training metrics and troubleshooting tips online | CNN codebase + accuracy report |
| Residual Networks (CV) | Study skip connections, deep network training | ResNet paper (He et al., 2016) | CS231n (Advanced CNN Architectures) | Implement ResNet-18 on TinyImageNet | Collaborate with peers for design review | ResNet code + training curves |
| Attention Mechanisms | Explore self-attention, transformer basics | Attention Is All You Need (Vaswani et al., 2017) | CS224n (Transformers) | Code a single-head attention layer | Discuss challenges in study groups and on GitHub | Attention implementation with visualization |
| Optimization Deep Dive | Advanced optimizers: AdamW, LAMB | Adam paper (Kingma & Ba, 2017); Deep Learning Tuning Playbook | Fast.ai (Practical Deep Learning) | Benchmark optimizers on a vision task | Share experiment results on GitHub or forums | Optimizer comparison dashboard |
| VAEs & GANs | Latent variable models, adversarial training | VAE paper (Kingma & Welling, 2013); GAN paper (Goodfellow et al., 2014) | CS236 (Deep Generative Models) | Train a DCGAN on CelebA | Engage in discussions about training challenges | Generated samples + FID score report |
| Transformers & BERT (NLP) | Pre-training, fine-tuning strategies | BERT paper (Devlin et al., 2018); RoBERTa analysis (Liu et al., 2019) | Hugging Face NLP Course | Fine-tune BERT for sentiment analysis | Participate in online transformer discussions | Fine-tuning notebook + accuracy metrics |
| Diffusion Models | Score-based generative models | DDPM paper (Ho et al., 2020); DDIM paper (Song et al., 2021) | Stable Diffusion Tutorials | Implement a 1D diffusion process | Engage with the research community via Twitter/LinkedIn | Diffusion code + generated samples |
| Vision Transformers (NLP, CV) | Patch embeddings, hybrid architectures | ViT paper (Dosovitskiy et al., 2020); DeiT (Touvron et al., 2021) | CS231n (Vision Transformers) | Train ViT on CIFAR-100 | Post initial findings on an ML blog | ViT implementation + ablation study |
| Paper Analysis | Critique methodology of recent SOTA paper | Select 1 NeurIPS/ICLR 2023-24 paper (e.g., LLaMA, DALL-E 3) | Paper author talks on YouTube | Reproduce key figures/tables | Post critiques on academic blogs/discussion boards | Critical analysis report |
| System Implementation | Replicate core model components | Official codebase (if available); Supplementary materials | Clone GitHub repositories | Refactor code for readability | Share detailed replication notes on a blog or forum | Clean reimplementation + documentation |
| Hyperparameter Search | Bayesian optimization, multi-objective tuning | Hyperparameter paper (Snoek et al., 2012); Optuna Docs | Weights & Biases Tutorials | Run large-scale hyperparameter sweep | Discuss results and adjustments on discussion boards | Hyperparameter analysis dashboard |
| Benchmarking | Compare with baselines, compute metrics | ML reproducibility checklist (Pineau et al.) | MLOps Zoomcamp (Evaluation) | Test on 2+ datasets (e.g., ImageNet-1k, COCO) | Share experiment results on GitHub or forums | Benchmark report with statistical tests |
| Choose Track: CV/NLP/RL | Deep dive into subfield tools/libraries | CV: Detectron2 Docs; NLP: Hugging Face; RL: Stable Baselines3 | Advanced domain courses (e.g., CS234 for RL) | Build an end-to-end project (e.g., object detection pipeline) | Engage with mentors and specialized online groups | Project codebase + demo video |
| Novel Research Project | Formulate hypothesis, design experiments | Literature from arXiv (last 6 months) | Research group meetings (simulated via Discord) | Write preprint-style paper | Present findings in virtual meetups | Publishable manuscript + conference submission |
| Measure Theory | Probability spaces, Lebesgue integral | Royden Ch. 2-3 | Read Royden Ch. 2 (3 hrs); Solve Ex. 2.5 (2 hrs) | Measure theory notes; Sigma-algebra examples |  |  |
| Specialization Elective | Choose: NLP (BERT) or CV (ResNet) | BERT (Devlin et al., 2018) / ResNet (He et al., 2015) | Implement BERT embedding or ResNet block (5 hrs) | Code + performance report |  |  |
| Portfolio Prep | GitHub, summary document | - | Organize code/docs (3 hrs); Write READMEs (2 hrs) | GitHub repo; 1-page research summary |  |  |