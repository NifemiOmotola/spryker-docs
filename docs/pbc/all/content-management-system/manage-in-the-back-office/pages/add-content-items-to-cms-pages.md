---
title: Add content items to CMS pages and blocks
description: Learn how to add content items to CMS pages in the Back Office
last_updated: Oct 22, 2022
template: back-office-user-guide-template
---

This document describes how to add a content item widget to a page and block using the Back Office.

## Prerequisites

To start adding content item widgets to pages, navigate to **Content&nbsp;<span aria-label="and then">></span> Pages**.

To start adding content item widgets to blocks, navigate to **Content&nbsp;<span aria-label="and then">></span> Blocks**.

{% info_block warningBox %}

Prior to adding a content item widget to a block or a page, make sure that the page is _active_ and _not expired_; otherwise, it will not be displayed on the website.

{% endinfo_block %}

## Adding content item widgets to pages

To add a content item widget to a page:

1. On the *Overview of CMS Pages* page, In the _Actions_ column, select **Edit&nbsp;<span aria-label="and then">></span> Placeholders** next to the page you want to add a content item widget to.
2. On the *Edit Placeholders: CMS Page [Name]* page, go to the *Placeholder* tab and place your cursor where you want to insert the content items.
3. In the editor pane, select the widget you want to add from the **Content Item** drop-down list.

![Content item menu page](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Content+Management+System/Content+Item+Widgets/Adding+Content+Item+Widgets+to+Pages+and+Blocks/content-item-menu-page.png)

The *Insert a Content Item* pop-up window opens.

![Insert content item window](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Content+Management+System/Content+Item+Widgets/Adding+Content+Item+Widgets+to+Pages+and+Blocks/insert-content-item-window.png)

5. Select a content item and its template, and click **Insert**.

{% info_block infoBox %}

Keep in mind that you can select only *one* item and *one* template at a time.

{% endinfo_block %}

This will insert a content item widget with the following details:
![Widget UI element](https://spryker.s3.eu-central-1.amazonaws.com/docs/User+Guides/Back+Office+User+Guides/Content+Management+System/Content+Item+Widgets/Adding+Content+Item+Widgets+to+Pages+and+Blocks/widget-ui-element.png)

* Content Item Type
* Content Item Key
* Name
* Template

{% info_block infoBox %}

Templates are project-specific and are usually created by a developer and a business person. If you are missing a Content Item Widget template, contact them and refer to [HowTo - Create a content item widget template](/docs/scos/dev/tutorials-and-howtos/howtos/feature-howtos/cms/howto-create-cms-templates.html#content-item-widget-template).

{% endinfo_block %}

6. Click **Save**. A new content item widget will be added to the page.

{% info_block infoBox %}

You can preview the page to see how the content item widget will be displayed on the website or publish it. To learn how to preview and publish the page, see  [Managing CMS pages](/docs/scos/user/back-office-user-guides/{{page.version}}/content/pages/managing-cms-pages.html)

{% endinfo_block %}
