---
title: "一般的なトラブルシューティングのヒント"
description: "Intune の問題を解決するための一般的なリソース。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f2a3f3b0fbc5df391dae957ddbabbfdbd5f82724
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a><span data-ttu-id="5f025-103">Microsoft Intune の一般的なトラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="5f025-103">General troubleshooting tips for Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5f025-104">Microsoft Intune を展開した後、構成やクライアントのデバイスに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5f025-104">After you deploy Microsoft Intune, you might encounter problems with your configuration or with client devices.</span></span> <span data-ttu-id="5f025-105">次のリソースを使用すると、問題解決のための原因を発見しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="5f025-105">Use the following resources to help you discover what's causing the problem so you can resolve it.</span></span>

> [!NOTE]
> <span data-ttu-id="5f025-106">サポート リクエストを作成したり、既存のリクエストを確認したりするには、[Office 365 管理センターにアクセスしてしてください](https://portal.office.com/admin/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f025-106">To create a support request, or to view an existing request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="5f025-107">サポート オプションの詳細については、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f025-107">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <a name="define-the-problem"></a><span data-ttu-id="5f025-108">問題の定義</span><span class="sxs-lookup"><span data-stu-id="5f025-108">Define the problem</span></span>

-   <span data-ttu-id="5f025-109">どのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="5f025-109">What is the behavior?</span></span>

-   <span data-ttu-id="5f025-110">この動作はだれが操作し、また、どのプラットフォームまたデバイスで生じていますか?</span><span class="sxs-lookup"><span data-stu-id="5f025-110">Who experiences this behavior, and on what platforms and devices?</span></span>

-   <span data-ttu-id="5f025-111">デバイスは以前は正常に動作していましたか?</span><span class="sxs-lookup"><span data-stu-id="5f025-111">Did the device work properly previously?</span></span>

-   <span data-ttu-id="5f025-112">Intune またはデバイスの構成にどのような変更を加えましたか?</span><span class="sxs-lookup"><span data-stu-id="5f025-112">What changes did you make to the Intune or device configuration?</span></span>

-   <span data-ttu-id="5f025-113">構成の変更以外に、操作環境にその他の変更が加えられましたか?</span><span class="sxs-lookup"><span data-stu-id="5f025-113">Were other changes were made to the environment in which you operate, other than configuration changes?</span></span>

-   <span data-ttu-id="5f025-114">この問題はどのくらいの頻度で発生しますか? 突発的ですか? あるいは一貫性がありますか?</span><span class="sxs-lookup"><span data-stu-id="5f025-114">How frequently does this problem occur, and is it sporadic or consistent?</span></span>

-   <span data-ttu-id="5f025-115">ユーザーに認証の問題が発生する可能性はありますか? </span><span class="sxs-lookup"><span data-stu-id="5f025-115">Could the user be experiencing an authentication issue?</span></span> <span data-ttu-id="5f025-116">可能性がある場合、ユーザーが Azure Active Directory を使用する他のサービスにサインインできるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f025-116">If this is a possiblity, see if the user can sign in to other services that use Azure Active Directory.</span></span> <span data-ttu-id="5f025-117">また、ユーザーが別のデバイスからサインインできるかどうかも確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f025-117">Also, see if the user can sign in from a different device.</span></span>

-   <span data-ttu-id="5f025-118">サービスの状態を確認しましたか?</span><span class="sxs-lookup"><span data-stu-id="5f025-118">Have you checked the service status?</span></span> <span data-ttu-id="5f025-119">Intune のサービス正常性は、[Office 365 管理ポータル](https://portal.office.com/Admin/Default.aspx)で監視できます。</span><span class="sxs-lookup"><span data-stu-id="5f025-119">You can monitor Intune service health in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx).</span></span> <span data-ttu-id="5f025-120">左側のウィンドウで **[サービス正常性]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f025-120">Choose **Service Health** in the left pane.</span></span>

## <a name="collect-available-data"></a><span data-ttu-id="5f025-121">利用可能なデータの収集</span><span class="sxs-lookup"><span data-stu-id="5f025-121">Collect available data</span></span>

- <span data-ttu-id="5f025-122">次のリソースは、デバイスのログを収集する方法を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5f025-122">The following resources can help you learn how to collect device logs:</span></span>
  - [<span data-ttu-id="5f025-123">USB ケーブルを使用して Android の診断データのログを IT 管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="5f025-123">Send Android diagnostic data logs to your IT administrator using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [<span data-ttu-id="5f025-124">メールを使用して Android の診断データのログを IT 管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="5f025-124">Send Android diagnostic data logs to your IT administrator using email</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [<span data-ttu-id="5f025-125">IT 管理者に Android の登録に関するエラーを送信する</span><span class="sxs-lookup"><span data-stu-id="5f025-125">Send Android enrollment errors to your IT administrator</span></span>](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [<span data-ttu-id="5f025-126">IT 管理者に iOS の登録に関するエラーを送信する</span><span class="sxs-lookup"><span data-stu-id="5f025-126">Send iOS enrollment errors to your IT administrator</span></span>](/intune-user-help/send-errors-to-your-it-admin-ios)

- <span data-ttu-id="5f025-127">管理コンソール データ。たとえば、ポリシー実装の問題の場合は、「[Microsoft Intune でユーザーとデバイスの管理にグループを使用する](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)」に記載されている説明に従って、目的のポリシーとその状態を調べます。</span><span class="sxs-lookup"><span data-stu-id="5f025-127">With admin console data (for example, for policy implementation issues), examine the intended policy and the status of that policy, as described in [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>

## <a name="research-the-solution"></a><span data-ttu-id="5f025-128">ソリューションの調査</span><span class="sxs-lookup"><span data-stu-id="5f025-128">Research the solution</span></span>

-   <span data-ttu-id="5f025-129">ソリューションについて Web を検索します。</span><span class="sxs-lookup"><span data-stu-id="5f025-129">Search the Web for a solution.</span></span> <span data-ttu-id="5f025-130">たとえば、エラー 0x80073CF0 が返された場合は、Web 上で **technet intune 0x80073cf0** を検索すると、「[Microsoft Intune のアプリ展開に関する問題のトラブルシューティング](troubleshoot-app-deployment-problems-in-microsoft-intune.md)」の記事が見つかります。</span><span class="sxs-lookup"><span data-stu-id="5f025-130">For example, if you receive the error 0x80073CF0, search for **technet intune 0x80073cf0** on the Web, and you'll find the article [Troubleshoot app deployment problems in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md).</span></span> <span data-ttu-id="5f025-131">この記事では、このエラーに対処するための推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f025-131">This article offers suggestions for addressing this error.</span></span>

-   <span data-ttu-id="5f025-132">[Intune TechNet フォーラム](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)で、回答を検索できます。</span><span class="sxs-lookup"><span data-stu-id="5f025-132">Search for an answer in the [Intune TechNet forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).</span></span>  <span data-ttu-id="5f025-133">これまで扱われたことのない問題の場合、コミュニティから提案を受けられるように、質問を投稿してください。</span><span class="sxs-lookup"><span data-stu-id="5f025-133">If the issue hasn't been previously addressed, post the question to see what suggestions the community might have.</span></span>

-   <span data-ttu-id="5f025-134">サポートを依頼します。</span><span class="sxs-lookup"><span data-stu-id="5f025-134">Open a support request.</span></span> <span data-ttu-id="5f025-135">お客様が問題を特定し、入手できるデータを収集されていると、Intune のサポートが問題の解決をより支援しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="5f025-135">Intune Support will be better able to help you resolve an issue after you've defined the problem and have collected the available data.</span></span>

    <span data-ttu-id="5f025-136">サポート リクエストを作成するには、[Office 365 管理センターにアクセスしてください](https://portal.office.com/admin/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f025-136">To create a support request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="5f025-137">サポート オプションの詳細については、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f025-137">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <a name="find-community-resources"></a><span data-ttu-id="5f025-138">コミュニティのリソースを探す</span><span class="sxs-lookup"><span data-stu-id="5f025-138">Find community resources</span></span>
<span data-ttu-id="5f025-139">以下のコミュニティ リソースには、その他の有用な情報があります。</span><span class="sxs-lookup"><span data-stu-id="5f025-139">You can find other helpful information in these community resources:</span></span>

-   <span data-ttu-id="5f025-140">[Microsoft Intune サバイバル ガイド](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx)。ここには、Intune の構成、保守、およびトラブルシューティングに役立つ多くのリソースへのリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="5f025-140">The [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contains links to many resources that can help you configure, maintain, and troubleshoot Intune.</span></span>

-   [<span data-ttu-id="5f025-141">Intune のブログ</span><span class="sxs-lookup"><span data-stu-id="5f025-141">The Intune blog</span></span>](http://blogs.technet.com/b/windowsintune/)

-   [<span data-ttu-id="5f025-142">Twitter で Intune をフォローする</span><span class="sxs-lookup"><span data-stu-id="5f025-142">Follow Intune on Twitter</span></span>](https://twitter.com/MSIntune)

-   [<span data-ttu-id="5f025-143">Intune フォーラム</span><span class="sxs-lookup"><span data-stu-id="5f025-143">The Intune forums</span></span>](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a><span data-ttu-id="5f025-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="5f025-144">Next steps</span></span>
<span data-ttu-id="5f025-145">以下のトピックには、特定の問題に関するトラブルシューティングのヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f025-145">The following topics have troubleshooting help for specific issues.</span></span> <span data-ttu-id="5f025-146">この情報を使っても問題が解決しない場合は、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」の説明に従って Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5f025-146">If that information doesn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

[<span data-ttu-id="5f025-147">Microsoft Intune におけるエンドポイント保護のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-147">Troubleshoot Endpoint Protection in Microsoft Intune</span></span>](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[<span data-ttu-id="5f025-148">Microsoft Intune での会社のリソースへのアクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-148">Troubleshoot company resource access problems with Microsoft Intune</span></span>](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[<span data-ttu-id="5f025-149">Microsoft Intune のアプリ展開に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-149">Troubleshoot app deployment problems in Microsoft Intune</span></span>](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[<span data-ttu-id="5f025-150">Intune のデバイス登録に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-150">Troubleshoot device enrollment in Intune</span></span>](troubleshoot-device-enrollment-in-intune.md)

[<span data-ttu-id="5f025-151">Microsoft Intune のポリシーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-151">Troubleshoot policies in Microsoft Intune</span></span>](troubleshoot-policies-in-microsoft-intune.md)

[<span data-ttu-id="5f025-152">Microsoft Intune でのクライアント セットアップのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-152">Troubleshoot client setup in Microsoft Intune</span></span>](troubleshoot-client-setup-in-microsoft-intune.md)

[<span data-ttu-id="5f025-153">Microsoft Intune でのソフトウェア更新のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f025-153">Troubleshoot software updates in Microsoft Intune</span></span>](troubleshoot-software-updates-in-microsoft-intune.md)
