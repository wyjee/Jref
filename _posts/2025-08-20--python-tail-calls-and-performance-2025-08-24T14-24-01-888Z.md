---
title: "[$] Python, tail calls, and performance"
link: "https://lwn.net/Articles/1033373/"
date: 2025-08-20
---

Ken Jin welcomed <a
href="https://ep2025.europython.eu/">EuroPython&#160;2025</a> attendees to
his talk entitled "Building a new tail-calling interpreter for Python", but
noted that the title really should be: "Measuring the performance of
compilers and interpreters is really hard".  Jin's efforts <a
href="https://lwn.net/Articles/1010905/">to switch the CPython interpreter to use tail calls</a>,
which can be optimized as regular jumps,
initially seemed to produce an almost miraculous performance improvement.
As his modified title suggests, the <a
href="https://blog.nelhage.com/post/cpython-tail-call/">actual improvement
was rather smaller</a>; there is still some performance improvement and
there are other benefits from the change.


Original link: https://lwn.net/Articles/1033373/