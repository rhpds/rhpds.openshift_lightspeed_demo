# ocp4_workload_rhel9_vm

Deploys a small RHEL 9 virtual machine for OpenShift Lightspeed demo purposes.

## Role Overview

Creates a lightweight RHEL 9 VM using OpenShift Virtualization with:
- 1 CPU core
- 2 GiB RAM
- 30 GiB disk
- Cloud-init user setup

## Requirements

- OpenShift Virtualization operator installed
- Cluster with available resources for the VM

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `ocp4_workload_rhel9_vm_namespace` | `lightspeed-demo` | Namespace for the VM |
| `ocp4_workload_rhel9_vm_name` | `rhel9-demo` | VM name |
| `ocp4_workload_rhel9_vm_cpu_cores` | `1` | Number of CPU cores |
| `ocp4_workload_rhel9_vm_memory` | `2Gi` | Memory allocation |
| `ocp4_workload_rhel9_vm_user` | `cloud-user` | Default user |
| `ocp4_workload_rhel9_vm_password` | `redhat` | Default password |

## Example Usage

```yaml
workloads:
- rhpds.openshift_lightspeed_demo.ocp4_workload_rhel9_vm
```

## License

Apache-2.0
