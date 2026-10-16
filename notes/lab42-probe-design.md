# Lab 42 — Design Three Probes

## Definitions

Liveness Probe

- Determines whether the application process is still running correctly.
- If the liveness probe fails repeatedly, Kubernetes restarts the container.

Readiness Probe

- Determines whether the application is ready to receive traffic.
- If the readiness probe fails, Kubernetes removes the Pod from service endpoints until it recovers.

Startup Probe

- Determines whether the application has completed startup.
- Prevents liveness checks from restarting the application before startup is finished.

## Check the Reference

Probe Design Guidelines:

- Startup probe protects slow-starting Spring Boot applications.
- Readiness probe must fail closed when required dependencies such as the database are unavailable.
- Liveness probe should verify application health without depending on temporary external conditions.
- Traffic should only reach Pods that pass readiness checks.
- Failed liveness checks result in container restart.
- Failed readiness checks remove the Pod from traffic but do not necessarily restart it.

## Paths

Planned Probe Endpoints:

Startup Probe

```text
Path: /actuator/health
Port: 8080
