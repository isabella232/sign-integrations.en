---
title: Veeva Vault User Guide
description: Veeva Vault customers user guide on how to user Adobe Sign integration with Veeva
products: Adobe Sign
content-type: reference
locnotes: All languages; screenshots to follow what's there already (seems there is a mix within a given language version of the article) 
type: Documentation
solution: Adobe Sign
role: User, Developer
topic: Integrations
---

# Adobe Sign for [!DNL Veeva Vault]: User Guide {#veeva-vault-user-guide}

[**Contact Adobe Sign Support**](https://adobe.com/go/adobesign-support-center)

This document is designed to help [!DNL Veeva Vault] customers learn how to use Adobe Sign for [!DNL Veeva Vault] integration to send an agreement. 

## Overview {#overview}

Adobe Sign integration with [!DNL Veeva Vault] facilitates the process of obtaining a signature or approval for any documentation that requires legal signatures or auditable document processing.

The overall process of sending documents for signature is similar to sending an email, so it is easy to adopt for most users.

Adobe Sign integration with [!DNL Veeva Vault] streamlines and expedite your document and signature workflows. By using the integration workflow, you:

* Saving time and resources spent on snail mail, overnighting, and faxing.
* Send contracts for e-signature or approval from [!DNL Veeva Vault], access real-time contract history, and view saved contracts.
* Track the deals in real-time across your organization and get updates when agreements are viewed, signed, canceled, or declined.
* eSign in over 20 languages and support fax-back service in 50+ locales worldwide.
* Create reusable Agreement Templates for sending options and enable one-click 'Send for Signature’ buttons.

## Send an Agreement using Adobe Sign for [!DNL Veeva Vault] {#send-sign-vault-agreement}

To send an agreement using Adobe Sign for Veeva:

1. Go to the [[!DNL Veeva Vault] login page](https://login.veevavault.com/) and enter your username and password. It opens your Vault's home page, as shown below.

    ![](images/vault-home.png)

1. Select **[!UICONTROL Library]** tab and then select **[!UICONTROL Create]** from the top-right corner.

    ![](images/create-library.png)

1. Select **[!UICONTROL Upload and Continue]**.

1. Upload any document from your local drive.

1. In the dialog that appears, select **[!UICONTROL Type]** as *[!UICONTROL Clinical]* and then select a **[!UICONTROL Subtype]** and **[!UICONTROL Classification]**, if required. 

    ![](images/choose-document-type.png)

1. Select **[!UICONTROL Ok]** to close the dialog.

1. Select **[!UICONTROL Next]**.

1. In the window that shows, fill in all the required fields in the metadata section and select **[!UICONTROL Save]**.

    ![](images/metadata-details.png)

1. It creates a test document in **[!UICONTROL Draft]** status, as displayed below.

    ![](images/document-draft.png)

1. From the top-right corner, select ![gear icon](images/icon-gear.png) dropdown menu and select **[!UICONTROL Start Review]**.

    ![](images/start-review.png)

1. Select the **[!UICONTROL Reviewer]** and **[!UICONTROL Review Due Date]**.

1. Select **[!UICONTROL Start]**. It changes the document Status to [!UICONTROL IN REVIEW].

    ![](images/in-review.png)

1. Complete the assigned task on behalf of the reviewers. Once you are done, it changes the document Status to [!UICONTROL REVIEWED].

    ![](images/reviewed-status.png)

1. Select ![gear icon](images/icon-gear.png) dropdown menu and select **[!UICONTROL Adobe Sign]**.

    ![](images/select-adobe-sign.png)

1. In the iFrame window that opens in Vault, enter the recipient's email address and select **[!UICONTROL Next]**.

    ![](images/iframe.png)

1. Once the document is processed, drag and drop the Signature fields on from the right panel and select **[!UICONTROL Send]**.  

    ![](images/add-signature-fields.png)

1. It sends the document to the recipient for signature. Once the recipient receives the document email, the document status changes from [!UICONTROL Reviewed] to [!UICONTROL In Adobe Signing].

    ![](images/in-adobe-signing.png)

1. Once all the signatures are captured and completed in Adobe Sign, the document Status in Vault changes to [!UICONTROL Approved].

1. Select **[!UICONTROL Document Files]** option and expand the **[!UICONTROL Renditions]** section in Vault. It automatically creates a new Rendition called 'Adobe Sign Rendition' once the document is in Approved state. 

    ![](images/document-files.png)

1. Download the Adobe Sign Rendition for validating the reciepient signature.

    ![](images/verify-signature.png)

## Cancel an Agreement using Adobe Sign for [!DNL Veeva Vault] {#cancel-sign-vault-agreement}

1. Go to the [[!DNL Veeva Vault] login page](https://login.veevavault.com/) and enter your username and password. It opens your Vault's home page, as shown below.

    ![](images/vault-home.png)

1. Select **[!UICONTROL Library]** tab and then select the document. The document status can be: [!UICONTROL In Adobe Sign Draft], [!UICONTROL In Adobe Sign Authoring], or [!UICONTROL In Adobe Signing].

    ![](images/document-adobe-sign-authoring.png)

1. Select **[!UICONTROL Cancel Adobe Sign]**.

    ![](images/cancel-document.png)

1. It triggers the Web Action and loads the iFrame window in [!UICONTROL Vault].

   ![](images/cancelled-document.png)

1. The document status automatically changes to [!UICONTROL Review].

    ![](images/cancel-reviewed.png)

After the document status changed to Review, you can again send it out for signature.

