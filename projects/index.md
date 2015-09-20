---
title: Projects
layout: base
---

## More Information

This page is intended to go into a little bit more depth on some of the activities I've been involved in over the past few years. It's not meant to be exhaustive.


### Autonomous Systems

My work in autonomy - both for spacecraft and unmanned aircraft - has mostly revolved around fault diagnosis and remediation.
The central challenge is for the craft's autonomy engine to generate a set of hypothesis pointing to the source of the fault,
discriminate among them, and take the appropriate action to bring the craft into the safest possible state.

There are a few different approaches to take, most of which involve using a model of the system to explain the observed behavior.
These approaches range from highly deterministic ones to Monte Carlo methods in which repeated runs converge on a likely path through the state space.

My majors efforts in this area has been in implementing these approaches in testbeds for the NASA Solar Probe mission,
as well as in other sponsored work for multi-agent, cooperative UAV autonomy testing.

*Communications*

 * "Investigating Model-Based Autonomy for Solar Probe Plus". Workshop on Spacecraft Flight Software. Presented at Caltech, 2013.


### Embedded Aerospace Software and Network Architectures

On my Github account I mirror the offical open-source releases of the NASA-GSFC [Core Flight Executive (CFE)](https://github.com/billvb/cfe) and [Operating System Abstraction Layer (OSAL)](https://github.com/billvb/osal).
Together, they constitute a robust, cross-platform and flight-proven framework in which to develop flight software applications (e.g., navigation, fault management, command management).

My group at APL maintains such a suite of mission-independent space flight software "apps" on top of CFE known as CORE.
Having this suite available to us dramatically reduces the cost and risk of software development for future missions,
and additionally provides incredible ease for prototyping and evaluating new technologies.

I've recently been part of an effort to demonstrate the versatility of our flight software suite on an off-the-shelf quad copter
(in our demonstation we use the Parrot AR Drone).
It provides a low-cost testbed for the maturation of budding technologies in addition to demonstrating the applicability of our software products in new markets.

*Communications*

 * "SpaceDrone - Running APL spacecraft flight software on an off-the-shelf commercial quadcopter". Winner of the APL Achievement Awards Ignition Grant Category. 2015.


### Cyber Security

*Communications*

 * (Internal/FOUO) Approach toward a quantifiable scheme for determing most-likely attack vectors, 2014.
 * (Internal/FOUO) On spacecraft cyber penetration and in-situ countermeasures, 2013.
 * "Protecting Against DNS Cache Poisoning Attacks". Published in the proceedings of the IEEE ICNP. Presented in Kyoto, Japan, 2010.
 * "Dynamic, Non-Interactive Key Management for the Bundle Protocol". Published in the proceedings of ACM MobiCom. Presented in Chicago, 2010.

