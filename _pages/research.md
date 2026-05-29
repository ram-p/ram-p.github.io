---
title: ""
permalink: /research/
excerpt_separator: <!--more-->
toc: true
author_profile: true
---
{% include toc %}

My research broadly focuses on resilience quantification and design in nonlinear systems and networks, under adversarial influences or system faults. A general theme in my research is **"ensuring safe and resilient behavior of systems under adversarial effects"**, in the context of systems operating in a hostile environment. 

Such effects can be modeled as: (a) arbitrary, bounded disturbances affecting system dynamics, (b) changes in the structure of actuated inputs, possibly through adversarial takeover, or (c) any sudden changes in system dynamics, often caused by component failures. This page briefly describes my contributions to this research theme.

# Resilience Quantification

A significant portion of my research has been devoted to assigning quantitative metrics to resilience of control systems, using control energy as a "proxy" for expended fuel. In simple terms, a *more resilient* control system would require *less additional energy* to achieve a task under adversarial effects. I introduce the metric of **"energetic resilience"** for such a quantification.

## Under Bounded Disturbances

The first contribution in resilience quantification considers simple linear systems subject to bounded disturbances, and attempts to quantify the "cost of disturbance" in regulating a system in finite time [[1]](#1). This quantification derives bounds on both additive and multiplicative metrics of the form
\\[
r_A = \sup_{\|x_0\|_2 \leq R} E_D - E_N; ~~~ r_M = \inf_{\|x_0\|_2 \geq R} \frac{E_N}{E_D},
\\]
where \\(E_N\\) and \\(E_D\\) are the energies used in the *nominal* and *disturbed* case respectively. Simply put, each metric measures the worst-case impact of the bounded disturbance on the energy expended by the system. The following figures show how these metrics vary with \\(R\\), the distance of \\(x_0\\) from the origin.

<img src="https://ram-p.github.io/images/rAvsR.png" alt = "Additive Metric" width="300"/> <img src="https://ram-p.github.io/images/rMvsR.png" alt = "Multiplicative Metric" width="300"/>

# Past Research

Here are some things I've worked on in the past. (See the [Publications](https://ram-p.github.io/publications/) section for more information.)

Optimization and IQCs
------
<img src="https://ram-p.github.io/images/Opt_IQC.png" alt = "Optimization and IQCs" width="300"/>

This work uses the framework of Integral Quadratic Constraints (IQCs), a tool from robust control, to analyze the convergence and noise amplification of gradient descent with varying step sizes. This varying step size is assumed to occur in a known interval. Building on prior constant step-size results, LMI conditions which are to be satisfied at each point in the step-size interval are constructed. This allows for certifying convergence rates and variance amplification of the iterate.

Multiple Models in Adaptive ILC
------
<img src="https://ram-p.github.io/images/MM-AILC.png" alt = "Multiple Models in AILC" width="300"/>

Based on the Multiple Models, Switching and Tuning (MMST) methodology, a new estimation and control procedure for discrete-time Adaptive Iterative Learning Control is proposed. This uses the analogy between the discrete-time axis and the iteration axis in Iterative Learning Control. Simulations demonstrate improved performance using multiple models for various classes of systems, even when tracking an iteration-varying reference.

Discrete-time Uncertainty and Disturbance Estimator
------
<img src="https://ram-p.github.io/images/DT-UDE.png" alt = "Discrete-time UDE" width="500"/>

A discrete-time version of the Uncertainty and Disturbance Estimator (UDE), a robust control strategy, is presented. This work proposes a new digital filter for disturbance estimation and compensation to derive a discrete-time error-based control law and prove stability. Interfacing with continuous-time systems uses a digital-analog converter and a zero-order-hold. A discrete-time controller—observer structure is also proposed, to address the case when only system outputs are accessible. Simulations on a variety of linear and nonlinear systems, including well-known systems in aerospace engineering and robotics, demonstrate the efficacy of the proposed methods.

# References

<a id="1">[1]</a> 
R. Padmanabhan, C. Bakker, S. A. Dinkar, and M. Ornik, ["How Much Reserve Fuel: Quantifying the Maximal Energy Cost of System Disturbances,"](https://ieeexplore.ieee.org/document/10886030) in _63rd IEEE Conference on Decision and Control (CDC)_, Milan, Italy, Dec. 2024. \[Available at [arXiv:2408.10913](https://arxiv.org/abs/2408.10913)\]