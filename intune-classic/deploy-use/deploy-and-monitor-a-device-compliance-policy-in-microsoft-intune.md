---
title: "コンプライアンス ポリシーを展開して監視する"
description: "このトピックのステップ バイ ステップの指示は、デバイスのコンプライアンス ポリシーを展開して監視するために使用します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0458560ed2667da08d1b59b813f1fb973c2ee4cd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a><span data-ttu-id="42898-103">Microsoft Intune でデバイスのコンプライアンス ポリシーを展開して監視する</span><span class="sxs-lookup"><span data-stu-id="42898-103">Deploy and monitor a device compliance policy in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a><span data-ttu-id="42898-104">コンプライアンス ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="42898-104">Deploy a compliance policy</span></span>
<span data-ttu-id="42898-105">[こちらの手順で作成した](create-a-device-compliance-policy-in-microsoft-intune.md)コンプライアンス ポリシーを、組織内のユーザーの 1 つ以上のグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="42898-105">Deploy the compliance policy that you [created](create-a-device-compliance-policy-in-microsoft-intune.md) to one or more groups of users in your organization.</span></span> <span data-ttu-id="42898-106">コンプライアンス ポリシーがユーザーに展開されると、ユーザーのデバイスのコンプライアンスがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="42898-106">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span>

1.  <span data-ttu-id="42898-107">**[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="42898-107">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
<span data-ttu-id="42898-108">![上部に [展開の管理] メニュー オプションが表示されているコンプライアンス ポリシー ページのスクリーンショット](./media/intune-sa-3c-deploy-compliance-policy2.png)</span><span class="sxs-lookup"><span data-stu-id="42898-108">![Screenshot of the compliance policy page showing the Manage Deployment menu option at the top](./media/intune-sa-3c-deploy-compliance-policy2.png)</span></span>

2.  <span data-ttu-id="42898-109">**[展開の管理]** ダイアログ ボックスで、ポリシーを展開するグループを 1 つ以上選択し、**[追加]** > **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="42898-109">In the **Manage Deployment** dialog box, choose one or more groups to which you want to deploy the policy, and then choose **Add** > **OK**.</span></span>
<span data-ttu-id="42898-110">![[展開の管理] ダイアログ ボックスのスクリーン ショット](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) 既に作成され、Intune と同期している Active Directory グループを使用するか、これらのグループを Intune コンソールで手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="42898-110">![Screenshot of the Manage Deployment dialog box](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Use Active Directory groups that you have already created and synced to Intune, or create these groups manually in the Intune console.</span></span> <span data-ttu-id="42898-111">ポリシーを展開する方法の詳細については、「[構成ポリシーを展開する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42898-111">To learn more about how to deploy policies, see [Deploy a configuration policy](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

<span data-ttu-id="42898-112">**[ポリシー]** ワークスペースの **[概要]** ページに表示されるステータスの概要とアラートを使用すると、注意が必要なポリシーの問題を識別できます。</span><span class="sxs-lookup"><span data-stu-id="42898-112">Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify problems with the policy that need your attention.</span></span> <span data-ttu-id="42898-113">ステータスの概要は **[ダッシュボード]** ワークスペースにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="42898-113">Additionally, a status summary appears in the **Dashboard** workspace.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42898-114">コンプライアンス ポリシーを展開していない状態で、Exchange 条件付きアクセス ポリシーを有効にすると、すべての対象デバイスからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="42898-114">If you have not deployed a compliance policy and you enable an Exchange conditional access policy, all targeted devices will have access.</span></span>

## <a name="monitor-the-compliance-policy"></a><span data-ttu-id="42898-115">コンプライアンス ポリシーの監視</span><span class="sxs-lookup"><span data-stu-id="42898-115">Monitor the compliance policy</span></span>

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a><span data-ttu-id="42898-116">コンプライアンス ポリシーに準拠していないデバイスを表示するには</span><span class="sxs-lookup"><span data-stu-id="42898-116">To view devices that do not conform to a compliance policy</span></span>

1.  <span data-ttu-id="42898-117">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[グループ]** > **[すべてのデバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="42898-117">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** > **All Devices**.</span></span>

2.  <span data-ttu-id="42898-118">デバイスの一覧内のデバイスの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="42898-118">Double-click the name of a device in the list of devices.</span></span>

3.  <span data-ttu-id="42898-119">**[ポリシー]** タブを選び、そのデバイスのポリシーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="42898-119">Choose the **Policy** tab to see a list of the policies for that device.</span></span>

4.  <span data-ttu-id="42898-120">**[フィルター]** ドロップダウン リストから **[コンプライアンス ポリシーに準拠しない]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="42898-120">From the **Filters** drop-down list, choose **Does not conform to compliance policy**.</span></span>
<span data-ttu-id="42898-121">![フィルター リストのオプション リストを示すスクリーンショット](./media/intune-sa-3e-view-device-noncompliance.png)</span><span class="sxs-lookup"><span data-stu-id="42898-121">![Screenshot that shows the list of options in the filters list](./media/intune-sa-3e-view-device-noncompliance.png)</span></span>

#### <a name="to-view-the-health-attestation-reports"></a><span data-ttu-id="42898-122">正常性構成証明書レポートを表示するには</span><span class="sxs-lookup"><span data-stu-id="42898-122">To view the health attestation reports</span></span>

1.  <span data-ttu-id="42898-123">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[レポート]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="42898-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Reports**.</span></span>

2.  <span data-ttu-id="42898-124">**[正常性構成証明書レポート - レポートの新規作成]** ページで、Intune によって収集されたすべての Windows 10 正常性構成証明書データを含むレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="42898-124">On the **Health Attestation Report - Create a new report** page, you can view a report with all the Windows 10 health attestation data that Intune has collected.</span></span> <span data-ttu-id="42898-125">フィルターを使用して、データのサブセットを含むレポートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="42898-125">You can also create a report with a subset of the data by using filters.</span></span> <span data-ttu-id="42898-126">フィルターは、デバイスの種類、オペレーティング システム、またはデータ ポイントのサブセットのみに基づいて設定できます。</span><span class="sxs-lookup"><span data-stu-id="42898-126">The filters can be based on the type of device, the operating system, or only a subset of data points.</span></span>

## <a name="how-intune-resolves-policy-conflicts"></a><span data-ttu-id="42898-127">Intune のポリシー競合の解決方法</span><span class="sxs-lookup"><span data-stu-id="42898-127">How Intune resolves policy conflicts</span></span>
<span data-ttu-id="42898-128">複数の Intune ポリシーを 1 つのデバイスに適用すると、ポリシーの競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42898-128">Policy conflicts can occur when multiple Intune policies are applied to a device.</span></span> <span data-ttu-id="42898-129">ポリシーの設定が重複した場合、Intune では次のルールを使用して競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="42898-129">If the policy settings overlap, Intune resolves any conflicts by using the following rules:</span></span>

-   <span data-ttu-id="42898-130">Intune の構成ポリシーと準拠ポリシーの設定が競合している場合は、構成ポリシーの設定よりも準拠ポリシーの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="42898-130">If the conflicting settings are from an Intune configuration policy and a compliance policy, the settings in the compliance policy take precedence over the settings in the configuration policy.</span></span> <span data-ttu-id="42898-131">構成ポリシーの設定の方が安全性が高い場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="42898-131">This happens even if the settings in the configuration policy are more secure.</span></span>

-   <span data-ttu-id="42898-132">複数の準拠ポリシーを展開した場合、Intune ではその中で最も安全なポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="42898-132">If you have deployed multiple compliance policies, Intune will use the most secure of these policies.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42898-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="42898-133">Next steps</span></span>
<span data-ttu-id="42898-134">条件付きアクセス ポリシーと共にコンプライアンス ポリシーを使用して、組織内のサービスへのアクセスを制御する方法については、「[電子メールと O365 サービスへのアクセスを制限する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42898-134">To learn how to use the compliance policy with conditional access policies to control access to services in your organization, see [Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span>


### <a name="see-also"></a><span data-ttu-id="42898-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="42898-135">See also</span></span>
[<span data-ttu-id="42898-136">Intune でのデバイス コンプライアンス ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="42898-136">Introduction to device compliance polices in Intune</span></span>](introduction-to-device-compliance-policies-in-microsoft-intune.md)
