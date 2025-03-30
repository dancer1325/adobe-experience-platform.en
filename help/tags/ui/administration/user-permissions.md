---
title: User Permissions for Tags
description: Learn about the different types of permissions available for tags and some basic implementation strategies for different business use cases.
exl-id: 9b48847a-6133-4dbd-b17d-e7b88152ad7d
---
# User permissions for tags

* User permissions for Adobe Experience Platform's tags -- are assigned, via Adobe Admin Console, to -- users
  * 💡-- via -- product profiles 💡
    * != assign to individual users
    * DIFFERENT permissions / product files

* goal
  * types of permissions / tags
  * functionalities / -- granted by the -- permissions
  * basic implementation strategies / use cases

## Permission types / tags

1. Platforms
2. Properties
3. Property Rights
4. Company Rights

### Platforms

* EXIST platform / EACH tag property  
* supported platforms
  * Web
  * Mobile
* allows
  * restricting OR granting access | PARTICULAR type of property
* use case
  * team / manages your mobile apps != team / manages your websites

### Properties

* by default, product profiles -- grant access to -- ALL properties / EXIST | your company 
* allows
  * restricting OR granting access / specific existing properties -- by -- name

### Property rights {#property-rights}

* TODO:
Any tag property that you create in the UI becomes available in Admin Console, allowing you to group the property with specific property rights in the same product profile


For example, if a given product profile does not have access to Property A1, users who belong to that profile cannot see or modify any settings within Property A1
If a user belongs to a profile that does have access to Property A1, the actions they can perform within Property A1 are determined by the rights they have been granted from this profile
If a user has permissions for Property A1 but has no assigned rights, then they have read-only access for that property

The following table outlines the available property rights and the functionalities they grant access to:

| Property right | Description |
| --- | --- |
| **Develop** | This allows you to perform the following actions:<ul><li>Create rules and data elements</li><li>Create libraries and build them in existing development environments</li><li>Submit a library for approval</li></ul>Most day-to-day tasks in the UI require this right. |
| **Approve** | This allows you to take a submitted library and build to the staging environment. You can also approve a library for publishing once testing has been completed. |
| **Publish** | This allows you to publish approved libraries to the production environment. |
| **Manage Extensions** | This allows you to perform the following actions: <ul><li>Install new extensions to a property</li><li>Modify the configuration for an already installed extension</li><li>Delete an extension</li></ul>See the extensions overview documentation for [more information on extensions](../managing-resources/extensions/overview.md). This role typically belongs to IT or Marketing, depending on your organization. |
| **Manage Environments** | This allows you to create and modify environments. See the [environments documentation](../publishing/environments.md) for more information. This role typically belongs to the IT group. |

{style="table-layout:auto"}

### Company rights

Company rights apply to permissions that span multiple properties.  These are outlined in the table below:

| Company right | Description |
| --- | --- |
| **Manage Properties** | This allows you to perform the following actions:<ul><li>Create new properties</li><li>Modify metadata and settings at the property level</li><li>Delete properties</li></ul>Administrators usually perform this role. See the [properties documentation](companies-and-properties.md) for more information. |
| **Develop Extensions** | Grants the ability to create and modify extension packages that are owned by the company, including private releases and requests for public release. |
| **Manage App Configurations** | This is only available to if you have a license for Adobe Journey Optimizer or another solution that grants access to mobile in-app and push messaging.  This allows you to manage the apps that Experience Cloud knows about along with the necessary push credentials needed to communicate with the Firebase Cloud Messaging service and the Apple Push Notification Service. |

{style="table-layout:auto"}

## Total user permissions

An individual user's total permissions are determined by their total membership in different product profiles. If a user belongs to multiple product profiles, the permissions from each profile are added together rather than multiplied.

For example, Product Profile A grants you the Develop right for Property 1. Product Profile B grants you the Publish right for Property 2. In this case, you can Develop in Property 1 and Publish in Property 2, but you cannot publish in Property 1 or Develop in Property 2 because you have not been granted explicit rights to do so.

## Rights scenarios 

Different companies have different needs when creating new product profiles. These needs vary based on company size, organization structure, the number of sites, the number of people involved in managing tags, and so on.

Below are a few common scenarios and a recommended starting point as you think about creating product profiles and adding users to them.

### One-person show

If you run a small company that has one person in charge of everything, grant this user permissions for all properties and assign them all rights listed above.

### Separation of duties

Consider a situation where many people in your organization are involved in tagging. You have one set of people (such as an external consultant) that creates rules and data elements, but you do not want them to have access to the production environment. In this case, you want to make sure that nobody deploys to Production except the IT team.

To accomplish this:

1. Create an account for your consultants and grant them only the Develop right.
1. The consultant builds and tests within the confines you set.
1. If the consultant wants a new extension or is ready to go live, a representative from your organization (with the appropriate rights) performs those actions.

### Enterprise

An enterprise company might have multiple sites divided geographically, with different teams responsible for each geo. Within those teams, different individuals develop and publish.

This is similar to "Separation of duties" above, but organized by geographic areas. For example, you can create a "Develop" profile and a "Publish" profile for North America, and create separate "Develop" and "Publish" groups for Europe.

## Example roles

The following table provides some examples of the types of roles you might have in your organization and which permissions you should assign them:

| Role | Description | Properties | Property Rights | Company Rights |
| --- | --- | --- | --- | --- |
| The Manager | Wants to see what is happening in the system, but should not be able to make any changes. | Auto-include | (None)  | (None) | 
| The Marketer | Can install extensions and set up new tags for existing properties, but cannot publish to the staging or production environments. | Auto-include | <ul><li>Develop</li><li>Manage Extensions</li></ul> | <ul><li>Manage Properties</li></ul> |
| The Mobile App Developer | Is responsible for implementing Adobe and 3rd-party solutions inside a native mobile app. | Auto-include | <ul><li>Develop</li><li>Manage Extensions</li></ul> | <li>Manage Properties</li><li>Manage App Configurations</li> |
| The IT Team | Does not actually modify any tags, but they have full control over the staging and production environments and what is in them. | Auto-include | (None) | <ul><li>Approve</li><li>Publish</li><li>Manage Environments</li></ul> |
| The Extension Developer | Develops extensions and can submit for approval, but cannot publish or add them to existing properties. | Auto-include | <ul><li>Develop</li></ul> | <ul><li>Manage Properties</li><li>Develop Extensions</li></ul> |
| The Super User | Does everything. | Auto-include | <ul><li>Develop</li><li>Approve</li><li>Publish</li><li>Manage Extensions</li><li>Manage Environments</li></ul> | <ul><li>Manage Properties</li></ul> |

{style="table-layout:auto"}

## Next steps

This document provided an overview of the available permissions for tags in Experience Platform. For steps on how to configure product profiles for tags in Adobe Admin Console, see the guide on [managing user permissions for data collection](../../../collection/permissions.md).
