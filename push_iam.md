---

copyright:
  years:  2017
lastupdated: "2017-10-09"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}

# Managing service access
{: #service-access-management}

With {{site.data.keyword.mobilepushshort}} and {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) account owners can manage user access in your account.
{: shortdesc}

As an account owner, you can set policies within your account to create different levels of access for different users. For example, certain users can have **Read only** access to one instance, but **Write** access to another. You can decide who is allowed to create, update, and delete instances of {{site.data.keyword.mobilepushshort}}.

For more information about IAM, see [IAM Access](/docs/iam/users_roles.html).

## User roles
{: #roles}

The scope of an access policy is based on a user's assigned role.
{: shortdesc}

Policies enable access to be granted at different levels. Some of the options include:
<ul><ul>
  <li>Access across all instances of the service in your account</li>
  <li>Access to an individual service instances in your account</li>
  <li>Access to a specific resource within an instance</li>
  <li>Access to all IAM-enabled services in your account</li>
</ul></ul>

Platform management roles enable users to perform tasks on service resources at the platform level. For example, roles can be assigned to determine who can create or delete IDs, create instances, and bind instances to apps. The following table details the actions as they correlate to platform management roles.

<table>
  <tr>
    <th>Platform role</th>
    <th>Permissions</th>
    <th>Example actions</th>
  </tr>
  <tr>
    <td><i>Viewer</i></td>
    <td>View {{site.data.keyword.mobilepushshort}} instances.</td>
    <td>You can see a Cloud Directory user's data or the identity provider configuration.</td>
  </tr>
  <tr>
    <td><i>Editor</i></td>
    <td>View and bind {{site.data.keyword.mobilepushshort}} instances.</td>
    <td>You can bind applications to an instance of {{site.data.keyword.mobilepushshort}}.</td>
  </tr>
  <tr>
    <td><i>Operator</i></td>
    <td>Create, delete, edit, suspend, resume, view, or bind {{site.data.keyword.mobilepushshort}} instances.</td>
    <td>You can create or delete an {{site.data.keyword.mobilepushshort}} instance from the catalog.</td>
  </tr>
  <tr>
    <td><i>Administrator</i></td>
    <td>All management actions for all services in the account.</td>
    <td>You can perform all operator actions and the ability to assign policies to other users.</td>
  </tr>
</table>

</br>
</br>
The following table details actions that are mapped to service access roles. Service access roles enable users to access {{site.data.keyword.mobilepushshort}} as well as the ability to call the {{site.data.keyword.mobilepushshort}} API.


<table>
  <tr>
    <th>Service role</th>
    <th>Permissions</th>
    <th>Example actions</th>
  </tr>
  <tr>
    <td><i>Reader</i></td>
    <td>View {{site.data.keyword.mobilepushshort}} instance data.</td>
    <td>Can view the details of the service instance such as user data or identity provider information.</td>
  </tr>
  <tr>
    <td> <i>Writer or Manager</i></td>
    <td>View and change an {{site.data.keyword.mobilepushshort}} instance.</td>
    <td>Can perform all Reader actions and edit the service instance, such as editing the identity provider configuration. </li></ul></td>
  </tr>
</table>

For more information about assigning user roles in the UI, see [Managing IAM access](/docs/iam/mngiam.html#iammanidaccser).


## {{site.data.keyword.mobilepushshort}} access policies
{: #access}

Every user who accesses the {{site.data.keyword.mobilepushshort}} service in your account must be assigned an access policy with an IAM user role defined. That policy determines what actions the user can perform within the context of the service or instance you select.
{: shortdesc}

The actions are customized and defined by the {{site.data.keyword.Bluemix_notm}} service as operations that are allowed to be performed in the service. The actions are then mapped to IAM user roles. Some of the actions taken you can track with the {{site.data.keyword.cloudaccesstrailshort}} service. In the following table, the actions and required permissions for {{site.data.keyword.mobilepushshort}} are mapped.

**Note:** The App secret is not be generated for the new instances as the {{site.data.keyword.mobilepushshort}} service has adopted IAM, you must use the [API keys instead](/docs/iam/apikeys.html).

|Action |Explanation |Required role |
|----------------------------------------------------|------------------|------------------------------|
|`GET /imfpush/v1/apps/{applicationId}/settings/*` |Get app settings |Manager, Writer, Reader|
|`DELETE /imfpush/v1/apps/{applicationId}/settings/* |Delete app settings |Manager|
|`PUT /imfpush/v1/apps/{applicationId}/settings/*` |Update app settings |Manager|
|`GET /imfpush/v1/apps/{applicationId}/devices/* ` |Get devices |Manager, Writer, Reader|
|`POST /imfpush/v1/apps/{applicationId}/devices` |Register device |Manager, Writer|
|`PUT /imfpush/v1/apps/{applicationId}/devices/{deviceId}` |Update device |Manager, Writer|
|`DELETE /imfpush/v1/apps/{applicationId}/devices/{deviceId}` |Delete device |Manager|
|`POST /imfpush/v1/apps/{applicationId}/messages` |Send messages |Manager, Writer|
|`POST /imfpush/v1/apps/{applicationId}/messages/bulk` |Send bulk messages |Manager, Writer|
|`DELETE /imfpush/v1/apps/{applicationId}/messages/{messageId}` |Delete a message |Manager|
|`GET /imfpush/v1/apps/{applicationId}/messages/*` |Get messages |Manager, Reader, Writer|
|`PUT /imfpush/v1/apps/{applicationId}/messages/{messageId}/deliverystatus` |Update message delivery status|Manager, Writer|
|`POST /imfpush/v1/apps/{applicationId}/tags` |Create tags |Manager, Writer|
|`PUT /imfpush/v1/apps/{applicationId}/tags/{tagName}` |Update tag   |Manager, Writer|
|`DELETE /imfpush/v1/apps/{applicationId}/tags/{tagName}` |Delete tag   |Manager|
|`GET /imfpush/v1/apps/{applicationId}/tags/*` |Get tags |Manager, Reader, Writer|
|`POST /imfpush/v1/apps/{applicationId}/subscriptions` |Create subscriptions |Manager, Writer|
|`DELETE /imfpush/v1/apps/{applicationId}/subscriptions` |Delete subscriptions |Manager|
|`GET /imfpush/v1/apps/{applicationId}/subscriptions` |Get Subscriptions |Manager, Reader, Writer|
|`POST /imfpush/v1/apps/{applicationId}/webhooks` |Create webhook |Manager, Writer|
|`PUT /imfpush/v1/apps/{applicationId}/webhooks/{webhookName}` |Update webhook |Manager, Writer|
|`DELETE /imfpush/v1/apps/{applicationId}/webhooks/{webhookName}` |Delete webhook |Manager|
|`GET /imfpush/v1/apps/{applicationId}/webhooks/*` |Get webhook |Manager, Reader, Writer|-|



