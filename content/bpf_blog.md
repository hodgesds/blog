+++
title = "Blogging with sched_ext"
date = 2025-07-16

[taxonomies]
categories = ["bpf"]
tags = ["bpf"]
+++

This blog is running using
[`scx_p2dq`](https://github.com/sched-ext/scx/tree/main/scheds/rust/scx_p2dq)
which is a scheduler I created. It uses a pick two load balancing algorithm to
load balance tasks across last level caches (LLCs) and a bunch of other cool
BPF features such as [BPF arenas](https://lwn.net/Articles/961594/). Sadly,
this blog is running on a small virtual machine so there isn't much load
balancing.

You can find a bunch of other schedulers in the
[scx repo](https://github.com/sched-ext/scx/tree/main) as long as you are
running a supported kernel (>6.14) then most schedulers should work.
