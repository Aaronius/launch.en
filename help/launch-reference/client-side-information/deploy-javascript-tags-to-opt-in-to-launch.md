---
title: Deploy JavaScript tags to opt in to Launch
seo-title: Deploy JavaScript tags to opt in to Launch in Adobe Experience Platform Launch
description: Deploy JavaScript tags to opt in to Adobe Experience Platform Launch
seo-description: Deploy JavaScript tags to opt in to Adobe Experience Platform Launch
---

# Deploy JavaScript tags to opt in to Launch

The combination of the European Union [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/art-7-gdpr/) and [ePrivacy](https://medium.com/mydata/consent-lost-gdpr-and-found-eprivacy-e85cf881ffb) legislation requires companies to be able to manage consent for their users. [!DNL Adobe] customers may require visitors to opt-in before [!DNL Adobe] solutions execute for any given visitor. Visitors should have the ability to manage their opt-in and opt-out status.

[!DNL Adobe Experience Cloud] customers require a variety of implementations of these requirements. Some use enterprise-level consent managers and others build their own.

For [!DNL Launch], extension developers use extensions and the rule builder to define opt-in and opt-out solutions.

This document contains information about how to prevent Adobe tags from firing until consent is acquired.

## Advertising Cloud

[!DNL Launch] does not fire [!DNL Advertising Cloud] automatically. [!DNL Advertising Cloud] only fires if you specifically tell it to in a rule action. Use the rule conditions to determine when and what to fire. For example, to use cookies to determine opt-in status, set a data element to read that cookie and use it as a condition in the rule to determine when to fire the Track Conversion action.

Integrations with consent managers (such as OneTrust) can set and track the consent cookies for customers, which can then be used in the rule builder.

## Analytics

In the Link Tracking section of the [!DNL Analytics] extension's configuration settings, make sure the following are _not_ selected:

* Track download links
* Track outbound links

When these settings are not selected, [!DNL Launch] does not fire [!DNL Adobe Analytics] automatically. [!DNL Analytics] fires only if you specifically tell it to in a rule action. Use the rule conditions to determine when and what to fire. For example, to use cookies to determine opt-in status, set a data element to read that cookie and use it as a condition in the rule to determine when to fire the Send Beacon action.

Integrations with consent managers (such as OneTrust) can set and track the consent cookies for customers, which can then be used in the rule builder.

## Audience Manager

DIL is currently set to fire automatically if it is placed on a customer page. There is currently no way to stop it from firing. [!DNL Adobe] is developing a way to pause the DIL from automatically firing while maintaining the correct cross-solution sequencing. This will be released soon.

[!DNL Adobe] recommends that you use server-side forwarding within [!DNL Analytics].

## Experience Cloud ID

[!DNL Experience Cloud ID] currently fires automatically if it is placed on a customer page. At this time, there is no way to stop it from firing. [!DNL Adobe] is developing a way to pause [!DNL Experience Cloud ID] from automatically firing while maintaining the correct cross-solution sequencing. This will be released soon.

## Target

[!DNL Launch] does not fire [!DNL Target] automatically. [!DNL Target] fires only if you specifically tell it to in a rule action. Use the rule conditions to determine when and what to fire. For example, to use cookies to determine opt-in status, set a data element to read that cookie and use it as a condition in the rule to determine when to fire the Load [!DNL Target] action.

Integrations with consent managers (such as OneTrust) can set and track the consent cookies for customers, which can then be used in the rule builder.
