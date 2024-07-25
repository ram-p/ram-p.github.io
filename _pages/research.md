---
layout: archive
title: ""
permalink: /research/
author_profile: true
---

Here are some things I've worked on in the past. (See the [Publications](https://ram-p.github.io/publications/) section for more information.)

Optimization and IQCs
------
<img src="https://ram-p.github.io/images/Opt_IQC.png" alt = "Optimization and IQCs" width="400"/>

This work uses the framework of Integral Quadratic Constraints (IQCs), a tool from robust control, to analyze the convergence and noise amplification of gradient descent with varying step sizes. This varying step size is assumed to occur in a known interval. Building on prior constant step-size results, LMI conditions which are to be satisfied at each point in the step-size interval are constructed. This allows for certifying convergence rates and variance amplification of the iterate.

Multiple Models in Adaptive ILC
------
<img src="https://ram-p.github.io/images/MM-AILC.png" alt = "Multiple Models in AILC" width="400"/>

Based on the Multiple Models, Switching and Tuning (MMST) methodology, a new estimation and control procedure for discrete-time Adaptive Iterative Learning Control is proposed. This uses the analogy between the discrete-time axis and the iteration axis in Iterative Learning Control. Simulations demonstrate improved performance using multiple models for various classes of systems, even when tracking an iteration-varying reference.

Discrete-time Uncertainty and Disturbance Estimator
------
<img src="https://ram-p.github.io/images/DT-UDE.png" alt = "Discrete-time UDE" width="400"/>

A discrete-time version of the Uncertainty and Disturbance Estimator (UDE), a robust control strategy, is presented. This work proposes a new digital filter for disturbance estimation and compensation to derive a discrete-time error-based control law and prove stability. Interfacing with continuous-time systems uses a digital-analog converter and a zero-order-hold. A discrete-time controller—observer structure is also proposed, to address the case when only system outputs are accessible. Simulations on a variety of linear and nonlinear systems, including well-known systems in aerospace engineering and robotics, demonstrate the efficacy of the proposed methods.