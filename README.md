![Onify Blueprints](https://files.readme.io/8ba3f14-onify-blueprints-logo.png)

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
![Test suite](https://github.com/onify/blueprint-dustin-index-product-catalog/workflows/Test%20suite/badge.svg)

# Onify Blueprint: Index product catalog from Dustin

[Dustin](https://www.dustin.se/) is the leading Nordic internet retailer of computer and electronic equipment. Many companies are buying products from Dustin and are using Dustins own portal for this. But many are looking for a way to incorporate the procurement process in their own custom portal (Onify). In this Blueprint we show how we can index product(s) catalog from Dustin. This way companies can make products available for request in the Onify portal.

![Onify Blueprint: Index product catalog from Dustin](blueprint.jpg "Blueprint")

## Requirements

* [Onify Hub](https://github.com/onify/install)
* [Onify Hub Functions](https://github.com/onify/hub-functions)
* [Camunda Modeler](https://camunda.com/download/modeler/)
* Dustin (custom product catalog and SFTP account)

## Setup

Add the following settings in Onify.

|Key|Name|Value|Type|Tag|Role|
|---|----|-----|----|---|----|
|dustin_sftp_host|Dustin SFTP Host|`sftp.dustin.eu`|string|dustin, frontend|admin|
|dustin_sftp_username|Dustin SFTP Username|`<USERNAME>`|string|dustin, frontend|admin|
|dustin_sftp_password|Dustin SFTP Password|`***`|password|dustin, frontend|admin|
|dustin_product_catalog_filename|Dustin Product Catalog Filename|`/<CUSTOMER>/Catalogue/<FILE>.xml`|string|dustin, frontend|admin|

> Note: Creating settings via admin interface add a trailing `_` in key. This is required for flow to work.

## Test

1. Open the BPMN diagram in Camunda Modeler.
2. Deploy the BPMN diagram (click `Deploy current diagram` and follow the steps).
3. Run it (click `Start current diagram`).

> Note: Disable or remove the `TESTING?` gateway when you deploy to production.

## Limitations

This Blueprint is only indexing products in a limited fashion. It only indexes one specific product catalog. We do not set any specific stock status (based on lead time information). We also need to add some actions if we want to be able to order the products :-)

## Support

* Community/forum: https://support.onify.co/discuss
* Documentation: https://support.onify.co/docs
* Support and SLA: https://support.onify.co/docs/get-support

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributors

Thanks [Tony Aronsson](https://github.com/Aronsson84) @ [Zitac](https://github.com/zitacconsulting) for the support.