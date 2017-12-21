---
title: "アプリのプロビジョニング プロファイル"
description: "Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルのポリシーを事前に展開するツールが用意されています。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5cbc3060e1f45c0a330e88a78a76345918610951
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a><span data-ttu-id="1296c-103">iOS モバイル プロビジョニング プロファイルのポリシーを使用して、アプリが期限切れにならないようにする</span><span class="sxs-lookup"><span data-stu-id="1296c-103">Use iOS mobile provisioning profile policies to prevent your apps from expiring</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1296c-104">iPhone および iPad に展開された Apple iOS 基幹業務アプリは、含まれるプロビジョニング プロファイルおよび証明書で署名されたコードで構築されます。</span><span class="sxs-lookup"><span data-stu-id="1296c-104">Apple iOS line of business apps that are deployed to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="1296c-105">アプリを実行すると、iOS は iOS アプリの整合性を確認し、プロビジョニング プロファイルで定義されたポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1296c-105">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="1296c-106">次の検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="1296c-106">The following validations happen:</span></span>

- <span data-ttu-id="1296c-107">**インストール ファイルの整合性** - iOS は、アプリの詳細と、エンタープライズ署名証明書の公開キーを比較します。</span><span class="sxs-lookup"><span data-stu-id="1296c-107">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="1296c-108">これらが異なる場合はアプリの内容が変更されている可能性があり、アプリは実行を許可されません。</span><span class="sxs-lookup"><span data-stu-id="1296c-108">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="1296c-109">**機能の強制** - iOS は、アプリのインストール (.ipa) ファイルに含まれる、(個々の開発者プロビジョニング プロファイルではなく) エンタープライズ プロビジョニング プロファイルからアプリの機能の適用を試行します。</span><span class="sxs-lookup"><span data-stu-id="1296c-109">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="1296c-110">アプリの署名に使用するエンタープライズ署名証明書は、通常 3 年間は継続します。</span><span class="sxs-lookup"><span data-stu-id="1296c-110">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="1296c-111">ただし、プロビジョニング プロファイルは 1 年後に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="1296c-111">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="1296c-112">証明書が有効である期間中、Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルのポリシーを事前に展開するツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1296c-112">While the certificate is still valid, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="1296c-113">証明書の期限が切れると、新しい証明書を使用してアプリを再び署名して、新しい証明書のキーを持つ新しいプロビジョニング プロファイルを埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1296c-113">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a><span data-ttu-id="1296c-114">基幹業務アプリの有効期限が切れる日付を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1296c-114">How to find out when a line of business app will expire</span></span>

1. <span data-ttu-id="1296c-115">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1296c-115">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** > **Apps**.</span></span>
2. <span data-ttu-id="1296c-116">アプリの一覧の **[有効期限の日付]** 列で、アプリの有効期限を確認します。</span><span class="sxs-lookup"><span data-stu-id="1296c-116">In the list of apps, look at the **Expiration date** column to see the expiry date for the app.</span></span> <span data-ttu-id="1296c-117">**[フィルター]** ドロップダウン リストを **[期限切れまたは間もなく有効期限が切れる]** に設定して、処理が必要なアプリのみを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1296c-117">You can also set the **Filters** drop-down list to **Expired/about to expire** to see only the apps for which you must take action.</span></span>

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a><span data-ttu-id="1296c-118">iOS モバイル プロビジョニング プロファイルのポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1296c-118">How to create an iOS mobile provisioning profile policy</span></span>


1. <span data-ttu-id="1296c-119">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[概要]** > **[ポリシーの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1296c-119">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Overview** > **Add Policy**.</span></span>
2. <span data-ttu-id="1296c-120">**[新しいポリシーの作成]** ダイアログ ボックスで、**[iOS]** > **[Mobile Provisioning Profile Policy]\(モバイル プロビジョニング プロファイルのポリシー)** の順に選択して、**[ポリシーの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1296c-120">In the **Create a New Policy** dialog box, choose **iOS** > **Mobile Provisioning Profile Policy**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="1296c-121">**[全般]** ページで、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="1296c-121">On the **General** page, configure the following values:</span></span>
    - <span data-ttu-id="1296c-122">**名前** -このモバイル プロビジョニング プロファイルのポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1296c-122">**Name** - Provide a name for this mobile provisioning profile policy.</span></span>
    - <span data-ttu-id="1296c-123">**説明** - 必要に応じて、ポリシーの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="1296c-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="1296c-124">**構成プロファイル ファイル** - **[インポート]** をクリックして、Apple Developer Web サイトからダウンロードした Apple モバイル構成プロファイル ファイル (拡張子 **.mobileprovision**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1296c-124">**Configuration profile file** - Click **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="1296c-125">終了したら、**[ポリシーの保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1296c-125">When you are done, choose **Save Policy**.</span></span>
5. <span data-ttu-id="1296c-126">次に、必要な iOS デバイスにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="1296c-126">Now, deploy the policy to the required iOS devices.</span></span> <span data-ttu-id="1296c-127">詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1296c-127">For more information, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
