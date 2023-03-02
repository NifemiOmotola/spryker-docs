---
title: BazaarVoice
description: Find out how you can integrate and use Bazaarvoice in your Spryker shop
template: howto-guide-template
redirect_from:
   - docs/aop/user/apps/bazaarvoice.html
   - docs/acp/user/apps/bazaarvoice.html
   - docs/pbc/all/ratings-reviews/third-party-integrations/bazaarvoice.html  
---

![BazaarVoice](https://spryker.s3.eu-central-1.amazonaws.com/docs/pbc/all/ratings-reviews/third-party-integrations/bazaarvoice/bazaarvoice.png)

The [BazaarVoice](https://www.bazaarvoice.com/?ref=spryker-documentation) app lets you collect and add user-generated content (UGC) to your product pages. 

The BazaarVoice service offers the following UGC: 

- [Rating summaries](https://knowledge.bazaarvoice.com/wp-content/conversations/en_US/Display/display_integration.html#rating-summary?ref=spryker-documentation), or star ratings
- [Product reviews](https://knowledge.bazaarvoice.com/wp-content/conversations/en_US/Display/display_integration.html#reviews?ref=spryker-documentation)  
<!---- [Questions and answers](https://knowledge.bazaarvoice.com/wp-content/conversations/en_US/Display/display_integration.html#questions--answers)-->

BazaarVoice uses the content syndication approach, which means that stores using BazaarVoice republish each others' content. For example, if a store within the BazaarVoice's network has got a new product review, this review is shared across all other stores in the network that also have this product.

{% info_block warningBox "Important" %}

To enable BazaarVoice to match your products to products in other stores and upload product reviews into your store, you must use UPCs or EANs as unique identifiers for your products.

{% endinfo_block %}

When you connect BazaarVoice, the app puts JavaScrip tags into your store, and the JavaScript code tells the app where to insert the BazaarVoice content—reviews, star ratings, or questions and answers.

{% info_block infoBox "Info" %}

If you have BazaarVoice integrated, the Spryker default [Product Ratings and Reviews feature](/docs/scos/user/features/{{site.version}}/product-rating-and-reviews-feature-overview.html) is turned off. This means that ratings and reviews collected with the default Spryker Product Ratings and Reviews feature are replaced with the BazzareVoice ratings and reviews.

{% endinfo_block %}
