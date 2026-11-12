# OpenShift Lightspeed Demo Collection

Ansible collection for deploying demo workloads for OpenShift Lightspeed environments.

The collection lives in the `automation/ansible` folder of the
[monorepo](../../README.md).

## Roles

- `ocp4_workload_lightspeed_demo` - Deploys the demo workloads (RHEL 9 VM,
  BYOK image, broken pod and troubleshooting case)

## Installation

```bash
ansible-galaxy collection install git+https://github.com/rhpds/rhpds.openshift_lightspeed_demo.git#/automation/ansible
```

## Usage

```yaml
workloads:
- rhpds.openshift_lightspeed_demo.ocp4_workload_lightspeed_demo
```
