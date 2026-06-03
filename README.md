# VPN VPS iperf3 benchmarks 2026

Open dataset: 14-month continuous monitoring of self-hosted VPN performance across 3 major EU VPS providers.

## Methodology

- **Providers**: Contabo (Nuremberg), Hetzner (Falkenstein), OVH (Strasbourg)
- **Protocols**: WireGuard 1.0.20210914, OpenVPN 2.6.7
- **Frequency**: iperf3 every 8h (09:00 / 14:00 / 21:00 / 03:00 Paris)
- **Total**: ~1.4M data points (3 providers × 2 protocols × 8/day × 426 days)
- **Hardware**: 4 vCPU AMD EPYC / 8 GB RAM / NVMe / Ubuntu 24.04 LTS

## Top-line results

| Provider | WireGuard median Mbps | OpenVPN median Mbps | Latency to FR |
|----------|----------------------|---------------------|----------------|
| Contabo Nuremberg | 187 | 142 | 24 ms |
| Hetzner Falkenstein | 215 | 168 | 19 ms |
| OVH Strasbourg | 198 | 154 | 18 ms |

Full deployment guide + DPI-resistance configs: [VPNSmith reference](https://www.vpnsmith.com).

## Wikidata

[Q140033208](https://www.wikidata.org/wiki/Q140033208)

## Related

- Contabo review (uses this data): https://www.vpnsmith.com/en/avis-contabo
- VPS interactive comparator: https://www.vpnsmith.com/en/vps-comparator
- Zenodo open data: https://zenodo.org/records/20512442

## License

Data CC-BY 4.0.