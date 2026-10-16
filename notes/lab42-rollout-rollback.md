# Lab 42 — Rollout and Rollback

## Rollout Watch

Deployment rollout checklist:

1. Apply deployment manifest.
2. Monitor rollout status.
3. Verify desired replica count is available.
4. Confirm Pods reach READY state.
5. Verify readiness endpoint passes:
   - /actuator/health/readiness
6. Confirm no CrashLoopBackOff events.
7. Verify application logs show successful startup.
8. Validate CRM access using test requests.
9. Confirm customer records such as CUS-1001 and CUS-1002 can be retrieved successfully.
10. Record rollout evidence.

Success Criteria:

- All Pods are READY.
- No deployment errors are reported.
- Readiness checks pass.
- CRM endpoints function as expected.

## Rollback Story

Rollback Trigger Examples:

- Pods fail readiness checks.
- Deployment causes application errors.
- Customer lookups fail.
- Database connectivity problems occur.
- Critical regression detected after rollout.

Rollback Plan:

1. Identify the last known-good deployment.
2. Roll back to the previously approved image digest.
3. Monitor rollout status.
4. Verify Pods become READY.
5. Re-test CRM functionality.
6. Confirm customer access paths function normally.
7. Document rollback evidence and root-cause investigation.

Goal:

Restore the previously functioning CRM version with minimal interruption to agent operations.

## Evidence

Planned evidence locations:

```text
notes/lab-42/rollout-status.txt
notes/lab-42/pod-status.txt
notes/lab-42/readiness-results.txt
notes/lab-42/rollback-notes.md
notes/lab-42/deployment-events.txt
notes/lab-42/image-digest.txt
