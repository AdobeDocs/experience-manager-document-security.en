---
title: AEM Document Security for Microsoft Office - Release Notes
description: Read the release notes before you install AEM Document Security 6.2 Extension for Microsoft Office.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
---
# AEM Document Security for Microsoft Office - Release Notes{#aem-document-security-for-microsoft-office-release-notes}

## What's new in AEM Document Security for Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}

* **Support for Office 2019**: Document Security Extension for Microsoft Office has added support for Microsoft Office 2019. It is also expected to work with Microsoft Office 2019 desktop applications installed as part of Office 365.

>[!NOTE]
>
>The document uses the following terms interchangeably: 
>
>* Adobe Experience Manager Document Security for Microsoft Office
>* Adobe Experience Manager Document Security Extension for Microsoft Office
>* Document Security Extension for Microsoft Office

## Installing and Configuring AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

This version of Document Security Extension for Microsoft Office is compatible with Adobe LiveCycle Rights Management ES2 and later and Document Security add-on for AEM forms.

Review the information in this document before you install AEM Document Security Extension for Microsoft Office. For detailed installation instructions, see the [Installing and Configuring AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md) article.

## Fixed issues {#fixed-issues}

* Strings are displayed vertically and wrong line breaks are added to the content. (CQ-4201054)

## Known issues {#known-issues}

### Third-party plug-ins not supported {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office does not work with third-party plug-ins. Uninstall any third-party plug-ins for Microsoft Office before you install the Document Security Extension for Microsoft Office.

### Disabled menu options in Microsoft Word, Excel, and PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office uses built-in protection features to protect documents, worksheets, and presentations. It disables a few Excel, Word, and PowerPoint menu options.

### Restrictions for Microsoft Office 2013, 2016, and 2019 {#restrictions-for-microsoft-office}

In Microsoft Office, the following options are unavailable during a protected session:

* Microsoft Office 2016 or Microsoft Office 2019

  * File &gt; Save As
  * File &gt; History
  * File &gt; Share
  * File &gt; Export
  * File &gt; Publish
  * File &gt; Account
  * File &gt; Info &gt; Protect Document/Workbook/Presentation &gt; Encrypt with Password
  * File &gt; Info &gt; Protect Document &gt;Add a Digital Signature
  * File &gt; Info &gt; Protect Document &gt; Mark as Final
  * Share option on top right

* Microsoft Office 2013

  * File &gt; Save As
  * File &gt; Share
  * File &gt; Export
  * File &gt; Account
  * File &gt; Info &gt; Protect Document/Workbook/Presentation &gt; Encrypt with Password
  * File &gt; Info &gt; Protect Document &gt;Add a Digital Signature
  * File &gt; Info &gt; Protect Document &gt; Mark as Final

### Opening a protected document from SharePoint Server {#opening-a-protected-document-from-sharepoint-server}

To open a protected document in Document Security Extension for Microsoft Office from SharePoint Server, first open the associated Microsoft Office program (Word, Excel, or PowerPoint), or the document may not open. An error message displays indicating that you install the applicable plug-in. Hence, it is recommended that you open the associated Microsoft Office program, before you open a protected document in Document Security Extension for Microsoft Office from SharePoint Server.

(Optional) It is recommended that you clear your cache folder before opening a protected document in Document Security Extension for Microsoft Office from SharePoint Server.

When you open a protected document from SharePoint Server, all permissions on the document are disabled, regardless of the policy that was applied.

### Apply a policy with a dynamic watermark to Microsoft Excel 2013, Microsoft Excel 2016, and Microsoft Excel 2019 file with no printer installed {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

Applying a policy with dynamic watermark to Excel 2013, 2016, or 2019 files on a computer without printers installed results in the error: "Internal error while applying dynamic watermark." This error also appears when you reopen the protected file. The watermark is not applied and it is not visible from View &gt; Page Layout.

### Disable Windows Data Execution Prevention for supported Office applications {#disable-windows-data-execution-prevention-for-supported-office-applications}

It is recommended that you disable the Windows Data Execution Prevention (DEP) setting when using Document Security Extension for Microsoft Office applications.

### Shared Microsoft Office files cannot be protected using Document Security Extension {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

When you protect any shared Microsoft Office file using Document Security Extension, an error occurs and the shared file is not secured.

### Starting Office applications on a machine containing Document Security Extension for Microsoft Office and McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

To ensure smooth startup of Office applications on a machine with Document Security and McAfee VirusScan (On-Access Scan enabled), disable the Buffer Overflow Protection option in the McAfee VirusScan Console.

### Installing Document Security Extension for Microsoft Office on a machine with an unsupported Microsoft Office language {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

Before you install the Document Security Extension for Microsoft Office on a machine that has a Microsoft Office application with an unsupported language, open the Office application at least once.

### Synchronize Offline button is enabled even when a user does not have offline permissions {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

The Synchronize Offline button is available even though the user does not have offline permissions for the document. However, selecting the button does nothing.

### No support for trial versions of Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}

Document Security Extension for Microsoft Office does not support trail versions of Microsoft Office. Before installing the extension, ensure that you installed a licensed copy of Microsoft Office and it is activated.

### Unable to open a protected Microsoft Office files {#unable-to-open-a-protected-microsoft-office-files}

If the protected view of the Microsoft Office is enabled, the Right Management Extension cannot open protected Microsoft Excel files (XLS, XLSX) and protected Microsoft PowerPoint (PPT) files from a remote location.

### Cells of Microsoft Excel document containing an image or background color appear on top of watermark {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

If a cell in an Excel document has an image or background color, and a dynamic watermark is applied, the image or color covers the watermark. This approach means that the watermark is covered by the image or background color in the cell.

### Usability issue with multiple certificates {#usability-issue-with-multiple-certificates}

If multiple certificates are present on the client machine and the user cancels the certificate selection dialog box, the dialog box appears again. The user has to cancel the dialog box twice.

### Microsoft PowerPoint allows editing protected documents {#microsoft-powerpoint-allows-editing-protected-documents}

On attempting to edit a protected document, Microsoft PowerPoint displays a message, "You are not allowed to modify this document. You cannot save your changes." After closing the message, users can continue to add text or edit the document. But, the changes made to the protected documents are not saved.

The above-mentioned behavior is as expected in PowerPoint 2013, PowerPoint 2016 and PowerPoint 2019.
