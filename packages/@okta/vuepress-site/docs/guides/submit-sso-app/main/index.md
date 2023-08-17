---
title: Submit an SSO integration
meta:
  - name: description
    content: Use this guide to learn how to submit your Okta Single Sign-On (SSO) integration for publication with the Okta Integration Network (OIN) Manager.
layout: Guides
---

This guide walks you through the process of submitting an SSO OIDC or SAML 2.0 integration to the Okta Integration Network (OIN) using the OIN Manager. It also shows you how to update a previously published integration or delete a draft submission.

> **Note:** SWA app integrations are no longer accepted for publication in the OIN catalog.

---

**Learning outcomes**

* Understand how to submit a new SSO integration to the OIN.
* Understand how to update or delete a previously published OIN SSO integration.

**What you need**

* A functional SSO integration created and tested in accordance to the [Build a Single Sign-On integration](/docs/guides/build-sso-integration/) guide

* The various items necessary for submission in accordance to the [OIN submission requirements](/docs/guides/submit-app-prereq/)

---

## Overview

The [Okta Integration Network (OIN) Manager](https://oinmanager.okta.com) is a submission tool that is connected to your developer org where you test and develop your Okta integration. Use this tool to submit your SSO app integration for verification and publishing in the public OIN catalog.

### Protocols supported

This guide covers submissions that use the following protocols:

* [OpenID Connect (OIDC)](https://openid.net/connect/)

    > **Note:** <br>
    > * To support the potentially large numbers of Okta orgs accessing an authorization server through the OIN, an OIDC integration can't use a custom authorization server, including the `default` server.
    > * ISVs shouldn't rely on the `email_verified` scope-dependent claim returned by an OIDC integration to evaluate whether a user has verified ownership of the email address associated with their profile.

* [Security Assertion Markup Language (SAML)](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html)

    > **Note:** SAML integrations must use SHA256 encryption for security. If you're using SHA-1 for encryption, see our guide on how to [Upgrade SAML Apps to SHA256](/docs/guides/updating-saml-cert/).

> **Note:** SWA app integrations are no longer accepted for publication in the OIN catalog. However, existing SWA apps are still maintained by the OIN team.

### Submission support

Getting your app integration in the OIN catalog involves two phases:

* creating a functional integration
* submitting it through the OIN publication process

For each phase in the process, Okta has an associated support stream to assist you.

* When you're constructing your Okta integration, you can post a question on the [Okta Developer Forum](https://devforum.okta.com/).

* If you need help during the submission process, use the Get Support section on the **My App Integrations** page after you sign in to the [OIN Manager](https://oinmanager.okta.com). This section provides the following resources from the [Okta developer portal](https://developer.okta.com/):

  * OIN integration guides
  * Okta, OIDC, SAML, and SCIM concepts
  * A search tool to find articles in the Okta developer portal

  If you have questions or need additional support to publish your app integration, you can reach out to the Okta OIN team directly at <oin@okta.com>.

## Submit an integration

1. To start your integration submission, open the [OIN Manager](https://oinmanager.okta.com) and click **Start Submission Form**.

1. Sign in to the OIN Manager with your Okta development org credentials. Ensure that this org contains your developed app integration for submission.

1. Click **Add New Submission** to create a new submission instance.

1. If you want to review an in-progress submission, click **View** beside the name of your integration.

    > **Note:** If you need to update an integration, see [Update your published integration](#update-your-published-integration).

1. Begin defining your submission by specifying details in the [General Settings](#configure-general-settings) and [protocol-specific](#configure-protocol-specific-settings) tabs.

### Configure general settings

On the **General Settings** tab, fill in the basic information about your integration:

#### App information

* **Does your app exist in the OIN?**: Indicate if your integration exists in the OIN.

   * If your integration already exists in the OIN, provide the **Existing OIN app name** so that the Okta OIN team can locate it.

   * **What changes are you making to the existing OIN integration?**: If your integration already exists in the OIN, summarize the changes that you're requesting in your update. This summary helps the Okta OIN team address your changes.

* **App name**: Provide a name for your integration. This is the main title used for your integration in the OIN.

* **App website**:  Provide a link to your product or service homepage or a specific location on your website where users can learn more about your integration.

* **Use case(s)**: Specify one or more use cases for Okta to categorize your integration in the OIN catalog. Click **+ Add Another** to choose up to five use cases. See [Use case guidelines](/docs/guides/submit-app-prereq/main/#use-case-guidelines).

* **App description**: Give a general description of your application and what the Okta integration does. See [App description guidelines](/docs/guides/submit-app-prereq/main/#app-description-guidelines).

* **App icon**: Upload a PNG, JPG, or GIF file of a logo to accompany your integration in the catalog. The logo file must be less than one MB in size. See [Logo guidelines](/docs/guides/submit-app-prereq/main/#logo-guidelines).

#### Customer support

* **Support contacts**: Include one or more public contact points for users who need assistance with your integration. You can also add a link to an FAQ or a troubleshooting guide. Use the dropdown menu to specify if you're adding an email, a URL, or a phone number, and then click **+ Add Another** to add additional contacts. Okta shares this information with customers in the OIN catalog description for your app integration.

* **Escalation support contact**: This is an email distribution list for Okta to use when contacting your company about your integration. Okta can use this escalation contact in an emergency, so make sure that the contact provided here isn't a generic contact, such as `support@example.com` or a 1-800 number. This contact information isn't shared with customers.

See [Customer support contact guidelines](/docs/guides/submit-app-prereq/main/#customer-support-contact-guidelines).

#### Test account

The Okta OIN team requires a dedicated account on your application to run their tests. This test account needs to be kept active beyond the submission period in case Okta needs to update or troubleshoot your app integration. See [Test account guidelines](/docs/guides/submit-app-prereq/main/#test-account-guidelines).

* **Test account URL**: This is a static URL to sign in to your application. An Okta OIN team member navigates to this URL and uses the account credentials you provide in the subsequent fields to sign in to your application.

* **Test account username or email**: The username for your application test account. The Okta OIN team signs in with this username to run tests. The preferred account username is `isvtest@okta.com`.

* **Test account password**: The password for your application test account.

* **Additional instructions**: Include any other information that you think the Okta OIN team needs to know about your integration, the test account, or the testing configuration.

### Configure protocol-specific settings

You can submit protocol support details all together or asynchronously. For example, if your application currently only supports SAML, you can create the submission with the SAML protocol details. Later, when you add Workflows Connector capabilities to your application, you can return to your integration submission to include Workflows Connector support.

>**Note:** If you don't see the protocol-specific settings you want in this section, select the **Instructions for** dropdown menu on this page.

<StackSnippet snippet="protocol-name" />

<StackSnippet snippet="submit" />

<br>

As you add configuration information about your integration to the submission page, the indicators in the top right show your progress towards 100% completion.

You must include all required information before you can click **Submit for Review** to move your integration into the submission phase.

## Update your published integration

If you need to make protocol changes to your integration that is already published in the OIN catalog, you can visit the [OIN Manager](https://oinmanager.okta.com/) and create an updated version of the integration.

Similarly, when you enable a new capability in your application (for example, adding SCIM provisioning onto an existing published SAML application), you don't need to create an entirely new submission. You can update your existing submission to enable and specify the settings for that protocol, then submit the updated integration.

1. Sign in to the OIN Manager using the credentials for your original dev org.
    >**Note:** You must submit the updated integration using the same dev org that was used to make the original submission, otherwise the Okta OIN team rejects the update.
1. The published integration appears on your integrations page. Click **Update**.

    This creates a new instance of your integration where you can safely change any of the parameters. Your existing integration remains in the OIN catalog and keeps the previous settings until this new version is published.
1. Update any of the parameters for your existing protocols or add a new protocol depending on your needs.

    If you need to leave your in-progress submission at any point, you can return to it through the OIN Manager. When you sign on again, the published version and your in-progress version appears. Click **Edit** on the in-progress version to pick up where you left off.
1. When you complete the updates or fill in the new protocol information so that the indicator shows 100% complete, you can click **Submit for Review**.

    At this point, the Okta OIN team is notified and your submission undergoes the same process flow as the original submission.

    After the new version of the integration reaches the **Publish** stage and is published by Okta, the new version replaces the old one in the OIN catalog.

>**Note:** You can have a maximum of 10 submissions for any development org in the OIN Manager.

## Delete draft submissions

There are two scenarios where you need to delete a draft submission:

1. You have 10 draft submissions, which is the maximum number permitted in the OIN Manager.
1. You have decided against completing a draft submission and want to remove it.

In either of these scenarios, the OIN Manager provides a method to delete unpublished submissions. For instructions on how to delete app integrations that are already published in the OIN catalog, see [Delete published submissions](#delete-published-submissions).

You can only delete unpublished submissions that are in **DRAFT** state.

To delete your submission:

1. Click the delete icon ![trash can; delete icon](/img/icons/delete_can.png) beside the **Edit** button. If the delete icon is unavailable, that submission can't be deleted.
1. Confirm the deletion in the dialog box.

No email confirmation is sent when deleting a submission. Deleted submissions can't be recovered.

If you need assistance with deleting a draft submission, contact the Okta OIN team at <oin@okta.com>.

## Delete published submissions

If you want to remove an app integration that is already published to the OIN catalog, this change must be processed by the Okta OIN team. Send an email to <oin@okta.com> with the URL of your dev org, the name of the app integration, and a link to its location in the OIN catalog.

Removing an app integration from the OIN doesn't prohibit existing users from accessing it. The app integration won't be removed from end-user dashboards until an admin for the customer's org removes the app integration from the org.

Finally, if you intend to remove your back-end application support for the Okta app integration, alert your customer admins about the change and if you're deploying a replacement solution.

## See also

<StackSnippet snippet="see-also" />