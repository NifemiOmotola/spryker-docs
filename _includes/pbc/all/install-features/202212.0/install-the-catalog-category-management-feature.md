

This document describes how to integrate the Catalog + Category Management feature into a Spryker project.

## Install feature core

Follow the steps below to install the Catalog + Category Management feature core.

### Prerequisites

To start feature integration, integrate the required features 

| NAME                | VERSION | INTEGRATION GUIDE                                            |
| ------------------- | ------- | ------------------------------------------------------------ |
| Spryker Core        | {{page.version}}  | [Spryker Core feature integration](/docs/scos/dev/feature-integration-guides/{{page.version}}/spryker-core-feature-integration.html) |
| Catalog             | {{page.version}}  |  |
| Category Management | {{page.version}}  | [Category Management feature integration](/docs/scos/dev/feature-integration-guides/{{page.version}}/category-management-feature-integration.html) |

### 1) Set up behavior

Activate the following plugins:

| PLUGIN  | SPECIFICATION  | PREREQUISITES | NAMESPACE  |
| -------------- | --------------- | ------------- | ---------------- |
| CategoryTreeFilterPageSearchResultFormatterPlugin | Populates the `categoryTreeFilter` aggregation with category nodes which have the `docCount` relevant for the result set. |               | Spryker\Client\CategoryStorage\Plugin\Elasticsearch\ResultFormatter |
| SortedCategoryQueryExpanderPlugin                 | Adds category sorting to the base query.                     |               | Spryker\Client\SearchElasticsearch\Plugin\QueryExpander      |

**src/Pyz/Client/Catalog/CatalogDependencyProvider.php**

```php
<?php

namespace Pyz\Client\Catalog;

use Spryker\Client\Catalog\CatalogDependencyProvider as SprykerCatalogDependencyProvider;
use Spryker\Client\CategoryStorage\Plugin\Elasticsearch\ResultFormatter\CategoryTreeFilterPageSearchResultFormatterPlugin;

class CatalogDependencyProvider extends SprykerCatalogDependencyProvider
{
        /**
     * @return \Spryker\Client\Search\Dependency\Plugin\ResultFormatterPluginInterface[]|\Spryker\Client\SearchExtension\Dependency\Plugin\ResultFormatterPluginInterface[]
     */
    protected function createCatalogSearchResultFormatterPlugins(): array
    {
        return [
            new CategoryTreeFilterPageSearchResultFormatterPlugin(),
        ];
    }
}
```

**src/Pyz/Client/Catalog/CatalogDependencyProvider.php**

```php
<?php

namespace Pyz\Client\Catalog;

use Spryker\Client\Catalog\CatalogDependencyProvider as SprykerCatalogDependencyProvider;
use Spryker\Client\Catalog\Plugin\ConfigTransferBuilder\CategoryFacetConfigTransferBuilderPlugin;
use Spryker\Client\SearchElasticsearch\Plugin\QueryExpander\SortedCategoryQueryExpanderPlugin;

class CatalogDependencyProvider extends SprykerCatalogDependencyProvider
{
    /**
     * @return \Spryker\Client\Search\Dependency\Plugin\QueryExpanderPluginInterface[]|\Spryker\Client\SearchExtension\Dependency\Plugin\QueryExpanderPluginInterface[]
     */
    protected function createCatalogSearchQueryExpanderPlugins()
    {
        return [
            new SortedCategoryQueryExpanderPlugin(CategoryFacetConfigTransferBuilderPlugin::PARAMETER_NAME),
        ];
    }
}
```

{% info_block warningBox "Verification" %}

Make sure the following:
- `CatalogClient::catalogSearch()` returns category nodes under the `categoryTreeFilter` index.
- The search query has a sort parameter.
- You can find categories using the global search on the Storefront.

{% endinfo_block %}

## Related features

Integrate the following related features:

| FEATURE  | REQUIRED FOR THE CURRENT FEATURE | INTEGRATION GUIDE     |
| ------------- | ---------------- | -------------------- |
| Catalog             |      &check;     | |
| Category Management |      &check;     | [Category Management feature integration](/docs/scos/dev/feature-integration-guides/{{page.version}}/category-management-feature-integration.html) |
