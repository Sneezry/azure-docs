---
title: 'Tutorial: Azure Active Directory integration with SCC LifeCycle'
description: Learn how to configure single sign-on between Azure Active Directory and SCC LifeCycle.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: jeedes
---
# Tutorial: Azure Active Directory integration with SCC LifeCycle

In this tutorial, you'll learn how to integrate SCC LifeCycle with Azure Active Directory (Azure AD). When you integrate SCC LifeCycle with Azure AD, you can:

* Control in Azure AD who has access to SCC LifeCycle.
* Enable your users to be automatically signed-in to SCC LifeCycle with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To configure Azure AD integration with SCC LifeCycle, you need the following items:

* An Azure AD subscription. If you don't have an Azure AD environment, you can get a [free account](https://azure.microsoft.com/free/).
* SCC LifeCycle single sign-on enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD single sign-on in a test environment.

* SCC LifeCycle supports **SP** initiated SSO.

## Add SCC LifeCycle from the gallery

To configure the integration of SCC LifeCycle into Azure AD, you need to add SCC LifeCycle from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **SCC LifeCycle** in the search box.
1. Select **SCC LifeCycle** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for SCC LifeCycle

Configure and test Azure AD SSO with SCC LifeCycle using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in SCC LifeCycle.

To configure and test Azure AD SSO with SCC LifeCycle, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure SCC LifeCycle SSO](#configure-scc-lifecycle-sso)** - to configure the single sign-on settings on application side.
    1. **[Create SCC LifeCycle test user](#create-scc-lifecycle-test-user)** - to have a counterpart of B.Simon in SCC LifeCycle that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **SCC LifeCycle** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type a URL using one of the following patterns:
	
    | **Identifier** |
    |----------|
    | `https://bs1.scc.com/<entity>` |
    | `https://lifecycle.scc.com/<entity>` |

    b. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<sub-domain>.scc.com/ic7/welcome/customer/PICTtest.aspx`

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier and Sign on URL. Contact [SCC LifeCycle Client support team](mailto:lifecycle.support@scc.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

5. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, click **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up SCC LifeCycle** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to SCC LifeCycle.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **SCC LifeCycle**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure SCC LifeCycle SSO

To configure single sign-on on **SCC LifeCycle** side, you need to send the downloaded **Metadata XML** and appropriate copied URLs from Azure portal to [SCC LifeCycle support team](mailto:lifecycle.support@scc.com). They set this setting to have the SAML SSO connection set properly on both sides.

   > [!NOTE]
   > Single sign-on has to be enabled by the [SCC LifeCycle support team](mailto:lifecycle.support@scc.com).

### Create SCC LifeCycle test user

In order to enable Azure AD users to log into SCC LifeCycle, they must be provisioned into SCC LifeCycle. There is no action item for you to configure user provisioning to SCC LifeCycle.

When an assigned user tries to log into SCC LifeCycle, an SCC LifeCycle account is automatically created if necessary.

> [!NOTE]
> The Azure Active Directory account holder receives an email and follows a link to confirm their account before it becomes active.

## Test SSO

In this section, you test your Azure AD single sign-on configuration with following options. 

* Click on **Test this application** in Azure portal. This will redirect to SCC LifeCycle Sign-on URL where you can initiate the login flow. 

* Go to SCC LifeCycle Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you click the SCC LifeCycle tile in the My Apps, this will redirect to SCC LifeCycle Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Next steps

Once you configure SCC LifeCycle you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).
