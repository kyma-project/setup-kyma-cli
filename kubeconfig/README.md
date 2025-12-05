# Kubeconfig action

## Overview

App push is an GitHub Action that generates kubeconfig with a Service Account-based or OIDC tokens.

## Usage

This action executes the `kyma alpha kubeconfig generate` command.
See the [`kyma alpha kubeconfig generate` documentation](https://kyma-project.io/external-content/cli/docs/user/gen-docs/kyma_alpha_kubeconfig_generate.html) for information on how to use the command.

This action can be used in a GitHub Actions workflow file as follows:

```yaml
- uses: kyma-project/setup-kyma-cli/kubeconfig@v1
  with:
    - api-server-url: server.url.example
    - ca-crt: Y2EtY3J0IGNvbnRlbnQ=
```

## Inputs

### `api-server-url` - required

A Kubernetes API server URL of the Kyma cluster.

### `ca-crt` - required

A Base64-encoded CA certificate for the API server.

### `audience`

Name of the OIDC audience.

## Outputs

### `kubeconfig`

A generated kubeconfig.

### `kubeconfig-base64`

A base64-encoded generated kubeconfig.

