---
title: Projects
layout: base
---

## Technical Posts

{% for post in site.posts %}
{% if post.tags contains "tech" %}
<p>
    <strong><a href="{{ post.url }}">{{ post.title }}</a></strong><br />
    {{ post.date | date: "%-d %B %Y" }}
</p>
{% endif %}
{% endfor %}

<hr />

## More Information

This page is intended to go into a little bit more depth on some of the activities I've been involved in over the past few years. Please pardon the dust; I add more information when I have the time.

### Space Cyber Security

*Please see my resume for a brief synopsis of my work in this field.*


### ExecSpec &mdash; Model-Based Spacecraft Fault Management

Traditional spacecraft autonomy systems are notoriously difficult to test, since they must be shown to react reliably to any number of potential faults in a complex hardware/software system in extreme environments. *ExecSpec* is a technology developed by JHUAPL to address these challenges and manage the complexity of designing and testing autonomy systems.

The essential aspect of *ExecSpec* is in providing a context in which a spacecraft's autonomy system can be expressed in sound formal foundations. Once reduced to a suitable computable structure, the autonomy system can be reasoned about rigorously and claims can be proven using model checkers that a given design will not put the spacecraft into an anomalous state. A further consequence of expressing the design in this way is that mission operators and system engineers can be given an intuitive display of the state of the system.

*ExecSpec* is the candidate autonomy engine for NASA's Solar Probe Plus mission, which is led by APL. We have many efforts going on in parallel integrating *ExecSpec* with well known model checkers and producing light-weight, high-performance flight software implementations.

My presentation "Investigating Model Based Autonomy for Solar Probe Plus" from the 2013 Workshop on Spacecraft Flight Software is on youtube [here](https://www.youtube.com/watch?v=ISCT4uvPU2o).

Note: "Autonomy" refers to the capability of the spacecraft to react and recover from on-board faults that usually occur while it is out of contact with the Earth.



### NASA cFE Flight Software Architecture

The NASA "Core Flight Executive" is a portable, cross-platform embedded system framework that has flown on dozens of recent space missions.
At APL, we maintain a fork of cFE that we baseline for all new space projects. 
This includes a suite of mission- and platform-independent flight software applications, in addition to another fork enabling cFE to leverage multicore systems. 
I've worked on both of these efforts and through them have become very familiar with the cFE framework - I consider it to be a fine example of well-engineered software, and can be applied to any number of situations where a publish-and-subscribe message passing framework makes sense.

Fortunately, NASA has allowed much of cFE (and its associated Operating System Abstraction Layer "OSAL") to become open sourced under the NASA Open Source Agreement. It's available at the [code.nasa.gov website](http://code.nasa.gov/project/core-flight-executive-cfe/), and I cloned it in my Github account for those who prefer git to SVN.

Many staff in my group independently offer consulting services to clients seeking to use the NASA cFE in their service or products. 
Please contact me if you are interested, I'd be delighted to get you in touch.


### DTN &mdash; Delay Tolerant Networking

In computer networking the term "DTN" &mdash; delay/disruption tolerant networking &mdash; refers to network architectures that are tolerant to extreme latency and/or frequently intermittent connectivity.
Many such environments exist, including deep space, undersea, or geographically isolated areas. In all of these cases, the TCP/IP internet protocol suite that we use on the Internet cannot scale to meet the challenges in these environments, and so this necessitates the development of a new protocol suite &mdash; one designed around the environmental constraints.

The DTN research group is an international and inter-agency effort to harness all available ground and space assets to create an "Interplanetary Internet" using a DTN protocol suite. 
This is similar to the challenge the pioneers of the Internet faced in the 1970s, and in fact Vint Cerf (one of those pioneers) is actively involved in this effort. 
There are many open problems, especially in security, routing, congestion control, and network management.

I have been involved, along with colleagues at APL, in the design and implementation of security extensions for the NASA reference implementation of the DTN protocols.
I've also done further work on protocols for key exchange in a DTN, proposing a mechanism for non-interactive key establishment.




