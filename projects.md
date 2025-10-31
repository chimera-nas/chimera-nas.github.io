---
title: Projects
layout: default
nav_order: nd   2
permalink: /projects
---

# Projects

The following projects are in development under the chimera-nas umbrella:

* [chimera](https://github.com/chimera-nas/chimera) library that implements user-space VFS with NFS, SMB, and S3 support.
* [libevpl](https://github.com/chimera-nas/libevpl) event-driven I/O library to allow portable use of hardware acceleration and kernel bypass APIs.  Used by chimera.
* [xdrzcc](https://github.com/chimera-nas/xdrzcc) compiler for XDR that facilitates zero-copy marshalling and unmarshalling.  Used to facilitate zero-copy ONC RPC2 and NFS.
* [flowbench](https://github.com/chimera-nas/flowbench) libevpl benchmark utility
* [prometheus-c](https://github.com/chimera-nas/prometheus-c) library for serving prometheus/OpenMetrics style metrics from a C program with very low per-sample overhead