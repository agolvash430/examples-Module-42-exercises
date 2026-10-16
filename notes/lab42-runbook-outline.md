# Lab 42 — Runbook Outline

## Headings

Create:

docs/kubernetes-runbook.md

Outline:

# Kubernetes Deployment Runbook

## Purpose

## Prerequisites

## Verify Image Digest

## Review ConfigMap Values

## Review Secret References

## Apply Namespace

## Apply ConfigMap

## Apply Secret

## Apply Deployment

## Apply Service

## Verify Rollout Status

## Verify Pod Readiness

## Test CRM Endpoint Access

## Review Application Logs

## Rollback Procedure

## Evidence Collection

## Troubleshooting Notes

## Apply Order

Recommended apply sequence:

1. Namespace (if used)
2. ConfigMap
3. Secret
4. Deployment
5. Service
6. Verify rollout status
7. Verify readiness
8. Perform CRM validation checks
9. Collect evidence

Reasoning:

- Configuration resources should exist before Pods start.
- Pods require configuration and secrets at startup.
- Services should target healthy Pods after deployment begins.
- Validation occurs only after readiness succeeds.

## Safety

Safety checks before deployment:

- Verify image uses an approved digest rather than `:latest`.
- Verify no secrets are stored in deployment manifests.
- Confirm Secret references resolve correctly.
- Confirm readiness and liveness probes are configured.
- Confirm resource requests and limits are present.
- Verify rollback target is documented.
- Verify correlation ID testing plan is available.
- Verify deployment does not expose customer data or credentials.

Release safeguards:

- No deployment with unresolved critical issues.
- No deployment with hardcoded secrets.
- No deployment without rollback instructions.
- No deployment without rollout verification.

## Scope

This runbook outlines the deployment, validation, rollback, and evidence-collection process for the CRM application in Kubernetes. It provides deployment sequencing and operational checkpoints but does not execute the deployment as part of this pre-lab exercise.

## Scope

Pre-lab only — do not finish the full lab in this exercise.
