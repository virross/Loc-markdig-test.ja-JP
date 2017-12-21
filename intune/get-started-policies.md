---
title: "ポリシーの概要"
titlesuffix: Azure portal
description: "ユーザーが自分のデバイスで許可のない操作を行うことを禁止する目的でポリシーを作成します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5bef1d46bff5d519ae6153f6858c929c70fc504a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-policies"></a><span data-ttu-id="993cd-103">ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="993cd-103">Get started with policies</span></span>

<span data-ttu-id="993cd-104">Intune を始める主な目的の 1 つは、企業ポリシーに準拠させるためにデバイスを登録することです。</span><span class="sxs-lookup"><span data-stu-id="993cd-104">One of the main goals of getting started with Intune is enrolling devices to make sure that they are compliant with corporate policies.</span></span> <span data-ttu-id="993cd-105">コンプライアンス ポリシーは、企業所有のキオスクなど、特別な種類のデバイスだけではなく、個人 (BYO) デバイス、タブレット、ユーザーなしデバイスなどの管理にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="993cd-105">Compliance policies not only help you to manage specialized device types, such as corporate-owned kiosks, but also personal (Bring Your Own) devices, tablets, and user-less devices.</span></span>

![データが非常に少ないコンプライアンス ダッシュボード](/intune/media/generic-compliance-dashboard.png)

<span data-ttu-id="993cd-107">コンプライアンス ポリシーは、モバイル デバイスのために次の管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="993cd-107">Compliance policies provide the following management capabilities for mobile devices:</span></span>

* <span data-ttu-id="993cd-108">各ユーザーが登録するデバイス数の制限。</span><span class="sxs-lookup"><span data-stu-id="993cd-108">Regulate numbers of devices each user enrolls</span></span>
* <span data-ttu-id="993cd-109">デバイスの設定 (デバイス レベルの暗号化、パスワードの文字数、カメラの使用など) の管理。</span><span class="sxs-lookup"><span data-stu-id="993cd-109">Manage devices settings (e.g. device-level encryption, password length, camera usage)</span></span>
* <span data-ttu-id="993cd-110">アプリ、電子メール プロファイル、VPN プロファイルなどの提供。</span><span class="sxs-lookup"><span data-stu-id="993cd-110">Deliver apps, email profiles, VPN profiles, etc.</span></span>
* <span data-ttu-id="993cd-111">セキュリティ コンプライアンス ポリシーのデバイス レベルの基準の評価。</span><span class="sxs-lookup"><span data-stu-id="993cd-111">Evaluate device-level criteria for security compliance policies</span></span>

<span data-ttu-id="993cd-112">プラットフォームごとにコンプライアンス ポリシーを登録します。</span><span class="sxs-lookup"><span data-stu-id="993cd-112">You create compliance policies for each platform separately.</span></span> <span data-ttu-id="993cd-113">この演習では、iOS のみ取り上げます。</span><span class="sxs-lookup"><span data-stu-id="993cd-113">For this exercise, we’ll stick to iOS.</span></span> <span data-ttu-id="993cd-114">次のポリシーは iOS デバイスでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="993cd-114">The following policies are available for iOS devices:</span></span>

* <span data-ttu-id="993cd-115">PIN またはパスワードの構成</span><span class="sxs-lookup"><span data-stu-id="993cd-115">PIN or password configuration</span></span>
* <span data-ttu-id="993cd-116">デバイスの暗号化</span><span class="sxs-lookup"><span data-stu-id="993cd-116">Device encryption</span></span>
* <span data-ttu-id="993cd-117">脱獄されたデバイス</span><span class="sxs-lookup"><span data-stu-id="993cd-117">Jailbroken device</span></span>
* <span data-ttu-id="993cd-118">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="993cd-118">Email profile</span></span>
* <span data-ttu-id="993cd-119">最小 OS バージョン</span><span class="sxs-lookup"><span data-stu-id="993cd-119">Minimum OS version</span></span>
* <span data-ttu-id="993cd-120">最大 OS バージョン</span><span class="sxs-lookup"><span data-stu-id="993cd-120">Maximum OS version</span></span>

<span data-ttu-id="993cd-121">__ポリシーの作成方法__</span><span class="sxs-lookup"><span data-stu-id="993cd-121">__How do I create a policy?__</span></span>

1. <span data-ttu-id="993cd-122">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="993cd-122">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="993cd-123">**[リソースの検索]** で **[Intune]** を探します。</span><span class="sxs-lookup"><span data-stu-id="993cd-123">**Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="993cd-124">**[デバイスのポリシー準拠]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="993cd-124">Select **Device compliance**.</span></span>
4. <span data-ttu-id="993cd-125">**[デバイスのポリシー準拠]** ブレードで、**[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="993cd-125">On the **Device compliance** blade, select **Policies**.</span></span>
5. <span data-ttu-id="993cd-126">**[ポリシーの作成]** を選択し、**[名前]** や **[説明]** など、詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="993cd-126">Select **Create Policy**, then fill in the details, like **Name** and **Description**.</span></span> <span data-ttu-id="993cd-127">**[プラットフォーム]** として **[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="993cd-127">Choose **iOS** as the **Platform**.</span></span>
6. <span data-ttu-id="993cd-128">**[設定]** で **[システム セキュリティ]** を選択し、**[モバイル デバイスのロック解除にパスワードを必要とする]** を **[必要]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="993cd-128">In **Settings**, select **System Security**, then toggle **Require a password to unlock mobile devices** to **Require**.</span></span> <span data-ttu-id="993cd-129">**[最低限必要なパスワードの長さ]**、**[必要なパスワードの種類]**、**[パスワードに使用する英数字以外の文字数]** など、他のルールも設定できます。</span><span class="sxs-lookup"><span data-stu-id="993cd-129">You can also set other rules, such as **Minimum password length**, **Required password type**, and **Number of non-alphanumeric characters in password**.</span></span> <span data-ttu-id="993cd-130">ポリシーの設定が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="993cd-130">When you’ve finished setting up your policy, select **OK**.</span></span>
7. <span data-ttu-id="993cd-131">**[ポリシーの作成]** ブレードに戻り、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="993cd-131">Return to the **Create policy** blade, then select **Create**.</span></span>
8. <span data-ttu-id="993cd-132">ポリシーが作成されたら、**[割り当て]** を選択し、テスト グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="993cd-132">Once the policy is created, select **Assignments** to assign it to your test group.</span></span> <span data-ttu-id="993cd-133">テスト グループ (この中にテスト ユーザーが入っています) を選択し、**[保存]** をクリックしてそのグループにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="993cd-133">Select your test group – which should have your test user in it – then assign the policy to that group by clicking **Save**.</span></span>
9. <span data-ttu-id="993cd-134">数分待つと、登録したデバイスから、企業ポリシーに準拠するためにパスワードの更新が必要であると伝えられます。</span><span class="sxs-lookup"><span data-stu-id="993cd-134">Wait a few minutes, then your enrolled device should prompt you that it needs an updated password in order to remain compliant with corporate policy.</span></span> <span data-ttu-id="993cd-135">これは **iOS 向けのポータル サイト アプリ**で手動確認できます。デバイス名をタップし、**[同期]** ボタンを押してください。</span><span class="sxs-lookup"><span data-stu-id="993cd-135">You can also manually check for this in the **Company Portal app for iOS** by tapping on the device name, then the **Sync** button.</span></span>

## <a name="next-steps"></a><span data-ttu-id="993cd-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="993cd-136">Next steps</span></span>

<span data-ttu-id="993cd-137">[デバイス登録の概要](get-started-enroll.md) - iOS デバイスの登録手順を最初から最後まで行い、登録方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="993cd-137">[Get started enrolling devices](get-started-enroll.md) - Learn the enrollment experience by going through a full enrollment experience of an iOS device.</span></span>

## <a name="learn-more"></a><span data-ttu-id="993cd-138">詳細情報</span><span class="sxs-lookup"><span data-stu-id="993cd-138">Learn more</span></span>

* [<span data-ttu-id="993cd-139">Intune デバイスのコンプライアンス対応ポリシーの監視</span><span class="sxs-lookup"><span data-stu-id="993cd-139">Monitor Intune Device compliance policies</span></span>](compliance-policy-monitor.md)
* [<span data-ttu-id="993cd-140">Intune での条件付きアクセス ポリシーの一般的な使用方法</span><span class="sxs-lookup"><span data-stu-id="993cd-140">Common ways to use conditional access policies with Intune</span></span>](conditional-access-intune-common-ways-use.md)
