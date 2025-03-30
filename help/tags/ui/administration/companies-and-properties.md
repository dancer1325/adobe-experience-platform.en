---
title: Properties
description: Learn how your extensions, environments, and libraries are organized and grouped for your organization in Adobe Experience Platform.
exl-id: e5b4a853-c23e-498c-9e20-e773ea1de88b
---
# Properties

* == collection of rules / data elements / configured extensions / environments / libraries

## Web properties

* OWN set of embed codes / EACH web property 
  * uses
    * deploy | MULTIPLE DISTINCT websites (== domains)
* 1 publish embed code / property

## Mobile properties

* -- can contain -- MULTIPLE applications
* allows
  * managing the SAME set of rules & extensions -- ACROSS -- MULTIPLE iOS & Android applications
* 1 configuration app ID / property

## Best practices | plan properties {#best-practices-for-planning-properties}

* take in account
  * Code structure
  * Data
  * Variables
  * Extensions, tags, and systems
  * People

### Code structure

* depending on product 
  * sites -- are based on -- HTML
  * mobile applications on -- are based on -- code 
* if HTML templates or codebases are SAME | MULTIPLE sites & applications -> use 1! tag property / manage MULTIPLE sites or apps

### Data

* if data / you collect is SIMILAR -> group those sites or applications | 1! property
  * Reason 🧠 avoid 
    * duplicating rules or
    * copying rules 🧠
* if your data collection needs to be UNIQUE / EACH site or application -> separate them / their OWN properties 
* lets you
  * control the data collection MORE specifically -- WITHOUT using -- large amounts of conditional logic | custom scripts

### Variables

* wonder if the variables are
  * similar,
    * if they are SIMILAR | ACROSS sites or applications -> include | SAME property
  * unique

### Extensions, tags, and systems

* wonder if the extensions, tags, and systems / you are going to deploy, are
  * similar,
    * if they are SIMILAR | ACROSS sites or applications -> include | SAME property
  * unique
    * if you are deploying [!DNL Adobe Analytics] | 1! site or application & your OTHER extensions and tags are ALSO UNIQUE -> create separate properties
      * Reason: 🧠 have MORE control 🧠

### People

* wonder if individuals, teams, and organizations / work | Adobe Experience Platform, they need access to
  * ALL your websites and applications,
  * SOME of them,
  * ONLY 1

* User Management features
  * allow you to
    * assign DIFFERENT roles / DIFFERENT people -- for --
      * ALL your properties or
      * per-property  
    * hide a property / CERTAIN users (non-admins)

## Properties page

* TODO:
A property can be any grouping of one or more domains and subdomains. 
You can manage and track these assets similarly. 
For example, suppose that you have multiple websites based on one template, and you want to track the same assets on all of them. 
You can apply one property to multiple domains.

The left side of the screen shows the companies in your organization. This is particularly useful if you manage multiple accounts. 
Select a company to see the properties and audit logs for that company.

Each property is shown in the Properties list.

The Properties list shows the following information:

* Property name
* Platform
* Status

Select a property to see an overview of that property. The overview shows any activity performed on the property. 
It also lists the metrics and extensions for the property.

## Create or configure a property

This section provides guidance on how to create or configure a tag property in Adobe Experience Platform.

>[!NOTE]
>
>Only a user with sufficient rights can create a property. See [User Management](user-permissions.md).

Before beginning, review the [Best practices for planning properties](companies-and-properties.md#best-practices-for-planning-properties) for properties.

Navigate to your company page, then select **[!UICONTROL Add Property]**, or select an existing property from the list and select **[!UICONTROL Configure]**.

![](../../images/property-settings.png)

### For Web

Follow the instructions to create a web property.

1. Fill in the fields:

   **Name:** The name of your property.

   **Domains:** The base URL of any sites you plan to deploy this property to

1. (Advanced) **[!UICONTROL Run rule components in sequence]** Select this checkbox to make conditions and actions wait for the previous one to complete before they run
1. (Advanced) **[!UICONTROL Return an empty string for missing data elements:]** If you reference a data element that does not exist within a library, that would normally return `undefined`.  Select this check box if you want that scenario to return an empty string instead.
1. (Advanced) **[!UICONTROL Configure for extension development:]** Select this check box if you plan to install development extensions that are being actively developed by your company
1. Select **[!UICONTROL Save]**.

### For Mobile

Follow the instructions to create a mobile property.

1. Fill in the fields: 

   * **Name:** The name of your property. 
   * **Privacy:** By default the privacy setting is set to Opted In, meaning that you would like for the SDK to collect and send data to solutions. If you select Opted Out, the SDK by default will NOT send data to solutions. If you choose Unknown as the setting, the SDK will require that the application first prompt the user to allow for data collection and sharing.

     >[!NOTE]
     >
     >These settings can be further controlled via API in the mobile application. 

   * **Use HTTPS:** Choose if all data communication should be sent over HTTP or HTTPS.

1. Select **[!UICONTROL Save]**.

After your property is created, Platform automatically adds a default host, a set of environments (Development, Staging, and Production), and the default extensions.

## Delete a property

* ❌can NOT be reversed❌
* requirements
  * admin-level user
* steps
  1. \| Properties list, select the property(S) / you want to delete
  2. Select **[!UICONTROL Delete]**
