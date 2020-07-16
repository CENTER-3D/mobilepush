---

copyright:
  years: 2015, 2020
lastupdated: "2020-06-18"

keywords: push notifications, push notification, notifications, tag-based, creating tags, managing tags, get tag, subscribe tag

subcollection: mobilepush

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:download: .download}
{:java: .ph data-hd-programlang='java'}
{:ruby: .ph data-hd-programlang='ruby'}
{:c#: .ph data-hd-programlang='c#'}
{:objectc: .ph data-hd-programlang='Objective C'}
{:python: .ph data-hd-programlang='python'}
{:javascript: .ph data-hd-programlang='javascript'}
{:php: .ph data-hd-programlang='PHP'}
{:swift: .ph data-hd-programlang='swift'}
{:reactnative: .ph data-hd-programlang='React Native'}
{:csharp: .ph data-hd-programlang='csharp'}
{:ios: .ph data-hd-programlang='iOS'}
{:android: .ph data-hd-programlang='Android'}
{:cordova: .ph data-hd-programlang='Cordova'}
{:xml: .ph data-hd-programlang='xml'}

# Tag-based notifications
{: #tag_based_notifications}

Tag-based notifications are messages that are targeted to all devices that are subscribed to a particular tag. Tags-based notifications allow segmentation of notifications based on subject areas or topics. Notification recipients can choose to receive notifications only if it is about a subject or topic that is of interest. Therefore, tags-based notification provides a means to segment recipients. This feature enables the ability to define tags and then send and receive messages by tags. A message is targeted to only the client application instances (on mobile, browser or as an app or extensions) that are subscribed to the tag. You must first create tags for the application, set up the tag subscriptions and then initiate the tag-based notifications. To send a tag-based notification that uses the REST API, ensure that the "tagNames" are provided when posting to the message resource.

You can define tags and then send and receive messages by using tags. You must first create the tags for the application, create subscriptions and then initiate the tag-based notifications. To send a Tag-based notification by using the [ReST API](https://eu-gb.imfpush.cloud.ibm.com/imfpush/){: external}, ensure that the `tagNames` are provided when posting to the message resource.

## Managing tags
{: #manage_tags}

Use the {{site.data.keyword.mobilepushshort}} console to create and delete tags for your application and then initiate tag-based notifications. The tag-based notification is received on devices that are subscribed to tags.

### Creating tags
{: #create_tags}

Tag-based notifications are messages that are targeted to all devices subscribed to a particular tag. Each device can subscribe to any number of tags. 

1. On the {{site.data.keyword.mobilepushshort}} console, select the **Tags** on the left navigation menu.
1. Click **Create** button.   
   - In the **Tag name** field, enter the name of the tag. For example, "coupons".
   - In the **Description** field, enter a tag description.
   - Click **Save**.

1. In the **Code Snippets** area, select the platform for your mobile application.
1. Modify the code snippets to handle errors and then copy the code snippets for each tag into your mobile application.

### Deleting tags
{: #delete_tags}

1. On the {{site.data.keyword.mobilepushshort}} console, select the **Tags**.
1. Select the tag that you want to delete and click **Delete** icon.

When a tag is deleted, information that is associated with the tag, including its subscribers and devices, are deleted. Automatic unsubscribe is not required, as the tag no longer exists. No further action is required from the client side.

### Editing a tag description
{: #edit_tags}

1. On the {{site.data.keyword.mobilepushshort}} console, select the **Tags** on the left navigation menu.
1. Select the tag that you want to edit.
1. Click the **Edit** icon.
1. Edit the tag description and then click **Save**.

## Get tags
{: #get_tags}

Tags provide a way to send targeted notifications to users based on their interests, unlike general broadcasts that are sent to all applications. You can create and manage tags by using the Tags tab on the {{site.data.keyword.mobilepushshort}} console or use REST APIs. You can use code snippets to manage and query your tag subscriptions for your mobile application. You can use the code snippets to get subscriptions, subscribe to a tag, unsubscribe from a tag, or get a list of available tags. Copy these code snippets to your mobile application.

- For Android, see `getTags` API and `getSubscriptions` API in [Push Notification get tags on Android](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-push/tree/Doc#ios-app).
- For Cordova, see `retrieveAvailableTags()` API and `retrieveSubscriptions()` API in [Push Notifications get tags on Cordova](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-push/tree/Doc#push-notification-service-tags).
- For iOS, see `retrieveAvailableTagsWithCompletionHandler` API in the [Push Notifications get tags on Swift](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-push/tree/Doc#retrieve-tags).
- For web browsers, see `retrieveAvailableTags()` API in [Push Notifications get tag on web browsers](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-javascript-webpush/blob/Doc/README.md#push-notification-service-tags).

## Subscribe tags
{: #Subscribe_tags}

Use the following API to allow your devices to retrieve tags, subscribe to a tag, retrieve subscriptions, and unsubscribe from a tag.

- For Android, use the `getTags`, `subscribe`, `getSubscriptions`, and `unsubscribeFromTags` API's. See [Push Notifications subscribe tags for Android](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-push/tree/Doc#push-notification-service-tags).
- For Cordova, use the `retrieveAvailableTags()`, `subscribe()`, `retrieveSubscriptions()`, and `unsubscribe()` API's. See [Push Notifications subscribe tags for Cordova](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-push/tree/Doc#push-notification-service-tags).
- For iOS, use the `retrieveAvailableTagsWithCompletionHandler`, `subscribeToTags`, `retrieveSubscriptionsWithCompletionHandler`, and `unsubscribeFromTags` API's. See [Push Notifications subscribe tags for Swift](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-push/tree/Doc#push-notification-service-tags).
- For web browsers, use the `retrieveAvailableTags()`, `subscribe()`, `retrieveSubscriptions()`, and `unSubscribe()` API's. See [Push Notifications subscribe tags for web browsers](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-javascript-webpush/blob/Doc/README.md#push-notification-service-tags).

## Using tag-based notifications
{: #using_tags}

Tag-based notifications are messages that are targeted to all devices that are subscribed to a particular tag. Each device can be subscribed to any number of tags. This topic describes how to send tag-based notifications. Subscriptions are maintained by the {{site.data.keyword.mobilepushshort}} service IBM Cloud instance. When a tag is deleted, all information that is associated with that tag, including its subscribers and devices are deleted. No automatic unsubscribe is needed for this tag since it no longer exists and no further action is required from the client side.

Create tags on the **Tag** screen. For information about how to create tags, see [Creating tags](/docs/mobilepush?topic=mobilepush-tag_based_notifications#create_tags).

1. From the {{site.data.keyword.mobilepushshort}} console, click **Notifications** on the left navigation menu.
1. Click **Create**, and compose a message.
   - Compose a new notification by providing the following information: **Notification text**, **Notification title** (optional), **Additional payload** (optional).
   - Select the **Target audience** by one of the following targets:
      - **Platforms** - Options are: **Android**, **iOS**, **Web Notifications**, **Chrome Apps and Extensions**, **Chrome Browser**, **Firefox**, **Safari**, and **All Devices**.
      - **Tags** - Enter the tags that you want to use, topic name or create a new tag.
1. Click **Send**.
