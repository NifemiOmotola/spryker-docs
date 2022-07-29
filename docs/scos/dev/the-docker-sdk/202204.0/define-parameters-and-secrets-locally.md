---
title: Define parameters and secrets locally
description: Learn how to declare parameters and define their values.
last_updated: July 28, 2022
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
| grant | Access type. Acceptable values are `limited` and `public`. The default one is `limited`. |
| bucket | Defines what the secret or parameter is used for. Acceptable values are `app`, `scheduler`, `pipeline`, and `common`. `common` is the default value. Common secrets and parameters can be used by all the buckets. |
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

3. Optional: Check your environment's parameters:

```bash
list-env
```


## Define parameter and secret values in SCCOS

To define parameter and secret values in a Spryker Cloud Commerce OS environment, follow [Define parameters and secretes in a SCCOS environment](/docs/cloud/dev/spryker-cloud-commerce-os/define-parameters-and-secrets-in-a-sccos-environment.html).
