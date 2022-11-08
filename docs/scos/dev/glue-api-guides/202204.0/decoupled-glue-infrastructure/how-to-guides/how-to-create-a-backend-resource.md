---
title: How to create a backend resource
description: This guide shows how to create an API endpoint using a resource for the backend API application.
last_updated: September 30, 2022
template: howto-guide-template
redirect_from:
  - /docs/scos/dev/glue-api-guides/202204.0/glue-backend-api/how-to-guides/how-to-create-a-backend-resource.html
---

This guide shows how to create an API endpoint using a resource for the backend API application.

Let's say you have a module named `ModuleRestApi`, where you want to have a new endpoint `/module` with `GET` and `POST` methods. To create the endpoint, follow these steps:

1. Create `ModuleRestApiConfig` and add the resource name:

**\Pyz\Glue\ModuleRestApi\ModuleRestApiConfig**

 ```php
<?php

namespace Pyz\Glue\ModuleRestApi;

use Spryker\Glue\Kernel\AbstractBundleConfig;

class ModuleRestApiConfig extends AbstractBundleConfig
{
    public const RESOURCE_MODULE = 'module';
}
``` 

2. Create `module_api.transfer.xml`:

```xml
<?xml version="1.0"?>
<transfers xmlns="spryker:transfer-01" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="spryker:transfer-01 http://static.spryker.com/transfer-01.xsd">

    //transfer that contains information from the request
    <transfer name="GlueRequest">
    </transfer>

    //transfer that contains information about resource
    <transfer name="GlueResource">
        <property name="type" type="string"/>
        <property name="id" type="string"/>
        <property name="attributes" type="AbstractAttributes"/>
    </transfer>

    //transfer that contains information for the response
    <transfer name="GlueResponse">
        <property name="resources" type="GlueResource[]" singular="resource"/>
    </transfer>
    //used for collect request body data(if needed)
  <transfer name="ModuleRestAttributes">
    //add transfer fields
  </transfer>
  
    //used for declared list of methods in Spryker\Glue\GlueApplicationExtension\Dependency\Plugin\ResourceInterface::getDeclaredMethods()
  <transfer name="GlueResourceMethodCollection">
    <property name="get" type="GlueResourceMethodConfiguration"/>
    <property name="post" type="GlueResourceMethodConfiguration"/>
  </transfer>

    //used for declared method in Spryker\Glue\GlueApplicationExtension\Dependency\Plugin\ResourceInterface::getDeclaredMethods()
  <transfer name="GlueResourceMethodConfiguration">
    <property name="controller" type="string"/>
    <property name="action" type="string"/>
    <property name="attributes" type="string"/>
  </transfer>
  
  //add other used transfers
</transfers>
```

3. Create `ModuleController`: 

**\Pyz\Glue\ModuleRestApi\Controller\ModuleController**

```php
<?php

namespace Pyz\Glue\ModuleRestApi\Controller;

use Generated\Shared\Transfer\ModuleRestAttributesTransfer;
use Generated\Shared\Transfer\GlueRequestTransfer;
use Generated\Shared\Transfer\GlueResourceTransfer;
use Generated\Shared\Transfer\GlueResponseTransfer;
use Pyz\Glue\ModuleRestApi\ModuleRestApiConfig;
use Spryker\Glue\Kernel\Backend\Controller\AbstractBackendApiController;

class ModuleResourceController extends AbstractBackendApiController
{
    public function getAction(
      string $id, 
      GlueRequestTransfer $glueRequestTransfer
    ): GlueResponseTransfer {
        return (new GlueResponseTransfer())
          ->addResource((new GlueResourceTransfer())
            ->setId($id)
            ->setType(ModuleRestApiConfig::RESOURCE_MODULE)
            ->setAttributes((new ModuleRestAttributesTransfer());
    }
    
    public function postAction(
      ModuleRestAttributesTransfer $moduleRestAttributesTransfer,
      GlueRequestTransfer $glueRequestTransfer
    ): GlueResponseTransfer {
        return (new GlueResponseTransfer())
          ->addResource((new GlueResourceTransfer())
            ->setType(ModuleRestApiConfig::RESOURCE_MODULE)
            ->setAttributes((new ModuleRestAttributesTransfer());
    }
}
```

4. Create `ModuleResource`. For no convention resource, it must implement `ResourceInterface`.

**\Pyz\Glue\ModuleRestApi\Plugin\ModuleResource**

```php
<?php

namespace Pyz\Glue\ModuleRestApi\Plugin;

use Generated\Shared\Transfer\GlueResourceMethodCollectionTransfer;
use Generated\Shared\Transfer\GlueResourceMethodConfigurationTransfer;
use Generated\Shared\Transfer\ModuleRestAttributesTransfer;
use Pyz\Glue\ModuleRestApi\Controller\ModuleResourceController;
use Spryker\Glue\ModuleRestApi\ModuleRestApiConfig;
use Spryker\Glue\GlueApplication\Plugin\GlueApplication\Backend\AbstractResourcePlugin;
use Spryker\Glue\GlueApplicationExtension\Dependency\Plugin\ResourceInterface;

class ModuleResource extends AbstractResourcePlugin implements ResourceInterface
{
    public function getType(): string
    {
        return ModuleRestApiConfig::RESOURCE_MODULE;
    }
    
    public function getController(): string
    {
        return ModuleResourceController::class;
    }

    public function getDeclaredMethods(): GlueResourceMethodCollectionTransfer
    {
        return (new GlueResourceMethodCollectionTransfer())
            ->setGet(new GlueResourceMethodConfigurationTransfer())
            ->setPost(
                (new GlueResourceMethodConfigurationTransfer())
                    ->setAction('postAction')->setAttributes(ModuleRestAttributesTransfer::class),
            );
    }
}
```

See also [How to create or change a convention](/docs/scos/dev/glue-api-guides/{{page.version}}/decoupled-glue-infrastructure/how-to-guides/how-to-create-or-change-a-convention.html) guide.

5. Declare the resource: 

**\Pyz\Glue\GlueStorefrontApiApplication\GlueStorefrontApiApplicationDependencyProvider**

```php
<?php

namespace Pyz\Glue\GlueBackendApiApplication;

use Pyz\Glue\ModuleRestApi\Plugin\ModuleResource;
use Spryker\Glue\GlueBackendApiApplication\GlueBackendApiApplicationDependencyProvider as SprykerGlueBackendApiApplicationDependencyProvider;

class GlueBackendApiApplicationDependencyProvider extends SprykerGlueBackendApiApplicationDependencyProvider
{
    /**
     * @return array<\Spryker\Glue\GlueApplicationExtension\Dependency\Plugin\ResourceInterface>
     */
    protected function getResourcePlugins(): array
    {
        return [
            new ModuleResource(),
        ];
    }
}
```

6. Build a fresh cache for the API applications controllers.

```bash
vendor/bin/glue glue-api:controller:cache:warm-up
```

If everything is set up correctly, you can access `https://glue-backend.mysprykershop.com/module`.
