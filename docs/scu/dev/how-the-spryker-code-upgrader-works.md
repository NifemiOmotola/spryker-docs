---
title: How the Spryker Code Upgrader works
description: Spryker Code Upgrader overview
template: concept-topic-template
redirect_from:
  - /docs/paas-plus/dev/how-the-spryker-code-upgrader-works.html
---

To update a project, the Spryker Code Upgrader runs the following steps.

### 1. Identifies the available updates for the Spryker modules

The Spryker Code Upgrader performs the following sub-steps:

1. To identify the modules to be updated, it compares the information present in the `composer.json` and `composer.lock` files with our latest released code.

2. It creates a list of modules and third-party libraries to be updated. Groups the modules according to how we released them.

{% info_block infoBox "Module groups" %}

As modules depend on other modules, we tend to release them in groups. When the Spryker Code Upgrader identifies a module to be updated, apart from the identified module, it also adds all the other related modules from its group to the list.

{% endinfo_block %}


### 2. Updates the modules and libraries

Using `composer`, the Upgrader updates the modules in groups. After updating the modules, the Upgrader returns the list of updated modules and proceeds to the next step.

If the Upgrader can’t update a module, it skips the module’s and the remaining groups. If all the groups failed to update, the Upgrader returns the errors and stops. With at least one group updated, it returns the list of updated modules and proceeds to the next step.

By default, the Spryker Code Upgrader updates only minor and patch versions. When the Upgrader finds a group with a [major release](/docs/scos/dev/architecture/module-api/semantic-versioning-major-vs.-minor-vs.-patch-release.html#what-is-a-major-release), it won't update it and informs you about that:

```bash
There is a major release available for module spryker/merchant-product-approval. 
Please follow the link below to find all documentation needed to help you upgrade to the latest release 
https://api.release.spryker.com/release-group/XXXX
```

To continue the usage of the Upgrader, install the major version manually, and re-run the Upgrader.

### 3. Creates a Git branch

Spryker Code Upgrader creates a separate Git branch to commit the changes to. The branch name follows the pattern: `upgradebot/upgrade-for-{base-branch-name}-{last-commit-hash-in-the-base-branch}`.

### 4. Commits the changes

Spryker Code Upgrader commits the changes in the `composer.json` and `composer.lock` files to the branch.

### 5. Pushes the changes

The Upgrader pushes the changes to your source code provider using the authentication details provided in [SprykerCI](/docs/scu/dev/spryker-ci.html).

### 6. Creates a PR

The Upgrader creates a PR using your source code provider API. After the PR is created, you can review and merge it to apply the updates.

## Next steps

[Spryker Code Upgrader in a development workflow](/docs/scu/dev/spryker-code-upgrader-in-a-development-workflow.html)
