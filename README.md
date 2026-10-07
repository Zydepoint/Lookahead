# Lookahead (WIP)
<b> Monitoring stack using Prometheus, Grafana for metrics and 'ntfy' for notifications. </b>

The Grafana dashboards are mostly uploaded, I will upload more later on. Some also requires Loki and Alloy, which I will add as well as the complete monitoring stack.

Every dashboard will complain that the Prometheus datasource does not exist. To solve this, go to the variable settings and configure your Prometheus datasource correctly and all panels should begin to display data. I have changed all panels to use `${datasource}` instead of a hardcoded instance, in which case one would have to change every individual panel of a dashboard.

## Exporters
Exporters will have to be installed for most of the dashboards to work. I use the following set:
- Proxmox: https://github.com/prometheus-pve/prometheus-pve-exporter
- Proxmox Backup Server: https://github.com/natrontech/pbs-exporter
- Traceroute/MTR: https://github.com/mgumz/mtr-exporter
- Tailscale: https://github.com/adinhodovic/tailscale-exporter
- Technitium DNS: https://github.com/guycalledseven/technitium-dns-prometheus-exporter
- ICMP & HTTP monitoring: https://github.com/prometheus/blackbox_exporter
- SNMP monitoring: https://github.com/prometheus/snmp_exporter

Some dashboards uses a fusion of two exporters, e.g. "Network Equipment - Health" uses both SNMP & ICMP monitoring.
