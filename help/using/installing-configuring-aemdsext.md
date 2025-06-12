---
title: Installing and Configuring AEM Document Security Extension for Microsoft Office
description: This document guides you through installing and configuring Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
---
# Installing and Configuring AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

This document guides you through installing and configuring the Adobe Experience Manager Document Security Extension for Microsoft Office.

This document includes information about the following tasks:

* Installing Document Security Extension for Microsoft Office.
* Preconfiguring the installer to point to the LiveCycle Rights Management ES2 or later or Document Security add-on for AEM 6.0 Forms or later.
* Configuring the automatic application of the default policy.

## Before you install {#before-you-install}

Before you install the Document Security Extension for Microsoft Office, ensure that:

* You have read the [Release Notes](document-security-extension-release-notes.md).
* Microsoft Office is activated. Activation dialog does not appear on opening Microsoft Office applications.
* Latest service packs for Microsoft Windows and Microsoft Office are installed.
* If you are installing Document Security for Microsoft Office for an unsupported language, open the Office application at least once.

>[!NOTE]
>
>Do not install the software in a folder whose name contains double-byte characters. If you do so, the AEM Document Security menu does not appear in Microsoft Office.

>[!NOTE]
>
>Installing a 32-bit version of Document Security Extension on a 64-bit operating system is supported, but the opposite way is not supported. You cannot install a 64-bit version of Document Security Extension for Microsoft Office on a 32-bit operating system.

### Disable McAfee VirusScan {#disable-mcafee-virusscan}

Disable the Buffer Overflow Protection option in the McAfee VirusScan console. Doing so ensures that Office applications start smoothly on a machine with Document Security Extension installed. And, McAfee VirusScan with On-Access Scan is enabled. These adjustments help prevent any conflicts that might hinder the startup process.

### Uninstall third-party plug-ins {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office does not support third-party plug-ins for Microsoft Office applications. As this extension conflicts with third-party plug-ins, uninstall any non-Adobe plug-ins for Microsoft Office before installing Document Security for Microsoft Office. Adobe does not provide support for Document Security for Microsoft Office applications with third-party plug-ins installed.

## System requirements {#system-requirements}

### Document Security Extension Client {#document-security-extension-client}

Ensure the following minimum configurations on which you want to install Document Security Extension:

* Microsoft Office 2019 Professional Plus on Microsoft Windows 11.
* 32-bit or 64-bit versions of Microsoft Windows 10 in English, French, German, Japanese, Italian, Spanish, Brazilian Portuguese, Korean, Simplified Chinese, or Traditional Chinese.
  **Note:** *Document security extension for Microsoft Office is also expected to work on Microsoft Surface devices.*

* 32-bit or 64-bit versions of Office 2016, 2019 and Microsoft Office desktop applications installed as part of Office 365 in English, French, German, Japanese, Italian, Spanish, Brazilian Portuguese, Korean, Simplified Chinese, or Traditional Chinese.

  **Note**: *AEM Document Security Extension for Microsoft Office does not support third-party plug-ins for Microsoft Office applications. As this extension may conflict with third-party plug-ins, any non-Adobe plug-ins for Microsoft Office applications must be uninstalled before installing Document Security Extension for Microsoft Office. Adobe does not provide support for Document Security Extensions for Microsoft Office applications with third-party plug-ins installed.*

* 1.3-GHz processor or higher
* 2 GB of RAM
* 100 MB of available hard disk space

### Document Security {#document-security}

To use Document Security Extension, ensure that you are able to connect to Adobe LiveCycle Rights Management ES2 and later or Document Security add-on for AEM 6.0 forms or later.

## Installing Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

You can download the installer from the [download page](download-installer.md). You cannot customize the installer executable file directly, but it can be installed interactively or in silent mode. To install the software, log in to Windows as an administrator.

Separate installers are available for 32-bit and 64-bit versions of Microsoft Office. For a 32-bit version of Microsoft Office, download DocumentSecurityExtensionforMicrosoftOffice.exe. For a 64-bit version of Microsoft Office, download DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>This document uses a 32-bit installer file (DocumentSecurityExtensionforMicrosoftOffice.exe) to explain various commands and options. If you are using a 64-bit version of Microsoft Office, use the 64-bit installer file (DocumentSecurityExtensionforMicrosoftOffice64.exe) to perform operations listed in this document.

### Install in silent mode {#install-in-silent-mode}

Use a file extractor utility, such as WinZip, to extract `DocumentSecurityExtensionforMicrosoftOffice.exe` from the installer file. Open the command prompt, go to the folder that contains the setup file, and type the following text:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

The installer is also available as an MSI file, which can be used for customization.

### Install an MSI file in silent mode {#install-an-msi-file-in-silent-mode}

1. Use a file extractor utility, such as WinZip, to extract the `DocumentSecurityExtensionforMicrosoftOffice.msi` file from the ZIP file.

1. Open the command prompt, go to the folder that contains the MSI file, and type the following text:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Preconfiguring the installer to connect to Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

You can preconfigure the Document Security Extension for the Microsoft Office installer to point to a LiveCycle or AEM server. Doing so ensures that users who install Document Security Extension for Microsoft Office can use the features without configuring a connection. As such, users can open protected documents with no configuration necessary. However, they cannot protect new documents until they configure the client to use a particular server.

The following steps describe how to create and configure an MSI file. This MSI file contains the registry values. These values are required to preconfigure the Document Security Extension for the Microsoft Office installer to the LiveCycle or AEM server that is installed in your enterprise.

### Prerequisites for customizing the installer {#prerequisites-for-customizing-the-installer}

Use the Orca database editor to customize the installer. The following steps describe how to create a custom MSI file by modifying a copy of the MSI installation file using the Orca database editor. Orca is available as part of the Windows SDK for Windows Server 2008 and .NET Framework 3.5. 

<!--

For more information about how to edit Microsoft Windows&reg; Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>It is recommended that you make a full backup of all installer files before you create the custom MSI file.

#### Install Orca {#install-orca}

1. Download the Windows SDK for Windows Server 2008 and .NET Framework 3.5.
1. Double-click the Orca.msi file in the \Microsoft SDK\bin folder.

   You also need the MSI variant of the installer file. Contact Adobe support to receive the latest version of the MSI installer.

   >[!NOTE]
   >
   >Always close the DocumentSecurityExtensionforMicrosoftOffice.msi file before running the installer. You cannot run the installer if Orca is using the MSI file.

### Create and configure the MSI file {#create-and-configure-the-msi-file}

1. Click **[!UICONTROL Start > Programs > Orca]**.

1. Click **[!UICONTROL File > Open]**, and then browse to the `DocumentSecurityExtensionforMicrosoftOffice.msi` file.

1. Select Property from the list of tables (on the left side).

1. Edit the following key Name values as applicable to your enterprise installation of Rights Management or Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>K</strong><strong>e</strong><strong>y Name</strong></p> </td>
   <td><p><strong>Description</strong></p> </td>
   <td><p><strong>K</strong><strong>e</strong><strong>y Value Default</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Display your name.</p> </td>
   <td><p>Default server</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>Host Server URL.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Select Registry from the list of tables (on the left side).

1. Edit the following key name value.

   | **Key Name** |**Description** |**Key Value Default** |
   |---|---|---|
   | `IsDefault` |The default APS server. |Default server |

1. Save the modified file to the same directory that contains the original MSI installer.

   >[!NOTE]
   >
   >A common practice is to use the same filename as the original MSI file (for example, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configuring automatic application of a default policy {#configuring-automatic-application-of-a-default-policy}

As part of the configuration, you can configure automatic application of a default policy so that the Document Security Extension for Microsoft Office protects every document that is saved.

You can specify one of the following options:

* Protect all documents with a default policy.
* Let users optionally save a file in an unprotected format when they cannot connect to the server. This flexibility allows you to account for cases when users are creating documents while disconnected from the network (for example, while on an airplane).

After you enable the auto-apply policy feature, the document is protected with the default policy in the following cases:

* A user edits and saves a newly created document
* A user edits and saves an unprotected document
* The user opens an application that opens with a default document, edits, and then saves the document

### Configure the auto-apply policy feature in the MSI file {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Before you begin, preconfigure the installer to point to your LiveCycle or AEM Forms Server, as described earlier in this article.

1. Click **[!UICONTROL Start > Programs > Orca]**.

1. Click **[!UICONTROL File > Open]**, and then browse to the `DocumentSecurityExtensionforMicrosoftOffice.msi` file.

1. Select Property from the list of tables (on the left side).

1. Edit the following key name values as applicable to your enterprise installation of Rights Management or Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Key Name</strong></p> </td>
   <td><p><strong>Description</strong></p> </td>
   <td><p><strong>K</strong><strong>e</strong><strong>y Value Default</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Enable or disable the Auto-apply policy feature.</p> <p><code>1</code>: Enable</p> <p>0: Disable</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>The policy is GUID to use when new documents are saved. This value applies to the Auto-apply policy feature.</p> </td>
   <td><p>Hexadecimal policy ID as visible on the RM server</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>Server URL.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Server port number.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Determines whether documents can be created without Document Security protection if the client cannot contact the server to protect the document on first save.</p> <p>1: Allow unprotected saves </p> <p>0: Prevent creation of new documents when the client cannot contact the server to save the document.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

   >[!NOTE]
   >
   >The `AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` option is useful when you want to remind customers to protect all documents without forcing them to do so. It is also useful when you know that users create documents while disconnected from the network. You do not want to prevent them from creating and saving documents.

1. Save the modified file to the same directory that contains the original MSI file.

   >[!NOTE]
   >
   >A common practice is to use the same filename as the original MSI file (for example, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Enabling automatic protection of new documents {#enabling-automatic-protection-of-new-documents}

The administrator can enable the ability to protect any document automatically that a user saves. The Administrator configures the Auto-apply policy feature in the installation program for Document Security Extension for Microsoft Office.

If the Auto-apply policy is enabled, all documents that the user saves are protected with the default policy. This action applies in these situations:

* When a user creates a new document, edits, and saves it.
* When a user opens an unprotected document, edits, and saves it.

For information about configuring the Auto-apply policy, see [Configure an automatic application of the default policy](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Enable ribbon-less user interface {#enable-ribbon-less-user-interface}

You can enable/disable the ribbon-less user interface by modifying settings in the Windows Registry. Perform the following steps to update the Registry and enable a ribbon-less user interface:

1. Take a backup of the Windows Registry before you make changes to it. For detailed instructions, see [How to Modify the Windows Registry](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. In the Registry Editor, navigate to HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Create a new Dword (32-bit) value named **HidePluginUI**.

1. Set the value of the **HidePluginUI** property to 1 to enable a ribbon-less user interface.

1. Close the Registry Editor.

## Enable watermark for printing in Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

You can change Windows Registry settings to make dynamic watermark co-exist with existing headers and footers. The registry settings make the watermark available only during printing. Perform the following steps to update the Registry and enable watermarks during printing:

1. Take a backup of the Windows Registry before you make changes to it. For detailed instructions, see [How to Modify the Windows Registry](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. In the Registry Editor, navigate to HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Create a new Registry key **WatermarkMode**.
1. In the WatermarkMode registry key, create a DWORD **WatermarkMode**, and set the value of DWORD **WatermarkMode** to **1**.

1. Close the Registry Editor.

>[!NOTE]
>
>In Windows Explorer, you can use the File menu or context menu to create a Microsoft Excel Document. For the documents created with stated methods, the print date cannot be retrieved or changed. It is a limitation of Microsoft Excel. AEM Document Security watermarks rely on the print date of the document. So, for such documents, the watermark is reverted to a previous date. Moreover, headers and footers are also not retained.

## Add a custom cover page to a document {#coverpage}

A user can attempt to open the protected document on a machine that does not have an AEM Document Security for Microsoft Office plug-in installed. Such machines cannot open the document. On such machines, you can display a cover page containing instructions to download AEM Document Security for Microsoft Office plug-in and other information.

### Before you configure a cover page {#before-you-configure-a-cover-page}

* Take a backup of the CommonResources.dll file. The default path is:

    * **(For 32-bit office on 32-bit machine)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

    * **(For 32-bit office on 64-bit machine)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

    * **(For 64-bit office on 64-bit machine)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Ensure that you have Microsoft Visual Studio 2008 or later installed. You can also use any other utility to edit the DLL files.
* Extract the templates.zip archive. The archive contains .xlsx, .docx, and .pptx templates for the cover page. Use only provided templates for file types .xlsx, .docx, and .pptx. You can create your own templates for other file types. Customize templates to include custom messages and instructions. You can find template.zip at:

[Get File](assets/templates.zip)

### Structure of the CommonResources.dll file {#structure-of-the-commonresources-dll-file}

The CommonResources.dll file contains information about the resource templates. It contains two name identifiers: TEMPLATE_FILE and RT_MANIFEST. To enable a custom cover page, the TEMPLATE_FILE name identifier is modified. The TEMPLATE_FILE name identifier has six resources:

<table>
 <tbody>
  <tr>
   <td><p><strong>Resource</strong></p> </td>
   <td><p><strong>Represents </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Configure the template as a cover page {#configure-the-template-as-a-cover-page}

1. Open Microsoft Visual Studio. Browse and open the CommonResources.dll file for editing.

   >[!NOTE]
   >
   >If the file does not appear in the Solution Explorer window, reopen the file using the Open With option. Select the Resource editor as the editor.

1. In the Solution Explorer window, expand the TEMPLATE_FILE directory, and delete resources 101.

1. Add the resources:

    1. With a project selected in Solution Explorer, on the Project menu, click Properties.
    1. Select the Resources tab.
    1. On the Resource Designer toolbar, point to Add Resource, click the arrow. For resource type, select TEMPLATE_FILE, and click import.
    1. In the **`Add existing file to resources`** dialog box, browse to the Resource.xlsx file, and then click Open. The file is added to the TEMPLATE_FILE directory.

   >[!NOTE]
   >
   >Ensure that the language settings are correct. Delete the resource with neutral language.

1. Repeat step 2 and 3 for all the resource types.

   >[!NOTE]
   >
   >Do not delete resource types and add them in random order. After 101, configure 102, and so on.

### Package custom CommonResources.dll file with the installer of AEM Document Security extension for Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

You can customize the CommonResources.dll file to add a custom cover page. After customizing the file, you can manually replace the original file with the custom file on all the workstations or you can choose an automated method to replace the file.

In a large environment, it is difficult and tedious to replace the default `CommonResources.dll file` manually with a custom `CommonResources.dll` file. You can use a self-extracting and packaging tool (For example, WinZip Self-Extractor) to package the custom CommonResources.dll file with AEM Document Security Extension for Microsoft Office installer. Later on, you can distribute the custom installer to all the workstation. This method reduces the time required to replace the default `CommonResources.dll` file with a custom file. It also ensures that all the workstation has the required CommonResources.dll file. Self-extracting and packaging tool is just one of the many possible methods of automatically replacing a file. You can choose any method that is suitable for your environment.

You can perform the following steps to package custom `CommonResources.dll`file with the installer of AEM Document Security extension for Microsoft Office:

1. Install a self-extractor and packager tool. For example, the WinZip Self-Extractor.
1. Create a new folder. For example, YOUR_FOLDER_NAME
1. Place the original installer of AEM Document Security Extension and custom CommonResources.dll file in the newly created folder.
1. Create a batch file in the folder. For example, YOUR_FOLDER_NAME\Installer.bat
1. Open the batch file for editing and add the following code to the batch file:

   ``` shell

    @echo off

    setlocal EnableDelayedExpansion

    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe


    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"

    set IDENTIFIER= %IDENTIFIER: =%

    if not %IDENTIFIER:x86=%==%IDENTIFIER% (

    REM Fetching install path for 32 bit machine.

    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"

    ) else (

        REM Fetching install path for 64 bit machine.

            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"

        )

    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"

    endlocal

   ```

   If you use any other version of LiveCycle or AEM Forms on JEE apart from LiveCycle Rights Management ES4 and version as 11.0.0, replace the path of the registry key as follows:

    * (LiveCycle&reg; Rights Management ES2 and version 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
    * (LiveCycle&reg; Rights Management ES3 and version 10.0)
    * (LiveCycle&reg; Rights Management ES4 and version 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
    * (AEM 6.0 Forms on JEE and later versions) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. In the above code, replace all the instances of YOUR_FOLDER_NAME with the name of the folder that you created in step 2.
1. **(For AEM Document Security Extension for Microsoft Office installer with .exe extension only)** Replace the following line of code:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
   with

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Save and close the batch file.
1. Use a self-extractor and packager tool to package the folder containing:

   * The custom CommonResources.dll file
   * The original installer of AEM Document Security extension for Microsoft Office
   * And, the batch file

   >[!NOTE]
   >
   >Ensure that the self-extracting package is set to run as an administrator and automatically
   >runs the batch file on completing the extraction.

Now, the self-extracting installer of AEM Document Security Extension for Microsoft Office packages a custom CommonResources.dll file and is ready for distribution.
