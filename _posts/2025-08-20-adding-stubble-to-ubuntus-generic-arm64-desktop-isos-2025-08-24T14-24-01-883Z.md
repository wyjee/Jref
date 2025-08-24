---
title: "Adding stubble to Ubuntu's generic Arm64 Desktop ISOs"
link: "https://lwn.net/Articles/1034579/"
date: 2025-08-20
---

<p>Tobias Heider has <a
href="https://discourse.ubuntu.com/t/what-s-new-for-generic-arm64-desktop-isos-in-25-10/66559">written</a>
an article that explains changes that are coming for Ubuntu's generic
Arm64 desktop ISO images in the 25.10 release. The current solution,
Heider says, depends on GRUB features that are unavailable in secure
boot mode and require adding device-specific logic to multiple
packages. The new solution, called <a
href="https://github.com/canonical/stubble?tab=readme-ov-file#stubble">stubble</a>,
is derived from <tt><a href="https://www.freedesktop.org/software/systemd/man/latest/systemd-stub.html">systemd-stub</a></tt>: 

<blockquote class="bq">
<p>A bundled stubble image contains stubble itself, a Linux kernel, a
HWID lookup table to map devices to device trees and multiple device
trees. When grub loads this "kernel", stubble executes first, reads
the SMBIOS table to generate HWIDs, looks for a match in the embeeded
lookup table and loads a matching device tree before passing control
to the actual Linux kernel.</p>

<p>The elegance in this approach lies in how it interacts with the
rest of the system. Integrating stubble happens entirely at build time
in the kernel package. The stubble package is a build dependency for
the kernel. After building the kernel itself, we bundle it with
stubble and our DTBs and ship the combined binary instead. The
resulting stubble + kernel + dtb bundle can be loaded by grub like any
other Ubuntu kernel. No further changes in grub or other packages are
necessary to make it work.</p>
</blockquote>
<p></p>

Original link: https://lwn.net/Articles/1034579/