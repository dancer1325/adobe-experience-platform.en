---
title: Tags Overview
description: Tags in Adobe Experience Platform are the next generation of tag management capabilities from Adobe. Tags give customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.
exl-id: 23d882a5-1ddd-404b-a7e9-3000f1804971
---
# Tags overview

* Adobe Experience Platform's Tags
  * == Adobe's NEXT generation of tag management capabilities
  * uses
    * customers -- can easily -- deploy & manage
      * analytics,
      * marketing,
      * advertising tags
  * enable build & maintain their OWN extensions (== integrations) / available | [!DNL Adobe Experience Cloud] customers

## Key benefits {#key-benefits}

* Faster time to value
* data centralized collection / organized
* integration of data + marketing technology

## Key features {#key-features}

* right panel -- to learn MORE about -- tags
  ![Tags properties in the Data Collection UI.](./images/ui/tags-overview/tags-properties.png)

### Extensions {#extensions}

* extension
  * == package of code (JavaScript, HTML, and CSS) / 
    * extends the tags functionality
    * use a virtually self-service interface

### Extension catalog {#extension-catalog}

* -- provided by -- INDEPENDENT software vendors

### Rule builder {#rule-builder}

* -- provide options for
  * Events
  * Conditions
  * Exceptions
  * Actions
* includes
  * real-time error checking
  * syntax highlighting

### Data elements {#data-elements}

* -- across -- 
  * web-based marketing technology
  * advertising technology

### Enterprise publishing {#enterprise-publishing}

* TODO:
The publishing process enables teams to publish code to pages. 
Different people can create an implementation, approve it, and publish it on your pages.

* Changes to your code are encapsulated within the libraries you define.
* You specify where and when you want your code deployed.
* Multiple libraries can be built in parallel by different teams.
* Unlimited development environments.
* A deliberate, permission-based process for merging libraries together.

### Open APIs {#open-apis}

* uses
  * automate implementations of 
    * individual technologies or
    * group of technologies

* use cases
  * Tags -- interact with the -- Reactor API
  * Deployments -- can be automated through -- APIs
  * Integrate the APIs -- with your -- OWN internal systems
  * build your OWN UI 

### Light, modular container tag {#modular-tag}

* TODO:
The content of your container is minified, including your custom code.
 Everything is modular.
 If you don't need an item, it is not included in your library.
 The result is an implementation that is fast and compact.
 See [Minification](./ui/publishing/builds.md).

## Other highlights {#other-highlights}

Tags provide several improvements over similar systems, including:

* No use of `document.write ()` where Chrome doesn't allow it.
* The Page Top and Page Bottom rules are bundled into the main library to minimize unnecessary HTTP calls.
* Custom action scripts within a rule can be loaded in parallel, but are executed sequentially.
* If you avoid Page Top and Page Bottom rules, the code is mostly asynchronous, with a path to getting fully async.
