---
title: "Azure AD authentication methods usage report API overview"
description: "The authentication methods usage report helps an organization understand how their end users are using Azure Active Directory capabilities such as self-service password reset and multi-factor authentication (MFA)."
author: dkershaw
localization_priority: Normal
ms.prod: identity and access reports
ms.date: 04/25/2019
---

# Azure AD Credentials Usage Report overview

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The authentication methods usage report helps an organization understand how their end users are using Azure Active Directory capabilities such as self-service password reset and Multi-Factor Authentication. Using this report, you can gain insights into how end users are registering and using these capabilities using the various authentication methods provided by Azure Active Directory. For example, you can use these reports to gather feedback when you are rolling out these capabilities within your organization. These reports will provide insights such as which authentication methods are more successful for your organization, what kind of errors the end users are running into as well as help you determine what kind of campaign you need to run to help your end users adopt these capabilities.

## What does this report cover?

- Authentication Method Registration Summary and Details (Self-service password reset registration at aka.ms/ssprsetup, Combined security info registration https://aka.ms/mysecurityinfo)
- Authentication Method Usage Summary and Details (Self-service password reset usage at https://aka.ms/sspr)

## What's not there?

- Authentication Method Registration Details for Multi-Factor Authentication at https://aka.ms/mfasetup
- Multi-Factor Authentication Usage (both Per-user and Conditional Access-based Multi-Factor Authentication)

## What can I do with APIs in Microsoft Graph?

Here are popular requests for working with this API:

Operation | URL | Description
:----------|:----|:----------
GET Credentials registration count | [https://graph.microsoft.com/beta/reports/credentialuserregistrationcount](https://developer.microsoft.com/graph/graph-explorer?request=reports/credentialuserregistrationcount&version=beta)| Get the number of users registered for self-service password reset and Multi-Factor Authentication
GET Credentials usage count  | [https://graph.microsoft.com/beta/reports/credentialusagesummary](https://developer.microsoft.com/graph/graph-explorer?request=reports/credentialusagesummary&version=beta)| Get the number of users using self-service password reset
GET Credentials registration details  | [https://graph.microsoft.com/beta/reports/credentialuserregistrationdetails](https://developer.microsoft.com/graph/graph-explorer?request=reports/credentialuserregistrationdetails&version=beta)|Get the user details for self-service password reset and Multi-Factor Authentication registration activities
GET Credentials usage details  | [https://graph.microsoft.com/beta/reports/usercredentialusagedetails](https://developer.microsoft.com/graph/graph-explorer?request=reports/usercredentialusagedetails&version=beta)| Get user details for all self-service password reset activities 


## What licenses do I need?

Usage Reports are available for features that you've licensed for. Hence, this report is available if you have the capability to leverage self-service password reset and MFA in your tenant.


## Next Steps
To learn how to deploy Azure Active Directory self-service password reset, go to https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment.
To learn how to deploy Azure Active Directory Multi-Factor Authentication, go to https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted.
To learn how to enable combined security info registration, go to https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined.

<!--
{
  "type": "#page.annotation",
  "suppressions": [
    "Error: /api-reference/beta/resources/azure-ad-auditlog-overview.md:\r\n      Exception processing links.\r\n    System.ArgumentException: Link Definition was null. Link text: !INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)\r\n      at ApiDoctor.Validation.DocFile.get_LinkDestinations()\r\n      at ApiDoctor.Validation.DocSet.ValidateLinks(Boolean includeWarnings, String[] relativePathForFiles, IssueLogger issues, Boolean requireFilenameCaseMatch, Boolean printOrphanedFiles)"
  ]
}
-->
