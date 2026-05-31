---
title: ""
permalink: /research/
excerpt_separator: <!--more-->
toc: true
layout: archive
author_profile: true
---
{% include toc %}

My research broadly focuses on resilience quantification and design in nonlinear systems and networks, under adversarial influences or system faults. A general theme in my research is **"ensuring safe and resilient behavior of systems under adversarial effects"**, in the context of systems operating in a hostile environment. 

Such effects can be modeled as: (a) arbitrary, bounded disturbances affecting system dynamics, (b) changes in the structure of actuated inputs, possibly through adversarial takeover, or (c) any sudden changes in system dynamics, often caused by component failures. This page briefly describes my contributions to this research theme.

# Resilience Quantification

A significant portion of my research has been devoted to assigning quantitative metrics to resilience of control systems, using control energy as a "proxy" for expended fuel. In simple terms, a *more resilient* control system would require *less additional energy* to achieve a task under adversarial effects. I introduce the metric of **"energetic resilience"** for such a quantification.

## Under Bounded Disturbances

The first contribution in resilience quantification considers simple linear systems subject to bounded disturbances, and attempts to quantify the "cost of disturbance" in regulating a system in finite time [[1]](#1). This quantification derives bounds on both additive and multiplicative metrics of the form
$$
r_A = \sup_{\|x_0\|_2 \leq R} E_D - E_N; ~ r_M = \inf_{\|x_0\|_2 \geq R} \frac{E_N}{E_D},
$$
where \\(E_N\\) and \\(E_D\\) are the energies used in the *nominal* and *disturbed* case respectively. Simply put, each metric measures the worst-case impact of the bounded disturbance on the energy expended by the system. The following figures show how these metrics vary with \\(R\\), the distance of \\(x_0\\) from the origin.

<img src="https://ram-p.github.io/images/rAvsR.png" alt = "Additive Metric" width="300"/> <img src="https://ram-p.github.io/images/rMvsR.png" alt = "Multiplicative Metric" width="300"/>

## Under a Partial Loss in Control Authority

The focus now shifts to systems under actuation constraints that lose authority over a subset of their actuators, termed a *partial loss in control authority*. Such a setting has prior practical, real-world motivation [[2]](#2), and has seen some investigation in the past by Bouvier *et al.* ([[3]](#3) and referenced papers within). However, these works have considered only linear systems, with resilience quantification in terms of reachable time. Using control energy as above, I am able to derive approximate bounds on *energetic resilience* metrics, even for nonlinear systems.

The first part of this work [[4]](#4) considers simple linear, driftless dynamics and derives bounds on metrics similar to those defined earlier. These results are eventually used to approximate a bound on the additive metric for nonlinear systems [[5]](#5) using approximate bounds on the worst-case total energy used. A key result in this work is proving that the difference between system responses of linear driftless dynamics and nonlinear dynamics is bounded under appropriate structural conditions. The two figures below show the behavior of the different metrics, on the left for linear driftless systems, and on the right for nonlinear systems.

<img src="https://ram-p.github.io/images/DftRes.png" alt = "Driftless Systems" width="300"/> <img src="https://ram-p.github.io/images/NLRes.png" alt = "Nonlinear Systems" width="300"/>

## Under Temporal Logic Specifications

The work discussed above uses only simple specifications of reaching a target set. We are currently exploring extending the notion of energetic resilience to systems with more complex specifications encoded through temporal logic. A first step towards this is presented in [[6]](#6), where we show how satisfying finite-horizon safety and reachability specifications can be rewritten as convex programs. We then show how the energetic resilience metric may be computed on this basis, with corresponding optimal controllers also emerging. Importantly, we prove certain compositional properties of the metric, describing how it may be computed when multiple specifications are chained together. The figures below show satisfying a complex specification for a mobile robot, as well as variation in the energetic resilience with initial state.

<img src="https://ram-p.github.io/images/Robot.png" alt = "Safe Reachability for a Mobile Robot" width="300"/> <img src="https://ram-p.github.io/images/TLRes.png" alt = "Energetic Resilience under Temporal Logic Specifications" width="300"/>

The focus of ongoing work is to develop a more comprehensive theory of resilience when a system's specifications change, likely involving ways to measure distances between multiple specifications.

# Resilient Design

The second broad theme of my research concerns *designing* resilient behavior in dynamical systems, i.e., how do we design inputs to ensure resilient behavior, under hostile effects as described earlier?

## System Level Synthesis in a Switched Systems Framework

System faults or adversarial effects can cause an abrupt change in dynamics in a control system, a framework that can be modeled through switched systems. A shift from nominal (1) to faulty (2) operation is depicted in the first figure here. In [[7]](#7), we address the problem of solving optimal control problems for such systems, motivated by issues in fault tolerance. As such problems are commonly non-convex in controller parameters, we use the framework of *System Level Synthesis (SLS)* to "convexify" these problems.

<img src="https://ram-p.github.io/images/FaultModel.png" alt = "Fault Model" width="300"/>

We present two broad classes of optimal control problems, depending on whether the switching signal is chosen stochastically or non-deterministically, and impose a prefix constraint which ensures the controller cannot depend on future values of the switching signal. Crucially, such a constraint is still linear in the SLS parameterization, despite the fact that SLS itself uses a nonlinear transformation on the original parameterization. This property leads to efficient convex reformulations of the original optimal control problems. The figure below shows the impact of controller memory on an optimal control problem which aims to minimize the maximum deviation of the state from the origin.

<img src="https://ram-p.github.io/images/L1.png" alt = "L1-optimal control" width="300"/>

Ongoing work is being devoted to improving scalability of the resulting convex programs, in particular by limiting measurement and switching signal memory, as well as clustering methods that use a single controller for a cluster of possible paths.

## Constrained Nonlinear Control through Driftless Approximation

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

<a id="2">[2]</a> 
M. Bartels, "Russia’s Nauka module briefly tilts space station with unplanned thruster fire," Aug. 2021. [Online]. Available: https://www.space.com/nauka-module-thruster-fire-tilts-space-station

<a id="3">[3]</a> 
J.-B. Bouvier and M. Ornik, ["Resilience of linear systems to partial loss of control authority,"](https://www.sciencedirect.com/science/article/pii/S0005109823001383) _Automatica_, 152, June 2023.

<a id="4">[4]</a>
R. Padmanabhan and M. Ornik, ["Energetic Resilience of Linear Driftless Systems,"](https://www.sciencedirect.com/science/article/pii/S2405896325014922) in _11th IFAC Symposium on Robust Control Design (ROCOND)_, Porto, Portugal, Jul. 2025. \[Available at [arXiv:2410.00323](https://arxiv.org/abs/2410.00323)\]

<a id="5">[5]</a>
R. Padmanabhan and M. Ornik, ["Approximate Energetic Resilience of Nonlinear Systems under Partial Loss of Control Authority,"](https://www.sciencedirect.com/science/article/pii/S0005109826000828) _Automatica_, 187, May 2026. \[Extended version available at [arXiv:2502.07603](https://arxiv.org/abs/2502.07603)\]

<a id="7">[7]</a>
R. Padmanabhan, A. Aspeel, N. Ozay, and M. Ornik, ["Mode-Prefix-Based Control of Switched Linear Systems with Applications to Fault Tolerance,"](https://ieeexplore.ieee.org/document/11036760) _IEEE Control Systems Letters_, 9, pp. 1784--1789, Jul. 2025. \[Available at [arXiv:2505.13105](https://arxiv.org/abs/2505.13105)\]