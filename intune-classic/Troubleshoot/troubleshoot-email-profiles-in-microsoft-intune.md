---
title: "電子メール プロファイルに関するトラブルシューティング"
description: "電子メール プロファイルに関する問題と、そのトラブルシューティングと解決方法。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2da5e4bfcc68c7329f540a1b29ac7457dbbac7b6
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a><span data-ttu-id="cadf3-103">Microsoft Intune の電子メール プロファイルに関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cadf3-103">Troubleshoot email profiles in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="cadf3-104">ここでは、電子メール プロファイルに関する問題と、そのトラブルシューティングと解決方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-104">Listed here are some email profile issues and how to troubleshoot and resolve them.</span></span>

<span data-ttu-id="cadf3-105">この情報で問題が解決しない場合、さらに役立つ方法を探すには、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cadf3-105">If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.</span></span>


## <a name="unable-to-send-images-from--email-account"></a><span data-ttu-id="cadf3-106">電子メール アカウントから画像を送信できない</span><span class="sxs-lookup"><span data-stu-id="cadf3-106">Unable to send images from  email account</span></span>
<span data-ttu-id="cadf3-107">電子メール アカウントを自動的に構成したユーザーが、自分のデバイスから画像を送信することができません。</span><span class="sxs-lookup"><span data-stu-id="cadf3-107">Users who have email accounts automatically configured are unable to send pictures or images from their devices.</span></span>
<span data-ttu-id="cadf3-108">**[サード パーティ アプリケーションから電子メールを送信できるようにする]** がオフになっている場合に、この問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-108">This occurs when the option **Allow e-mail to be sent from third-party applications** is not enabled.</span></span>

### <a name="intune-solution"></a><span data-ttu-id="cadf3-109">Intune での解決方法</span><span class="sxs-lookup"><span data-stu-id="cadf3-109">Intune solution</span></span>

1.  <span data-ttu-id="cadf3-110">Microsoft Intune 管理コンソールで、**[ポリシー]** ワークロード &gt;**[構成ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-110">Open the Microsoft Intune Administration Console, select **Policy** workload &gt; **Configuration Policy**.</span></span>

2.  <span data-ttu-id="cadf3-111">電子メール プロファイルを選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-111">Select the email profile and choose **Edit**.</span></span>

3.  <span data-ttu-id="cadf3-112">**[サード パーティ アプリケーションから電子メールを送信できるようにする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="cadf3-112">Select **Allow e-mail to be sent from third-party applications.**</span></span>

### <a name="configuration-manager-integrated-with-intune-solution"></a><span data-ttu-id="cadf3-113">Windows Intune と統合された Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cadf3-113">Configuration Manager integrated with Intune solution</span></span>

1.  <span data-ttu-id="cadf3-114">Configuration Manager コンソール &gt;**[資産とコンプライアンス]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="cadf3-114">Open the Configuration Manager console &gt; **Assets and Compliance**.</span></span>

2.  <span data-ttu-id="cadf3-115">**[概要]** -&gt; **[コンプライアンス設定]** -&gt; **[会社のリソースへのアクセス]** の順に展開して、**[電子メール プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-115">Expand **Overview** -&gt; **Compliance Settings** -&gt; **Company Resource Access**, and select **Email Profiles**.</span></span>

3.  <span data-ttu-id="cadf3-116">電子メール プロファイルを右クリックし、**[プロパティ]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="cadf3-116">Right-click the e-mail profile, and open **Properties**.</span></span>

4.  <span data-ttu-id="cadf3-117">**[同期設定]** タブで、**[サード パーティ アプリケーションから電子メールを送信できるようにする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="cadf3-117">On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.</span></span>


## <a name="device-already-has-an-email-profile-installed"></a><span data-ttu-id="cadf3-118">デバイスに電子メール プロファイルが既にインストールされている</span><span class="sxs-lookup"><span data-stu-id="cadf3-118">Device already has an email profile installed</span></span>

<span data-ttu-id="cadf3-119">Intune によるプロファイルのプロビジョニングの前にユーザーが電子メール プロファイルをインストールしてある場合、Intune による電子メール プロファイルの展開の結果はデバイスのプラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-119">If the user has installed an email profile prior to provision of a profile by Intune, the result of the Intune email profile deployment depends on the device platform:</span></span>

<span data-ttu-id="cadf3-120">-**iOS**: Intune は、ホスト名と電子メール アドレスに基づいて既存の重複する電子メール プロファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-120">-**iOS**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="cadf3-121">ユーザーによって作成された重複する電子メール プロファイルは、Intune の管理者が作成したプロファイルの展開をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cadf3-121">The duplicate email profile created by the user will block the deployment of an Intune admin-created profile.</span></span> <span data-ttu-id="cadf3-122">これは一般的な問題です。iOS ユーザーは通常、電子メール プロファイルを作成し、それから登録するためです。</span><span class="sxs-lookup"><span data-stu-id="cadf3-122">This is a common problem as iOS users will typically create an email profile, then enroll.</span></span> <span data-ttu-id="cadf3-123">ポータル サイトは、手動で設定した電子メール プロファイルに起因してポリシーに準拠していないことをユーザーに通知し、そのプロファイルを取り除くようにユーザーに要求します。Intune プロファイルを展開できるように、ユーザーは電子メール プロファイルを取り除く必要があります。</span><span class="sxs-lookup"><span data-stu-id="cadf3-123">The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed.</span></span> <span data-ttu-id="cadf3-124">この問題を防ぐには、電子メール プロファイルをインストールする前に登録し、Intune によるプロファイルの展開を許可するようにユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-124">To prevent the problem instruct your users to enroll before installing an email profile and to allow Intune to deploy the profile.</span></span>

<span data-ttu-id="cadf3-125">-**Windows**: Intune は、ホスト名と電子メール アドレスに基づいて既存の重複する電子メール プロファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-125">-**Windows**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="cadf3-126">Intune は、ユーザーによって作成された既存の電子メール プロファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="cadf3-126">Intune will overwrite the existing email profile created by the user.</span></span>

<span data-ttu-id="cadf3-127">-**Samsung KNOX Standard**: Intune は、電子メール アドレスに基づいて重複する電子メール アカウントを識別し、Intune プロファイルで上書きします。</span><span class="sxs-lookup"><span data-stu-id="cadf3-127">-**Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and will overwrite it with the Intune profile.</span></span> <span data-ttu-id="cadf3-128">ユーザーがそのアカウントを構成した場合、Intune プロファイルによって再び上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cadf3-128">If the user configures that account, it will be overwritten again by the Intune profile.</span></span> <span data-ttu-id="cadf3-129">このため、アカウントの構成を上書きされたユーザーが混乱する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cadf3-129">Note that this may cause some confusion to the user whose account configuration gets overwritten.</span></span>

<span data-ttu-id="cadf3-130">Samsung KNOX はプロファイルを識別するためにホスト名を使用しないため、複数の電子メール プロファイルを作成して異なるホスト上の同じ電子メール アドレスに展開することはお勧めしません。プロファイルが相互に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cadf3-130">Since Samsung KNOX does not use hostname to identify the profile, we recommend that you not create multiple email profiles to deploy to the same email address on different hosts, as these will overwrite each other.</span></span>

## <a name="error--0x87d1fde8-for-knox-standard-device"></a><span data-ttu-id="cadf3-131">KNOX Standard デバイスのエラー 0x87D1FDE8</span><span class="sxs-lookup"><span data-stu-id="cadf3-131">Error  0x87D1FDE8 for KNOX Standard device</span></span>
<span data-ttu-id="cadf3-132">**問題**: さまざまな Android デバイスで Samsung KNOX Standard の Exchange Active Sync 電子メール プロファイルを作成して展開すると、デバイスの [プロパティ] &gt; [ポリシー] タブに **0x87D1FDE8** または **[修復できませんでした]** というエラーが報告される。</span><span class="sxs-lookup"><span data-stu-id="cadf3-132">**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for various Android devices, the error **0x87D1FDE8** or **remediation failed** is reported in the device's properties &gt; policy tab.</span></span>

<span data-ttu-id="cadf3-133">Samsung KNOX の EAS プロファイルおよびソース ポリシーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="cadf3-133">Review the configuration of your EAS profile for Samsung KNOX and source policy.</span></span> <span data-ttu-id="cadf3-134">Samsung Note 同期オプションはサポートされなくなったため、このオプションをプロファイルで選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="cadf3-134">The Samsung Notes sync option is no longer supported and that option should not be selected in your profile.</span></span> <span data-ttu-id="cadf3-135">デバイスには、ポリシーを処理するための十分な時間を最大 24 時間設定してください。</span><span class="sxs-lookup"><span data-stu-id="cadf3-135">Be sure devices have had enough time to process the policy, up to 24 hours.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cadf3-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cadf3-136">Next steps</span></span>
<span data-ttu-id="cadf3-137">このトラブルシューティング情報を使っても問題が解決しない場合は、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」の説明に従って Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="cadf3-137">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
