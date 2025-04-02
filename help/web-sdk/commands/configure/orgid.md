---
title: orgId
description: The orgId property is a string that tells Adobe which organization that data is sent to.
exl-id: 0e04e85a-800c-4927-a165-80a5a578f4c2
---
# `orgId`

* `orgId` property
  * string / 24-character alpha-numeric
  * "....@AdobeOrg"
    * pattern
  * == organization data / -- sent to -- Adobe
  * ⚠️if you use Web SDK -> MANDATORY ⚠️
  * how to locate?
    1. Log in | [experience.adobe.com](https://experience.adobe.com)
    2. **`[Ctrl]`** + **`[I]`**
       1. -> [!UICONTROL User Data Debugger] window 
    3. | assigned orgs, copy "Current Org ID"

## Configure an `orgID` using the Web SDK tag extension
* TODO:
Enter the org ID in the **[!UICONTROL IMS organization ID]** text field when [configuring the tag extension](/help/tags/extensions/client/web-sdk/web-sdk-extension-configuration.md).

1. Log in to [experience.adobe.com](https://experience.adobe.com) using your Adobe ID credentials.
1. Navigate to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.
1. Select the desired tag property.
1. Navigate to **[!UICONTROL Extensions]**, then click **[!UICONTROL Configure]** on the [!UICONTROL Adobe Experience Platform Web SDK] card.
1. Input the desired org ID into the [!UICONTROL IMS organization ID] text field near the top.
1. Click **[!UICONTROL Save]**, then publish your changes.

## Configure an `orgID` using the Web SDK JavaScript library

Set the `orgId` string when running the `configure` command. If you omit this property when configuring the Web SDK, the Web SDK throws a console error and data is not sent to Adobe.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
});
```
