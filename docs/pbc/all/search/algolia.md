---
title: Algolia
description: Algolia is a search engine that 
---

By default, all Spryker stores have [Elasticsearch](https://www.elastic.co/elasticsearch/) as their search engine. However, you can replace it with the Algolia one.

The Algolia search engine that stands out from others due to its performance. With the Algolia app, your users can conduct advanced search of active concrete products in your store. 

{% info_block infoBox "Product offers and product reviews" %}

Algolia searches in product offers and product reviews as well. However, these entities are represented in product attributes in the Algolia search results.

{% endinfo_block %}

To use Algolia as your search engine, you need an account with Algolia. For details about Algolia integration, see [Integrate Algolia](/docs/pbc/all/search/integrate-algolia.html).

## Searchable attributes

Your users can search for active concrete products by the following attributes:

- SKU
- Name
- Description
- Keywords
- Currency
- Gross Price
- Net Price
- Product Abstract SKU
- Rating (average approved rating for a respective abstract product)
- Images
- Categories
- Attributes
- Merchants

Here is an example of the search results with these attributes in Algolia:

![algolia-search-results](https://spryker.s3.eu-central-1.amazonaws.com/docs/pbc/all/search/algolia/algolia/algolia-search-results.png)

## Indexes

An index is the place where the data used by Algolia is stored.

In case of the Spryker store, the index is a complete list of all active concrete products that can appear in search results.
There are separate indexes per locale and per sorting strategy. With the Algolia app, the search results in your store can be sorted by:

- Relevance
- From highest to lowest rating
- From lowest to highest rating
- By price in ascending order
- By price in descending order

For example, if you have two locales, there will be 10 indexes for your store in Algolia: one per each locale and per sorting strategy:
![algolia-indexes](https://spryker.s3.eu-central-1.amazonaws.com/docs/pbc/all/search/algolia/algolia/algolia-index.png)

The Algolia index is always kept up-to-date with the product data changes. That means, that if a Back Office user added or changed some searchable product attribute, like, for example, a description, the change is immediately reflected in the Algolia search results as well.
