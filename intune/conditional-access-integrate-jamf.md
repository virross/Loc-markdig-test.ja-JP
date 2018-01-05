---
title: "コンプライアンスのために Jamf Pro を Intune と統合する"
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
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d561b95c41349f50d2aca361304d561bc7ca3fb
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a><span data-ttu-id="ec499-103">コンプライアンスのために Jamf Pro を Intune と統合する</span><span class="sxs-lookup"><span data-stu-id="ec499-103">Integrate Jamf Pro with Intune for compliance</span></span>

|<span data-ttu-id="ec499-104">適用先: Azure Portal での Intune</span><span class="sxs-lookup"><span data-stu-id="ec499-104">Applies to: Intune in the Azure portal</span></span> |
|--|
|<span data-ttu-id="ec499-105">クラシック ポータルで Intune に関するドキュメントをお探しですか。</span><span class="sxs-lookup"><span data-stu-id="ec499-105">Looking for documentation about Intune in the classic portal?</span></span> <span data-ttu-id="ec499-106">[こちらを検索してください](/intune/introduction-intune?toc=/intune-classic/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="ec499-106">[Go here](/intune/introduction-intune?toc=/intune-classic/toc.json).</span></span>|
| |

<span data-ttu-id="ec499-107">組織で [Jamf Pro](https://www.jamf.com) を使用してエンド ユーザーの Mac を管理している場合、Microsoft Intune コンプライアンス ポリシーと Azure Active Directory の条件付きアクセスを使用して、組織内のデバイスがコンプライアンスに確実に準拠するようにできます。</span><span class="sxs-lookup"><span data-stu-id="ec499-107">If your organization uses [Jamf Pro](https://www.jamf.com) to manage your end users' Macs, you can use Microsoft Intune compliance policies with Azure Active Directory conditional access to ensure that devices in your organization are compliant.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec499-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec499-108">Prerequisites</span></span>

<span data-ttu-id="ec499-109">Jamf Pro で条件付きアクセスを構成するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec499-109">You need the following to configure conditional access with Jamf Pro:</span></span>

- <span data-ttu-id="ec499-110">macOS 条件付きアクセス用の Intune プライベート プレビューへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ec499-110">Access to the Intune Private Preview for macOS conditional access</span></span>
- <span data-ttu-id="ec499-111">Jamf Pro 10.1.0 以降</span><span class="sxs-lookup"><span data-stu-id="ec499-111">Jamf Pro 10.1.0 or later</span></span>
- [<span data-ttu-id="ec499-112">macOS 用ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="ec499-112">Company Portal app for macOS</span></span>](https://aka.ms/macoscompanyportal)
- <span data-ttu-id="ec499-113">OS X 10.11 Yosemite 以降を使用する macOS デバイス</span><span class="sxs-lookup"><span data-stu-id="ec499-113">macOS devices with OS X 10.11 Yosemite or later</span></span>

## <a name="connecting-intune-to-jamf-pro"></a><span data-ttu-id="ec499-114">Intune の Jamf Pro への接続</span><span class="sxs-lookup"><span data-stu-id="ec499-114">Connecting Intune to Jamf Pro</span></span>

<span data-ttu-id="ec499-115">次の方法で Intune を Jamf Pro に接続できます。</span><span class="sxs-lookup"><span data-stu-id="ec499-115">You can connect Intune with Jamf Pro by:</span></span>

1. <span data-ttu-id="ec499-116">Azure で新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ec499-116">Creating a new application in Azure</span></span>
2. <span data-ttu-id="ec499-117">Intune の Jamf Pro との統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="ec499-117">Enabling Intune to integrate with Jamf Pro</span></span>
3. <span data-ttu-id="ec499-118">Jamf Pro で条件付きアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="ec499-118">Configure conditional access in Jamf Pro</span></span>

## <a name="create-a-new-application-in-azure-active-directory"></a><span data-ttu-id="ec499-119">Azure Active Directory で新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ec499-119">Create a new application in Azure Active Directory</span></span>

1. <span data-ttu-id="ec499-120">**[Azure Active Directory]** > **[アプリの登録]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ec499-120">Open **Azure Active Directory** > **App Registrations**.</span></span>
2. <span data-ttu-id="ec499-121">**[新しいアプリケーションの登録]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-121">Click **+New application registration**.</span></span>
3. <span data-ttu-id="ec499-122">「**Jamf 条件付きアクセス**」など、**表示名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec499-122">Enter a **display name**, such as **Jamf Conditional Access**.</span></span>
4. <span data-ttu-id="ec499-123">**[Web アプリ/API]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec499-123">Select **Web app / API**.</span></span>
5. <span data-ttu-id="ec499-124">Jamf Pro インスタンス URL を使用して、**サインオン URL** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec499-124">Specify the **Sign-On URL** using your Jamf Pro instance URL.</span></span>
6. <span data-ttu-id="ec499-125">**[アプリケーションの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-125">Click **Create application**.</span></span>
7. <span data-ttu-id="ec499-126">新しく作成した**アプリケーション ID** を保存し、**[設定]** を開き、**[API アクセス]** > **[キー]** に移動して、新しいアプリケーション キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec499-126">Save the newly-created **Application ID**, then open **Settings** and navigate to **API Access** > **Keys** to create a new Application Key.</span></span> <span data-ttu-id="ec499-127">**説明** (**期限切れ**になるまでの期間) を入力し、アプリケーション キーを保存します。</span><span class="sxs-lookup"><span data-stu-id="ec499-127">Enter a **Description**, how long to wait before it **Expires**, then save the Application Key.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ec499-128">アプリケーション キーは、このプロセス中 1 回のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec499-128">The Application Key is only shown once during this process.</span></span> <span data-ttu-id="ec499-129">簡単に取得できる場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="ec499-129">Be sure to save it somewhere where you can easily retrieve it.</span></span>

8. <span data-ttu-id="ec499-130">**[設定]** を開き、**[API アクセス]** > **[必要なアクセス許可]** に移動し、すべてのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="ec499-130">Open **Settings**, then navigate to **API Access** > **Required Permissions** and delete all permissions.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ec499-131">新しい必要なアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="ec499-131">Add a new required permission.</span></span> <span data-ttu-id="ec499-132">アプリケーションは必要なアクセス許可が 1 つの場合にのみ正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="ec499-132">The application can have only work properly if it has the single required permission.</span></span>

9. <span data-ttu-id="ec499-133">**[Microsoft Intune API]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-133">Select **Microsoft Intune API** and click **Select**.</span></span>
10. <span data-ttu-id="ec499-134">**[Send device attributes to Microsoft Intune]\(デバイス属性を Microsoft Intune に送信する\)** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-134">Choose **Send device attributes to Microsoft Intune** and click **Select**.</span></span>
11. <span data-ttu-id="ec499-135">アプリケーションの必要なアクセス許可を保存した後、**[アクセス許可の付与]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-135">Click the **Grant Permissions** button after saving the required permissions for the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec499-136">アプリケーション キーが期限切れになった場合は、Microsoft Azure で新しいアプリケーション キーを作成し、Jamf Pro で条件付きアクセス データを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec499-136">If the Application Key expires, you must create a new Application Key in Microsoft Azure and then update the Conditional Access data in Jamf Pro.</span></span> <span data-ttu-id="ec499-137">Azure では、サービスの中断を防ぐため、古いキーと新しいキーの両方をアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec499-137">Azure allows you to have both the old key and new key active to prevent service disruptions.</span></span>

## <a name="enable-intune-to-integrate-with-jamf-pro"></a><span data-ttu-id="ec499-138">Intune の Jamf Pro との統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="ec499-138">Enable Intune to integrate with Jamf Pro</span></span>

1. <span data-ttu-id="ec499-139">Microsoft Azure Portal で **[Microsoft Intune]** > **[デバイスのポリシー準拠]** > **[Partner device management]\(パートナー デバイス管理\)** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ec499-139">In the Microsoft Azure portal, open **Microsoft Intune** > **Device Compliance** > **Partner device management**.</span></span>
2. <span data-ttu-id="ec499-140">アプリケーション ID を **[Jamf Azure Active Directory App ID]** フィールドに貼り付けることによって、Jamf 用コンプライアンス コネクタを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec499-140">Enable the Compliance Connector for Jamf by pasting the Application ID into the **Jamf Azure Active Directory App ID** field.</span></span>
3. <span data-ttu-id="ec499-141">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-141">Click **Save**.</span></span>

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a><span data-ttu-id="ec499-142">Jamf Pro で Microsoft Intune 統合を構成する</span><span class="sxs-lookup"><span data-stu-id="ec499-142">Configure Microsoft Intune Integration in Jamf Pro</span></span>

1. <span data-ttu-id="ec499-143">Jamf Pro で、**[グローバル管理]** > **[条件付きアクセス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec499-143">In Jamf Pro, navigate to **Global Management** > **Conditional Access**.</span></span> <span data-ttu-id="ec499-144">**[Microsoft Intune 統合]** タブの **[編集]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-144">Click the **Edit** button on the **Microsoft Intune Integration** tab.</span></span>
2. <span data-ttu-id="ec499-145">**[Microsoft Intune 統合の有効化]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ec499-145">Select the checkbox for **Enable Microsoft Intune Integration**.</span></span>
3. <span data-ttu-id="ec499-146">前の手順で保存した、**場所**、**ドメイン名**、**アプリケーション ID**、**アプリケーション キー**を含む、Azure テナントについての必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec499-146">Provide the required information about your Azure tenant, including **Location**, **Domain name**, and the **Application ID** and **Application Key** you saved from the previous steps.</span></span>
4. <span data-ttu-id="ec499-147">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec499-147">Click **Save**.</span></span> <span data-ttu-id="ec499-148">Jamf Pro は設定をテストし、成功を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec499-148">Jamf Pro will test your settings and verify your success.</span></span>

## <a name="set-up-compliance-policies-and-register-devices"></a><span data-ttu-id="ec499-149">コンプライアンス ポリシー設定してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="ec499-149">Set up compliance policies and register devices</span></span>

<span data-ttu-id="ec499-150">Intune と Jamf の統合の構成が完了したら、[Jamf で管理されたデバイスにコンプライアンス ポリシーを適用する](conditional-access-assign-jamf.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec499-150">After you finish configuring integration between Intune and Jamf, you need to [apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md).</span></span>

## <a name="information-shared-from-jamf-pro-to-intune"></a><span data-ttu-id="ec499-151">Intune に Jamf Pro から共有する情報</span><span class="sxs-lookup"><span data-stu-id="ec499-151">Information shared from Jamf Pro to Intune</span></span>

<span data-ttu-id="ec499-152">Jamf Pro は、管理対象の macOS デバイスについてのインベントリ情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ec499-152">Jamf Pro captures inventory information about managed macOS devices.</span></span> <span data-ttu-id="ec499-153">Jamf Pro は、Intune に次の情報をレポートします。</span><span class="sxs-lookup"><span data-stu-id="ec499-153">Jamf Pro reports the following information to Intune:</span></span>

* <span data-ttu-id="ec499-154">デバイスの Azure AD ID</span><span class="sxs-lookup"><span data-stu-id="ec499-154">Device Azure AD ID</span></span>
* <span data-ttu-id="ec499-155">JAMF のインベントリ状態 (過去 24 時間以内に Jamf Pro でチェックインされたコンピューターのインベントリ状態)</span><span class="sxs-lookup"><span data-stu-id="ec499-155">JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)</span></span>
* <span data-ttu-id="ec499-156">OS のバージョン</span><span class="sxs-lookup"><span data-stu-id="ec499-156">OS Version</span></span>
* <span data-ttu-id="ec499-157">ユーザーの Azure AD ID</span><span class="sxs-lookup"><span data-stu-id="ec499-157">User Azure AD ID</span></span>
* <span data-ttu-id="ec499-158">暗号化 (FileVault 2)</span><span class="sxs-lookup"><span data-stu-id="ec499-158">Encrypted (FileVault 2)</span></span>
* <span data-ttu-id="ec499-159">Gatekeeper ステータス</span><span class="sxs-lookup"><span data-stu-id="ec499-159">Gatekeeper Status</span></span>
* <span data-ttu-id="ec499-160">パスワード: 文字セットの最小数</span><span class="sxs-lookup"><span data-stu-id="ec499-160">Password: minimum number of character sets</span></span>
* <span data-ttu-id="ec499-161">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="ec499-161">Password expiration (days)</span></span>
* <span data-ttu-id="ec499-162">パスワードの種類 - 簡易、英数字、または不明</span><span class="sxs-lookup"><span data-stu-id="ec499-162">Password Type - simple, alphanumeric, or unknown</span></span>
* <span data-ttu-id="ec499-163">自動ログインの防止</span><span class="sxs-lookup"><span data-stu-id="ec499-163">Prevent Auto Login</span></span>
* <span data-ttu-id="ec499-164">必要なパスコードの長さ</span><span class="sxs-lookup"><span data-stu-id="ec499-164">Required Passcode Length</span></span>
* <span data-ttu-id="ec499-165">パスワード: 再利用を防止する前のパスワードの数</span><span class="sxs-lookup"><span data-stu-id="ec499-165">Password: number of previous passwords to prevent reuse</span></span>
* <span data-ttu-id="ec499-166">システム整合性の保護</span><span class="sxs-lookup"><span data-stu-id="ec499-166">System Integrity Protection</span></span>
* <span data-ttu-id="ec499-167">最後のチェックイン時刻</span><span class="sxs-lookup"><span data-stu-id="ec499-167">Last Check-In Time</span></span>
* <span data-ttu-id="ec499-168">アーキテクチャの種類</span><span class="sxs-lookup"><span data-stu-id="ec499-168">Architecture Type</span></span>
* <span data-ttu-id="ec499-169">使用可能な RAM スロット</span><span class="sxs-lookup"><span data-stu-id="ec499-169">Available RAM Slots</span></span>
* <span data-ttu-id="ec499-170">バッテリ容量</span><span class="sxs-lookup"><span data-stu-id="ec499-170">Battery Capacity</span></span>
* <span data-ttu-id="ec499-171">ブート ROM</span><span class="sxs-lookup"><span data-stu-id="ec499-171">Boot ROM</span></span>
* <span data-ttu-id="ec499-172">バス速度</span><span class="sxs-lookup"><span data-stu-id="ec499-172">Bus Speed</span></span>
* <span data-ttu-id="ec499-173">キャッシュ サイズ</span><span class="sxs-lookup"><span data-stu-id="ec499-173">Cache Size</span></span>
* <span data-ttu-id="ec499-174">［デバイス名］</span><span class="sxs-lookup"><span data-stu-id="ec499-174">Device Name</span></span>
* <span data-ttu-id="ec499-175">ドメイン参加</span><span class="sxs-lookup"><span data-stu-id="ec499-175">Domain Join</span></span>
* <span data-ttu-id="ec499-176">Jamf ID</span><span class="sxs-lookup"><span data-stu-id="ec499-176">Jamf ID</span></span>
* <span data-ttu-id="ec499-177">MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="ec499-177">MAC address</span></span>
* <span data-ttu-id="ec499-178">Make</span><span class="sxs-lookup"><span data-stu-id="ec499-178">Make</span></span>
* <span data-ttu-id="ec499-179">モデル</span><span class="sxs-lookup"><span data-stu-id="ec499-179">Model</span></span>
* <span data-ttu-id="ec499-180">モデル識別子</span><span class="sxs-lookup"><span data-stu-id="ec499-180">Model Identifier</span></span>
* <span data-ttu-id="ec499-181">NIC 速度</span><span class="sxs-lookup"><span data-stu-id="ec499-181">NIC Speed</span></span>
* <span data-ttu-id="ec499-182">コア数</span><span class="sxs-lookup"><span data-stu-id="ec499-182">Number of Cores</span></span>
* <span data-ttu-id="ec499-183">プロセッサ数</span><span class="sxs-lookup"><span data-stu-id="ec499-183">Number of Processors</span></span>
* <span data-ttu-id="ec499-184">OS</span><span class="sxs-lookup"><span data-stu-id="ec499-184">OS</span></span>
* <span data-ttu-id="ec499-185">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ec499-185">Platform</span></span>
* <span data-ttu-id="ec499-186">プロセッサ速度</span><span class="sxs-lookup"><span data-stu-id="ec499-186">Processor Speed</span></span>
* <span data-ttu-id="ec499-187">プロセッサの種類</span><span class="sxs-lookup"><span data-stu-id="ec499-187">Processor Type</span></span>
* <span data-ttu-id="ec499-188">セカンダリ MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="ec499-188">Secondary MAC Address</span></span>
* <span data-ttu-id="ec499-189">シリアル番号</span><span class="sxs-lookup"><span data-stu-id="ec499-189">Serial Number</span></span>
* <span data-ttu-id="ec499-190">SMC バージョン</span><span class="sxs-lookup"><span data-stu-id="ec499-190">SMC Version</span></span>
* <span data-ttu-id="ec499-191">RAM 合計</span><span class="sxs-lookup"><span data-stu-id="ec499-191">Total RAM</span></span>
* <span data-ttu-id="ec499-192">UDID</span><span class="sxs-lookup"><span data-stu-id="ec499-192">UDID</span></span>
* <span data-ttu-id="ec499-193">ユーザーの電子メール</span><span class="sxs-lookup"><span data-stu-id="ec499-193">User Email</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec499-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="ec499-194">Next steps</span></span>

- [<span data-ttu-id="ec499-195">Jamf で管理されたデバイスにコンプライアンス ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="ec499-195">Apply compliance policies to Jamf-managed devices</span></span>](conditional-access-assign-jamf.md)
