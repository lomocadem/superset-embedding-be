# superset-embedding-be

## To Add more variables:
* Create github action secret with prefix K8S_ENV_ at https://github.com/lomocadem/superset-embedding-be/settings/secrets/actions
* Update cicd/deployment.yaml file to map secret with variable name

```yaml
...
    spec:
      containers:
      - name: fastapi
        env:
        - name: SUPERSET_USER <= variable name
          valueFrom:
            secretKeyRef:
              key: K8S_ENV_SUPERSET_USER <= secret name
              name: sps-embedding-be-envs

```
