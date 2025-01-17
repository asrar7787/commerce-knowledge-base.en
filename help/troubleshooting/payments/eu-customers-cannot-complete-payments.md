---
title: EU customers cannot complete payments
description: This article provides a fix for the issue of customers from the European Union not being able to complete payments.
exl-id: 8309d96b-47a3-4d27-b538-e6e3bcdfb7d4
---
# EU customers cannot complete payments

This article provides a fix for the issue of customers from the European Union not being able to complete payments.

## Affected products and versions

* Adobe Commerce on cloud infrastructure, all versions
* Adobe Commerce on-premises 2.2.x, 2.3.x
* Magento Open Source 2.2.x, 2.3.x

## Issue

Customers from the EU complain that their credit card transactions are being declined.

## Cause

The European Union revised a regulation called Payment Services Directive (PSD) with an updated version [PSD2](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32015L2366&from=EN). This is a European Union (EU) directive enforced to regulate payment services and payment service providers throughout the EU and European Economic Area (EEA). Strong Customer Authentication (SCA) is a requirement of PSD2 to increase payment data security and authentication. If your payment solutions do not comply with the directive requirements, this may result in customers not being able to complete payments. Please find more details in the [related Adobe Commerce DevBlog post](https://community.magento.com/t5/Magento-DevBlog/3D-Secure-2-0-changes/ba-p/136460).

## Solution

Follow the recommendations from the [Adobe Commerce Payment Provider Recommendations section of the DevBlog](https://community.magento.com/t5/Magento-DevBlog/3D-Secure-2-0-changes/ba-p/136460#recommendations).
