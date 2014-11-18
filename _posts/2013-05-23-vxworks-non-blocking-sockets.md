---
title: VxWorks Non-Blocking Sockets
layout: post 
summary: Lessons learned on VxWorks nonblocking I/O
tags: tech
---

*Reminder: VxWorks does support regular POSIX socket-programming, but does provides its own (relatively convenient) networking library in `sockLib.h`*

Generally in POSIX socket programming, to set a socket to non-blocking one would generally do:

    
    #include <fctnl.h>
    
    s = socket( ... );
    fcntl(s, F_SETFL, O_NONBLOCK, 1);

However, most VxWorks versions do *not* support `fcntl()` -- one should use `ioctl()` instead. However, ensure it is the one defined in `ioLib.h` and *not* the one in `ioctl.h` (VxWorks includes both).

*VxWorks*
    
    #include <ioLib.h>
    int blocking = 1;
    s = socket( ... );
    ioctl(s, FIONBIO, (int)&blocking);

Note the strange cast. The prototype for ioctl is `ioctl(int, int, int)`.

*Unix*

    #include <sys/ioctl.h>
    #include <errno.h>

    int s, blocking = 1;
    s = socket(AF_INET, SOCK_DGRAM, IPPROTO_UDP);
    ioctl(s, FIONBIO, &blocking) ;

Of course, we want to check if `ioctl()` returns negative on error. If it does, and `perror()` reports "Bad Address", this means the kernel attempted to access an address outside of the calling process's address space. It probably means you forgot an `&`. 
