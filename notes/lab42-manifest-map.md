# Lab 42 — Map the Manifests

## Object List

Planned Kubernetes objects:

1. Deployment
2. Service
3. ConfigMap
4. Secret
5. Namespace (if required by course environment)

Purpose:

- Deployment: Manages CRM application Pods and replicas.
- Service: Provides stable network access to CRM Pods.
- ConfigMap: Stores non-sensitive application configuration.
- Secret: Stores sensitive runtime values such as database credentials.
- Namespace: Provides logical isolation for lab resources.

## Holds / Must Not Hold

Deployment

Holds:
- Container image reference
- Replica count
- Resource requests and limits
- Readiness and liveness configuration

Must Not Hold:
- Plain-text passwords
- API tokens
- Database credentials

Service

Holds:
- Port mappings
- Service selectors

Must Not Hold:
- Secrets
- Application configuration data

ConfigMap

Holds:
- Non-sensitive configuration
- Spring profile settings
- Application feature flags

Must Not Hold:
- Passwords
- Tokens
- Secrets

Secret

Holds:
- Database username
- Database password
- Other sensitive runtime credentials

Must Not Hold:
- Source code
- Application binaries

## Labels

Example label plan:

```text
app=crm-api
component=backend
environment=lab
owner=crm-team
