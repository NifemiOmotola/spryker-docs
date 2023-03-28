---
title: Update Spryker
description: The article describes how to update a Spryker-based project, make the Spryker update process smoother, easier, and update efforts predictable
last_updated: Jun 16, 2021
template: concept-topic-template
originalLink: https://documentation.spryker.com/2021080/docs/updating-a-spryker-based-project
originalArticleId: 0aac9b81-7db9-4a7e-87f8-35c2ac6efe1d
redirect_from:
  - /2021080/docs/updating-a-spryker-based-project
  - /2021080/docs/en/updating-a-spryker-based-project
  - /docs/updating-a-spryker-based-project
  - /docs/en/updating-a-spryker-based-project
  - /v6/docs/updating-a-spryker-based-project
  - /v6/docs/en/updating-a-spryker-based-project
  - /v5/docs/updating-a-spryker-based-project
  - /v5/docs/en/updating-a-spryker-based-project
  - /v4/docs/updating-a-spryker-based-project
  - /v4/docs/en/updating-a-spryker-based-project
---

Updating your Spryker shop is always an effort. New features, fixes, and updates are coming every day, and modules become more and more outdated. This raises many questions, the most common of which are:
* Do I actually need to update my project?
* If yes—how to do it wisely, to spend less time and stay up-to-date?
* How often should I update?
* What does the update process look like and how to plan and organize it?

This article gives answers to these questions and provides recommendations that will help you make the Spryker update process smoother, easier, and update efforts predictable.

## Spryker product structure

The smallest building block of Spryker is a *module*. Usually, a module does not represent a complete functionality. A complete functionality, or a *feature*, is represented by an aggregation of a set of modules. A feature is a virtual entity, which binds together a number of modules to satisfy certain functionalities. Check out the [Spryker feature repository](https://github.com/spryker-feature/) for detailed information about each feature.

The set of features makes up a *product*. Spryker offers the following products:
* [B2B Demo Shop](/docs/scos/user/intro-to-spryker/b2b-suite.html)
* [B2C Demo Shop](/docs/scos/user/intro-to-spryker/b2c-suite.html)
* [Master Suite](/docs/scos/user/intro-to-spryker/master-suite.html)

Schematically, the Spryker product structure looks like this:

![image](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Updating+a+Spryker-based+Project/product-structure.png)

## Why and when to update your Spryker shop

The most typical reasons to update modules or features are the following:
* There are important security or bug fixes that have been introduced recently.
* You want a new specific feature or module in your project, which requires a newer version of your modules.
* Your project has been started shortly before a new [product release](/docs/scos/user/intro-to-spryker/spryker-release-process.html#product-releases).
* You experience some issues with the shop that you would like to report or consult about.
* If you plan to extend your shop in future with new features from the ones that exist in Spryker or are coming out soon, your project should be always up to date. It will ease the new feature installation and reduce the migration efforts, allowing you to get the desired functionality faster.

{% info_block warningBox "Warning" %}

The more outdated your module versions become, the more effort will be needed to install the new features in future.

{% endinfo_block %}

The most *reasonable strategy* of staying up to date is sticking to the Spryker release cycle and updating modules whenever there is a new release announcement. To get notified about releases,  [subscribe to the release notes](/docs/scos/user/intro-to-spryker/releases/releases.html). During the active development phase, it makes sense to do updates more often, for example, monthly.

## Features versus individual module updates

When you know that you need to update your project, you need to decide at which level you want to do updates: at the *feature *level* or the *module* level*.

{% info_block infoBox %}

Spryker does big [Product Releases](/docs/scos/user/intro-to-spryker/spryker-release-process.html#product-releases) of features every several months. The *modules* fall under the [Code Release](/docs/scos/user/intro-to-spryker/spryker-release-process.html#atomic-code-releases) process, and therefore there can be up to several module updates per day.

{% endinfo_block %}

The table below shows when it might be more relevant to you to make updates at the feature level and when at the module level.

| FEATURE-LEVEL UPDATE | MODULE-LEVEL UPDATE |
| --- | --- |
| Your project is in *operations mode*. The project is completed and is in the support phase, not much development is happening. | Your project is in active *development mode*, and you want to update more often to get the latest features and bugfixes. |
| You want to update as soon as a Spryker Product Release happens. | You are getting core commitments from Spryker at the module level. |
| Your strategy is to install and update features at once. | Your strategy is to have smaller and simpler updates more often. |
|  | You want to do updates with a single-module precision. |
|  | You want to be more flexible and be able to split updates into chunks, distributing them across your sprints. |
|  | You have not been updating for a while (6+ months), and now you have to do a big update. |
|  | Your project is highly customized, and you extended a lot of code at the project level. |

## Switch from feature to module dependencies

To switch from updates on a feature level to a module level, you need to update your `composer. json` by replacing feature dependencies with the module dependencies which the features consist of.

### Check the features in your project

If you started with Spryker features, your `composer.json` should look similar to the following:

```json
"ext-readline": "*",
"ext-redis": "*",
"spryker-eco/loggly": "^0.1.0",
"spryker-feature/agent-assist": "^{{page.version}}",
"spryker-feature/alternative-products": "^{{page.version}}",
"spryker-feature/approval-process": "^{{page.version}}",
"spryker-feature/availability-notification": "^{{page.version}}",
"spryker-feature/cart": "^{{page.version}}",
....
```

## Check the modules a feature consists of

Every Spryker feature is a standalone module with a `composer.json` file with a list of individual Spryker modules as dependencies. A feature contains no functional code; the entire code is kept in modules.
Following the example with the `spryker-feature/agent-assist` feature, check [its composer.json file](https://github.com/spryker-feature/product-sets/blob/master/composer.json):

```json
{
  "name": "spryker-feature/product-sets",
  "description": "Product Sets [feature]",
  "type": "metapackage",
  "license": "proprietary",
  "minimum-stability": "dev",
  "prefer-stable": true,
  "require": {
    "php": ">=7.2",
    "spryker-shop/product-set-detail-page": "^1.5.0",
    "spryker-shop/product-set-list-page": "^1.0.1",
    "spryker-shop/product-set-widget": "^1.3.0",
    "spryker/product-set": "^1.4.0",
    "spryker/product-set-gui": "^2.3.0",
    "spryker/product-set-page-search": "^1.3.0",
    "spryker/product-set-storage": "^1.6.0"
  },
  "extra": {
    "branch-alias": {
      "dev-master": "202001.x-dev"
    }
  }
}
```

In the `require` part, you can see the modules this feature consists of.

### Replace feature dependencies with module dependencies

You can replace the `spryker-feature/agent-assist` dependency in your `composer.json` with the list of its dependencies (modules). After doing the same to other features, the project starts depending on modules instead of features. At the same time, the shops functionality does not change.









## Upgrade iteratively

To make your update process as smooth as possible, we recommend following the best practices described in this section.

### Bugfix and minor version updates

For *bugfix* and *minor* module version updates, run the update for modules from your update iteration. Example:

```BASH
composer update spryker/propel spryker/oms spryker/currency spryker/money spryker/glossary spryker/mail spryker/customer-extension spryker/calculation spryker/price-product …
```

The list of modules to be updated might change if Composer warns you about dependencies on other modules. Keep adding them to the list, but make sure your update iteration does not get blown up too much. Otherwise, split the iteration into several ones.

Before taking minor updates to the modules you customized on the project level, we recommend double-checking that the update does not conflict with the project-level logic. . You can do it as follows:

1. Go to `https://github.com/[module-name-here]/compare/[your-version]…[available-version]`.  For example, [https://github.com/spryker/queue/compare/1.1.2...1.2.0](https://github.com/spryker/queue/compare/1.1.2...1.2.0).
2. Carefully check the code changes.
3. Fix or integrate with the issues if any.

### Major version updates and new packages installation

<a name="{major}"></a>For *major* module version updates or installation of *new packages*, follow the steps below.

1. Require a new module:

```BASH
php -d memory_limit=-1 composer.phar require "spryker/sales:^8.0.0"
```
If no extra dependencies are found, `composer.json` will be updated, respectively. Otherwise, see the [Troubleshooting](#troubleshooting) section at the end of the article, *In case when update is not possible* part.

2. [Check the migration guide](/docs/scos/dev/module-migration-guides/about-migration-guides.html) for the respective major module version. See the [Sales](/docs/scos/dev/module-migration-guides/migration-guide-sales.html) migration guide for example. Find the section for your module version and complete all the steps it contains.
3.  Check for project changes, just like for the *minor* updates in the section above. Go to  `https://github.com/[module-name-here]/compare/[your-version]…[available-version]` and check if there are any changes that might conflict with your business logic.

## Test after each iteration

{% info_block infoBox %}

To find out about the obvious update errors before executing the tests, run `php -d memory_limit=-1 ./vendor/bin/phpstan analyze --no-progress src/ -l 5`. Keep in mind, that it has to be set up and green before the updates happen.

{% endinfo_block %}

Once you've completed the update, it's necessary to make sure that everything still works as expected, and nothing is broken. To do so, complete the following steps right after the update:

### 1. Run automated tests

Automoted tests are must-have for every project in general and are very helpful in case of updates. We recommend to run the following tests:
* Acceptance tests—cover the most critical e-commerce functionality of your shop.
* Functional tests—cover your Facade methods in Zed.
* Unit tests—cover classes with complex business logic and tricky algorithms.

See the [Testing](/docs/scos/dev/guidelines/testing-guidelines/test-framework.html) section for information about what Spryker has to offer in terms of testing your project's code.

{% info_block infoBox "Note" %}

The goal of the automoted tests in case of updates is not to have a 100% code coverage, but rather qualitative coverage of your critical functionality.

{% endinfo_block %}

### 2. Run code analysis tools

We find the following static code analysis tools the most helpful for running after the update and strongly recommend that you use them:
* [PhpStan](https://github.com/phpstan/phpstan):  helps you find incompatible interface signatures, undefined method calls, missing classes, use of deprecated methods (phpstan-deprecation-rules), and many more. See [PHPStan](/docs/scos/dev/sdk/development-tools/phpstan.html) for information about how to install and use the tool.
* [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer): keeps the project code clean and consistent after the update. See [Code Sniffer](/docs/scos/dev/sdk/development-tools/code-sniffer.html) for information about how to use the tool.
* [Architecture Sniffer](https://github.com/spryker/architecture-sniffer): helps you maintain the quality of the architecture. See [Architecture Sniffer](/docs/scos/dev/sdk/development-tools/architecture-sniffer.html) for information about how to run the tool.

### 3. Make other possible checks

In addition to the automotive tests and code analysis tools, you can optionally do the following:
* *Re-install the project locally* after the update, to make sure the installation process is not broken, demo-data import along with [publish and synchronization](/docs/scos/dev/back-end-development/data-manipulation/data-publishing/publish-and-synchronization.html) work as expected.
* *Run a manual smoke test* either locally or on stage to make sure everything works and looks fine. This is especially important in case you don't have enough acceptance test coverage.

## Prevent potential issues

One of the most common issues projects face during the upgrade, is the situation, when a Spryker class that was inherited at the project level also got updated on the Spryker side. This can result in code syntax issues or logical issues, and it's completely in the project's team hands to spot and fix such issues. However, there are some recommendations that can help you avoid them:

### 1. Avoid inheritance

*Minimizing the number of inheritance cases* on your project is the best approach to avoid inheritance issues. Let's see how you can achieve that.

Usually, when you're inheriting a class from Spryker, you want to change its behavior. But before extending the class, check if you can do the following:
* *Configure the behavior*. Check your environment and module configs. If configuration can fit your needs - that would be the best solution.
* Change the behavior by *introducing a new plugin or an event listener*. If the behavior you want to inherit is triggered by one of the plugins in a plugin stack or by an event listener, just add a new plugin and introduce a new class at the project level (potentially, implementing some interface). You don't need inheritance in this case.
* *Use a composition pattern*. There is a lot of information on the internet for *composition vs. inheritance* that will help you to understand the pattern. The main idea is to introduce a new class at the project level and to use the class you wanted to inherit as a constructor dependency, for example, kind of "wrapping". Even though this is a very good practice, it might not work in cases when you want to change protected methods.
* *Do you really need the inheritance?* In case of heavy customizations, think if you really need to extend the existing Spryker class. Replacing it by introducing a new class at the project level and instantiating it in the corresponding factory instead of the Spryker one - would be the preferred way to go.

### 2. Follow the best practices for inheritance

Sometimes inheritance is exactly what you need, and none of the above strategies works for you, which is also fine. In this case, *minimizing the amount of inherited code* is a rule of thumb. To follow this rule, you can take this approach:
1. First of all, *reduce the number of extended methods in a class*. Sometimes, developers just copy-paste the whole class to the project namespace, change the methods they want, and leave the rest as is. Don't do that: remove the methods you didn't touch.
2. Now, focusing on a method you change, *reduce the amount of the inherited code*, delegating the rest to the `parent:: class` call. Ideally, you should have only project-specific logic in your new inherited class.
3. In some complicated cases, for example, if you want to remove/add a line from the middle of the original method and none of the above techniques works,  surround your change with a meaningful comment. The comment should explain why you made the change, ideally also mentioning the related (Jira) ticket number. That will help the person who does the update understand your goal and take the necessary steps.

### 3. Lock your module version after inheritance

If you inherit a class from Spryker, there is one more way to "protect" yourself during the update by locking your module version to the current minor. You can do this by, for example, replacing the *carret* module version (“^1.3.2”) with the *tilde* version (“~1.3.2”) in your `composer.json`. Next time when the class you've updated gets minor changes on the Spryker side, composer will warn you about the locked version, and you will have to investigate why this module was locked. Make sure to leave a meaningful comment in your VCS when locking the module for the person who will investigate that.

In Spryker we have the [Composer Constrainer](/docs/scos/dev/architecture/module-api/using-composer-constraint-for-customized-modules.html) tool that will try to lock modules for you automatically by searching for inherited classes in your project namsepace.

## Updating and installing features

At some point, you will need to add new or update the existing features for your project. This section will help you do that.

{% info_block infoBox "Info" %}

You can learn about a new Spryker feature from the [Release Notes](/docs/scos/user/intro-to-spryker/releases/release-notes/release-notes.html). We recommend [subscribing to our release mail](/docs/scos/user/intro-to-spryker/releases/releases.html) in order not to miss a new release announcement.
A complete list of all Spryker features can be found in the [Features](/docs/scos/user/features/{{site.version}}/features.html) section. This section contains general descriptions of the features and links to their [Integration Guides](/docs/scos/dev/feature-integration-guides/{{site.version}}/feature-integration-guides.html) that you will use to install or update the features.  

{% endinfo_block %}

To install a new feature or update an existing one, follow the instructions of the [Integration Guide](/docs/scos/dev/feature-integration-guides/{{site.version}}/feature-integration-guides.html) for the feature you want to install/update.

{% info_block warningBox "Warning" %}

Make sure you use the integration guide for the feature version you need. To select a specific version of the feature integration guide, choose the documentation (product release) version in the green dropdown in the right corner of the page. This will switch the version of the documentation to the selected one.

{% endinfo_block %}

Keep in mind, that if the selected feature version is newer than that of the installed features, you need to replace the feature with its modules in your composer.json. For example, `spryker-feature/gift-cards":"^201907.0"`
should be replaced with

```json
"spryker-shop/cart-code-widget": "^1.0.0",
"spryker-shop/gift-card-widget": "^1.1.0",`
...
```

{% info_block infoBox "Info" %}

A new feature might require a higher major version for a specific module. In this case, do a [single module update](#major-version-updates-and-new-packages-installation).

{% endinfo_block %}

## Troubleshooting

This section contains common issues with the updates and provides solutions on how to fix them. If your issue is not on the list, and you need help, please [contact us](#let-us-know).

### I see Spryker Code Sniffer updates

In case you see Code Sniffer updates from Spryker, first check if the new code sniffer rules have been added. Investigate what they are doing and decide with the team if you need them.
If you don't need those roles, exclude them from the list.

{% info_block infoBox "Note" %}

In some projects, all Spryker sniffs might be included automatically.

{% endinfo_block %}

To exclude / include sniff rules, adjust the following section in `ruleset.xml` file:

```xml
<rule ref="vendor/spryker/code-sniffer/Spryker/ruleset.xml">
	<exclude name="Spryker.Factory.NoPrivateMethods"/>
  ...
</rule>
```

### Update is not possible

There can be several cases when the update is not possible:

#### 1. Update is "ignored" by Composer

There may be situations when you know there is a new version, but Composer returns the following message:

```BASH
...
Updating dependencies (including require-dev)
Nothing to install or update....
```

Most likely, this means that the update requires some other dependencies that currently can not be satisfied in the project.
One of the ways to check what’s missing is to use `composer why-not` command like this:

```BASH
php -d memory_limit=-1 composer.phar why-not "spryker/symfony:^3.2.0"
```

Composer will return what exactly is needed:

```BASH
spryker/symfony 3.2.0 requires symfony/stopwatch (^4.0.0)
myProject/platform dev-develop does not require symfony/stopwatch (but v2.8.34 is installed)
```

Make sure to first update the packages that are required first, and then try updating again.

#### 2. Dependencies prevent package from updating

You might see a message like this one:

```BASH
Updating dependencies (including require-dev)
Your requirements could not be resolved to an installable set of packages.
Problem 1
- Conclusion: don't install silex/web-profiler v1.0.8
- Conclusion: remove symfony/stopwatch v4.1.7
- Installation request for silex/web-profiler ~1.0.8 -> satisfiable by silex/web-profiler[1.0.x-dev, v1.0.8].
- Conclusion: don't install symfony/stopwatch v4.1.7
....
```

To understand what's missing, run `composer why-not` as in the previous step.

#### Complicated cases

Each situation requires a custom approach. If you have not found your solution here, but think it might help others, please feel free to add it here by clicking **Edit or Report** right under the title of this article.

## Let us know

Please let us know if anything goes wrong with your update:

* You find an issue in the code while reviewing the diff in a Spryker repo.
* After running autotests / testing the website you find an issue that broke the website. If this is not a project-related conflict and other projects can potentially be affected, please report the issue as soon as you can.
* There are missing steps in a [migration guide](/docs/scos/dev/module-migration-guides/about-migration-guides.html) in our documentation.

Reach us out at:
* *Support and community*: share your problem or solution or learn from others in our [community slack](https://sprykercommunity.slack.com/join/shared_invite/zt-gdakzwk3-~B_gJXbUxMdzkBwTQVjNgg#/).
* *Create a request* on our [support portal](https://spryker.force.com/support/s/).
* *Contribute to code*: if you want to share your fix with us, let Spryker take care of it. Spryker can support it in the future and make the fix available for your other projects. To contribute to code, create a pull request on the module's [Github repository](https://github.com/spryker);
* *Contribute to documentation*: if you found an issue in a migration guide or some parts of it are missing - you can suggest a change by clicking **Edit or Report** right below the article title.

## Reference

Check out the [How to migrate and update Spryker projects video](https://training.spryker.com/pages/spryker-tv?wchannelid=papy2tx2f6&wmediaid=kitd5w26zq) for more details on the topic.