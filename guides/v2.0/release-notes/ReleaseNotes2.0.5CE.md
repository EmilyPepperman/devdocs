---
group: release-notes
subgroup: 02_rel-notes
title: Magento Open Source 2.0.5 Release Notes 
menu_title: Magento Open Source 2.0.5 Release Notes 
menu_order: 190
level3_menu_node: level3child
level3_subgroup: ce20-relnotes
---

We are pleased to present Magento Open Source 2.0.5. This release includes miscellaneous functional fixes. 


Backward-incompatible changes are documented in [Magento 2.0 Backward Incompatible Changes]({{ site.baseurl }}/guides/v2.0/release-notes/changes_2.0.html){: target="_blank"}.

### Fixed issues

####  Upgrade and Installation


<!-- 50224 --> *  Magento no longer assumes hard-coded root {% glossarytooltip 50e49338-1e6c-4473-8527-9e401d67ea2b %}category{% endglossarytooltip %} IDs or default category IDs. Previously, Magento used hard-coded IDs for these values, which could produce inconsistent data during store installation.

#### Import/Export

<!-- 46245 --> * Product import now works successfully in a multi-store environment. Previously, Magento would display the following error message,  "URL key for specified store already exists", when importing products into a multi-store configuration. 

<!-- 48722 --> * Export performance has been enhanced.  Pages no longer hang randomly, and CPU usage is no longer pegged.  [(GITHUB-3217)](https://github.com/magento/magento2/issues/3217){: target="_blank"}

#### Database

<!-- 49004 --> * Magento no longer duplicates queries to the database from the {% glossarytooltip 8d40d668-4996-4856-9f81-b1386cf4b14f %}Catalog{% endglossarytooltip %} page. Instead, if Magento has already loaded specific data during request processing, it re-uses it instead of duplicating the query. 

<!-- 49003 --> * Magento no longer duplicates SQL queries on {% glossarytooltip f3944faf-127e-4097-9918-a2e9c647d44f %}CMS{% endglossarytooltip %} and Category pages. Previously, significant duplications occurred. 

#### Miscellaneous

<!-- 47255 --> * Selecting the Use Aggregated Data option now correctly displays Dashboard data. [(GITHUB-3459)](https://github.com/magento/magento2/issues/3459){: target="_blank"}

<!-- 51074 --> * Magento now displays the expected color swatch when you select a color swatch for a {% glossarytooltip 2fd4d100-28d2-45ca-bec1-128444ea98e6 %}configurable product{% endglossarytooltip %}. Previously, Magento did not change the color when you selected a swatch.

<!-- 48659 -->* {% glossarytooltip a2aff425-07dd-4bd6-9671-29b7edefa871 %}HTML{% endglossarytooltip %} template minification now properly handles commented code.


<!-- 48760 --> * Deleting one of several custom options no longer deletes all options. Previously, deleting one option from the Product page also deleted all other custom options. [(GITHUB-2989)](https://github.com/magento/magento2/issues/2989){: target="_blank"}  


<!-- 50279 --> * When Full Page {% glossarytooltip 0bc9c8bc-de1a-4a06-9c99-a89a29c30645 %}Cache{% endglossarytooltip %} (FPC) is enabled, the CAPTCHA image differs for every user. Previously, the CAPTCHA image on the registration page remained the same for every customer after FPC was enabled.

<!-- 50195 --> * Google no longer indexes the {% glossarytooltip 29ddb393-ca22-4df9-a8d4-0024d75739b1 %}Admin{% endglossarytooltip %} {% glossarytooltip a05c59d3-77b9-47d0-92a1-2cbffe3f8622 %}URL{% endglossarytooltip %}. Previously, Google indexed the Admin side {% glossarytooltip 9ebd108f-d925-4c41-b6ba-affc1890d8b8 %}meta tag{% endglossarytooltip %}. The {% glossarytooltip b00459e5-a793-44dd-98d5-852ab33fc344 %}frontend{% endglossarytooltip %} meta tag was not affected. 


<!-- 43959 --> * Magento no longer sends a subscription success email whenever a customer enters his email address to subscribe to a newsletter. Users receive a "thank you for your subscription" message and a subscription success email only when registering for the first time. 

<!-- 47458 --> * Guests can now successfully click on the product page link for any item in an emailed shared wishlist. 

<!-- 50912 --> * Custom customer attributes are now saved at {% glossarytooltip 278c3ce0-cd4c-4ffc-a098-695d94d73bde %}checkout{% endglossarytooltip %}. 

### System requirements

Our technology stack is built on {% glossarytooltip bf703ab1-ca4b-48f9-b2b7-16a81fd46e02 %}PHP{% endglossarytooltip %} and MySQL. Magento 2.0.1 and later support PHP 5.5, 5.6, 7.0.2, and MySQL 5.6. For more information, see 
[System Requirements]({{ site.baseurl }}/magento-system-requirements.html){:target="_blank"}.

### Installation instructions

#### New installations

New users can now complete a full installation of Magento Open Source 2.0.5 from an archive file on the [Download](https://www.magentocommerce.com/download){: target="_blank"} page.

##### <b>Download a new installation</b>#####

1. Go to the [Magento Open Source Download](https://www.magentocommerce.com/download){: target="_blank"} page.

2. Under Full Release, select a format for the download archive file. Then, click **Download**.

3.	Follow the Magento [installation instructions]({{ site.baseurl }}/guides/v2.0/install-gde/prereq/integrator_install.html#integrator-first-composer-ce){: target="_blank"}.

##### <b>Install a new installation with Composer</b>#####

1. Go to the [Magento Open Source Download](https://www.magentocommerce.com/download){: target="_blank"} page.

2.	Under **Download with Composer**, click **Download**.

3.	Follow the instructions to download Composer, and get the Magento Open Source {% glossarytooltip 7490850a-0654-4ce1-83ff-d88c1d7d07fa %}metapackage{% endglossarytooltip %}.


#### **Upgrade existing installations**

If you installed Magento Open Source 2.0.0 from an archive, you must perform some additional tasks before you can upgrade your installation. Current users of Magento 2.0.0/2.0.1/2.0.2/2.0.3/2.0.4 must first update the installer from the command line. Then, update the installation from the [Web Setup Wizard](http://docs.magento.com/m2/ce/user_guide/system/web-setup-wizard.html){: target="_blank"} or command line. For detailed instructions, see the [technical bulletin]({{ site.baseurl }}/guides/v2.0/release-notes/tech_bull_201-upgrade.html){: target="_blank"}.


##### <b>Upgrade an existing installation from the Setup Wizard</b>#####

1.	Log in to Admin with Administrator privileges.

2.	On the Admin sidebar, click **System**. Under **Tools**,  choose **Web Setup Wizard**.

3.	Click  **System Upgrade**. Follow the onscreen instructions to complete the upgrade.

For more information, see [Upgrade the Magento installation and components]({{ site.baseurl }}/guides/v2.0/comp-mgr/bk-compman-upgrade-guide.html){: target="_blank"}.


##### <b>Upgrade an existing installation from the GitHub repository</b>#####
Developers who contribute to the Open Source codebase can [upgrade manually]({{ site.baseurl }}/guides/v2.0/comp-mgr/bk-compman-upgrade-guide.html){: target="_blank"} from the Magento Open Source GitHub repository.

1.	Go to the [Contributing Developers]({{ site.baseurl }}/guides/v2.0/install-gde/install/cli/dev_options.html){: target="_blank"} page.

2.	Follow the instructions to pull the updates from the repository and update {% glossarytooltip d85e2d0a-221f-4d03-aa43-0cda9f50809e %}Composer{% endglossarytooltip %}.

### Migration toolkits

The [Data Migration Tool]({{ page.baseurl }}/migration/migration-migrate.html){: target="_blank"} helps transfer existing Magento 1.x store data to Magento 2.x. This command-line interface includes verification, progress tracking, logging, and testing functions. For installation instructions, see [Install the Data Migration Tool]({{ page.baseurl }}/migration/migration-tool-install.html){: target="_blank"}. Consider exploring or contributing to the [ Magento Data Migration repository](https://github.com/magento/data-migration-tool){: target="_blank"}.

The [Code Migration Toolkit](https://github.com/magento/code-migration){: target="_blank"} helps transfer existing Magento 1.x store extensions and customizations to Magento 2.0.x. The command-line interface includes scripts for converting Magento 1.x modules and layouts.












