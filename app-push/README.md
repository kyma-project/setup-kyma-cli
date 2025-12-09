# App push action

## Overview

App push is an GitHub Action that pushes the application to the Kubernetes cluster.

## Usage

This action executes the `kyma app push` command.
See the [`kyma app push` documentation](https://kyma-project.io/external-content/cli/docs/user/gen-docs/kyma_app_push.html) for information on how to use the command.

Use this action in a GitHub Actions workflow file as follows:

```yaml
- uses: kyma-project/setup-kyma-cli/app-push@v1
  with:
    - name: my-app
```

## Inputs

### `kubeconfig`

A base64 encoded input kubeconfig data.

### `namespace`

Namespace where the app is deployed. Default is `default`.

### `name` - required: true

Name of the app.

### `quiet`

Suppresses non-essential output (prints only the URL of the pushed app, if exposed). Default is `false`.

### `image`

Pre-built image reference. Used if code-path or Dockerfile is not provided.

### `image-pull-secret`

Name of the Kubernetes Secret with credentials to pull the image.

### `code-path`

Path to app sources to build and push using `kyma app push`. It requires the Docker Registry module.

### `dockerfile`

A custom Dockerfile path (if using Docker build path in Kyma CLI).

### `dockerfile-build-arg`

Variables used while building an application from Dockerfile as args, separated by semicolon (key=value;key2=value2).

### `dockerfile-context`

Context path for building Dockerfile (defaults to the current working directory).

### `expose`

Expose app via APIRule. Default is `false`.

### `istio-inject`

Enable Istio sidecar injection. Default is `false`.

### `container-port`

Port on which the application is exposed.

### `mount-config`

Mount ConfigMap content, separated by semicolons, to the `/bindings/configmap-<CONFIGMAP_NAME>` path.

### `mount-secret`

Mount Secret content, separated by semicolons, to the `/bindings/secret-<SECRET_NAME>` path.

### `env`

Environment variables, separated by semicolons, for the app in format NAME=VALUE.

### `env-from-configmap`

Environment variables for the app, separated by semicolons, loaded from a ConfigMap in format `ENV_NAME=RESOURCE:RESOURCE_KEY` for a single key or `RESOURCE[:ENVS_PREFIX]` to fetch all keys.

### `env-from-file`

Environment variables for the app, separated by semicolons, loaded from a file in format `ENV_NAME=FILE_PATH:FILE_KEY` for a single key or `FILE_PATH[:ENVS_PREFIX]` to fetch all keys.

### `env-from-secret`

Environment variables for the app, separated by semicolons, loaded from a Secret in format `ENV_NAME=RESOURCE:RESOURCE_KEY` for a single key or `RESOURCE[:ENVS_PREFIX]` to fetch all keys.

### `insecure`

Disables SecurityContext configuration for the app deployment.

### `mount-service-binding-secret`

Mounts Secret, separated by semicolons, as service binding at `/bindings/secret-<NAME>` (readOnly).

## Outputs

### `url`

A resolved HTTPS URL of the deployed app.
