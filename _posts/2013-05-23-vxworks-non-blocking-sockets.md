---
title: VxWorks Non-Blocking Sockets
layout: post 
summary: Lessons learned on VxWorks nonblocking I/O
tags: tech
---

<p>
<em>This documents a lesson learned while working on the testbed from piece of flight software written circa-1999.
It is not intended to be relevant to more recent versions of VxWorks.</em>
</p>

<p>
First, a reminder: While VxWorks does mostly support regular POSIX socket programming, it does provides its own (relatively convenient) networking library in `sockLib.h`
</p>

<p>
Generally in POSIX socket programming, to set a socket to non-blocking one would generally do:
</p>

<h3>Normal Sockets</h3>
<pre>
#include &lt;fctnl.h&gt;

int main()
{
    /* ...  */

    int s = socket( ... );
    fcntl(s, F_SETFL, O_NONBLOCK, 1);

    /* ... */
}
</pre>

<p>
However, most VxWorks versions do <strong>not</strong> support `fcntl()` -- one should use `ioctl()` instead. However, ensure it is the one defined in `ioLib.h` and <strong>not</strong> the one in `ioctl.h` (VxWorks includes both).
</p>

<h3>VxWorks using ioLib</h3>

<pre>
#include &lt;ioLib.h&gt;

int main()
{
    /* ... */

    int blocking = 1;
    int s = socket( ... );
    ioctl(s, FIONBIO, (int)&blocking);

    /* ... */
}
</pre>

<p>
Note the strange cast. The prototype for ioctl is `ioctl(int, int, int)`.
</p>

<h3>VxWorks using Unix-style sockets</h3>
<pre>
#include &lt;sys/ioctl.h&gt;
#include &lt;errno.h&gt;

int main()
{
    /* ... */

    int s, blocking = 1;
    s = socket(AF_INET, SOCK_DGRAM, IPPROTO_UDP);
    ioctl(s, FIONBIO, &blocking) ;

    /* ... */
}
</pre>

<p>
Of course, we want to check if `ioctl()` returns negative on error. If it does, and `perror()` reports "Bad Address", this means the kernel attempted to access an address outside of the calling process's address space. It probably means you forgot an `&amp;`. 
</p>
