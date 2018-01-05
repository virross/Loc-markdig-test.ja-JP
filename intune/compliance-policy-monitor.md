---
title: "Intune デバイスのコンプライアンス対応ポリシーの監視"
titlesuffix: Azure portal
description: "デバイスのコンプライアンス対応ポリシーを監視する方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b293ff41af58d4ab41a8477219939b13ffe361c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-intune-device-compliance-policies"></a><span data-ttu-id="5fe83-103">Intune デバイスのコンプライアンス対応ポリシーの監視</span><span class="sxs-lookup"><span data-stu-id="5fe83-103">Monitor Intune Device compliance policies</span></span>

<span data-ttu-id="5fe83-104">コンプライアンス対応レポートを使用すると、管理者は組織内のデバイスのコンプライアンス対応の状況を分析して、組織内のユーザーがコンプライアンス関連の問題に直面したときに迅速にトラブルシューティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-104">Compliance reports help admins to analyze the compliance posture of devices in their organization, and quickly troubleshoot compliance related issues encountered by users inside their organization.</span></span> <span data-ttu-id="5fe83-105">デバイスの総合的なコンプライアンスの状態、設定別のコンプライアンスの状態、およびポリシー別のコンプライアンスの状態に関する情報を表示し、個々のデバイスにドリルダウンして、デバイスに影響を与える特定の設定やポリシーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-105">You can view information about the overall compliance state of devices, compliance state for an individual setting, compliance state for an individual policy and drill down into individual devices to view specific settings and policies that affect the device.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5fe83-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="5fe83-106">Before you begin</span></span>

<span data-ttu-id="5fe83-107">次の手順に従って、Azure ポータルで **Intune Device compliance dashboard (Intune デバイス コンプライアンス ダッシュボード)** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-107">Follow the steps below to find the **Intune Device compliance dashboard** in the Azure portal:</span></span>

1.  <span data-ttu-id="5fe83-108">[Azure Portal](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="5fe83-108">Go to the [Azure Portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="5fe83-109">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5fe83-109">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="5fe83-110">**[Intune]** &gt; **[デバイスのポリシー準拠]** &gt; **[概要]** の順に選択すると、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** が開きます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-110">Choose **Intune** &gt; **Device compliance** &gt; **Overview**, then the **Device compliance dashboard** opens.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="5fe83-111">デバイスのコンプライアンス ポリシーを受け取るには、Intune にデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fe83-111">Devices must be enrolled into Intune to receive device compliance policies.</span></span>

## <a name="device-compliance-dashboard"></a><span data-ttu-id="5fe83-112">デバイス コンプライアンス ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="5fe83-112">Device compliance dashboard</span></span>

<span data-ttu-id="5fe83-113">**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で、デバイスのコンプライアンス ポリシーの状態を監視できます。このダッシュボードでは、組織内のデバイスのコンプライアンスの状況を表示するさまざまなタイル内で多数のレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-113">In the **Device compliance dashboard**, you can monitor the Device compliance policy states, which provides different reports within different tiles that give you the compliance posture of devices in your organization.</span></span> <span data-ttu-id="5fe83-114">表示できるレポートは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5fe83-114">You can view the following reports:</span></span>

-   <span data-ttu-id="5fe83-115">全体的なデバイスのコンプライアンス対応の集計</span><span class="sxs-lookup"><span data-stu-id="5fe83-115">Overall device compliance aggregate</span></span>

-   <span data-ttu-id="5fe83-116">ポリシーごとのデバイスのコンプライアンス対応</span><span class="sxs-lookup"><span data-stu-id="5fe83-116">Per-policy device compliance</span></span>

-   <span data-ttu-id="5fe83-117">設定ごとのデバイスのコンプライアンス対応</span><span class="sxs-lookup"><span data-stu-id="5fe83-117">Per-setting device compliance</span></span>

![デバイス コンプライアンス ダッシュボード](./media/idc-1.png)

<span data-ttu-id="5fe83-119">また、個々のデバイスに適用される特定のコンプライアンス ポリシーおよび設定や、デバイスのこれらの設定ごとのコンプライアンスの最終状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-119">You can also view the specific compliance policies and settings that apply to an individual device, and the final compliance state for each of those settings on the device.</span></span>

### <a name="overall-device-compliance-aggregate-report"></a><span data-ttu-id="5fe83-120">全体的なデバイスのコンプライアンス対応集計レポート</span><span class="sxs-lookup"><span data-stu-id="5fe83-120">Overall device compliance aggregate report</span></span>

<span data-ttu-id="5fe83-121">Intune に登録されたすべてのデバイスの集約されたコンプライアンス対応状態を示すドーナツ グラフです。</span><span class="sxs-lookup"><span data-stu-id="5fe83-121">It’s a donut chart showing the aggregate compliance state for all Intune enrolled devices.</span></span> <span data-ttu-id="5fe83-122">デバイスのコンプライアンス対応状態は、Intune と Azure Active Directory の 2 つの異なるデータベースで保持されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-122">The device compliance states are kept in two different databases, Intune and Azure Active Directory.</span></span> <span data-ttu-id="5fe83-123">デバイスのコンプライアンス対応ポリシーの詳細は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5fe83-123">Here’s more details about the device compliance policy states:</span></span>

-   <span data-ttu-id="5fe83-124">**準拠**: デバイスに管理者が適用対象とするデバイス コンプライアンス ポリシーが 1 つ以上適切に適用されています。</span><span class="sxs-lookup"><span data-stu-id="5fe83-124">**Compliant**: The device successfully applied one or more device compliance policy settings targeted by the admin.</span></span>

-   <span data-ttu-id="5fe83-125">**非準拠:** 管理者またはユーザーが適用対象とするデバイス コンプライアンス ポリシーの設定の 1 つ以上の適用に失敗し、管理者が適用対象とするポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="5fe83-125">**Not-compliant:** The device failed to apply one or more device compliance policy settings targeted by the admin or the user hasn’t complied with the policies targeted by the admin.</span></span>

-   <span data-ttu-id="5fe83-126">**猶予期間:** デバイスは 1 つ以上のデバイス コンプライアンス ポリシー設定を持つことを管理者によって指定されているものの、ユーザーがまだポリシーを適用していないことを示します。つまり、デバイスは非準拠ですが、管理者が定義した猶予期間にあります。</span><span class="sxs-lookup"><span data-stu-id="5fe83-126">**In-grace period:** The device was targeted by the admin with one or more device compliance policy settings, but the user hasn’t applied the policies yet, which means the device is not-compliant, but it’s in the grace-period defined by the admin.</span></span>

    -   <span data-ttu-id="5fe83-127">コンプライアンス非対応のデバイスのアクションの詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5fe83-127">Learn more about Actions for non-compliant devices.</span></span>

-   <span data-ttu-id="5fe83-128">**同期されていないデバイス:** 次のいずれかの理由により、デバイスがデバイス コンプライアンス ポリシーの状態の報告に失敗しています。</span><span class="sxs-lookup"><span data-stu-id="5fe83-128">**Device not synced:** The device failed to report its device compliance policy status because one of the following:</span></span>

    -   <span data-ttu-id="5fe83-129">**不明**: デバイスが何らかの理由でオフラインか、Intune または Azure AD との通信に失敗しています。</span><span class="sxs-lookup"><span data-stu-id="5fe83-129">**Unknown**: The device is offline or failed to communicate with Intune or Azure AD for other reasons.</span></span>

    -   <span data-ttu-id="5fe83-130">**エラー**: デバイスが Intune および Azure AD との通信に失敗し、何らかの理由でエラー メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="5fe83-130">**Error**: The device failed to communicate with Intune and Azure AD, and received an error message with the reason.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="5fe83-131">Intune に登録されていないが、デバイス コンプライアンス ポリシーの適用対象となっているデバイスは、**[準拠]** バケットでこのレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-131">Devices that are enrolled into Intune, but not targeted by any device compliance policies will be included in this report under the **Compliant** bucket.</span></span>

#### <a name="drill-down-option"></a><span data-ttu-id="5fe83-132">ドリルダウン オプション</span><span class="sxs-lookup"><span data-stu-id="5fe83-132">Drill-down option</span></span>

<span data-ttu-id="5fe83-133">**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で、[デバイスのポリシー準拠] タイルをクリックして、デバイス コンプライアンス ポリシーの対象となっている各デバイスの特定の**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-133">From the **Device compliance dashboard**, If you click on the Device compliance tile, you can drill-down into a specific **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by the device compliance policies.</span></span>

![デバイス コンプライアンス ダッシュボードでのドリルダウン](./media/idc-2.png)

<span data-ttu-id="5fe83-135">特定のユーザーの詳細情報が必要な場合は、ユーザーの電子メール エイリアスを入力して、デバイスのポリシー準拠チャート レポートをフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-135">If you need more details about a specific user, you can filter the Device compliance chart report by typing the user’s e-mail alias.</span></span>

![デバイス コンプライアンス ダッシュボードの特定のユーザー](./media/idc-3.png)

<span data-ttu-id="5fe83-137">また、デバイスのポリシー準拠チャートでさまざまなコンプライアンス対応状態をクリックして、ユーザーのデバイス コンプライアンス ポリシー状態の詳細を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-137">You can also click the different compliance status on the Device compliance chart to see more details about the user’s devices compliance policy statuses.</span></span>

![デバイス コンプライアンス ダッシュボードのさまざまな状態](./media/idc-4.png)

#### <a name="filter"></a><span data-ttu-id="5fe83-139">フィルター</span><span class="sxs-lookup"><span data-stu-id="5fe83-139">Filter</span></span>

<span data-ttu-id="5fe83-140">**[フィルター]** ボタンをクリックすると、次のオプションを示すフィルターのフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-140">If you click on **Filter button**, the filter fly-out opens with the following options:</span></span>

-   <span data-ttu-id="5fe83-141">モデル</span><span class="sxs-lookup"><span data-stu-id="5fe83-141">Model</span></span>

    -   <span data-ttu-id="5fe83-142">テキストボックスで文字列を無料で検索できます</span><span class="sxs-lookup"><span data-stu-id="5fe83-142">Textbox accepting free search string</span></span>
<br></br>
-   <span data-ttu-id="5fe83-143">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="5fe83-143">Platform</span></span>

    -   <span data-ttu-id="5fe83-144">Android</span><span class="sxs-lookup"><span data-stu-id="5fe83-144">Android</span></span>

    -   <span data-ttu-id="5fe83-145">iOS</span><span class="sxs-lookup"><span data-stu-id="5fe83-145">iOS</span></span>

    -   <span data-ttu-id="5fe83-146">Mac OS</span><span class="sxs-lookup"><span data-stu-id="5fe83-146">Mac OS</span></span>

    -   <span data-ttu-id="5fe83-147">Windows</span><span class="sxs-lookup"><span data-stu-id="5fe83-147">Windows</span></span>

    -   <span data-ttu-id="5fe83-148">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="5fe83-148">Windows Phone</span></span>

-   <span data-ttu-id="5fe83-149">状態</span><span class="sxs-lookup"><span data-stu-id="5fe83-149">Status</span></span>

    -   <span data-ttu-id="5fe83-150">準拠</span><span class="sxs-lookup"><span data-stu-id="5fe83-150">Compliant</span></span>

    -   <span data-ttu-id="5fe83-151">非準拠</span><span class="sxs-lookup"><span data-stu-id="5fe83-151">Not Compliant</span></span>

    -   <span data-ttu-id="5fe83-152">猶予時間中</span><span class="sxs-lookup"><span data-stu-id="5fe83-152">In Grace period</span></span>

    -   <span data-ttu-id="5fe83-153">Unknown</span><span class="sxs-lookup"><span data-stu-id="5fe83-153">Unknown</span></span>

    -   <span data-ttu-id="5fe83-154">エラー</span><span class="sxs-lookup"><span data-stu-id="5fe83-154">Error</span></span>

<span data-ttu-id="5fe83-155">**[更新]** ボタンをクリックすると、フライアウトが閉じ、選択したフィルター条件に従って結果が更新されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-155">If clicking the **Update button**, the fly out should close and the results should update as per the selected filter criteria.</span></span>

##### <a name="device-details"></a><span data-ttu-id="5fe83-156">デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="5fe83-156">Device details</span></span>

<span data-ttu-id="5fe83-157">デバイスをクリックすると、選択したデバイスで**デバイス ブレード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-157">Clicking on a device, opens the **Devices Blade** with the device selected.</span></span> <span data-ttu-id="5fe83-158">ここに、そのデバイスに適用されているデバイス コンプライアンス ポリシー設定の詳細が示されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-158">This provides more details on the device compliance policy setting applied for that device.</span></span>

![デバイス コンプライアンス ダッシュボード](./media/idc-6.png)

<span data-ttu-id="5fe83-160">デバイス ポリシーの設定自体をクリックすると、管理者が適用対象にしたデバイス コンプライアンス設定で指定されたデバイス コンプライアンス ポリシー名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-160">When you click on the device policy setting itself, you can see the device compliance policy name originated that device compliance setting targeted by the admin.</span></span>

![デバイス コンプライアンス設定の名前](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a><span data-ttu-id="5fe83-162">ポリシーごとのデバイスのコンプライアンス対応レポート</span><span class="sxs-lookup"><span data-stu-id="5fe83-162">Per-policy device compliance report</span></span>

<span data-ttu-id="5fe83-163">このレポートは、コンプライアンス ポリシー ビューごとに、各コンプライアンス対応状態のデバイスの合計数を示します。</span><span class="sxs-lookup"><span data-stu-id="5fe83-163">This report provides you per compliance policy view and the total number of devices in each compliance state.</span></span> <span data-ttu-id="5fe83-164">**[Policy compliance (ポリシー準拠)]** タイルは、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で利用でき、管理者が以前に作成したすべてのポリシー、ポリシーが適用されているプラットフォーム、準拠デバイスの数、および非準拠デバイスの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-164">The **Policy compliance** title is available from the **Device compliance dashboard**, and it shows all policies previously created by the admin, the platforms the policy is applied, number of compliant devices and number of non-compliant devices.</span></span>

![ポリシーごとのデバイスのコンプライアンス対応レポート](./media/idc-8.png)

<span data-ttu-id="5fe83-166">[Policy compliance (ポリシー準拠)] タイルをクリックし、いずれかのデバイス コンプライアンス ポリシーをクリックすると、そのデバイス コンプライアンス ポリシーの対象にした各デバイスの**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-166">When you click on the Policy compliance tile, then click on one of the device compliance policies, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy.</span></span>

![[Policy compliance (ポリシー準拠)] タイル](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a><span data-ttu-id="5fe83-168">設定ごとのデバイスのコンプライアンス対応レポート</span><span class="sxs-lookup"><span data-stu-id="5fe83-168">Per-setting device compliance report</span></span>

<span data-ttu-id="5fe83-169">このレポートでは、コンプライアンス設定ごとの、各コンプライアンス対応状態のデバイスの合計数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-169">This report allows you to view, per compliance setting, the total number of devices in each compliance state.</span></span> <span data-ttu-id="5fe83-170">**[設定コンプライアンス]** タイルは、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で利用でき、管理者が以前に作成したすべてのデバイス コンプライアンス ポリシーのすべてのデバイス コンプライアンス ポリシー設定、ポリシー設定が適用されたプラットフォーム、および非準拠デバイスの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-170">The **Settings compliance** title is available from the **Device compliance dashboard**, and it shows all device compliance policy settings from all device compliance policies created by the admin, the platforms which the policy settings were applied, and the number of non-compliant devices.</span></span>

![設定ごとのデバイスのコンプライアンス対応レポート](./media/idc-10.png)

<span data-ttu-id="5fe83-172">[コンプライアンスの設定] タイルをクリックし、いずれかのデバイス コンプライアンス ポリシー設定をクリックすると、そのデバイス コンプライアンス ポリシー設定の対象にした各デバイスの**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5fe83-172">When you click on the Setting compliance tile, then click on one of the device compliance policy settings, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy setting.</span></span>

![[コンプライアンスの設定] タイル](./media/idc-11.png)
