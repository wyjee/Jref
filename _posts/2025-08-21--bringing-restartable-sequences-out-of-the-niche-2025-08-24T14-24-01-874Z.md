---
title: "[$] Bringing restartable sequences out of the niche"
link: "https://lwn.net/Articles/1033955/"
date: 2025-08-21
---

The <a href="https://lwn.net/Articles/697979/">restartable sequences</a> feature, which
was added to the 4.18 kernel in 2018, exists to enable better performance
in certain types of threaded applications.  While there are users for
restartable sequences, they tend to be relatively specialized code; this is
not a tool that most application developers reach for.  Over time, though,
the use of restartable sequences has grown, and it looks to grow further as
the feature is tied to new capabilities provided by the kernel.  As
restartable sequences become less of a niche feature, though, some problems
have turned up; fixing one of them may involve an ABI change visible in
user space.


Original link: https://lwn.net/Articles/1033955/