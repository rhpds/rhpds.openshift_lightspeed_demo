# OpenShift Lightspeed Demo Collection

Ansible collection for deploying demo workloads for OpenShift Lightspeed environments.

## Roles

- `ocp4_workload_rhel9_vm` - Deploys a small RHEL 9 virtual machine for demo purposes

## Installation

```bash
ansible-galaxy collection install git+https://github.com/rhpds/rhpds.openshift_lightspeed_demo.git
```

## Usage

```yaml
workloads:
- rhpds.openshift_lightspeed_demo.ocp4_workload_rhel9_vm
```
