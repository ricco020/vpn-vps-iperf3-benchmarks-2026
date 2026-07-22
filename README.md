# Self-Hosted VPN Throughput - Benchmarking Methodology & Toolkit

A **reproducible methodology** for benchmarking self-hosted VPN throughput
(WireGuard, OpenVPN) on cloud VPS providers with iperf3. This repository
documents **how to run the tests** so anyone can reproduce them on their own
servers. It does **not** publish claimed measurements - the only trustworthy
number is one you measure on your own box.

## Why advertised bandwidth != real VPN throughput
Encryption overhead, kernel vs user-space (WireGuard runs in kernel space and is
typically close to line rate; OpenVPN adds more per-packet CPU cost), MTU, and
provider network paths all affect the result. Measure, do not assume.

## Reproducible method
1. Provision a VPS (e.g. Contabo, Hetzner, OVH) - e.g. 4 vCPU / 8 GB / NVMe / Ubuntu 24.04.
2. Install WireGuard (kernel module) and/or OpenVPN 2.6.
3. From a fixed client, run `iperf3 -c <server> -t 60` (TCP, single-thread) over the tunnel.
4. Record throughput (Mbps), latency (ms) and CPU. Repeat at several times of day.

**Expected shape** (general, verify on your hardware): on a 1 Gbps link,
kernel-mode WireGuard runs close to line rate with low CPU; OpenVPN is lower
because of user-space per-packet overhead. Numbers vary by provider, region and
kernel - run your own.

## Reference
Self-host VPN deployment guides and configs: https://www.vpnsmith.com

## License
CC BY 4.0
