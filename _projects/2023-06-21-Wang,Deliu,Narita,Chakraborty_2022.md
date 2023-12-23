---
# layout: post
title: Wang, Deliu, Narita, Chakraborty (2022) 
date: 2023-06-21
description: "[06/21/23] SMART-EXAM: Incorporating Participants’ Welfare into Sequential Multiple Assignment Randomized Trials"
img: assets/img/POTD/Deming2023F7.png
importance: 2
tags: methodology
# category: Paper of the Day (POTD)
---
See paper [here](https://arxiv.org/abs/2210.16255).
#
### Abbreviations
- DTRs: Dynamic treatment regimes, sequences of decision rules that recommend treatments based on patients’ time-varying clinical conditions.
- SMART: Sequential multiple assignment randomized trial, an experimental design that can provide high-quality evidence for constructing optimal DTRs.
  - Conventional SMART: Participants are randomized to available treatments at multiple stages with balanced randomization probabilities.
  - STAR*D: Sequenced Treatment Alternatives to Relieve Depression, 1st-gen SMART, randomizes participants within their preferred treatment categories (switch or augment) during the second and third randomization stages.
  - SMART-AR: SMART with adaptive randomization, using Q-learning to determine the randomization probabilities in favor of superior treatments based on the complete data trajectories from previous participants in the trial.
  - RA-SMART: response-adaptive SMART, inferior treatment at stage 1 will have a lower randomization probability at stage 2.
  - SMART-EXAM [this paper]: incorporates participants’ preferences and predicted treatment effects into the randomization procedure, has the potential to improve participants’ welfare in terms of both the participants’ (already enrolled and future patients) preferences and their final outcomes.
- SDM: Shared decision making, where healthcare providers and patients exchange information about patient’s disease-related characteristics and the benefits and side effects of each treatment, and finally achieve a consensus about which treatment should be prescribed.
- RAR: Response-adaptive randomization, allow for potential adjustments of randomization probabilities, in accordance with accumulating information about the treatment performance.
- ACTE: Average choice-specific treatment effects, the conditional treatment effect among those who would choose a particular treatment option.
- EXAM: Experiment-as-Market, an extension of the RCT, allows for incorporating both participants’ preferences and treatment effects into the randomization procedure, while maintaining robust inferences comparable to RCTs. EXAM aims to strike a balance between making accurate inferences for future patients, and improving the welfare of enrolled participants through an imaginary centralized market (Narita, 2021).

### A generic two-stage SMART

- $$\left(\boldsymbol{O}_{1 i}, A_{1 i}, \boldsymbol{O}_{2 i}, A_{2 i}, Y_i\right)$$: the observed trajectory for the $$i$$-th participant, iid.
- $$\boldsymbol{O}_{t i}(t=1,2)$$: the vector of covariates obtained prior to treatment at stage $t$. 
- $$R_i$$ in $$\boldsymbol{O}_{2 i}$$: intermediate response status, with $R_i=1 / 0$ for responder and non-responders, respectively. 
- $$A_{t i}$$: treatment indicator of stage $$t$$. $$A_{1 i} \in\{-1,1\}, A_{2 i} \in\{-1,1\}$$ for non-responders, and $$A_{2 i}=0$$ for responders. 
- $$Y_i$$: final continuous outcome and WLOG, higher values of $$Y_i$$ are preferred. 
- $$\boldsymbol{H}_{t i} \in \mathcal{H}_t$$: history data of the $$i$$-th participant at stage $$t$$, with $$\boldsymbol{H}_{1 i}=\boldsymbol{O}_{1 i}, \boldsymbol{H}_{2 i}=\left(\boldsymbol{O}_{1 i}, A_{1 i}, \boldsymbol{O}_{2 i}\right)$$, where $$\mathcal{H}_t$$ is the space of possible histories at stage $$t$$.
- $$\boldsymbol{d}_j=\left(d_{j, 1}, d_{j, 2}\right)$$: j-th two-stage DTR, a vector of decision rules that map patient history data to one of the available treatments.
- $$Y^{d_j}=R^{a_1} Y^{s\left(a_1, 0\right)}+\left(1-R^{a_1}\right) Y^{s\left(a_1, a_2\right)}$$: PO under DTR $$\boldsymbol{d}_j=\left(a_1, a_2\right)$$.
- $$\boldsymbol{d}^*=\underset{d_j \in \mathcal{D}}{\arg \max } \mu_{d_j}$$: optimal DTR, DTR with the highest expected outcome $$\mu_{d_j}$$.
- Inverse probability weighting (IPW) estimator for the expected outcome of DTR $$\boldsymbol{d}_j=\left(a_1, a_2\right)$$: $$\hat{\mu}_{\boldsymbol{d}_j}=\frac{\sum_{i=1}^N W_i^{\boldsymbol{d}_j} Y_i}{\sum_{i=1}^N W_i^{\boldsymbol{d}_j}}$$, where $$N$$ is the total sample size, $$W_i^{d_j}=\frac{I\left(A_{1 i}=a_1\right)}{p_{1, a_1, i}}\left\{R_i+\frac{\left(1-R_i\right) I\left(A_{2 i}=a_2\right)}{p_{2, a_2, i}}\right\}$$ is the weight of the $$i$$-th individual for DTR $$\boldsymbol{d}_j=\left(a_1, a_2\right), p_{1, a_1, i}=\operatorname{Pr}\left(A_{1 i}=a_1\right)$$, and $$p_{2, a_2, i}=\operatorname{Pr}\left(A_{2 i}=a_2 \mid R_i=0\right)$$.