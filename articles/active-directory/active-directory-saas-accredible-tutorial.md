---
title: "教程：Azure Active Directory 与 Accredible 集成 | Microsoft Docs"
description: "了解如何在 Azure Active Directory 和 Accredible 之间配置 SSO。"
services: active-directory
documentationCenter: na
author: jeevansd
manager: femila
ms.reviewer: joflore
ms.assetid: 7284dfb6-df62-41f1-a4a4-1b8322b7ef44
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 12/07/2017
ms.author: jeedes
ms.openlocfilehash: b0e33d2a1d455e233672bf1467efcfaf9df2cab3
ms.sourcegitcommit: 094061b19b0a707eace42ae47f39d7a666364d58
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2017
---
# <a name="tutorial-azure-active-directory-integration-with-accredible"></a>教程：Azure Active Directory 与 Accredible 集成

在本教程中，了解如何将 Accredible 与 Azure Active Directory (Azure AD) 集成。

将 Accredible 与 Azure AD 集成具有以下优势：

- 可在 Azure AD 中控制谁有权访问 Accredible。
- 可以让用户使用其 Azure AD 帐户以 SSO 的方式自动登录到 Accredible。
- 可在中心位置（即 Azure 门户）管理帐户。

如需了解有关 SaaS 应用与 Azure AD 集成的详细信息，请参阅 [Azure Active Directory 的应用程序访问与单一登录是什么](active-directory-appssoaccess-whatis.md)。

## <a name="prerequisites"></a>先决条件

要配置 Azure AD 与 Accredible 的集成，需要以下项目：

- 一个 Azure AD 订阅
- 启用 Accredible 单一登录的订阅

> [!NOTE]
> 不建议使用生产环境测试本教程中的步骤。

测试本教程中的步骤应遵循以下建议：

- 除非必要，请勿使用生产环境。
- 如果没有 Azure AD 试用环境，可以[获取一个月的试用版](https://azure.microsoft.com/pricing/free-trial/)。

## <a name="scenario-description"></a>方案描述
在本教程中，将在测试环境中测试 Azure AD 单一登录。 本教程中概述的方案包括两个主要构建基块：

1. 从库中添加 Accredible
2. 配置并测试 Azure AD 单一登录

## <a name="adding-accredible-from-the-gallery"></a>从库中添加 Accredible
要配置 Accredible 与 Azure AD 的集成，需要从库中将 Accredible 添加到托管 SaaS 应用列表。

要从库中添加 Accredible，请执行以下步骤：

1. 在 **[Azure 门户](https://portal.azure.com)**的左侧导航面板中，单击“Azure Active Directory”图标。 

    ![“Azure Active Directory”按钮][1]

2. 导航到“企业应用程序”。 然后转到“所有应用程序”。

    ![“企业应用程序”边栏选项卡][2]
    
3. 若要添加新应用程序，请单击对话框顶部的“新建应用程序”按钮。

    ![“新建应用程序”按钮][3]

4. 在搜索框中，键入“Accredible”，在结果面板中选择“Accredible”，然后单击“添加”按钮添加该应用程序。

    ![结果列表中的 Accredible](./media/active-directory-saas-accredible-tutorial/tutorial_accredible_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>配置和测试 Azure AD 单一登录

在本部分中，基于一个名为“Britta Simon”的测试用户使用 Accredible 配置和测试 Azure AD SSO。

要运行 SSO，Azure AD 需要知道与 Azure AD 用户相对应的 Accredible 用户。 换句话说，需要建立 Azure AD 用户与 Accredible 中相关用户之间的链接关系。

在 Accredible 中，可通过将 Azure AD 中“用户名”的值指定为“用户名”的值，建立此链接关系。

要配置和测试 Accredible 的 Azure AD SSO，需要完成以下构建基块：

1. **[配置 Azure AD 单一登录](#configure-azure-ad-single-sign-on)** - 使用户能够使用此功能。
2. **[创建 Azure AD 测试用户](#create-an-azure-ad-test-user)** - 使用 Britta Simon 测试 Azure AD 单一登录。
3. **[创建 Accredible 测试用户](#create-an-accredible-test-user)** - 在 Accredible 中创建 Britta Simon 的对应用户，并将其链接到该用户的 Azure AD 表示形式。
4. **[分配 Azure AD 测试用户](#assign-the-azure-ad-test-user)** - 使 Britta Simon 能够使用 Azure AD 单一登录。
5. **[测试单一登录](#test-single-sign-on)** - 验证配置是否正常工作。

### <a name="configure-azure-ad-single-sign-on"></a>配置 Azure AD 单一登录

在本部分中，会在 Azure 门户中启用 Azure AD SSO 并在 Accredible 应用程序中配置 SSO。

**要配置 Accredible 的 Azure AD SSO，请执行以下步骤：**

1. 在 Azure 门户中的 Accredible 应用程序集成页上，单击“SSO”。

    ![配置单一登录链接][4]

2. 在“单一登录”对话框中，选择“基于 SAML 的单一登录”作为“模式”以启用单一登录。
 
    ![“单一登录”对话框](./media/active-directory-saas-accredible-tutorial/tutorial_accredible_samlbase.png)

3. 在“Accredible 域和 URL”部分中，执行以下步骤：

    ![Accredible 域和 URL SSO 信息](./media/active-directory-saas-accredible-tutorial/tutorial_accredible_url.png)

    a. 在“标识符”文本框中，键入一个 URL：
    | |
    |--|
    |  `https://api.accredible.com/sp/admin/accredible` |
    | `https://api.accredible.com/sp/user/accredible` |

    b. 在“回复 URL”文本框中，使用以下模式键入 URL：`https://api.accredible.com/v1/saml/admin/<Unique id>/consume`

    > [!NOTE] 
    > 答复 URL 值不是真实值。 根据用户角色，使用相应的标识符值。 每个客户具有唯一的回复 URL，具体取决于其 ID。 请联系 [Accredible 支持团队](mailto:support@accredible.com)获取这些值。
 
4. 在“SAML 签名证书”部分中，单击“元数据 XML”，并在计算机上保存元数据文件。

    ![证书下载链接](./media/active-directory-saas-accredible-tutorial/tutorial_accredible_certificate.png) 

5. 单击“保存”按钮。

    ![配置单一登录“保存”按钮](./media/active-directory-saas-accredible-tutorial/tutorial_general_400.png)

6. 要在 Accredible 端配置 SSO，需要将下载的元数据 XML 发送给 [Accredible 支持团队](mailto:support@accredible.com)。 他们会对此进行设置，使两端的 SAML SSO 连接均正确设置。

> [!TIP]
> 之后在设置应用时，就可以在 [Azure 门户](https://portal.azure.com)中阅读这些说明的简明版本了！  从“Active Directory”>“企业应用程序”部分添加此应用后，只需单击“单一登录”选项卡，即可通过底部的“配置”部分访问嵌入式文档。 可在此处阅读有关嵌入式文档功能的详细信息：[ Azure AD 嵌入式文档]( https://go.microsoft.com/fwlink/?linkid=845985)

### <a name="create-an-azure-ad-test-user"></a>创建 Azure AD 测试用户

本部分的目的是在 Azure 门户中创建名为 Britta Simon 的测试用户。

   ![创建 Azure AD 测试用户][100]

**若要在 Azure AD 中创建测试用户，请执行以下步骤：**

1. 在 Azure 门户的左窗格中，单击“Azure Active Directory”按钮。

    ![“Azure Active Directory”按钮](./media/active-directory-saas-accredible-tutorial/create_aaduser_01.png)

2. 若要显示用户列表，请转到“用户和组”，然后单击“所有用户”。

    ![“用户和组”以及“所有用户”链接](./media/active-directory-saas-accredible-tutorial/create_aaduser_02.png)

3. 若要打开“用户”对话框，在“所有用户”对话框顶部单击“添加”。

    ![“添加”按钮](./media/active-directory-saas-accredible-tutorial/create_aaduser_03.png)

4. 在“用户”对话框中，执行以下步骤：

    ![“用户”对话框](./media/active-directory-saas-accredible-tutorial/create_aaduser_04.png)

    a.在“横幅徽标”下面，选择“删除上传的徽标”。 在“姓名”框中，键入“BrittaSimon”。

    b.保留“数据库类型”设置，即设置为“共享”。 在“用户名”框中，键入用户 Britta Simon 的电子邮件地址。

    c. 选中“显示密码”复选框，然后记下“密码”框中显示的值。

    d. 单击“创建” 。
  
### <a name="create-an-accredible-test-user"></a>创建 Accredible 测试用户

本部分需在 Accredible 中创建名为“Britta Simon”的用户。 需要将用户的 emailid 发送给 [Accredible 支持团队](mailto:support@accredible.com)，他们稍后会验证电子邮件并发送邀请邮件，以便你在 accredible 平台中添加用户。
 
### <a name="assign-the-azure-ad-test-user"></a>分配 Azure AD 测试用户

在本部分中，通过向 Britta Simon 授予 Accredible 的访问权限支持她使用 Azure SSO。

![分配用户角色][200] 

**要将 Britta Simon 分配到 Accredible，请执行以下步骤：**

1. 在 Azure 门户中打开应用程序视图，导航到目录视图，接着转到“企业应用程序”，并单击“所有应用程序”。

    ![分配用户][201] 

2. 在应用程序列表中，选择“Accredible”。

    ![应用程序列表中的 Accredible 链接](./media/active-directory-saas-accredible-tutorial/tutorial_accredible_app.png)  

3. 在左侧菜单中，单击“用户和组”。

    ![“用户和组”链接][202]

4. 单击“添加”按钮。 然后在“添加分配”对话框中选择“用户和组”。

    ![“添加分配”窗格][203]

5. 在“用户和组”对话框的“用户”列表中，选择“Britta Simon”。

6. 在“用户和组”对话框中单击“选择”按钮。

7. 在“添加分配”对话框中单击“分配”按钮。
    
### <a name="test-single-sign-on"></a>测试单一登录

在本部分中，使用访问面板测试 Azure AD 单一登录配置。

在访问面板中单击 Accredible 磁贴时，应该会自动登录 Accredible 应用程序。
有关访问面板的详细信息，请参阅 [Introduction to the Access Panel](active-directory-saas-access-panel-introduction.md)（访问面板简介）。 

## <a name="additional-resources"></a>其他资源

* [有关如何将 SaaS 应用与 Azure Active Directory 集成的教程列表](active-directory-saas-tutorial-list.md)
* [Azure Active Directory 的应用程序访问与单一登录是什么？](active-directory-appssoaccess-whatis.md)



<!--Image references-->

[1]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_01.png
[2]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_02.png
[3]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_03.png
[4]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_04.png

[100]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_100.png

[200]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_200.png
[201]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_201.png
[202]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_202.png
[203]: ./media/active-directory-saas-accredible-tutorial/tutorial_general_203.png
