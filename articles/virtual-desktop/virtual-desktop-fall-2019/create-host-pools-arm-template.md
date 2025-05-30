---
title: Azure Virtual Desktop (classic) host pool Azure Resource Manager - Azure
description: How to create a host pool in Azure Virtual Desktop (classic) with an Azure Resource Manager template.
author: Heidilohr
ms.topic: how-to
ms.custom: devx-track-arm-template
ms.date: 03/30/2020
ms.author: helohr
manager: femila
---
# Create a host pool in Azure Virtual Desktop (classic) with an Azure Resource Manager template

>[!IMPORTANT]
>This content applies to Azure Virtual Desktop (classic), which doesn't support Azure Resource Manager Azure Virtual Desktop objects.

Host pools are a collection of one or more identical virtual machines within Azure Virtual Desktop tenant environments. Each host pool can contain an application group that users can interact with as they would on a physical desktop.

Follow this section's instructions to create a host pool for a Azure Virtual Desktop tenant with an Azure Resource Manager template provided by Microsoft. This article will tell you how to create a host pool in Azure Virtual Desktop, create a resource group with VMs in an Azure subscription, join those VMs to the AD domain, and register the VMs with Azure Virtual Desktop.

## What you need to run the Azure Resource Manager template

Make sure you know the following things before running the Azure Resource Manager template:

- Where the source of the image you want to use is. Is it from Azure Gallery or is it custom?
- Your domain join credentials.
- Your Azure Virtual Desktop credentials.

When you create a Azure Virtual Desktop host pool with the Azure Resource Manager template, you can create a virtual machine from the Azure gallery, a managed image, or an unmanaged image. To learn more about how to create VM images, see [Prepare a Windows VHD or VHDX to upload to Azure](../../virtual-machines/windows/prepare-for-upload-vhd-image.md) and [Create a managed image of a generalized VM in Azure](../../virtual-machines/windows/capture-image-resource.md).

## Run the Azure Resource Manager template for provisioning a new host pool

To start, go to [this GitHub URL](https://github.com/Azure/RDS-Templates/tree/master/wvd-templates/Create%20and%20provision%20WVD%20host%20pool).

### Deploy the template to Azure

If you're deploying in an Enterprise subscription, scroll down and select **Deploy to Azure**, then skip ahead fill out the parameters based on your image source.

If you're deploying in a Cloud Solution Provider subscription, follow these steps to deploy to Azure:

1. Scroll down and right-click **Deploy to Azure**, then select **Copy Link Location**.
2. Open a text editor like Notepad and paste the link there.
3. Right after "https://portal.azure.com/" and before the hashtag (#) enter an at sign (@) followed by the tenant domain name. Here's an example of the format you should use: `https://portal.azure.com/@Contoso.onmicrosoft.com#create/`.
4. Sign in to the Azure portal as a user with Admin/Contributor permissions to the Cloud Solution Provider subscription.
5. Paste the link you copied to the text editor into the address bar.

For guidance about which parameters you should enter for your scenario, see the Azure Virtual Desktop [Readme file](https://github.com/Azure/RDS-Templates/blob/master/wvd-templates/Create%20and%20provision%20WVD%20host%20pool/README.md). The Readme is always updated with the latest changes.

## Assign users to the desktop application group

After the GitHub Azure Resource Manager template completes, assign user access before you start testing the full session desktops on your virtual machines.

First, [download and import the Azure Virtual Desktop PowerShell module](/powershell/windows-virtual-desktop/overview/) to use in your PowerShell session if you haven't already.

To assign users to the desktop application group, open a PowerShell window and run this cmdlet to sign in to the Azure Virtual Desktop environment:

```powershell
Add-RdsAccount -DeploymentUrl "https://rdbroker.wvd.microsoft.com"
```

After that, add users to the desktop application group with this cmdlet:

```powershell
Add-RdsAppGroupUser <tenantname> <hostpoolname> "Desktop Application Group" -UserPrincipalName <userupn>
```

The user's UPN should match the user's identity in Azure Active Directory (for example, user1@contoso.com). If you want to add multiple users, you must run this cmdlet for each user.

After you've completed these steps, users added to the desktop application group can sign in to Azure Virtual Desktop with supported Remote Desktop clients and see a resource for a session desktop.

>[!IMPORTANT]
>To help secure your Azure Virtual Desktop environment in Azure, we recommend you don't open inbound port 3389 on your VMs. Azure Virtual Desktop doesn't require an open inbound port 3389 for users to access the host pool's VMs. If you must open port 3389 for troubleshooting purposes, we recommend you use [just-in-time VM access](../../security-center/security-center-just-in-time.md).
