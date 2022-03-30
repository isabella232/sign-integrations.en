---
title: Workday Installation Guide
description: Installation guide for enabling the Adobe Sign integration with Workday
uuid: 56478222-fe66-4fa5-aac3-0ecdf2863197
product: Adobe Sign
topic-tags: EchoSign/Integrations
content-type: reference
discoiquuid: 29d55a25-6e2f-4c59-ae7c-c21bb82cecba
locnotes: All languages; screenshots for Tier 1 and 2 only (see the currently published localized page for guidance)
type: Documentation
solution: Acrobat Sign
role: User, Developer
topic: Integrations
exl-id: 8f12b524-2123-45d4-98d5-b2b23580a5ea
---
# [!DNL Workday] Installation Guide{#workday-installation-guide}

[**Contact Adobe Sign Support**](https://adobe.com/go/adobesign-support-center)

## Overview {#overview}

This document explains how to integrate Adobe Sign into your [!DNL Workday] tenant. To use Adobe Sign within [!DNL Workday], you need to know how to create and modify [!DNL Workday] items such as:

* Business process framework
* Tenant set-up and configuration
* Reporting and [!DNL Workday] studio integration

The high-level steps to complete the integration are: 

* Activate your Administrative account in Adobe Sign (New Customers Only)
* Configure a Group in Adobe Sign to hold the [!DNL Workday] integration user
* Establish the OAuth relationship between [!DNL Workday] and Adobe Sign

## Activate your Adobe Sign account {#activating-your-adobe-sign-account}

Existing customers with established accounts can skip to the [Configure Adobe Sign for [!DNL Workday]](#config) topic.

For customers who are new to Adobe Sign and do not have a pre-existing log-in, an Adobe on-boarding specialist provisions your account (in Adobe Sign) for [!DNL Workday]. Once complete, you receive a confirmation email as shown below.

![Image of the Welcome Email from Adobe Sign](images/welcome-email-2020.png)

You need to follow the directions in the email to initialize your account and access your Adobe Sign [!UICONTROL Home] page.

![The Adobe Sign Dashboard page](images/classic-home.png) 

## Configure Adobe Sign for [!DNL Workday] {#config}

To configure Adobe Sign for [!DNL Workday], you need to generate following two dedicated objects in the Adobe Sign system:

* **A [!DNL Workday] group**: [!DNL Workday] requires a dedicated “group” within the Adobe Sign account to enable integration functionality. The Adobe Sign group is used to control only the [!DNL Workday] usage of Adobe Sign. Any other potential usage, such as Salesforce.com or Arriba is not impacted. The email notifications are suppressed in [!DNL Workday] group so that the [!DNL Workday] users only receive notifications within their [!DNL Workday] inbox.

* **An authenticating user to hold the integration key**: A [!DNL Workday] group must have only one group level administrator, who is the authoritative holder of the integration key. We recommend that the administrator use a functional email address such as `HR@MyDomain.com` instead of a personal email to reduce the risk of having the user disabled in future and consequently disabling the integration.

### Create a user and group in Adobe Sign {#create-a-user-and-group-in-adobe-sign}

To create a user in Adobe Sign:

1. Log in to Adobe Sign as the account administrator.
1. Navigate to **[!UICONTROL Account]** > **[!UICONTROL Users]**.
1. Click the ![plus icon image](images/icon_plus.png) to create a new user. 

    ![Image of the navigation path to create a new user](images/navigate-to-group-unbranded.png)

1. In the dialog that opens, provide the new user details:

    * Provide a functional email that you can access.
    * Enter an appropriate First and Last name value.
    * Select **[!UICONTROL Create a new group for this user]** from the User Group.    
    * Provide the **[!UICONTROL New Group Name]** with an intuitive name like *[!DNL Workday]*.

    ![The Create a User panel](images/create-user.png)

1. Click **[!UICONTROL Save]**.

    It brings you back to the [!UICONTROL Users] page that lists the new user with a **[!UICONTROL CREATED]** status. 

    ![A view of the new created user](images/post-user-creation.png)

To verify the email address of the user with “Created” status:

1. Log in to the new user’s email.
2. Find the “Welcome to Adobe Sign” email.
3. Click where it says **[!UICONTROL Click here to set your password]**.
4. Set the password.

Once you verify the email address, the status of the user changes from [!UICONTROL CREATED] to [!UICONTROL ACTIVE].

![Image of the new activated user](images/actived-users-575.png) 

### Define the authenticating user {#define-the-authenticating-user}

To promote the new user in the [!DNL Workday] group:

1. Navigate to the [!UICONTROL Users] page (if not already there).
2. Double-click the user in the [!DNL Workday] group.

    This opens an [!UICONTROL Edit] page for the user permissions.

3. Check the **[!UICONTROL Group Admin]**.
4. Click **[!UICONTROL Save]**.

![](images/user-permissions-edit1-575.png) 

## Configure the [!DNL Workday] tenant {#configure-workday}

To complete the connection between the [!DNL Workday] tenant and Adobe Sign, we need to establish a trusted relationship between the services. Once done, we can add a Review Document Step that enables the signature process through Adobe Sign.

>[!NOTE]
>
>Adobe Sign is branded as Adobe Document Cloud throughout the [!DNL Workday] environment.

To establish the trusted relationship:

1. Log in to [!DNL Workday] as an account administrator.
1. Open the **[!UICONTROL Edit Tenant Setup - Business Processes]** page.
1. Locate the [!UICONTROL eSignature Configuration] section:

    ![](images/esignature_configurations.png)

1. Click **[!UICONTROL Authenticate with Adobe]**.

    This starts the OAuth2.0 authentication sequence.

1. When asked, provide the credentials for the Adobe Sign Group admin that you created earlier.
1. Approve the access to Adobe Sign.

>[!NOTE]
>
>Make sure that you completely log out of any other Adobe Sign instance before proceeding.

Once connected, the Adobe configuration enabled checkbox is set and you can begin using Adobe Sign with [!DNL Workday].

### Configure the Review Document Step {#configure-review}

The document for the Review Document Step can be either one of the following:

* A static document
* A document generated by a Generate Document step within the same business process
* A formatted report created with the [!DNL Workday] Report Designer

You may add any of these docs with [Adobe Text Tags](https://adobe.com/go/adobesign_text_tag_guide) to control the look and position of the Adobe Signing specific components. The document source must be specified within the business process definition. It is not possible to upload an ad-hoc document while the business process is executing.

Unique to using Adobe Sign with a Review Document Step is the ability to have serialized Signer Groups. This allows you to specify role-based groups that sign in sequence. Adobe Sign does not support parallel signing groups.

For assistance configuring the Review Document Step, refer to the [Quick Start guide](https://adobe.com//go/adobesign_workday_quick_start){target="_blank"}.  

## Support {#support}

### [!DNL Workday] support {#workday-support}

[!DNL Workday] is the integration owner, and should be your first point of contact for questions about the scope of the integration, feature requests, or problems in day to day function of the integration.

You may refer to the following [!DNL Workday] community articles on how to troubleshoot the integration and generate documents:

* [Troubleshoot eSignature integrations](https://doc.workday.com/#/reader/3DMnG~27o049IYFWETFtTQ/zhA~hYllD3Hv1wu0CvHH_g)
* [Review documents step](https://doc.workday.com/#/reader/3DMnG~27o049IYFWETFtTQ/TboWWKQemecNipWgxLAjqg)
* [Dynamic document generation](https://community.workday.com/saml/login?destination=/articles/176443)
* [Offer document generation tips](https://community.workday.com/node/183242)

### Adobe Sign support {#adobe-sign-support}

Adobe Sign is the integration partner, and should be contacted if the integration is failing to obtain signatures, or if notification of pending signatures fails.

Adobe Sign Customers should contact their Customer Success Manager (CSM) for support. Alternatively, Adobe Technical Support can be reached by phone: 1-866-318-4100, wait for product list then enter: 4 and then 2 (as prompted).

* [Adding Adobe text tags to documents](https://adobe.com/go/adobesign_text_tag_guide)  
* [Review document configuration and examples](https://www.adobe.com//go/adobesign_workday_quick_start)

## Common questions {#faq}

### Why is the status not being updated within [!DNL Workday] even when the document is fully signed? {#why-is-the-status-not-being-updated-within-workday-even-the-document-is-fully-signed}

The document status in [!DNL Workday] may not reflect if the candidate does not click the '[!UICONTROL Submit]' button after signing in Adobe Sign. 

As per [!DNL Workday] task Check eSignature Signing Status: To start the process, the user can submit the associated Inbox task.

As per [!DNL Workday] Development: The original signing completes the process only if the user submits the inbox task after signing the document. After signing, the iframe is closed and the user is redirected to the same task where they can click the [!UICONTROL Submit] button to complete the process.
