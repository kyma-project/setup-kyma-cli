# Setup Kyma CLI

## Status

[![REUSE status](https://api.reuse.software/badge/github.com/kyma-project/setup-kyma-cli)](https://api.reuse.software/info/github.com/kyma-project/setup-kyma-cli)

## Overview
<!--- mandatory section --->

Setup Kyma CLI is an GitHub Action that installs [Kyma CLI](https://github.com/kyma-project/cli).

## Usage

This action downloads the Kyma CLI binary, and caches the result.

This action can be used in a GitHub Actions workflow file as follows:

```yaml
- uses: kyma-project/setup-kyma-cli@v1
  with:
    - version: latest
```

## Inputs

### `version`

Version of the Kyma CLi to download.
By default the action downloads the latest CLI version, including prereleases.
Version can be set to either the version number, or one of the following special values:

* `latest` (default) – downloads the latest version.
* `stable` – downloads the latest stable version.
* `nightly` – downloads the` 0.0.0-dev` version, build everyday.

### `target-dir`

Name of the target directory where to install the Kyma CLI.
On Linux and Mac OS runners the default is `~/.local/bin`.
On Windows runners the default is `C:\vcpkg`.

### `token`

A GitHub token used for Kyma CLI download. Default is `${{github.token}}`.

### `force`

Boolean to tell the action to download Kyma CLI even if cache with the executable exits. Default is `false`.

## Contributing
<!--- mandatory section - do not change this! --->

See the [Contributing Rules](CONTRIBUTING.md).

## Code of Conduct
<!--- mandatory section - do not change this! --->

See the [Code of Conduct](CODE_OF_CONDUCT.md) document.

## Licensing
<!--- mandatory section - do not change this! --->

See the [license](./LICENSE) file.
