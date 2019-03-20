---
title: Azure Media Services v3 overview | Microsoft Docs
description: This article provides a high-level overview of Media Services and provides links to articles for more details.
services: media-services
documentationcenter: na
author: Juliako
manager: femila
editor: ''
tags: ''
keywords: azure media services, stream, broadcast, live, offline

ms.service: media-services
ms.devlang: multiple
ms.topic: overview
ms.tgt_pltfrm: multiple
ms.workload: media
ms.date: 03/14/2019
ms.author: juliako
ms.custom: mvc
#Customer intent: As a developer or a content provider, I want to encode, stream (on demand or live), analyze my media content so that my customers can: view the content on a wide variety of browsers and devices, gain valuable insights from recorded content.
---

# What is Azure Media Services v3?

Azure Media Services is a cloud-based platform that enables you to build solutions that achieve broadcast-quality video streaming, enhance accessibility and distribution, analyze content, and much more. Whether you are an application developer, a call center, a government agency, an entertainment company, Media Services helps you create applications that deliver media experiences of outstanding quality to large audiences on today’s most popular mobile devices and browsers. 

## What can I do with Media Services?

Media Services enables you to build a variety of media workflows in the cloud, the following are some examples of what can be accomplished with Media Services.  

* Deliver videos in various formats so they can be played on a wide variety of browsers and devices. For both on-demand and live streaming delivery to various clients (mobile devices, TV, PC, etc.) the video and audio content needs to be encoded and packaged appropriately. To see how to deliver and stream such content, see [Quickstart: Encode and stream files](stream-files-dotnet-quickstart.md).
* Stream live sporting events to a large online audience, such as soccer, baseball, college and high school sports, and more. 
* Broadcast public meetings and events such as town halls, city council meetings, and legislative bodies.
* Analyze recorded videos or audio content. For example, to achieve higher customer satisfaction, organizations can extract speech-to-text and build search indexes and dashboards. Then, they can extract intelligence around common complaints, sources of complaints, and other relevant data.
* Create a subscription video service and stream DRM protected content when a customer (for example, a movie studio) needs to restrict the access and use of proprietary copyrighted work.
* Deliver offline content for playback on airplanes, trains, and automobiles. A customer might need to download content onto their phone or tablet for playback when they anticipate to be disconnected from the network.
* Implement an educational e-learning video platform with Azure Media Services and [Azure Cognitive Services APIs](https://docs.microsoft.com/azure/#pivot=products&panel=ai) for speech-to-text captioning, translating to multi-languages, etc. 
* Use Azure Media Services together with [Azure Cognitive Services APIs](https://docs.microsoft.com/azure/#pivot=products&panel=ai) to add subtitles and captions to videos to cater to a broader audience (for example, people with hearing disabilities or people who want to read along in a different language).
* Enable Azure CDN to achieve large scaling to better handle instantaneous high loads (for example, the start of a product launch event). 

## v3 capabilities

v3 is based on a unified API surface, which exposes both management and operations functionality built on Azure Resource Manager. 

This version provides the following capabilities:  

* **Transforms** that help you define simple workflows of media processing or analytics tasks. Transform is a recipe for processing your video and audio files. You can then apply it repeatedly to process all the files in your content library, by submitting jobs to the Transform.
* **Jobs** to process (encode or analyze) your videos. An input content can be specified on a job using HTTPS URLs, SAS URLs, or paths to files located in Azure Blob storage. Currently, AMS v3 does not support chunked transfer encoding over HTTPS URLs.
* **Notifications** that monitor job progress or states, or Live Events start/stop and error events. Notifications are integrated with the Azure Event Grid notification system. You can easily subscribe to events on several resources in Azure Media Services. 
* **Azure Resource Management** templates can be used to create and deploy Transforms, Streaming Endpoints, Live Events, and more.
* **Role-based access control** can be set at the resource level, allowing you to lock down access to specific resources like Transforms, Live Events, and more.
* **Client SDKs** in multiple languages: .NET, .NET core, Python, Go, Java, and Node.js.

## Naming conventions

Azure Media Services v3 resource names (for example, Assets, Jobs, Transforms) are subject to Azure Resource Manager naming constraints. In accordance with Azure Resource Manager, the resource names are always unique. Thus, you can use any unique identifier strings (for example, GUIDs) for your resource names. 

Media Services resource names cannot include: '<', '>', '%', '&', ':', '&#92;', '?', '/', '*', '+', '.', the single quote character, or any control characters. All other characters are allowed. The max length of a resource name is 260 characters. 

For more information about Azure Resource Manager naming, see: [Naming requirements](https://github.com/Azure/azure-resource-manager-rpc/blob/master/v1.0/resource-api-reference.md#arguments-for-crud-on-resource) and [Naming conventions](https://docs.microsoft.com/azure/architecture/best-practices/naming-conventions).

## v3 API design principles

One of the key design principles of the v3 API is to make the API more secure. v3 APIs do not return secrets or credentials on a **Get** or **List** operation. The keys are always null, empty, or sanitized from the response. You need to call a separate action method to get secrets or credentials. Separate actions enable you to set different RBAC security permissions in case some APIs do retrieve/display  secrets while other APIs do not. For information on how to manager access using RBAC, see [Use RBAC to manage access](https://docs.microsoft.com/azure/role-based-access-control/role-assignments-rest).

Examples of this include 

* not returning ContentKey values in the Get of the StreamingLocator, 
* not returning the restriction keys in the get of the ContentKeyPolicy, 
* not returning the query string part of the URL (to remove the signature) of Jobs' HTTP Input URLs.

See the [Get content key policy - .NET](get-content-key-policy-dotnet-howto.md) example.

## How can I get started with v3?

For information on how to start developing with the Media Services v3 API using various tools and SDKs, see [Start developing](developers-guide.md).

## v3 content map

The Media Services v3 content is organized according to the following structure (also reflected in the table of contents):

|Sections| Description|
|---|---|
| Overview | Explains the functionality of Media Services and what you can do with the service.|
| Quickstarts | Show fundamental day-1 instructions for new customers to quickly try out Media Services.|
| Tutorials | Show scenario-based procedures for some of the top Media Services tasks.|
| Samples | Links to code samples. |
| Concepts | Contain in-depth explanation of [Media Services v3 concepts and functionality](concepts-overview.md). The fundamental concepts described in these topics should be reviewed prior to starting development.<br/><br/>* Cloud upload and storage<br/>* Encoding<br/>* Media analytics<br/>* Packaging, delivery, protection<br/>* Live streaming<br/>* Monitoring<br/>* Player clients<br/><br/>and more. |
| How-to guides | Demonstrate how to complete a task.|

## Next steps

To see how easy it is to start encoding and streaming video files, check out [Stream files](stream-files-dotnet-quickstart.md). 

