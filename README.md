JSRTO High-Speed Railway (HSR) Dataset Notes
Overview
This document describes the high-speed railway (HSR) trace data used in the paper:
> **JSRTO: Mixed-Traffic Joint Scheduling for Robust Traffic Offloading in Satellite-Assisted HSR Networks**
The goal of this note is to help readers understand:
 what kind of dataset is used in JSRTO,
 how it is used in the training and evaluation pipeline,
 what information is available from the public traces,
 what information is not directly available,
 and what additional assumptions are introduced in the paper for reproducibility.
---
What dataset is used?
JSRTO uses public real HSR wireless link-quality traces collected in an extreme-mobility rail environment.
According to the paper, the experimental traces come from a public HSR dataset reported in prior work on 5G/LTE measurements under extreme mobility. In JSRTO, these traces are used to model the time-varying quality of terrestrial communication links along the train route.
In practical terms, the dataset is used as a source of:
 time-varying serving-link quality,
 realistic mobility-induced channel fluctuations,
 non-stationary communication conditions,
 and heterogeneous link dynamics across different users / traffic demands.
---
Why is this dataset important in JSRTO?
A central claim of JSRTO is that scheduling and offloading policies should be evaluated under real non-stationary HSR conditions, rather than only under simplified synthetic assumptions.
The dataset is therefore important because it provides:
1. Realistic temporal variation  1. The wireless environment changes quickly along the railway path.
2. Extreme mobility characteristics  2. The train scenario produces stronger non-stationarity than ordinary mobile settings.
3. More realistic policy evaluation  3. The scheduling method is tested under practical channel variations instead of idealized stationary models.
---
How is the dataset used in the paper?
The HSR traces are not treated as a standalone machine learning dataset in the usual sense. Instead, they are used as an environmental input source inside the simulator / scheduling framework.
More specifically, the traces support:
 terrestrial link-quality evolution over time,
 realistic state construction for the scheduler,
 delay and queue dynamics under non-stationary link conditions,
 and trace-driven evaluation of the proposed policy.
The paper combines the public HSR traces with:
 a mixed-traffic service model,
 queue evolution,
 terrestrial/satellite transmission decisions,
 and a graph-based RL scheduling framework.
So the dataset is part of the system simulation and evaluation backbone, not just a benchmarking table.
---
