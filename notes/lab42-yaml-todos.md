# Lab 42 — Deployment YAML TODOs

## Core Fields

Planned Deployment YAML fields:

- apiVersion
- kind
- metadata
  - name
  - labels
- spec
  - replicas
  - selector
  - template
    - metadata
      - labels
    - spec
      - containers
        - name
        - image
        - ports
        - env
        - readinessProbe
        - resources

Example checklist:

- Deployment name defined
- Replica count defined
- Labels and selectors match
- Container image defined
- Environment variables provided externally
- Readiness probe
