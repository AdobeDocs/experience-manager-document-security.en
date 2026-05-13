---
title: Troubleshooting AEM Document Security Extension for Microsoft Office
description: If you have problems installing, configuring, or using the AEM Document Security Extension for Microsoft Office, follow the instructions listed in this document.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
TQID: https://experienceleague.adobe.com/3YVMcSeYDXCWkVeG8HmlJOgja9OwLqs1gpPWP8rhhs0
product_v2:
  - id: e8f6de9b-cf88-4405-8d10-15efa08c230e
    internal-label: Experience Manager Forms
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: fd5d26fd-7180-407d-bbd8-5f8a17f9c0b8
    internal-label: Installation and configuration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Troubleshooting AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Troubleshooting Installation and Configuration issues {#troubleshootinginstallationandconfiguration}

If you have problems installing and configuring the AEM Document Security Extension for Microsoft Office, make sure that you carefully followed the instructions listed in the - before you install - section of the [installation](installing-configuring-aemdsext.md) article.

If you installed and configured everything according to the documentation, review the following sections for issues similar to what you are experiencing.

### Document Security Extension fails to load for Microsoft Office applications {#document-security-extension-fails-to-load-for-microsoft-office-applications}

The LoadBehavior property in Windows Registry specifies the runtime behavior of the document security plug-in. If the LoadBehavior property is set to 3, all the plug-ins are loaded automatically. Before installing the Document Security Extension for Microsoft Office, ensure that the value LoadBehavior property is set to 3.

1. Take a backup of the Windows Registry before you make changes to it. For detailed instructions, see [How to Modify the Windows Registry](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. In the Registry Editor, navigate toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin or HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Set the value of the **LoadBehavior** property to 3.

1. Close the Registry Editor.

For detailed information about LoadBehavior, see the [Registry Entries for VSTO Add-ins](https://learn.microsoft.com/en-us/visualstudio/vsto/registry-entries-for-vsto-add-ins?view=vs-2022&redirectedfrom=MSDN#LoadBehavior) article.

## Troubleshooting administrative tasks {#admintasks}

This section discusses possible issues with your installed AEM Document Security Extension.

### Microsoft Office applications don't start smoothly on installing Document Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

To ensure that Office applications start smoothly with Document Security Extension installed and McAfee VirusScan with On-Access Scan enabled, disable the Buffer Overflow Protection in the McAfee VirusScan Console.
