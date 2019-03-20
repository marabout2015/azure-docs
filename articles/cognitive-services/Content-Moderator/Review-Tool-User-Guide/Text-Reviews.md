---
title: Review text in Azure Content Moderator - Content Moderator
description: Learn how to review text in Content Moderator to see its score and detected tags. Use the information to detemine whether content is appropriate.
services: cognitive-services
author: sanjeev3
manager: mikemcca
ms.service: cognitive-services
ms.subservice: content-moderator
ms.topic: article
ms.date: 01/10/2019
ms.author: sajagtap

---

# Let human reviewers review text

You can use Azure Content Moderator to review text by using scores and detected tags. Use the information to determine whether content is appropriate. 

## Select or enter the text to review

In Content Moderator, select the **Try** tab. Then, select the **Text** option to go to the text moderation start screen. Enter any text, or submit the default sample text for automated text moderation. You can enter a maximum of 1,024 characters.

## Get ready to review results

The Review tool first calls the Text Moderation API. Then, it generates text reviews by using the detected tags. The Review tool matches score results for your team's attention.

## Review text results

Detailed results appear in the windows. Results include detected tags and terms that were returned by the Text Moderation API. To toggle a tag's selection status, select the tag. You can also work with any custom tags that you might have created.

![Screenshot of the review tool showing flagged text in a Chrome browser window](../images/reviewresults_text.png)
