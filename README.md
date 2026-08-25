# OpenShift Lightspeed Demo Collection

Ansible collection for deploying demo workloads for OpenShift Lightspeed environments.

## Roles

- `ocp4_workload_lightspeed_demo` - Deploys demo content for OpenShift Lightspeed (RHEL 9 VM, RAG, broken pod, optional Perses dashboards)

## Installation

```bash
ansible-galaxy collection install git+https://github.com/rhpds/rhpds.openshift_lightspeed_demo.git
```

## Usage

```yaml
workloads:
- rhpds.openshift_lightspeed_demo.ocp4_workload_lightspeed_demo
```
