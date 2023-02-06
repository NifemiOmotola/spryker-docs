---
title: Define parameters and secrets
description: Learn how to declare parameters and define their values.
last_updated: Dec 2, 2022
template: howto-guide-template
---

This document describes how to declare parameters and secrets and define their values without exposing them in deploy files.

## Declare parameters and secrets

1. Define parameters and secrets in the needed deploy file as follows:

```yaml
...
environment-configuration:
    secrets:
        - name: {SECRET_NAME}
          grant: {PERMISSIONS}
          bucket: {BUCKET}
    params:
        - name: {PARAMETER_NAME}
          bucket: {BUCKET}
          default: {DEFAULT_VALUE}
          grant: {PERMISSIONS}
...
```
| PARAMETER | DESCRIPTION |
| - | - |
| name | Unique identifier of a secret or parameter. You will use it when defining its value in `.env.docker.local`. |
| grant | Users' permissions. `limited` provides read while `public` provides read and write permissions. The default one is `limited`. |
| bucket | Defines what the secret or parameter is used for. Acceptable value is `app`. |
| default | Default parameter value. Accepts string, number, and json values. |

2. Bootstrap the declared parameters:

```bash
docker/sdk boot {DEPLOY_FILE_NAME}
```

## Define parameter and secret values locally

1. Generate a file for parameter and secret values:

```bash
docker/sdk generate-env
```

This generates the `.env.docker.local` file and adds it to `.gitignore`.

2. In `.env.docker.local`, define parameter and secret values:

```text
{SECRET_NAME}='{SECRET_VALUE}'
{PARAMETER_NAME}=`{PARAMETER_VALUE}`
```

3. Bootstrap the defined values:
```bash
docker/sdk boot {DEPLOY_FILE_NAME}
```

Now you can launch the application with the defined parameters. To check all the environment's parameters, run `docker/sdk boot list-env`.


## Define parameter and secret values in SCCOS

To define parameter and secret values in a Spryker Cloud Commerce OS environment, follow [Define parameters and secretes in SCCOS environments](/docs/cloud/dev/spryker-cloud-commerce-os/define-parameter-and-secret-values-in-sccos-environments.html).
