---
title: "Intune で Mobile Threat Defense デバイス コンプライアンス ポリシーを作成する"
titlesuffix: Azure portal
description: "Intune で Mobile Threat Defense デバイス コンプライアンス ポリシーを作成する"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e9b1a3dc42a9c18d61fc9b55d5a7b71f00c3e29
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a><span data-ttu-id="78254-103">Intune で Mobile Threat Defense (MTD) デバイス コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="78254-103">Create Mobile Threat Defense (MTD) device compliance policy with Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="78254-104">このトピックは、すべての Mobile Threat Defense パートナーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="78254-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="78254-105">Intune で MTD を使用すると、モバイル デバイス上で脅威を検出し、リスクを評価できます。</span><span class="sxs-lookup"><span data-stu-id="78254-105">Intune with MTD helps you detect threats and assess risk on mobile devices.</span></span> <span data-ttu-id="78254-106">リスクを評価する Intune デバイス コンプライアンス ポリシー ルールを作成すれば、デバイスがポリシーに準拠しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="78254-106">You can create an Intune device compliance policy rule that assesses risk to determine if the device is compliant or not.</span></span> <span data-ttu-id="78254-107">さらに、条件付きアクセス ポリシーを使用することで、デバイスのコンプライアンスに基づいて、サービスへのアクセスを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="78254-107">You can then use a conditional access policy to block access to services based on device compliance.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="78254-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="78254-108">Before you begin</span></span>

<span data-ttu-id="78254-109">MTD の設定の一部として、MTD パートナー コンソールで、さまざまな脅威を高、中、低として分類するポリシーを作成しておきます。</span><span class="sxs-lookup"><span data-stu-id="78254-109">As part of the MTD setup, in the MTD partner console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="78254-110">これにより、Intune デバイス コンプライアンス ポリシーに Mobile Threat Defense レベルを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78254-110">You now need to set the Mobile Threat Defense level in the Intune device compliance policy.</span></span>

<span data-ttu-id="78254-111">MTD でのデバイス コンプライアンス ポリシーの前提条件:</span><span class="sxs-lookup"><span data-stu-id="78254-111">Prerequisites for device compliance policy with MTD:</span></span>

-   <span data-ttu-id="78254-112">MTD と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="78254-112">Set up MTD integration with Intune</span></span>

## <a name="to-create-a-mtd-device-compliance-policy"></a><span data-ttu-id="78254-113">MTD デバイス コンプライアンス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="78254-113">To create a MTD device compliance policy</span></span>

1.  <span data-ttu-id="78254-114">[Azure Portal](https://portal.azure.com/) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="78254-114">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="78254-115">**Azure ダッシュボード**で、左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="78254-115">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="78254-116">**[Intune]** を選択すると、**Intune ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="78254-116">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="78254-117">**Intune ダッシュ ボード**で、**[デバイスのポリシー準拠]** を選択し、**[管理]** セクションで **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-117">On the **Intune Dashboard**, choose **Device compliance**, then choose **Policies** under the **Manage** section.</span></span>

5.  <span data-ttu-id="78254-118">**[Create policy]\(ポリシーの作成\)** を選択し、デバイス コンプライアンスの **[名前]**、**[説明]** を入力し、 **[プラットフォーム]** を選択してから **[設定]** セクションの **[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-118">Choose **Create policy**, enter the device compliance **Name**, **Description**, select the **Platform**, then choose **Configure** under the **Settings** section.</span></span>

6.  <span data-ttu-id="78254-119">**[コンプライアンス ポリシー]** ブレードで、**[Device Health]\(デバイスの正常性\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-119">On the **compliance policy** blade, choose **Device Health**.</span></span>

7.  <span data-ttu-id="78254-120">**[Device Health]\(デバイスの正常性\)** ブレードの、**[Require the device to be at or under the Mobile threat Defense Level]\(デバイスが Mobile Threat Defense レベル以下であることが必要)** の下で Mobile Threat レベルをドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-120">On the **Device Health** blade, choose the Mobile Threat Level from the drop-down list under the **Require the device to be at or under the Mobile threat Defense Level**.</span></span>

    <span data-ttu-id="78254-121">a.</span><span class="sxs-lookup"><span data-stu-id="78254-121">a.</span></span>  <span data-ttu-id="78254-122">**[セキュリティ保護]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="78254-122">**Secured**: This is the most secure.</span></span> <span data-ttu-id="78254-123">デバイスにいかなる脅威も存在できず、デバイスからは引き続き会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="78254-123">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="78254-124">いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="78254-124">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="78254-125">b.</span><span class="sxs-lookup"><span data-stu-id="78254-125">b.</span></span>  <span data-ttu-id="78254-126">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="78254-126">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="78254-127">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="78254-127">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="78254-128">c.</span><span class="sxs-lookup"><span data-stu-id="78254-128">c.</span></span>  <span data-ttu-id="78254-129">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="78254-129">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="78254-130">高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="78254-130">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="78254-131">d.</span><span class="sxs-lookup"><span data-stu-id="78254-131">d.</span></span>  <span data-ttu-id="78254-132">**[High]** (高): 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="78254-132">**High**: This is the least secure.</span></span> <span data-ttu-id="78254-133">この場合、すべての脅威レベルが許可され、レポート目的のみで Mobile Threat Defense が使用されます。</span><span class="sxs-lookup"><span data-stu-id="78254-133">This allows all threat levels, and uses Mobile Threat Defense for reporting purposes only.</span></span> <span data-ttu-id="78254-134">デバイスには、この設定でアクティブ化された MTD アプリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78254-134">Devices are required to have the MTD app activated with this setting.</span></span>

8.  <span data-ttu-id="78254-135">**[OK]** を 2 回クリックしてから、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-135">Click **OK** twice, then choose **Create**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78254-136">Office 365 またはその他のサービスに対する条件付きアクセス ポリシーを作成すると、デバイス コンプライアンス評価が適用され、非準拠デバイスはデバイスで脅威が解決されるまで会社のリソースへのアクセスは禁止されます。</span><span class="sxs-lookup"><span data-stu-id="78254-136">If you create conditional access policies for Office 365 or other services, the device compliance evaluation is assessed and non-compliant devices are blocked from accessing corporate resources until the threat is resolved in the device.</span></span>

## <a name="to-assign-a-mtd-device-compliance-policy"></a><span data-ttu-id="78254-137">MTD デバイス コンプライアンス ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="78254-137">To assign a MTD device compliance policy</span></span>

<span data-ttu-id="78254-138">デバイス コンプライアンス ポリシーをユーザーに割り当てるには、前に構成したポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-138">To assign a device compliance policy to users, choose a policy that you have previously configured.</span></span> <span data-ttu-id="78254-139">既存のポリシーは、**[デバイス コンプライアンス ポリシー]** ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78254-139">Existing policies can be found in the **Device Compliance policies** blade.</span></span>

1. <span data-ttu-id="78254-140">ユーザーに割り当てるポリシーを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78254-140">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="78254-141">これにより表示されたブレードで、**[Azure Active Directory セキュリティ グループ]** を選択し、ポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="78254-141">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>

2. <span data-ttu-id="78254-142">**[グループの選択]** を選択すると、ブレードが開き、Azure AD セキュリティ グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78254-142">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="78254-143">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="78254-143">Choosing **Select**  deploys the policy to users.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="78254-144">ポリシーがユーザーに適用されました。</span><span class="sxs-lookup"><span data-stu-id="78254-144">You have applied the policy to users.</span></span> <span data-ttu-id="78254-145">ポリシーの対象となっているユーザーが使用しているデバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="78254-145">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78254-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="78254-146">Next steps</span></span>

- [<span data-ttu-id="78254-147">Intune で MTD を有効にする</span><span class="sxs-lookup"><span data-stu-id="78254-147">Enable MTD with Intune</span></span>](mtd-connector-enable.md)