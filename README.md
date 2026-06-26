  # CNV Capacity Planning Calculator

  **🔗 [Launch Calculator](https://prasaddesala.github.io/cnv-capacity-calculator/cnv_capacity_planning_calculator.html)**

  A web-based calculator for planning OpenShift Virtualization (CNV) infrastructure capacity.

  ## Overview

  This tool helps you calculate worker node requirements for CNV deployments based on:
  - Number of VMs
  - VM specifications (vCPU, RAM, disk)
  - Worker node specifications
  - Overcommit ratios
  - Storage replication factors

  ## Features

  - **Real-time calculations** - Results update instantly as you change inputs
  - **Multiple architectures** - Supports hyperconverged, dedicated storage, and external SAN scenarios
  - **Zone distribution** - Calculates distribution across 3 availability zones
  - **Utilization warnings** - Alerts when resources are over-subscribed
  - **Generic calculator** - Architecture-agnostic math tool you interpret based on your setup

  ## Important Notes

  This is a **generic math calculator** that does NOT account for:
  - ODF storage pod overhead (OSDs, MONs, MGRs)
  - CNV operator/virt-handler overhead
  - OpenShift system pod overhead
  - Hypervisor overhead (~10% of physical resources)
  - Network bandwidth or IOPS limits

  **Recommendation**: Add 15-20% buffer to calculated node counts or treat utilization percentages as higher than displayed.

  ## Example Scenarios

  ### 1500 VMs - Hyperconverged
  VMs: 1500
  vCPU per VM: 2
  RAM per VM: 4 GB
  Disk per VM: 30 GB
  Node CPU: 48 cores
  Node RAM: 384 GB
  Storage per node: 7 TB
  Result: ~20 worker nodes

  ## Browser Compatibility

  Works in all modern browsers:
  - Chrome/Edge 90+
  - Firefox 88+
  - Safari 14+

  ## License

  MIT License - Feel free to use and modify

  ## Contributing

  Issues and pull requests welcome!
