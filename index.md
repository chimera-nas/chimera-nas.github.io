---
layout: home
nav_order: 1
---

# Introduction 

Modern operating systems kernels such as Linux typically contain a virtual file system (VFS) abstraction.  The VFS provides a generic, standardized API for interacting with file systems.  Along with the VFS, there is often a set of core infrastructure that all the file systems share, such as caches.   Most operating systems also have network attached storage (NAS) clients and servers built in for protocols such as NFS and SMB.  This allows applications to interact with remote file systems in the same way they interact with local ones.

The primary goal of the chimera-nas project is to replicate the VFS abstraction in user-space, primarily for NAS applications.  A secondary goal is to improve upon the performance possible with the traditional model by making the file system API fully event-driven, asynchronous, and zero-copy.  In the era of spinning rust, making operations like opening a file, changing permissions, or listing a directory contents synchronous blocking calls made sense.   The expected latency was very long and the number of operations per second the underlying hardware could perform in the first place was low.   In the modern era of individual NVMe drives being capable of millions of IOPS apiece, this is no longer the case.   In order to fully utilize storage IOPS we need to be able to perform thousands of concurrent file system operations.  In order to perform thousands of concurrent file system operations efficiently we need to be able to have more than one in flight at a time per thread.  Happily, all the popular NAS protocols are already asynchronous RPC models which are perfectly capable of this.  If we replace the traditional synchronous file system API with an asynchronous one, and we build file systems to that new API, we can achieve better efficiency.

# Projects
* [libevpl](https://chimeraproject.io/libevpl) is an event-driven I/O framework that allows a developer to write familiar sockets-like code and then leverage a variety of backend acceleration SDKs such as RDMA and VFIO transparently.
* [chimera](https://chimeraproject.io/chimera) builds on top of libevpl and implements the NFS3, NFS4, SMB, and S3 protocols.

