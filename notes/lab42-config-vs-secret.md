# Lab 42 — Config versus Secret

## Sort the List

ConfigMap Candidates (Non-Sensitive):

- SPRING_PROFILES_ACTIVE
- SERVER_PORT
- LOG_LEVEL
- FEATURE_FLAGS
- APPLICATION_NAME
- ACTUATOR_ENDPOINT_SETTINGS
- JAVA_OPTS (non-sensitive values)

Secret Candidates (Sensitive):

- SPRING_DATASOURCE_USERNAME
- SPRING_DATASOURCE_PASSWORD
- API_KEYS
- ACCESS
