# OpenShift Lightspeed Demo

Monorepo for the OpenShift Lightspeed demo catalog items.

## Layout

- `automation/ansible/` — Ansible collection `rhpds.openshift_lightspeed_demo`
  (workloads that deploy the demo resources)
- `content/` — Showroom lab guide (Antora)
- `byok/` — Markdown source documents for the Bring Your Own Knowledge (BYOK)
  demo image
- `utilities/` — Helper scripts to build and serve the guide locally
- `site.yml` — Antora playbook for the showroom guide
- `ui-config.yml` — Showroom UI configuration (tabs, view switcher)

## Preview the guide

A rendered preview is published to GitHub Pages on every push to `main`:
https://rhpds.github.io/rhpds.openshift_lightspeed_demo/

To build and serve locally:

```bash
utilities/lab-build
utilities/lab-serve
```

## Use the collection

See [automation/ansible/README.md](automation/ansible/README.md).
