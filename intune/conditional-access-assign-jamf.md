---
title: "Jamf 管理されたデバイスにコンプライアンス ポリシーを適用します。"
titlesuffix: Azure portal
description: "コンプライアンスを Jamf で管理されたデバイスのセキュリティ保護に役立てます。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c72de87b87775155672994163140e342b7ba99b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a><span data-ttu-id="c9c89-103">Jamf Pro で管理された Mac にコンプライアンスを適用します</span><span class="sxs-lookup"><span data-stu-id="c9c89-103">Enforce compliance on Macs managed with Jamf Pro</span></span>

|<span data-ttu-id="c9c89-104">適用先: Azure Portal での Intune</span><span class="sxs-lookup"><span data-stu-id="c9c89-104">Applies to: Intune in the Azure portal</span></span> |
|--|
|<span data-ttu-id="c9c89-105">クラシック ポータルで Intune に関するドキュメントをお探しですか。</span><span class="sxs-lookup"><span data-stu-id="c9c89-105">Looking for documentation about Intune in the classic portal?</span></span> <span data-ttu-id="c9c89-106">[こちらを検索してください](/intune/introduction-intune?toc=/intune-classic/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="c9c89-106">[Go here](/intune/introduction-intune?toc=/intune-classic/toc.json).</span></span>|
| |

<span data-ttu-id="c9c89-107">Azure Active Directory および Microsoft Intune の条件付きアクセス ポリシーを使用して、エンド ユーザーが組織の要件に準拠することを確実にできます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-107">You can use Azure Active Directory and Microsoft Intune's conditional access policies ensure that your end users are compliant with organizational requirements.</span></span> <span data-ttu-id="c9c89-108">これらのポリシーは [Jamf Pro で管理されている](conditional-access-integrate-jamf.md) Mac に適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-108">You can apply these policies to Macs that are [managed with Jamf Pro](conditional-access-integrate-jamf.md).</span></span> <span data-ttu-id="c9c89-109">これには、Intune と Jamf Pro の両方のコンソールへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9c89-109">This requires access to both the Intune and Jamf Pro consoles.</span></span>

## <a name="set-up-device-compliance-policies-in-intune"></a><span data-ttu-id="c9c89-110">Intune のデバイス コンプライアンス ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c9c89-110">Set up device compliance policies in Intune</span></span>

1. <span data-ttu-id="c9c89-111">Microsoft Azure を開き、**[Intune]** > **[デバイスのポリシー準拠]** > **[ポリシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-111">Open Microsoft Azure, then navigate to **Intune** > **Device Compliance** > **Policies**.</span></span> <span data-ttu-id="c9c89-112">準拠していないユーザーとグループに対する一連のアクション (警告の電子メールの送信など) の選択を含む、macOS 用のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-112">You can create policies for macOS, including choosing a series of actions (e.g., sending warning emails) to noncompliant users and groups.</span></span>
2. <span data-ttu-id="c9c89-113">目的のグループを検索し、それらにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-113">Search for your desired groups, then apply the policies to them.</span></span>

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a><span data-ttu-id="c9c89-114">macOS 用ポータル サイト アプリを Jamf Pro に展開する</span><span class="sxs-lookup"><span data-stu-id="c9c89-114">Deploy the Company Portal app for macOS in Jamf Pro</span></span>

<span data-ttu-id="c9c89-115">以下の手順に従って、macOS 用ポータル サイト アプリをバックグラウンドのインストールとして Jamf Pro に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9c89-115">You should deploy the Company Portal app for macOS in Jamf Pro as a background installation following the procedure below:</span></span>

1. <span data-ttu-id="c9c89-116">macOS デバイスで、[macOS 用のポータル サイト アプリ](https://go.microsoft.com/fwlink/?linkid=862280)の現在のバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-116">On a macOS device, download the current version of the [Company Portal app for macOS](https://go.microsoft.com/fwlink/?linkid=862280).</span></span> <span data-ttu-id="c9c89-117">インストールはしないでください。Jamf Pro にアップロードするには、アプリのコピーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9c89-117">Do not install it; you need a copy of the app to upload to Jamf Pro.</span></span>
2. <span data-ttu-id="c9c89-118">Jamf Pro を開き、**[コンピューターの管理]** > **[パッケージ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-118">Open Jamf Pro, then navigate to **Computer management** > **Packages**.</span></span>
3. <span data-ttu-id="c9c89-119">macOS 用のポータル サイト アプリで新しいパッケージを作成し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-119">Create a new package with the Company Portal app for macOS, then click **Save**.</span></span>
4. <span data-ttu-id="c9c89-120">**[コンピューター]** > **[ポリシー]** を開き、**[新規]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-120">Open **Computers** > **Policies**, then select **New**.</span></span>
5. <span data-ttu-id="c9c89-121">**[全般]** ペイロードを使用して、ポリシーの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-121">Use the **General** payload to configure settings for the policy.</span></span> <span data-ttu-id="c9c89-122">これらの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9c89-122">These settings should be:</span></span>
   - <span data-ttu-id="c9c89-123">トリガー: **[登録完了]** と **[Recurring Check-in]\(定期的なチェックイン\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-123">Trigger: select **Enrollment Complete** and **Recurring Check-in**</span></span>
   - <span data-ttu-id="c9c89-124">実行の頻度: **[Once per computer]\(コンピューターにつき 1 回\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-124">Execution Frequency: select **Once per computer**</span></span>
6. <span data-ttu-id="c9c89-125">**[パッケージ]** ペイロードを選択し、**[構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-125">Select the **Packages** payload and click **Configure**.</span></span>
7. <span data-ttu-id="c9c89-126">**[追加]** をクリックし、ポータル サイト アプリでパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-126">Click **Add** to select the package with the Company Portal app.</span></span>
8. <span data-ttu-id="c9c89-127">**[アクション]** ポップアップ メニューから **[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-127">Choose **Install** from the **Action** pop-up menu.</span></span>
9. <span data-ttu-id="c9c89-128">パッケージの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-128">Configure the settings for the package.</span></span>
10. <span data-ttu-id="c9c89-129">**[スコープ]** タブをクリックし、ポータル サイト アプリをインストールするコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-129">Click the **Scope** tab to specify on which computers the Company Portal app should be installed.</span></span> <span data-ttu-id="c9c89-130">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-130">Click **Save**.</span></span> <span data-ttu-id="c9c89-131">ポリシーは、次回、選択したトリガーがコンピューターで発生し、**[全般]** ペイロードの条件を満たしている場合にスコープのデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-131">The policy will run scoped devices the next time the selected trigger occurs on the computer and meets the criteria in the **General** payload.</span></span>

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a><span data-ttu-id="c9c89-132">ユーザーに Azure Active Directory で自分のデバイスを登録させるためのポリシーを Jamf Pro で作成する</span><span class="sxs-lookup"><span data-stu-id="c9c89-132">Create a policy in Jamf Pro to have users register their devices with Azure Active Directory</span></span>

> [!NOTE]
> <span data-ttu-id="c9c89-133">次の手順に進む前に、macOS 用の[ポータル サイトの展開](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos)を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9c89-133">You need to [deploy the Company Portal](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) for macOS before going through the next steps.</span></span>  

<span data-ttu-id="c9c89-134">エンドユーザーは、デバイスを Jamf Pro によって管理されるデバイスとして Azure AD で登録するために、Jamf セルフ サービスを経由してポータル サイト アプリを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9c89-134">End users need to launch the Company Portal app through Jamf Self Service to register the device with Azure AD as a device managed by Jamf Pro.</span></span> <span data-ttu-id="c9c89-135">この場合、エンドユーザーは操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9c89-135">This will require your end users to take action.</span></span> <span data-ttu-id="c9c89-136">電子メール、Jamf Pro 通知、またはエンドユーザーへの他の通知方法を通して、Jamf セルフ サービスでボタンをクリックするように[エンド ユーザーに連絡する](end-user-educate.md)ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-136">We recommend that you [contact your end user](end-user-educate.md) through email, Jamf Pro notifications, or any other methods of notifying your end users to click the button in Jamf Self Service.</span></span>

> [!WARNING]
> <span data-ttu-id="c9c89-137">ポータル サイト アプリを Jamf セルフ サービスから起動してデバイスの登録を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9c89-137">The Company Portal app must be launched from Jamf Self Service to begin device registration.</span></span> <br><br><span data-ttu-id="c9c89-138">ポータル サイト アプリを手動で起動した場合 (たとえば、アプリケーション フォルダーまたはダウンロード フォルダーから起動)、デバイスは登録されません。</span><span class="sxs-lookup"><span data-stu-id="c9c89-138">Launching the Company Portal app manually (e.g., from the Applications or Downloads folders) will not register the device.</span></span> <span data-ttu-id="c9c89-139">エンドユーザーがポータル サイトを手動で起動した場合は、"AccountNotOnboarded" という警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-139">If an end user launches the Company Portal manually, they will see a warning, 'AccountNotOnboarded'.</span></span>

1. <span data-ttu-id="c9c89-140">Jamf Pro で **[コンピューター]** > **[ポリシー]** に移動し、デバイス登録用の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-140">In Jamf Pro, navigate to **Computers** > **Policies**, and create a new policy for device registration.</span></span>
2. <span data-ttu-id="c9c89-141">トリガーや実行の頻度など、**[Microsoft Intune 統合]** ペイロードを構成します。</span><span class="sxs-lookup"><span data-stu-id="c9c89-141">Configure the **Microsoft Intune Integration** payload, including the trigger and execution frequency.</span></span>
3. <span data-ttu-id="c9c89-142">**[スコープ]** タブをクリックし、ポリシーのスコープをすべての対象デバイスにします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-142">Click the **Scope** tab, and scope the policy to all targeted devices.</span></span>
4. <span data-ttu-id="c9c89-143">**[セルフ サービス]** タブをクリックし、Jamf セルフ サービスでポリシーを利用可能にします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-143">Click the **Self Service** tab to make the policy available in Jamf Self Service.</span></span> <span data-ttu-id="c9c89-144">ポリシーを **[デバイスのポリシー準拠]** カテゴリに含めます。</span><span class="sxs-lookup"><span data-stu-id="c9c89-144">Include the policy in the **Device Compliance** category.</span></span> <span data-ttu-id="c9c89-145">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9c89-145">Click **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9c89-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c9c89-146">Next steps</span></span>

- [<span data-ttu-id="c9c89-147">Azure Active Directory の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="c9c89-147">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [<span data-ttu-id="c9c89-148">Azure Active Directory の条件付きアクセスの概要</span><span class="sxs-lookup"><span data-stu-id="c9c89-148">Get started with conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
