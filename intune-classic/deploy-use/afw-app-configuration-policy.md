---
title: "Android for Work アプリ構成ポリシー"
description: "Intune のモバイル アプリ構成ポリシーを使用して、ユーザーが Android for Work アプリを実行するときに必要となる可能性がある設定を指定できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 69232c105b5373fd26f169c3e5da71205e64c416
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a><span data-ttu-id="89587-103">Microsoft Intune でのモバイル アプリ構成ポリシーを使用した Android for Work アプリの構成</span><span class="sxs-lookup"><span data-stu-id="89587-103">Configure Android for Work apps with mobile app configuration policies in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="89587-104">Microsoft Intune のモバイル アプリ構成ポリシーを使用して、ユーザーがアプリを実行するときに必要となる可能性がある設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="89587-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="89587-105">たとえば、アプリは次の内容を指定することをユーザーに要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="89587-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="89587-106">カスタム ポート番号</span><span class="sxs-lookup"><span data-stu-id="89587-106">A custom port number</span></span>
-   <span data-ttu-id="89587-107">言語の設定</span><span class="sxs-lookup"><span data-stu-id="89587-107">Language settings</span></span>
-   <span data-ttu-id="89587-108">会社のロゴなどのブランドの設定</span><span class="sxs-lookup"><span data-stu-id="89587-108">Branding settings such as a company logo</span></span>

<span data-ttu-id="89587-109">ユーザーが設定を誤って入力すると、ヘルプ デスクの負荷が増加し、新しいアプリの採用が遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89587-109">If users enter settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="89587-110">モバイル アプリ構成ポリシーを使用すると、ユーザーがアプリを実行する前にこれらの設定をデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="89587-110">Mobile app configuration policies let you deploy these settings to devices before users run the app.</span></span> <span data-ttu-id="89587-111">設定は自動的に指定されるため、ユーザーの操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="89587-111">The settings are supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="89587-112">アプリ構成ポリシーを利用するには、アプリの開発元が作成時にエンタープライズ アプリ構成を公開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="89587-112">To utilize app configuration policies, the app developer must have exposed enterprise app configurations when they created it.</span></span> <span data-ttu-id="89587-113">たとえば、Google Chrome は、既定のブックマーク、許可するサイト、拒否するサイトの設定を公開しているので、アプリ構成ポリシーを利用できます。</span><span class="sxs-lookup"><span data-stu-id="89587-113">For example, Google Chrome exposes settings that let you set default bookmarks, allowed and denied sites, and more.</span></span> <span data-ttu-id="89587-114">このような設定がサポートされているかどうか、およびポリシーで指定する方法については、アプリの開発元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="89587-114">Contact the developer of the app to see if these settings are supported and how to specify them in the policy.</span></span>

<span data-ttu-id="89587-115">アプリ構成ポリシーは、構成するアプリを展開したユーザーと同じユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="89587-115">You deploy the app configuration policy to the same users to whom you have deployed the app you want to configure.</span></span> <span data-ttu-id="89587-116">アプリ設定はアプリの実行時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="89587-116">App settings are applied when the app is run.</span></span>

## <a name="configure-a-mobile-app-configuration-policy"></a><span data-ttu-id="89587-117">モバイル アプリ構成ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="89587-117">Configure a mobile app configuration policy</span></span>

1.  <span data-ttu-id="89587-118">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[概要]** &gt; **[ポリシーの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="89587-118">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="89587-119">ポリシーの一覧で **[Android for Work]** を展開し、**[モバイル アプリ構成ポリシー (Android for Work)]** を選択し、**[ポリシーを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="89587-119">In the list of policies, expand **Android for Work**, choose **Mobile App Configuration Policy (Android for Work)**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="89587-120">この種類のポリシーではカスタム設定のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="89587-120">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="89587-121">推奨設定はありません。</span><span class="sxs-lookup"><span data-stu-id="89587-121">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="89587-122">**[ポリシーの作成]** ページの **[全般]** セクションで、名前とモバイル アプリ構成ポリシーのオプションの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="89587-122">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4. <span data-ttu-id="89587-123">ページの **[モバイル アプリ構成ポリシー]** セクションで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="89587-123">In the **Mobile App Configuration Policy** section of the page, specify the following information:</span></span>
    - <span data-ttu-id="89587-124">**[この構成が適用されるアプリケーションのパッケージ ID]** - パッケージ ID は、Google Play ページのアプリ URL の ’id=’ セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="89587-124">**Package ID for the application that this configuration applies to** - The package ID can be found in the 'id=' section of the app URL on it's Google Play page.</span></span> <span data-ttu-id="89587-125">たとえば、Microsoft Excel アプリのパッケージ ID は **com.microsoft.office.excel** です。</span><span class="sxs-lookup"><span data-stu-id="89587-125">For example, the package ID for the Microsoft Excel app is **com.microsoft.office.excel**.</span></span>
    - <span data-ttu-id="89587-126">テキスト ボックスに構成するアプリ設定のデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="89587-126">In the text box, enter the data for the app settings you want to configure.</span></span> <span data-ttu-id="89587-127">これらの設定は、アプリの提供元から入手します。</span><span class="sxs-lookup"><span data-stu-id="89587-127">You get these settings from the supplier of the app.</span></span> <span data-ttu-id="89587-128">これらの設定をサポートしていないアプリもあります。</span><span class="sxs-lookup"><span data-stu-id="89587-128">Not all apps support these settings.</span></span>
5.  <span data-ttu-id="89587-129">**[検証]** をクリックして、入力したデータが有効なプロパティ リスト形式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="89587-129">Click **Validate** to ensure that the data that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="89587-130">**[検証]** をクリックすると、Intune によって、入力した構成データが有効な形式であるかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="89587-130">When you click **Validate**, Intune checks that the configuration data you entered is in a valid format.</span></span> <span data-ttu-id="89587-131">データが関連付けられているアプリで動作するかどうかはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="89587-131">It does not check that the data will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="89587-132">終了したら、 **[ポリシーの保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89587-132">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="89587-133">新しいポリシーは、 **[構成ポリシー]** ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="89587-133">The new policy is displayed in the **Configuration Policies** node.</span></span>


## <a name="deploy-the-app-configuration-policy"></a><span data-ttu-id="89587-134">アプリ構成ポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="89587-134">Deploy the app configuration policy</span></span>
<span data-ttu-id="89587-135">モバイル アプリ構成ポリシーを作成したら、設定が適用されるアプリを展開するユーザーと同じユーザーにポリシーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89587-135">After you have created a mobile app configuration policy, you must deploy it to the same users to whom you deploy the app to which the settings will apply.</span></span>

<span data-ttu-id="89587-136">ポリシーを展開する方法の詳細については、「[構成ポリシーを展開する](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89587-136">For information about how to deploy policies, see [deploy a configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)</span></span>

<span data-ttu-id="89587-137">Android for Work デバイスにアプリを展開する方法については、「[How to deploy Android for Work apps with Intune](android-for-work-apps.md)」(Android for Work アプリを展開する方法) を参照してください</span><span class="sxs-lookup"><span data-stu-id="89587-137">For information about how to deploy apps to Android for Work devices, see [How to deploy Android for Work apps with Intune](android-for-work-apps.md).</span></span>

<span data-ttu-id="89587-138">展開したアプリをデバイスで実行すると、モバイル アプリ構成ポリシーで構成した設定を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="89587-138">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="89587-139">各ユーザーの各アプリには、1 つのアプリ構成ポリシーのみを展開します。</span><span class="sxs-lookup"><span data-stu-id="89587-139">Only deploy one app configuration policy for each app to a user.</span></span>
