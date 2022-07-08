---
title: Install Spryker on Windows
description: Get started with Spryker via Docker on Windows
last_updated: Jul 5, 2022
template: concept-topic-template
---

To install Spryker on Windows, follow these steps:

## 1. Open Ubuntu

If Ubuntu is not yet installed on your machine, [download](https://apps.microsoft.com/store/detail/ubuntu/9PDXGNCFSCZV?ref=spryker-documentation) it from the Microsoft Store.

## 2. Clone the Demo Shop of your choice

- B2B Demo Shop

```shell
git clone https://github.com/spryker-shop/b2b-demo-shop.git -b 202204.0-p1 --single-branch ./b2b-demo-shop
```

- B2C Demo Shop

```shell
git clone https://github.com/spryker-shop/b2c-demo-shop.git -b 202204.0-p1 --single-branch ./b2c-demo-shop
```

- B2B Marketplace Demo Shop

```shell
git clone https://github.com/spryker-shop/b2b-demo-marketplace.git -b 202204.0-p1 --single-branch ./b2b-demo-marketplace
```

- B2C Marketplace Demo Shop

```shell
git clone https://github.com/spryker-shop/b2c-demo-marketplace.git -b 202204.0-p1 --single-branch ./b2c-demo-marketplace
```

## 3. Go to the newly created folder

```shell
cd <new-folder-name>
```

## 4. Clone the Docker SDK repository into the same folder

```shell
git clone https://github.com/spryker/docker-sdk.git --single-branch docker
```

## 5. Bootstrap the local Docker environment

1. Run the following command:
   
```shell
docker/sdk bootstrap deploy.dev.yml
```

{% info_block infoBox "Info" %}

If you do not need to build Spryker with development tools and file synchronization, run the following command:

```shell
docker/sdk bootstrap
```
This mode is better suited to showcase Spryker features.

{% endinfo_block %}

2. Update the host file `C:\Windows\System32\drivers\etc\hosts` the command that the `docker/sdk bootstrap` command displays.

## 6. Build and start your local instance

```shell
docker/sdk up
```

## 7. Open your new Spryker project in the browser

* Storefront [yves.de.spryker.local](yves.de.spryker.local)
* Back-Office [backoffice.de.spryker.local](backoffice.de.spryker.local)
* Frontend API [glue-storefront.de.spryker.local](glue-storefront.de.spryker.local) and its schema [swagger.spryker.local](swagger.spryker.local)

{% info_block infoBox "Good to know" %}

Whenever you see `.de.` in your URL, it means that this application is store specific. Out of the box, Spryker comes with three stores (de, at, and us).

{% endinfo_block %}

If you see `.de.` in your URL, it means that this application is store-specific. By default, Spryker comes with three stores: de, at, and us.

{% endinfo_block %}

If you need more details on the installation, see the following guides:
- [Installing in Development mode on Windows](/docs/scos/dev/setup/installing-spryker-with-docker/installation-guides/installing-in-development-mode-on-windows.html)
- [Installing in Demo mode on Windows](/docs/scos/dev/setup/installing-spryker-with-docker/installation-guides/installing-in-demo-mode-on-windows.html)

