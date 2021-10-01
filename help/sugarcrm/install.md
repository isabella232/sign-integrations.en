---
title: Adobe EchoSign for SugarCRM
description: Installation guide for enabling the Adobe Sign integration with SugarCRM
product: Adobe Sign
content-type: reference
type: Documentation
solution: Adobe Sign
role: User, Developer
topic: Integrations
---

# Overview

Adobe EchoSign for SugarCRM is the leading eSignature and web contracting solution that delivers electronic signature automation in SugarCRM for eSignatures and fax signatures. Users can directly send contracts from SugarCRM, view contract history and save eSigned contracts with associated accounts, contacts, quotes and more.
Adobe EchoSign for SugarCRM is available for all supported versions of SugarCRM, including 6.3 - 6.7 for on-demand or on-premise solutions.

## About This Guide

This document is a guide for SugarCRM administrators to install and configure Adobe EchoSign for SugarCRM plugin.

## Install this Plugin

1. Get the Adobe EchoSign for SugarCRM archive file from the [SugarExchange listing](http://www.sugarexchange.com/product_details.php?product=1123).
1. Log into SugarCRM with your administrator account.
1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Module Loader]**.
1. To upload the archive file of the Adobe EchoSign for SugarCRM plugin, select **[!UICONTROL Browse]**, then select the archive file, and then select **[!UICONTROL Upload]**.
1. After the archive file is uploaded, select **[!UICONTROL Install]** to begin installation.
1. Review the terms and conditions, then select **[!UICONTROL Accept]** > **[!UICONTROL Commit]**.
1. If the plugin installs successfully, the progress bar indicates 100% success.  If the progress bar does not reach 100%, select **[!UICONTROL Display Log]** to see the error encountered by SugarCRM.
1. After installing, go to **[!UICONTROL Administration > Repair]** and Select **[!UICONTROL Quick Repair and Rebuild]**.

>[!NOTE]
>
>If you are installing the plugin on SugarCRM OnDemand, file a support ticket with SugarCRM to temporarily remove the restrictions of the package inspector for OnDemand so that the package can be installed. This is part of the standard process.

## Upgrade the Plugin

If you are updating the Adobe EchoSign for SugarCRM plugin to a newer version, you should install the plugin without uninstalling the previous version.
After upgrading the plugin, go to **[!UICONTROL Administration]** > **[!UICONTROL Repair]** and select **[!UICONTROL  Quick Repair and Rebuild]**.

**Note:** If you uninstall a previous plugin, do not remove the tables during the uninstall. Else, you may lose the EchoSign agreement data.

## Configure the Plugin

1. If you are already an Adobe EchoSign customer, continue to Step 2.  

    If you do not have an EchoSign account, [sign up for a FREE 14-day trial](https://sugarcrmintegration.echosign.com/public/login) and follow the online registration steps until your Adobe EchoSign account is enabled.
1. Sign into [Echo Sign account](http://www.echosign.com) and follow these steps:
    1. Select **[!UICONTROL Account]** tab.
    1. Select **[!UICONTROL EchoSign API]** on the lower left side. 
    1. Select **[!UICONTROL Enable API Access]** and get your API key from the page.
1. In SugarCRM, go to **[!UICONTROL Administration]** > **[!UICONTROL Adobe EchoSign Settings]** and enter the API key in the field labeled [!UICONTROL EchoSign API Key].
1. Optionally, configure the plugin with the following settings:

    1. Automatically attach PDF when creating an agreement from a Quote: Select whether to automatically attach a PDF of the quote if a SugarCRM user creates an EchoSign agreement from the Quotes module.
    1. Manage recipients list: Select which modules appear in the Recipient subpanel in the EchoSign Agreements module. This also adds the EchoSign Agreements subpanel to those modules.
    1. Add the send buttons to these modules: Select if you want the Create EchoSign Agreement button/action to be included with the Quote module’s primary actions.
    1. Select **[!UICONTROL Save]** to store your settings.

**Note:** The Adobe EchoSign for SugarCRM plugin requires the [PHP SOAP extension](http://www.php.net/manual/en/book.soap.php): . To enable SOAP support, configure PHP with enable-soap.

## Get Agreement updates (for SugarCRM versions 6.3 or higher)

For version 6.3 and later, you can use the following two options to get agreement updates. In previous versions of SugarCRM, the plug-in by default only offers the Callback Method (Option 1).

### Option 1: Set up the Callback Method for Pushing Updates to EchoSign

If your website is public facing, you can have Adobe EchoSign ping your SugarCRM instance whenever a new event occurs. SugarCRM then updates the agreement status, events and download the signed document (if signed) automatically and in real-time. (If you are behind a firewall, you need to whitelist the EchoSign server IP addresses or use the Scheduled Job method of updating EchoSign Agreements described in the next section of this guide).

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Adobe EchoSign Settings]**.
1. Check the checkbox **[!UICONTROL Use EchoSign callback method]** to update events and statuses of agreements.
1. Select **[!UICONTROL Save]**.

### Option 2: Set up a Scheduled Job for SugarCRM Instances Behind a Firewall

The EchoSign for SugarCRM plugin can also use a Scheduled Job to query EchoSign for updates to Agreements that are Out For Signature. Scheduled job query method can be used if you have an on-premise SugarCRM installation is behind a firewall.  

To setup:

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Scheduler]**. 
1. From the tab dropdown menu, select **[!UICONTROL Create Scheduler]**. 
1. Enter a Job Name.
1. For the Job field, select **[!UICONTROL Adobe EchoSign Status Updater]**.
1. Set the job to run as frequently as needed. We suggest setting it to run every 10 minutes, which means that after an agreement is opened, read or signed, it may take up to 10 minutes for SugarCRM to be updated with that information.  

    **Note:** If you have lots of agreements out for signature, having this run too frequently may cause your system to slow down.
 
1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Adobe EchoSign Settings]**.
1. Uncheck the box **[!UICONTROL Use EchoSign callback method]** to update events and statuses of agreements.
1. Select **[!UICONTROL Save]**.
    Note: Turn on Schedulers in SugarCRM for this to work.

To add Echosign agreements to other SugarCRM modules:

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Studio ]**.
1. From the left column folder tree, select the module for adding EchoSign Agreements.
1. Select **[!UICONTROL Relationships ]**> **[!UICONTROL Add Relationships]**.
1. From the dropdown menu, select Type as **[!UICONTROL One to Many]** and Module as **[!UICONTROL EchoSign Agreements]**.
1. Select **[!UICONTROL Save & Deploy]**.
 
EchoSign Agreements now appear in the module and agreements can be created and tracked there.
 
**Other Configuration Steps**

* **Hiding EchoSign Modules**: You can hide the EchoSign Recipients and EchoSign Events modules by going to Administration » Display Module Tabs and Subpanels and moving them to the hidden column. 
* **Disabling packageScan**: If you have enabled packageScan on your own system, you need to disable it during installation. If you are using SugarCRM On-Demand, contact SugarCRM support to disable packageScan for you.

## Uninstall the Plugin

1. Log into SugarCRM with your administrator account.
1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Module Loader]**.
1. Select **[!UICONTROL Uninstall]** next to the [!UICONTROL EchoSign for SugarCRM plugin].
1. Select **[!UICONTROL Commit]** to begin uninstallation. You can also select to remove the database tables created for the plugin.

    If the plugin uninstalls successfully, the progress bar indicates 100% success. If the progress bar does not reach 100%, select [!UICONTROL Display Log] to see the error encountered by SugarCRM.
 
## Use Adobe EchoSign for SugarCRM

You can create an Adobe EchoSign agreement associated with an account, contact, quote, or other SugarCRM modules. You can attach files, specify recipients, and send for signature. Adobe EchoSign updates SugarCRM with the current status of the agreement and stores the signed contract in SugarCRM once it is fully executed. 

### Creating Agreements 

Agreements may be created through the EchoSign Agreements module or through modules configured by a SugarCRM administrator. 
 
Figure 1: EchoSign Agreement Edit View 
Creating and editing an Adobe EchoSign Agreement 

1. From the Actions list on the EchoSign Agreements tab, select Create EchoSign Agreement. 
1. In the main section of the EchoSign Agreement, enter the following information or select from various agreement options:

a) Name: Enter a name for the agreement. 
b) Signature Type: Select the type of signature accepted for the document. The options are e-Signature and Fax Signature. 
c) I Also Need to Sign This Agreement: Indicate whether the sender also needs to sign the agreement. 
d) Signature Order: If the previous option I Also Need to Sign This Agreement is checked, then also select the order in which the sender and recipients should sign.
e) Remind Recipients to Sign: Select how often to remind a recipient to sign a document. The options are Daily or Weekly. 
f) Days Until Signing Deadline: Specify the number of days until the agreement must be signed.
g) Preview, position signature or add form fields:  Select this option to preview the agreement before it is sent or drag and drop signature fields, initial fields, or other form fields on to the agreement before it is sent to recipients. After you have previewed the document or dragged the fields you want on to the document, remember to select the Send button to send the agreement to the recipient.
h) Host Signing for the First Signer: Indicate whether the sender would like to host the agreement signing in-person. 
i) Message: Include a message for the recipient. 
j) Account, Opportunity, Quote: Select or modify the Account, Opportunity, or Quote associated with this agreement.
k) Language: Specify the language in which the signing page and email notifications will be displayed to the recipients.

1. In the Security Options section of the EchoSign Agreement, enter the following information:

a) Password Required to Sign: Indicate whether a password must be entered before a recipient may sign a document. 
b) Password Required to Open: Indicate whether a password must be entered before a recipient may open a PDF of the agreement or signed agreement
c) Password: Specify the password to use to sign or to open a document. 
d) Confirm Password: Confirm the password to use to sign or to open a document. 
1. In the Other section of the EchoSign Agreement, enter the following information: 
a) User: Specify a SugarCRM user. The default is the user currently signed into the system.
b) Teams: To change the primary team assignment, enter the name of the new primary team. To assign additional teams to the record, select Select and select from the team from the Team List, or select Add to add team fields and enter the team names. For more information, see ‘Assigning Records to Users and Teams’ in the SugarCRM Application Guide.

1. Select Save.  
 
Figure 2: EchoSign agreement detail view
After an EchoSign Agreement is saved, the Detail View of the agreement includes the following subpanels: 
• Recipients: Any contacts listed in this subpanel will receive the documents specified in the Documents subpanel.  You must add one or more recipients before you send the agreement.
• Documents: Upload a new document or select a document already uploaded into SugarCRM to send for signature. 
• Events: Any action regarding the agreement such as when the agreement was sent for signature, viewed or signed is listed in this subpanel. 
To edit an EchoSign Agreement, select the Edit button on the Detail View of the agreement. 
Note: After an agreement has been sent for signature, the Edit button is removed from the Detail View to preserve the record of events.  However you can enable the Edit button if you go to Admin » Adobe EchoSign Settings and uncheck the option ‘After an agreement is sent out for signature, disable the ability to edit or delete.’

Adding a document to an EchoSign Agreement 
SugarCRM users may either upload a new document or select a document already uploaded into SugarCRM by using the Documents subpanel of an EchoSign Agreement record. 
To upload a document, select the Upload Document button in the Documents subpanel, and a form will appear. See the ‘Documents Module’ section of the SugarCRM Application Guide for more information on the individual fields of that form. 
To select a document, select the Select option in the Documents subpanel. See ‘Viewing and Managing Record Information’ in the SugarCRM Application Guide for more information on how to manage related information in subpanels. 
 
Figure 3: Documents subpanel
Specifying a recipient for an EchoSign Agreement 
1. Select Add Recipient in the Recipient subpanel of an EchoSign Agreement. 
1. Enter the following information: 
a) Recipient: Select the type of recipient from the drop-down menu. Type the name or e-mail address of the Recipient in the text field. SugarCRM will look up the name as you type and offer a list of selections. Select a name if a match is found. You can also select the arrow icon to select a name from a pop-up window. To erase the name from the field, select the X icon. 
b) Role: Select a role from the drop-down menu. The options are Signer and CC and Approver.  An Approver does not have to sign the document. 
1. Select Save. 
 
Figure 4: Recipients subpanel 
Sending agreements for signature 
When agreements are ready to be sent for signature, select the Send for Signature button. In SugarCRM 6.5+, the Send for Signature option appears in the dropdown menu at the top left of the page.  Recipients then receive an e-mail informing them of the documents awaiting their signature. After the recipients have signed the document, the sender receives a notification by e-mail that the document has been signed. 
If the Host Signing for First Signer option is checked, clicking Send for Signature opens a pop-up window to allow the signer to sign the document with the sender present. 
A Host Signing for Current Signer link also appears next to the Host Signing for First Signer field, which can be accessed until the document is signed. Use this link to host agreement signing for multiple signers, or to reopen the pop-up window if it accidentally closed. 
If Preview, position signature or add form fields option is checked, clicking Send for Signature opens a pop-up window to allow the sender to preview the document or drag fields on to the document before it is sent.  Remember to select the Send button in that window to send the agreement to the recipient. 
 
Figure 5: Select Send for Signature to send a document to a recipient for a signature. 
Sending from a Quote Record
Adobe EchoSign has a direct integration with Quotes in SugarCRM so that the PDF of the quote is automatically generated and attached to the agreement record.
When viewing a Quote, select the option Create EchoSign Agreement.  Then quote will be generated and automatically attached to the agreement.  The new agreement will also automatically associate any related Opportunity, Account, or Quote.  
Figure 6: Select Create EchoSign Agreement to send a quote for signature from within the Quotes module. 
You can turn off the auto-attachment of the quote PDF to the agreement by going to Administration » Adobe EchoSign Settings, and unchecking the box ‘Automatically attach PDF when creating an agreement from a Quote’.
Canceling an agreement 
An EchoSign Agreement may be canceled after it has been sent for a signature if all recipients have not yet signed the document. A button labeled Cancel Agreement appears in the Detail View of an agreement after a document has been sent for signature. Select this button to cancel the agreement. 
 
Figure 7: After an agreement is sent out for a signature, select Cancel Agreement to cancel it.
Note: If an EchoSign Agreement has been sent for a signature and the record is deleted, the agreement is first canceled before it’s deleted. 
Tracking signatures 
The Events subpanel of an EchoSign Agreement tracks the status of agreements sent for signature. To see the latest updates on an EchoSign Agreement, select the Update Status button/action. This button/action is made available only after agreements have been sent for signature. 
 
Figure 7: After an agreement is sent out for a signature, select Update Status to retrieve the latest status.
 
Figure 8: Go to Events subpanel to view agreement history
Sending Reminders
After the agreement is sent, you can send a reminder to the current signer by clicking the ‘Send Reminder’ option.  That will immediately send an email reminder to the current signer about the agreement that is waiting for signature.
 
Figure 9: Reminders
