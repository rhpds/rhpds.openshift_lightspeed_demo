# ocp4_workload_lightspeed_demo

Deploys demo content for OpenShift Lightspeed demonstrations including RHEL 9 VM, RAG integration, and intentionally broken pod for troubleshooting scenarios.

## Overview

This workload deploys demo-specific content for OpenShift Lightspeed demonstrations. It should be run **after** the `ai_workloads.ocp4_workload_ols` workload has successfully installed and configured the OpenShift Lightspeed operator.

## Components

### 1. RHEL9 VM Deployment
Creates a lightweight RHEL 9 virtual machine using OpenShift Virtualization:
- 1 CPU core
- 2 GiB RAM
- 30 GiB disk
- Cloud-init user setup

### 2. RAG Integration
Patches the OLSConfig with a RAG (Retrieval-Augmented Generation) image containing ACME Corporation demo content. This allows Lightspeed to provide context-aware responses based on custom documentation.

### 3. Broken Pod
Creates an intentionally misconfigured pod with a typo in the nodeSelector (`wrker` instead of `worker`). This is used for demonstration purposes to showcase Lightspeed's troubleshooting capabilities.

## Dependencies

- OpenShift Virtualization operator installed (for VM deployment)
- OpenShift Lightspeed Operator must be installed and running
- OLSConfig resource must exist in the cluster
- `ai_workloads.ocp4_workload_ols` workload must complete successfully first

## Variables

### General Configuration
| Variable | Default | Description |
|----------|---------|-------------|
| `ocp4_workload_lightspeed_demo_ols_namespace` | `openshift-lightspeed` | Namespace where OLS is installed |

### RHEL9 VM Configuration
| Variable | Default | Description |
|----------|---------|-------------|
| `ocp4_workload_lightspeed_demo_vm_namespace` | `lightspeed-demo` | Namespace for the VM |
| `ocp4_workload_lightspeed_demo_vm_name` | `rhel9-demo` | VM name |
| `ocp4_workload_lightspeed_demo_vm_running` | `true` | Start VM after creation |
| `ocp4_workload_lightspeed_demo_vm_cpu_cores` | `1` | Number of CPU cores |
| `ocp4_workload_lightspeed_demo_vm_memory` | `2Gi` | Memory allocation |
| `ocp4_workload_lightspeed_demo_vm_disk_size` | `30Gi` | Disk size |
| `ocp4_workload_lightspeed_demo_vm_image` | `quay.io/containerdisks/rhel:9-latest` | Container disk image |
| `ocp4_workload_lightspeed_demo_vm_user` | `cloud-user` | Default user |
| `ocp4_workload_lightspeed_demo_vm_password` | `redhat` | Default password |

### RAG Configuration
| Variable | Default | Description |
|----------|---------|-------------|
| `ocp4_workload_lightspeed_demo_enable_rag` | `true` | Enable RAG integration |
| `ocp4_workload_lightspeed_demo_rag_image` | `quay.io/dialvare/acme-byok:latest` | RAG container image |

### Broken Pod Configuration
| Variable | Default | Description |
|----------|---------|-------------|
| `ocp4_workload_lightspeed_demo_create_broken_pod` | `true` | Create broken pod for demo |
| `ocp4_workload_lightspeed_demo_broken_pod_namespace` | `broken` | Namespace for broken pod |
| `ocp4_workload_lightspeed_demo_broken_pod_name` | `broken-pod` | Name of broken pod |

## Example Usage

This workload is typically deployed as part of an AgnosticV catalog item:

```yaml
workloads:
- agnosticd.ai_workloads.ocp4_workload_ols
- rhpds.openshift_lightspeed_demo.ocp4_workload_lightspeed_demo

# Configure demo content
ocp4_workload_lightspeed_demo_enable_rag: true
ocp4_workload_lightspeed_demo_create_broken_pod: true
```

## Author

Prakhar Srivastava <psrivast@redhat.com>

## License

Apache-2.0
