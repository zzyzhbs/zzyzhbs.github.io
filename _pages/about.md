---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<span class="anchor" id="about-me"></span>

I am a master's student in Computer Science and Engineering at UC San Diego (Class of 2027). Before UCSD I studied Computer Science at Wuhan University (B.Eng., 2021–2025) and spent the fall of 2023 at UC Berkeley on exchange. My interests are robotics software, lab automation and agent systems: control loops on real hardware, and the tests and logs that make them repeatable. Recent work includes closed-loop waypoint navigation on a Rubik Pi rover, workload modeling for Transformer inference on edge FPGAs at ICSLAB, Wuhan University, and linear probing of a text-to-music diffusion model.

<span class="anchor" id="projects"></span>

# Projects & Research

<div class="paper-box"><div class="paper-box-image"><div><div class="badge">ROS 2, Rubik Pi 3, 2026</div><a href="images/projects/nav_trajectory.png" target="_blank" rel="noopener"><img src="images/projects/nav_trajectory.png" alt="Estimated paths of seven navigation runs over three waypoints and three AprilTag landmarks, best run highlighted" width="100%"></a><p class="caption">Estimated paths of the 7 runs flagged complete; the best run is highlighted. Filter estimates, no external ground truth.</p></div></div>
<div class="paper-box-text" markdown="1">

**Closed-loop waypoint navigation with AprilTag landmarks**

<span class="meta">UC San Diego, Sep 2026 – present. Team of 2; responsible for scheme design and parameter tuning, calibration, sensor experiments, test tooling and real-robot validation. The navigation core was written by my teammate.</span>

A small rover drifts when it executes motion primitives open-loop, so after every primitive it stops, observes AprilTag landmarks, updates an SE(2) extended Kalman filter with chi-square gating, and replans. A fine spin-calibration level cut the smallest executable turn from about 24° to 3.05° (CCW) and 4.55° (CW). Across 24 archived runs, the best run ended with estimated residuals of 3.1, 3.3 and 5.1 cm at the three waypoints (filter estimates, no external ground truth).

**Current progress:** The navigation logic does not depend on ROS and passes 93 offline test cases, including runs against a simulated rover with systematic error. The 24 runs logged 184 landmark observations, and the 42 rejected ones were recorded with their reasons.

**Next:** The project is ongoing. The next three stages are Kalman-filter SLAM mapping (estimating the landmark map and the trajectory from an unknown start pose), path planning, and system integration.

<span class="links"><a href="https://github.com/zzyzhbs/apriltag-waypoint-navigation" target="_blank" rel="noopener">Code on GitHub</a> · <a href="https://www.youtube.com/shorts/DX3TtBoyumA" target="_blank" rel="noopener">Video</a></span>

</div></div>

<div class="paper-box no-image">
<div class="paper-box-text" markdown="1">

<span class="badge badge--inline">ICSLAB, Wuhan University, 2024–2025</span>

**Workload modeling and scheduling for Transformer inference on edge FPGAs**

<span class="meta">Research assistant, Aug 2024 – Jun 2025, advised by Prof. Dazhao Cheng.</span>

Non-linear Transformer operators are costly on FPGAs, and their resource demands are hard to schedule together. I simplified the operators with low-order polynomial approximation and integer quantization (after I-BERT), and modeled scheduling as integer nonlinear programming over resource vectors and a task dependency graph, solved by dynamic programming. In simulation the best static configuration, Fix(18,2,2,2), averaged 18.39% longer inference time than the dynamic-programming schedule. I also lead-wrote, on the PI's behalf, the lab's NSFC Young Scientists Fund (Category C) proposal.

</div></div>

<div class="paper-box"><div class="paper-box-image"><div><div class="badge">Mustango, SynTheory, 2026</div><a href="images/projects/mustango_probe.png" target="_blank" rel="noopener"><img src="images/projects/mustango_probe.png" alt="Bar chart of linear-probe accuracy by music-theory concept on Mustango representations, each against chance" width="100%"></a><p class="caption">Linear-probe accuracy by concept against chance, from the submitted notebook (section 2.2 table); the notes bar is a handcrafted chroma control, not the model. Tempo, a regression task, reached R² 0.74.</p></div></div>
<div class="paper-box-text" markdown="1">

**Probing music-theory concepts in a text-to-music diffusion model**

<span class="meta">UC San Diego, May – Jun 2026. Team of 4; responsible for the Mustango deployment, all Mustango probing experiments, and merging four models' results into one notebook.</span>

Does a latent-diffusion music generator encode music theory in its intermediate representations? Adapting the SynTheory probing method, I trained linear probes on Mustango's VAE latents and UNet activations over a 17-run sweep of layers and diffusion timesteps. Chord-type accuracy reached 0.88 on 1,000 clips (chance 0.25), while pitch-class accuracy from VAE latents stayed near chance (about 0.10 against 0.08) even with frequency-preserving pooling. A handcrafted chroma control on the same split reached 0.72, so the bottleneck is in the latent representation, not in the pooling.

</div></div>

<div class="paper-box"><div class="paper-box-image"><div><div class="badge">PLINK, GCTA, 2026</div><a href="images/projects/gwas_qq.png" target="_blank" rel="noopener"><img src="images/projects/gwas_qq.png" alt="Q-Q plot of observed against expected p-values for linear regression and the linear mixed model" width="100%"></a><p class="caption">Q-Q plot of observed against expected p-values for both methods on 118,836 variants, from the repository's results/plots.</p></div></div>
<div class="paper-box-text" markdown="1">

**A reproducible GWAS pipeline: linear regression versus linear mixed model**

<span class="meta">UC San Diego, Jan – Mar 2026. Team of 3; main contributor.</span>

Population structure inflates association statistics, so this pipeline takes 1000 Genomes CHB chromosome 22 (118,836 variants and 103 samples after QC), simulates a trait from 20 causal variants (seed 42), and runs PLINK linear regression against a GCTA linear mixed model, reporting λGC with Manhattan and Q-Q plots. An interactive driver checks the environment, runs the five steps in order, and retries or skips a failed step. Both methods gave λGC close to 1, a small change on a cohort that was already well mixed, so the run is a check of the pipeline rather than a demonstration of the mixed model's advantage.

<span class="links"><a href="https://github.com/zzyzhbs/gwas-lmm-comparison" target="_blank" rel="noopener">Code on GitHub</a></span>

</div></div>

<span class="anchor" id="education"></span>

# Education & Awards

<table class="edu">
<tr><td><strong>UC San Diego</strong><br>M.S. in Computer Science and Engineering, GPA 4.0/4.0</td><td class="date">Sep 2025 – 2027 (expected)</td></tr>
<tr><td><strong>Wuhan University</strong><br>B.Eng. in Computer Science and Technology, GPA 3.87/4.00</td><td class="date">Sep 2021 – Jun 2025</td></tr>
<tr><td><strong>UC Berkeley</strong><br>Exchange student, Berkeley Global Access, GPA 4.0</td><td class="date">Aug – Dec 2023</td></tr>
</table>

- NOIP 2019, First Prize, Shanxi Division (ranked 10 of 293)
- CCF CSP, top 10%
- Luojia Excellence International Exchange Scholarship, Wuhan University, 2024 (RMB 50,000)

<span class="anchor" id="contact"></span>

# Contact

Email is the best way to reach me: [s7yuan@ucsd.edu](mailto:s7yuan@ucsd.edu). Code is on [GitHub](https://github.com/zzyzhbs){:target="_blank" rel="noopener"}. A one-page résumé is linked as CV in the left column; a Chinese version is at the end of this page.

<span class="anchor" id="zh"></span>

# 中文摘要

袁盛琪，UCSD 计算机科学与工程硕士在读（2027 届），本科武汉大学。方向：机器人软件、实验室自动化、智能体系统。做过：Rubik Pi 小车 AprilTag 闭环航点导航（方案设计、标定、实车验证；项目仍在推进中，后续三个阶段依次为卡尔曼滤波 SLAM 建图、路径规划与系统集成）；边缘端 Transformer 推理调度（最优静态配置 Fix(18,2,2,2) 的平均推理时间比动态规划调度方案高 18.39%；受托主笔青年科学基金申请书）；Mustango 乐理探测（和弦 0.88，随机 0.25）；GWAS 流水线（PLINK 对 GCTA）。[中文简历（PDF）](pdf/Shengqi_Yuan_Resume_ZH.pdf)
