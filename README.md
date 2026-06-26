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

  ## How to Use

  1. Download `cnv_capacity_planning_calculator.html`
  2. Open it in any modern web browser
  3. Adjust the input values for your scenario:
     - VM workload specifications (count, vCPU, RAM, disk)
     - Worker node specifications (CPU, RAM, storage)
     - Overcommit ratios
  4. Results calculate automatically
  5. Review the summary report at the bottom

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

  ### 1500 VMs - Dedicated Storage
  VMs: 1500 (set disk to 0 in calculator)
  Storage: Calculate separately - need 9 ODF nodes with 15 TB each
  VM workers: 20 nodes (from calculator)
  Total: 32 nodes (3 control + 9 ODF + 20 VM workers)

  ## Architecture Support

  - **Hyperconverged**: VMs + ODF storage on same nodes
  - **Dedicated Storage**: Separate ODF storage nodes and VM compute nodes
  - **External SAN**: Pure Storage or other external storage arrays

  ## Browser Compatibility

  Works in all modern browsers:
  - Chrome/Edge 90+
  - Firefox 88+
  - Safari 14+

  ## License

  MIT License - Feel free to use and modify

  ## Contributing

  Issues and pull requests welcome!
