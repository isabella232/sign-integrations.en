---
title: Adobe Sign for NetSuite Release Notes
description: Learn about the new features and changes that are included in the current release of the Adobe Sign integration for NetSuite.
type: Documentation
solution: Adobe Sign
role: User, Developer
topic: Integrations
exl-id: 6317723e-447a-4506-a621-4d967bdd6561
---
# Adobe Sign for NetSuite Release Notes

## Update to package v4.0.4

4.0.4 is fully adapted to use account-specific domains for all newly generated traffic.

The Adobe Sign icon has been updated to the new graphic.

## Previous Releases 

### Adobe Sign for NetSuite 4.0.4 

4.0.4 is fully adapted to use account-specific domains for all newly generated traffic.

The Adobe Sign icon has been updated to the new graphic.

### Adobe Sign for NetSuite 4.0.2 

Rebranded to **Adobe Sign** (from *Adobe Document Cloud eSign services*)  
You now see *Adobe Sign* where you previously saw *Adobe eSign Services* as evidence of the rebranding.

### Adobe Sign for NetSuite 4.0.1 

Due to an API regression bug introduced when NetSuite performed their platform update, a new package (v4.0.1) has been released.

Customers are encouraged to update to the newest package.

### Adobe Sign for NetSuite 4.0 

**Added auto provisioning of users through NetSuite**

A new custom preference has been added for v4.0. When enabled, users who send agreements in NetSuite are automatically auto-provisioned with an Adobe Document Cloud eSign services user account.

**Certified with 'Built for NetSuite'**

This version achieved the 'Built for NetSuite' certification and meets all the latest NetSuite design best practices.

**Rebranded to Adobe Document Cloud eSign services (from EchoSign)** 

You now see Adobe Document Cloud eSign Services (or Adobe eSign Services for short) where you previously saw Adobe EchoSign as evidence of the rebranding.

**Implemented enhanced security with OAuth** 

To improve data security, eSign services now use OAuth 2.0 to authenticate your Adobe Document Cloud eSign services account within NetSuite. This new protocol lets NetSuite talk to eSign services without requesting your eSign services password. Since sensitive information is not being shared directly between the apps, your account is less likely to be compromised. This improvement does not impact your implementation, but you must do a one-time setup to authorize your NetSuite package to communicate with the Adobe Document Cloud. This is done during the installation process. For customers upgrading from a previous version of the package—v3.5.9 and prior—the API key previously used is replaced by an OAuth token generated during the authorization process.

**Migrated the eSign services from SOAP APIs to REST APIs**

To improve efficiency, flexibility and processing speed, Adobe Document Cloud eSign services, and consequently the v4.0 integration for NetSuite, has migrated from SOAP-based to REST-based APIs.

### Adobe Sign for NetSuite 3.0 

**Advanced Participant Roles - Approver** 

* One or more recipients can be marked as approver(s) in an agreement
* Approvers are required to review and approve the document
* Approvers can also be required to fill data into the agreement before approving

**Preview Document or Drag and Drop Form Fields Before Sending** 

Preview agreement or drag and drop form fields before sending for signature

**Send Reminder to Current Signer** 

Send immediate reminder to current signer

**Advanced Signer Authentication Policies** 

* **Knowledge-Based Authentication:** Answer questions to verify signer identity
    * Requires Signers to prove their identity by answering questions taken from hundreds of public and commercial databases
    * Name on signature is taken from the user’s authenticated name and cannot be changed at the time of signing
    * Powered by RSA
    * KBA usage is limited per account, per month. Contact Sales for more information.

* **Web identity:** Sign in with Facebook, LinkedIn, Google, or other third-party web service before signing.

    * Signer can only sign after verifying their identity using a 3rd party Web service.
    * Name on signature is taken from the user’s web service pro!le and cannot be changed at the time of signing
    * Audit trail captures identity verification details

* **One Time Password**
    * Apply authentication methods for internal or external signers or all signers. External signers must use a password or use Knowledge-Based Authentication while Internal signers do not

**Additional Custom Preferences**

* Add Signed PDF as a link to the URL or as attachment hosted in NetSuite
* Add Audit Trail to Agreement record a$er agreement is signed
* Use the transaction contact as signer by default, instead of Customer email
* Grant Senders the option to mark recipients as Approvers

**Transaction Files** 

You can select files to attach from the current transaction with new ‘Transaction Files’ dropdown list.

**Adobe PDF Certification For All EchoSign Documents** 

* All PDF files sent or downloaded from EchoSign are certified with an Adobe EchoSign Digital Certificate
* Acrobat or Reader displays the certification guaranteeing that the document has not been tampered with for additional trust and peace of mind

**Collect Supporting Documents** 

* Senders can collect additional supporting documents from Signers during signing, such as a driver’s license, business certificate, and more.
* Collected documents become part of the official record of the signed agreement

**Conditional Data Fields** 

* Define conditional logic for agreement fields 
* Conditions can be based on values for one or more fields on the agreement
* Conditions can be de!ned through the drag-and-drop forms authoring UI or through text-tags
* Signer is presented with the appropriate fields when signing a document based on the de!ned conditions

**Additional EchoSign Form Fields Enhancements** 

* Dropdown menus
* Field masking
* Radio buttons
* Create shorter text tags to maintain document structure
