---
title: Test Fastly on Production if a Live Site uses the same domain
description: If you have a live site up-and-running on your production domain (`example.com`) and you need to test your new store on Adobe Commerce on cloud infrastructure's Production environment with Fastly CDN enabled, we recommend using the subdomain (like `prod.example.com`), having previously added it to Fastly, for any pre-launch testing activities. This article discusses the details and provides useful links to the related Adobe Commerce documentation resources.
exl-id: bc9d11c8-ce47-461d-b5b8-c03494bc4ceb
---
# Test Fastly on Production if a Live Site uses the same domain

If you have a live site up-and-running on your production domain (`example.com`) and you need to test your new store on Adobe Commerce on cloud infrastructure's Production environment with Fastly CDN enabled, we recommend using the subdomain (like `prod.example.com`), having previously added it to Fastly, for any pre-launch testing activities. This article discusses the details and provides useful links to the related Adobe Commerce documentation resources.

## Issue

Your current store that uses the `example.com` production domain is live and operating. However, you need to test your new store, built with Adobe Commerce on cloud infrastructure and deployed to the Production environment, with the Fastly full page cache service enabled.

The problem is that the Production environment of your Adobe Commerce on cloud infrastructure project uses the same live domain (`example.com`), and you cannot switch your new site to this domain, simultaneously having your current live store running &ndash; on the same domain.

### Why use Fastly for testing on the Production environment?

In theory, you could skip using Fastly CDN and test your Adobe Commerce on cloud infrastructure store on the Production environment without full page cache enabled.

However, with full-page cache enabled, your store performs differently; you never know the real live performance of your site if you have not tested it with CDN before launching. Testing your store on Production with Fastly CDN enabled is the official Adobe Commerce recommendation.

## Solution: use production subdomain

Use the first-level subdomain (`prod.example.com`) for your new Adobe Commerce on cloud infrastructure store on the Production environment while keeping the current live site on the base domain (`example.com`).

When planning your Adobe Commerce on cloud infrastructure project, you may specify such a production subdomain and request the cloud infrastructure team to point the subdomain to the Fastly service.

Follow these steps to process the subdomain within your Adobe Commerce on cloud infrastructure project:

* [Submit a support ticket](/help/help-center-guide/help-center/magento-help-center-user-guide.md#submit-ticket) requesting to add the subdomain to the Fastly service/Nginx configuration (for Adobe Commerce on cloud infrastructure Pro plan architecture).
* Configure the corresponding DNS settings on your side.

After performing the steps for subdomain configuration, you must also take these steps to validate your production domain for the SSL certificate:

* Upload the DNS TXT record for SSL validation of your production domain.
* [Submit a support ticket](/help/help-center-guide/help-center/magento-help-center-user-guide.md#submit-ticket) requesting to validate the production domain for the SSL certificate.

Using the subdomain allows you to perform a "soft launch" of your store in the future &ndash; since such launch only requires updating the corresponding DNS settings.

## Related documentation

In our support knowledge base:

* [Configure Fastly DNS settings on Staging and Production environments](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/how-to/configure-fastly-dns-settings-on-staging-and-production-environments.html)
* [Set up Fastly for Starter plan on cloud](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/how-to/set-up-fastly-for-starter-plan-on-cloud.html)
* [Potential blockers for launching on Adobe Commerce on cloud infrastructure](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/blockers-launching-on-magento-commerce-cloud.html)

In our developer documentation:

* [Fastly Overview](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/cdn/fastly.html)
* [Go live checklist: DNS configurations for Fastly](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/launch/checklist.html)
