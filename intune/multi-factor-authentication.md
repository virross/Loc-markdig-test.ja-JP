---
title: "Intune へのデバイスの登録での多要素認証"
titlesuffix: Azure portal
description: "デバイス登録で Azure AD の多要素認証を要求する方法。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: a3aabe77257fd7e6964dd7bd83035c8a491a58b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a><span data-ttu-id="f27a7-103">Intune へのデバイスの登録での多要素認証</span><span class="sxs-lookup"><span data-stu-id="f27a7-103">Multi-factor authentication for Intune device enrollments</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f27a7-104">Intune では、デバイス登録に Azure Active Directory (AD) 多要素認証 (MFA) 機能を利用し、会社のリソースを守ります。</span><span class="sxs-lookup"><span data-stu-id="f27a7-104">Intune can use Azure Active Directory (AD) multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.</span></span>

<span data-ttu-id="f27a7-105">MFA は、次の確認方法のうち 2 つ以上を必須にすることで機能します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-105">MFA works by requiring any two or more of the following verification methods:</span></span>

- <span data-ttu-id="f27a7-106">ユーザーが知っている情報 (通常はパスワードまたは PIN)。</span><span class="sxs-lookup"><span data-stu-id="f27a7-106">Something you know (typically a password or PIN).</span></span>
- <span data-ttu-id="f27a7-107">ユーザーの所持品 (電話など、容易には複製できない、信頼済みのデバイス)。</span><span class="sxs-lookup"><span data-stu-id="f27a7-107">Something you have (a trusted device that is not easily duplicated, like a phone).</span></span>
- <span data-ttu-id="f27a7-108">ユーザー自身 (指紋など、生体認証)</span><span class="sxs-lookup"><span data-stu-id="f27a7-108">Something you are (biometrics, like a fingerprint).</span></span>

<span data-ttu-id="f27a7-109">MFA は、iOS、Android、Windows 8.1 以上、Windows Phone 8.1 以上、Windows 10 Mobile 以上のデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f27a7-109">MFA is supported for iOS, Android, Windows 8.1 or later, Windows Phone 8.1, or Windows 10 Mobile or later devices.</span></span>

<span data-ttu-id="f27a7-110">MFA を有効にするには、エンド ユーザーは 2 種類の資格情報を提供し、デバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27a7-110">When you enable MFA, end users must supply two forms of credentials to enroll a device.</span></span>

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a><span data-ttu-id="f27a7-111">デバイス登録時に多要素認証を要求するように Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="f27a7-111">Configure Intune to require multi-factor authentication at device enrollment</span></span>

<span data-ttu-id="f27a7-112">デバイスの登録時に MFA を要求するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f27a7-112">To require MFA when a device is enrolled, follow these steps:</span></span>

>[!Important]
><span data-ttu-id="f27a7-113">Microsoft Intune 登録には、**デバイス ベースのアクセス規則**を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="f27a7-113">Do not configure **Device based access rules** for Microsoft Intune enrollment.</span></span>

1. <span data-ttu-id="f27a7-114">資格情報を利用し、[Microsoft Azure Portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f27a7-114">Sign in to your [Microsoft Azure portal](https://portal.azure.com) with your credentials.</span></span>
2. <span data-ttu-id="f27a7-115">ポータルで、**[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-115">In the portal, choose **Azure Active Directory**.</span></span>
2. <span data-ttu-id="f27a7-116">**[Azure Active Directory]** で、**[管理]** > **[エンタープライズ アプリケーション]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-116">In **Azure Active Directory**, choose **Manage** > **Enterprise applications**.</span></span>
3. <span data-ttu-id="f27a7-117">**[エンタープライズ アプリケーション]** で、**[管理]** > **[すべてのアプリケーション]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-117">In **Enterprise applications**, choose **Manage** > **All applications**.</span></span> <span data-ttu-id="f27a7-118">管理するすべての Azure アプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27a7-118">You see a list of all Azure apps that you manage.</span></span>
3. <span data-ttu-id="f27a7-119">この一覧から、**[Microsoft Intune enrollment]\(Microsoft Intune 登録\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-119">From the list, choose **Microsoft Intune enrollment**.</span></span>
4. <span data-ttu-id="f27a7-120">**[Microsoft Intune Enrollment]\(Microsoft Intune 登録\)** で、**[セキュリティ]** > **[条件付きアクセス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-120">In **Microsoft Intune Enrollment**, choose **Security** > **Conditional access**.</span></span>
5. <span data-ttu-id="f27a7-121">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="f27a7-121">Choose **New policy**.</span></span>
6. <span data-ttu-id="f27a7-122">**[新しいポリシー]** で、ポリシーのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-122">In **New** policy, type a descriptive name for the policy.</span></span>
7. <span data-ttu-id="f27a7-123">**[割り当て]** セクションで、**[ユーザーとグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-123">In the **Assignments** section, choose **Users and groups**.</span></span>
8. <span data-ttu-id="f27a7-124">**[ユーザーとグループ]** で、このポリシーを受けるユーザーまたはグループを選択し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-124">In **Users and groups**, choose the users or groups that will receive this policy, then choose **Done**.</span></span>
9. <span data-ttu-id="f27a7-125">**[割り当て]** セクションで、**[クラウド アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-125">In the **Assignments** section, choose **Cloud apps**.</span></span>
10. <span data-ttu-id="f27a7-126">**[クラウド アプリ]** の **[挿入]** タブで、**[アプリを選択]** を選択し、**[選択]** > **[Microsoft Intune Enrollment]\(Microsoft Intune 登録\)** の順に選択し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-126">On the **Include** tab of **Cloud apps**, choose **Select apps**, then choose **Select** > **Microsoft Intune Enrollment**, and then choose **Done**.</span></span>
11. <span data-ttu-id="f27a7-127">**[割り当て]** セクションで、**[条件]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-127">In the **Assignments** section, choose **Conditions**.</span></span>
12. <span data-ttu-id="f27a7-128">**[条件]** では、MFA 設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f27a7-128">In **Conditions**, you do not need to configure any settings for MFA.</span></span>
13. <span data-ttu-id="f27a7-129">**[アクセス制御]** セクションで、**[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-129">In the **Access controls** section, choose **Grant**.</span></span>
14. <span data-ttu-id="f27a7-130">**[許可]** で、**[アクセス権の付与]** を選択し、**[多要素認証を要求する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-130">In **Grant**, choose **Grant access**, and then select **Require multi-factor authentication**.</span></span>
    <span data-ttu-id="f27a7-131">**[デバイスは準拠としてマーク済みである必要があります]** は選択しないでください。登録されるまで、デバイスの準拠状態は評価できません。</span><span class="sxs-lookup"><span data-stu-id="f27a7-131">Do not select **Require device to be marked as compliant** because a device cannot be evaluated for compliance until it is enrolled.</span></span>
15. <span data-ttu-id="f27a7-132">**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-132">Choose **Select**.</span></span>
16. <span data-ttu-id="f27a7-133">**[新しいポリシー]** で、**[ポリシーを有効にする]** > **[オン]** の順に選択し、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27a7-133">In **New policy**, choose **Enable policy** > **On**, and then choose **Create**.</span></span>



## <a name="next-steps"></a><span data-ttu-id="f27a7-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="f27a7-134">Next steps</span></span>

<span data-ttu-id="f27a7-135">エンド ユーザーがデバイスを登録するとき、PIN、スマートフォン、生体認証など、2 つ目の識別形態で認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27a7-135">When end users enroll their device, they now must authenticate with a second form of identification, like a PIN, a phone, or biometrics.</span></span>
