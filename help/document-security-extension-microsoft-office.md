---
title: Introduction to AEM Document Security Extension for Microsoft&reg; Office
description: Using document Security Extension for Microsoft&reg; Office, you can apply predefined confidentiality settings to your Microsoft&reg; Office files.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
---
# Introduction to AEM Document Security Extension for Microsoft&reg; Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe&reg; Experience Manager Document Security Extension for Microsoft&reg; Office ensures that only the people you authorize can use Word, Excel, and PowerPoint files that contain your intellectual property. By using Document Security Extension for Microsoft&reg; Office, you can apply predefined confidentiality settings to your files.

Document Security Extension for Microsoft&reg; Office extends LiveCycle Rights Management and Document Security add-on for Adobe Experience Manager Forms to protect Word, Excel, and PowerPoint files and to allow authorized users who have this software installed to use policy-protected files according to the confidentiality settings established in the policy.

## How Document Security protects intellectual property {#how-document-security-protects-intellectual-property}

Document Security ensures that only the people that you authorize can use files that contain your intellectual property. Using Document Security, you can protect files by using confidentiality policies. A *policy* is a collection of information that includes confidentiality settings and a list of authorized users. The settings you specify in a policy determine how a recipient can use a file to which you apply the policy. For example, you can specify whether recipients can print or copy text or save changes.

Document Security administrators and users create policies. Administrators create organizational policies that are available to all authorized users. Administrators or policy set coordinators can also create groups of policies called *policy sets* that are available to a subset of users. Users can create their own policies, which only they can use. Administrators, policy set coordinators, and users create policies by using the Document Security web pages.

Although policies are stored on Document Security, you apply them to files through Word, Excel, or PowerPoint. When you apply a policy to a file, the information that the file contains is protected by the confidentiality settings that are specified in the policy. When you distribute the policy-protected file, only the recipients who are authorized by the policy can access the file's contents.

Using a policy to protect a file gives you ongoing control over that file, even after you distribute it. You can audit events to track when and how recipients are using your file, make changes to the policy, prevent users from continuing to access the file, and change the policy that is attached to the file.

## How policies work {#how-policies-work}

Policies contain information about the authorized users and the confidentiality settings to apply to intellectual property. Users can be any user who is recognized by Document Security through inclusion in a linked LDAP or Active Directory list. Users can also be people who were invited to register with Document Security or for whom the administrator created an account.

The confidentiality settings in a policy determine how the recipients can use files that are protected by the policy. For example, policies specify whether recipients can print files, copy content to other files, or save changes to protected files. Policies can also specify different confidentiality settings for various users.

When you apply a policy to a file, the information that the file contains is protected by the confidentiality settings that are specified in the policy. When you distribute the file, Document Security authenticates the recipients who attempt to open the file and authorizes access according to the privileges specified in the policy.

After a policy is applied to a file, the confidentiality settings of the policy can be changed at any time. Doing so lets you add or remove authorized users or change the privileges for users after they received the file. The policy applied to the file can be changed, and access to the file can be revoked so that anyone with a copy of the file can no longer open it.

If the policy permits offline access, recipients can also use policy-protected files offline (without an active Internet or network connection) for the time period specified in the policy.

## How policy-protected files work {#how-policy-protected-files-work}

For a user to open and use policy-protected Word, Excel, and PowerPoint files, the policy must include the user as a recipient or allow anonymous access. And, the user must have Document Security Extension for Microsoft&reg; Office installed. To give a policy-protected file to someone who does not have Document Security Extension for Microsoft&reg; Office, either give them a copy of the software or tell them how to download it from your website. If you do not have the installer, you can download it from the [download page](https://experienceleague.adobe.com/docs/experience-manager-document-security/using/download-installer.html?lang=en).

When a user attempts to open a policy-protected file, Document Security Extension for Microsoft&reg; Office connects to Document Security to authenticate the user. If Document Security is configured to audit file usage, the user sees a notification indicating that the file usage is being audited. Document Security determines which file permissions to grant the user and the user can then use the file according to the policy settings, under these conditions:

* For the validity period that is specified in the policy.
* Until an administrator or the person who applied the policy either revokes the access to the file or changes the policy.

  If the person who applied the policy changes the policy or revokes access to the file, the user's permissions for the file are changed or removed even though the user already has the file. If the file itself was revoked, a URL may be provided to the user to get an updated copy.

  Policy-protected files can be opened offline (without an Internet or network connection), if the policy permits offline access, during the offline lease period that is specified in the policy. When the offline lease period ends, the user must go online and synchronize with Document Security, which starts a new lease period.

  If the policy allows the file to be saved and a user saves a copy of the policy-protected file, the policy is automatically applied and enforced for the saved file. Events, such as attempts to open the new file, are also audited and recorded the same as for the original file.

## Using Document Security to protect your files {#using-document-security-to-protect-your-files}

You can use policies to protect your files in various situations.

For example, a manufacturer is accepting bids from vendors who provide parts for a new product. The manufacturer must provide the bidders with proprietary information to finalize their submissions. The manufacturer uses Document Security to protect the files with a policy that allows the bidders to open the files and view the information. However, bidders are prevented from changing, printing, or copying the files and anyone who does not have permission is prevented from opening the files.

After accepting one of the bids, the manufacturer updates the policy to give the successful bidder permissions to print, copy, and save changes locally, and to remove the unsuccessful bidders so that they no longer have permission to open the files.

While working with the successful bidder, the manufacturer's engineers change some of the design specifications in the files. To publish the new specifications, the manufacturer revokes access to some of the files and publishes new versions. When engineers for the successful bidder attempt to open the file, they see a message that access to the file was revoked. The message contains a URL where they can download a new version of the file.

## Additional Information {#additional-information}

The resources in this table can help you learn more about AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>For information about</p> </th>
   <th><p>See</p> </th>
  </tr>
  <tr>
   <td><p>AEM forms Administrator Help</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/docs/experience-manager-65/forms/administrator-help/get-started/configure-general-aem-forms-settings.html?lang=en">Administrator Help</a> or, on the Document Security administration pages, click the Help link in the upper-right corner of a page.</p> </td>
  </tr>
  <tr>
   <td><p>Patch updates, technical notes, and additional information about this product version</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&support-tab=home#support">Experience Cloud Technical Support</a></p> </td>
  </tr>
 </tbody>
</table>
