Hello! This document provides a concise and reproducible description of the **high-speed railway (HSR) trace data** used in the paper:

> **JSRTO: Mixed-Traffic Joint Scheduling for Robust Traffic Offloading in Satellite-Assisted HSR Networks**

It is written for GitHub repositories and project documentation, so readers can quickly understand:

- what dataset is used,
- how it is used in JSRTO,
- what the public trace data provides,
- what it does **not** provide,
- and what additional assumptions are needed for reproduction.

---

## Overview

In JSRTO, the experiments are driven by **public real HSR wireless link-quality traces** collected under an extreme-mobility railway scenario.

These traces are not used as a standalone machine learning benchmark dataset.  
Instead, they are used as an **environment input source** inside the scheduling and simulation framework.

In other words, the trace data supports the construction of a realistic communication environment for:

1. terrestrial link-quality evolution,
2. mixed-traffic scheduling,
3. queue and delay dynamics,
4. and robust policy evaluation under non-stationary HSR conditions.

---

## Why this dataset matters

A key point of JSRTO is that traffic scheduling and offloading should not be evaluated only under simplified or stationary channel assumptions.

The HSR trace data is important because it introduces:

### 1. Realistic temporal variation
Wireless link quality changes over time along the railway route.

### 2. Extreme mobility effects
The train scenario leads to strong non-stationarity that is harder than ordinary mobile settings.

### 3. Practical evaluation conditions
The scheduling policy is tested under realistic link evolution rather than synthetic static assumptions.

---

## What dataset is used?

JSRTO uses **public HSR wireless traces** reported in prior work on **5G/LTE measurements in extreme-mobility railway environments**.

The paper uses these traces to represent time-varying terrestrial communication quality along the train trajectory.

From a practical perspective, the dataset provides information related to:

- serving-link quality over time,
- mobility-induced channel fluctuations,
- realistic communication instability,
- and non-stationary wireless behavior in HSR scenarios.

---

## How the dataset is used in JSRTO

The traces are integrated into the environment rather than treated as a simple table of samples.

More specifically, they are used for:

- modeling terrestrial link-quality changes,
- building scheduler state inputs,
- driving queue and delay evolution,
- and enabling trace-driven evaluation of the proposed method.

The full JSRTO environment combines the public HSR traces with:

- a mixed-traffic service model,
- heterogeneous traffic scheduling,
- terrestrial/satellite transmission decisions,
- queue-aware system dynamics,
- and a graph-based reinforcement learning framework.

So the dataset is part of the **simulation backbone**, not just an external benchmark.

---

## What the public traces directly provide

Based on the paper description, the public HSR traces mainly provide information about:

- serving wireless link quality,
- time-varying link behavior,
- and realistic terrestrial communication dynamics in a real HSR environment.

This is enough to model realistic **serving-link evolution** over time.

---

## What the public traces do not directly provide

The public trace source does **not** directly provide a complete multi-user wireless interaction map for the full JSRTO system.

In particular, the traces do not directly include:

- full cross-link channel state information (CSI),
- a complete interference matrix across all users and links,
- or the full space-ground coupling structure needed by the joint scheduler.

This is an important limitation because JSRTO solves a **joint scheduling and offloading problem**, which requires richer interaction information than a single serving-link trace alone.

---
