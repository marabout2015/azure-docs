---
title: 'Tutorial: Azure Active Directory integration with Procore SSO | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Procore SSO.
services: active-directory
documentationCenter: na
author: jeevansd
manager: femila
ms.reviewer: joflore

ms.assetid: 9818edd3-48c0-411d-b05a-3ec805eafb2e
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 11/13/2018
ms.author: jeedes

ms.collection: M365-identity-device-management
---
# Tutorial: Azure Active Directory integration with Procore SSO

In this tutorial, you learn how to integrate Procore SSO with Azure Active Directory (Azure AD).

Integrating Procore SSO with Azure AD provides you with the following benefits:

- You can control in Azure AD who has access to Procore SSO.
- You can enable your users to automatically get signed-on to Procore SSO (Single Sign-On) with their Azure AD accounts.
- You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [what is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md)

## Prerequisites

To configure Azure AD integration with Procore SSO, you need the following items:

- An Azure AD subscription
- A Procore SSO single sign-on enabled subscription

> [!NOTE]
> To test the steps in this tutorial, we do not recommend using a production environment.

To test the steps in this tutorial, you should follow these recommendations:

- Do not use your production environment, unless it is necessary.
- If you don't have an Azure AD trial environment, you can [get a one-month trial](https://azure.microsoft.com/pricing/free-trial/).

## Scenario description

In this tutorial, you test Azure AD single sign-on in a test environment. 
The scenario outlined in this tutorial consists of two main building blocks:

1. Adding Procore SSO from the gallery
2. Configuring and testing Azure AD single sign-on

## Adding Procore SSO from the gallery

To configure the integration of Procore SSO into Azure AD, you need to add Procore SSO from the gallery to your list of managed SaaS apps.

**To add Procore SSO from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon. 

	![The Azure Active Directory button][1]

2. Navigate to **Enterprise applications**. Then go to **All applications**.

	![The Enterprise applications blade][2]

3. To add new application, click **New application** button on the top of dialog.

	![The New application button][3]

4. In the search box, type **Procore SSO**, select **Procore SSO** from result panel then click **Add** button to add the application.

	![Procore SSO in the results list](./media/procoresso-tutorial/tutorial_procoresso_addfromgallery.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with Procore SSO based on a test user called "Britta Simon".

For single sign-on to work, Azure AD needs to know what the counterpart user in Procore SSO is to a user in Azure AD. In other words, a link relationship between an Azure AD user and the related user in Procore SSO needs to be established.

To configure and test Azure AD single sign-on with Procore SSO, you need to complete the following building blocks:

1. **[Configuring Azure AD Single Sign-On](#configuring-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Creating an Azure AD test user](#creating-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
3. **[Creating a Procore SSO test user](#creating-a-procore-sso-test-user)** - to have a counterpart of Britta Simon in Procore SSO that is linked to the Azure AD representation of user.
4. **[Assigning the Azure AD test user](#assigning-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Testing single sign-on](#testing-single-sign-on)** - to verify whether the configuration works.

### Configuring Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal and configure single sign-on in your Procore SSO application.

**To configure Azure AD single sign-on with Procore SSO, perform the following steps:**

1. In the Azure portal, on the **Procore SSO** application integration page, click **Single sign-on**.

	![Configure single sign-on link][4]

2. On the **Select a Single sign-on method** dialog, Click **Select** for **SAML** mode to enable single sign-on.

    ![Configure Single Sign-On](common/tutorial_general_301.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Configure Single Sign-On](common/editconfigure.png)

4. On the **Basic SAML Configuration** section, the user does not have to perform any steps as the app is already pre-integrated with Azure.

	![Procore SSO Domain and URLs single sign-on information](./media/procoresso-tutorial/tutorial_procoresso_url.png)

5. On the **SAML Signing Certificate** page, in the **SAML Signing Certificate** section, click **Download** to download **Federation Metadata XML** and then save Metadata file on your computer.

	![The Certificate download link](./media/procoresso-tutorial/tutorial_procoresso_certificate.png) 

6. On the **Set up Procore SSO** section, copy the appropriate URL as per your requirement.

	a. Login URL

	b. Azure AD Identifier

	c. Logout URL

	![Procore SSO Configuration](common/configuresection.png)

7. To configure single sign-on on **Procore SSO** side, login to your procore company site as an administrator.

8. From the toolbox drop down, click on **Admin** to open the SSO settings page.

	![Configure Single Sign-On](./media/procoresso-tutorial/procore_tool_admin.png)

9. Paste the values in the boxes as described below-

	![Configure Single Sign-On](./media/procoresso-tutorial/procore_setting_admin.png)	

	a. In the **Single Sign On Issuer URL** text box, paste the value of **Azure AD Identifier** which you have copied from the Azure portal.

	b. In the **SAML Sign On Target URL** box, paste the value of **Login URL** which you have copied from the Azure portal.

	c. Now open the **Federation Metadata XML** downloaded above from the Azure portal and copy the certificate in the tag named **X509Certificate**. Paste the copied value into the **Single Sign On x509 Certificate** box.

10. Click on **Save Changes**.

11. After these settings, you needs to send the **domain name** (e.g **contoso.com**) through which you are logging into Procore to the [Procore Support team](https://support.procore.com/) and they will activate federated SSO for that domain.

<!--### Next steps

To ensure users can sign-in to Procore SSO after it has been configured to use Azure Active Directory, review the following tasks and topics:

- User accounts must be pre-provisioned into Procore SSO prior to sign-in. To set this up, see Provisioning.
 
- Users must be assigned access to Procore SSO in Azure AD to sign-in. To assign users, see Users.
 
- To configure access polices for Procore SSO users, see Access Policies.
 
- For additional information on deploying single sign-on to users, see [this article](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis#deploying-azure-ad-integrated-applications-to-users).-->

### Creating an Azure AD test user

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

	![Create Azure AD User][100]

2. Select **New user** at the top of the screen.

	![Creating an Azure AD test user](common/create_aaduser_01.png) 

3. In the User properties, perform the following steps.

	![Creating an Azure AD test user](common/create_aaduser_02.png)

    a. In the **Name** field, enter **BrittaSimon**.
  
    b. In the **User name** field, type **brittasimon\@yourcompanydomain.extension**  
       For example, BrittaSimon@contoso.com

    c. Select **Properties**, select the **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Select **Create**.

### Creating a Procore SSO test user

Please follow the below steps to create a Procore test user on Procore SSOc side.

1. Login to your procore company site as an administrator.	

2. From the toolbox drop down, click on **Directory** to open the company directory page.

	![Configure Single Sign-On](./media/procoresso-tutorial/Procore_sso_directory.png)

3. Click on **Add a Person** option to open the form and enter perform following options -

	![Configure Single Sign-On](./media/procoresso-tutorial/Procore_user_add.png)

    a. In the **First Name** textbox, type user's first name like **Britta**.

    b. In the **Last name** textbox, type user's last name like **Simon**.

	c. In the **Email Address** textbox, type user's email address like **BrittaSimon\@contoso.com**.

    d. Select **Permission Template** as **Apply Permission Template Later**.

    e. Click **Create**.

4. Check and update the details for the newly added contact.

	![Configure Single Sign-On](./media/procoresso-tutorial/Procore_user_check.png)

5. Click on **Save and Send Invitation** (if an invite through mail is required) or **Save** (Save directly) to complete the user registration.
	
	![Configure Single Sign-On](./media/procoresso-tutorial/Procore_user_save.png)

### Assigning the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to Procore SSO.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**.

	![Assign User][201]

2. In the applications list, select **Procore SSO**.

	![Configure Single Sign-On](./media/procoresso-tutorial/tutorial_procoresso_app.png)

3. In the menu on the left, click **Users and groups**.

	![Assign User][202]

4. Click **Add** button. Then select **Users and groups** on **Add Assignment** dialog.

	![Assign User][203]

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. In the **Add Assignment** dialog select the **Assign** button.

### Testing single sign-on

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Procore SSO tile in the Access Panel, you should get automatically signed-on to your Procore SSO application.
For more information about the Access Panel, see [Introduction to the Access Panel](../user-help/active-directory-saas-access-panel-introduction.md).

## Additional resources

* [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](tutorial-list.md)
* [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: common/tutorial_general_01.png
[2]: common/tutorial_general_02.png
[3]: common/tutorial_general_03.png
[4]: common/tutorial_general_04.png

[100]: common/tutorial_general_100.png

[201]: common/tutorial_general_201.png
[202]: common/tutorial_general_202.png
[203]: common/tutorial_general_203.png
