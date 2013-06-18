---
title: More Info
layout: base
---

## More Information

This page is intended to go into a little bit more depth on some of the activities I've been involved in over the past few years. Please pardon the dust; I add more when I have the time.

### ExecSpec

Traditional spacecraft autonomy systems are notoriously difficult to test, since they must be shown to react reliably to any number of potential faults in a complex hardware/software system in extreme environments. *ExecSpec* is a technology developed by JHUAPL to address these challenges and manage the complexity of designing and testing autonomy systems.

The essential aspect of *ExecSpec* is in providing a context in which a spacecraft's autonomy system can be expressed in sound formal (mathematical) foundations. Once reduced to a suitable computable structure, the autonomy system can be reasoned about rigorously and claims can be proven (using model checkers or theorem provers) to assert that a given design will not put the spacecraft into an anomalous state. A further consequence of expressing the design in this way is that mission operators and system engineers can be given an intuitive display of the state of the system.

*ExecSpec* is the candidate autonomy engine for NASA's Solar Probe Plus mission, which is led by APL. We have many efforts going on in parallel integrating *ExecSpec* with well known model checkers and producing rigorous, high-performance flight software implementations.

Note: "Autonomy" refers to the capability of the spacecraft to react and recover from on-board faults that usually occur while it is out of contact with the Earth.

### DTN

In short, this is a international and inter-agency effort to harness all available ground and space assets to produce the "Interplanetary Internet". When I have the time, I'll give more details.
