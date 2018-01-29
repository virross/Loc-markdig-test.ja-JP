---
title: "Azure Portal での Intune の概要"
titlesuffix: Azure portal
description: "Azure Portal での Intune の基本と、Intune を利用してデバイスを管理する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 2426a0c972aef67adbbba6bb12a66d0e40a2b660
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a><span data-ttu-id="abaac-103">Azure Portal での Microsoft Intune の概要</span><span class="sxs-lookup"><span data-stu-id="abaac-103">Introduction to Microsoft Intune in the Azure portal</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="abaac-104">Microsoft Intune は Azure Portal に含まれるようになり、これまで使い慣れたワークフローと機能は変更されました。</span><span class="sxs-lookup"><span data-stu-id="abaac-104">Microsoft Intune is now in the Azure portal, meaning that the workflows and functionality you are used to are now different.</span></span>
<span data-ttu-id="abaac-105">新しいポータルでは、Azure Portal の新機能と更新された機能が提供されており、組織のモバイル デバイス、PC、アプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="abaac-105">The new portal offers you new and updated functionality in the Azure portal where you can manage your organization's mobile devices, PCs, and apps.</span></span>

* <span data-ttu-id="abaac-106">[Azure での Intune の機能の移動先](ui-changes.md)は、Azure への移行で変更された特定のワークフローと UI を示すリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="abaac-106">[Where did my features go in Azure?](ui-changes.md) is a reference to show you the specific workflows and UIs that have changed with the move to Azure.</span></span>
* <span data-ttu-id="abaac-107">[Azure Portal での Intune クラシック グループ](groups-get-started.md)は、グループを管理するための Azure Active Directory セキュリティ グループへの切り替えの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="abaac-107">[Intune classic groups in the Azure portal](groups-get-started.md) explains the implications of the shift to Azure Active Directory security groups for group management.</span></span>




<span data-ttu-id="abaac-108">このライブラリでは新しいポータルに関する情報を参照でき、情報は継続的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="abaac-108">You can find information about the new portal in this library, and it is continually updated.</span></span> <span data-ttu-id="abaac-109">内容についてご提案がございましたら、トピックのコメント欄にフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="abaac-109">If you have suggestions you'd like to see, leave feedback in the topic comments.</span></span> <span data-ttu-id="abaac-110">ご意見をお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="abaac-110">We'd love to hear from you.</span></span>

<span data-ttu-id="abaac-111">新しいエクスペリエンスの概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="abaac-111">Highlights of the new experience include:</span></span>

- <span data-ttu-id="abaac-112">すべての Enterprise Mobility + Security (EMS) コンポーネント用の統合コンソール</span><span class="sxs-lookup"><span data-stu-id="abaac-112">An integrated console for all your Enterprise Mobility + Security (EMS) components</span></span>
- <span data-ttu-id="abaac-113">Web 標準に基づく HTML ベースのコンソール</span><span class="sxs-lookup"><span data-stu-id="abaac-113">An HTML-based console built on web standards</span></span>
- <span data-ttu-id="abaac-114">多数のアクションを自動化するために Microsoft Graph API をサポート</span><span class="sxs-lookup"><span data-stu-id="abaac-114">Microsoft Graph API support to automate many actions</span></span>
- <span data-ttu-id="abaac-115">Azure Active Directory (AD) グループによってすべての Azure アプリケーション間での互換性を提供</span><span class="sxs-lookup"><span data-stu-id="abaac-115">Azure Active Directory (AD) groups to provide compatibility across all your Azure applications</span></span>
- <span data-ttu-id="abaac-116">最新の Web ブラウザーの大部分に対応</span><span class="sxs-lookup"><span data-stu-id="abaac-116">Support for most modern web browsers</span></span>

## <a name="before-you-start"></a><span data-ttu-id="abaac-117">開始する前に</span><span class="sxs-lookup"><span data-stu-id="abaac-117">Before you start</span></span>

<span data-ttu-id="abaac-118">Azure Portal で Intune を使用するには、Intune の管理者およびテナント アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="abaac-118">To use Intune in the Azure portal, you must have an Intune admin and tenant account.</span></span> <span data-ttu-id="abaac-119">まだお持ちでない場合は、[アカウントにサインアップ](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)してください。</span><span class="sxs-lookup"><span data-stu-id="abaac-119">[Sign up for an account](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) if you don't already have one.</span></span>

## <a name="supported-web-browsers-for-the-azure-portal"></a><span data-ttu-id="abaac-120">Azure Portal でサポートされている Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="abaac-120">Supported web browsers for the Azure portal</span></span>

<span data-ttu-id="abaac-121">Azure Portal は、ほとんどの最新 PC、Mac、タブレットで動作します。</span><span class="sxs-lookup"><span data-stu-id="abaac-121">The Azure portal runs on most modern PCs, Macs, and tablets.</span></span> <span data-ttu-id="abaac-122">携帯電話はサポート対象外です。</span><span class="sxs-lookup"><span data-stu-id="abaac-122">Mobile phones are not supported.</span></span>
<span data-ttu-id="abaac-123">現時点では、以下のブラウザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="abaac-123">Currently, the following browsers are supported:</span></span>

- <span data-ttu-id="abaac-124">Microsoft Edge (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="abaac-124">Microsoft Edge (latest version)</span></span>
- <span data-ttu-id="abaac-125">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="abaac-125">Microsoft Internet Explorer 11</span></span>
- <span data-ttu-id="abaac-126">Safari (最新バージョン、Mac のみ)</span><span class="sxs-lookup"><span data-stu-id="abaac-126">Safari (latest version, Mac only)</span></span>
- <span data-ttu-id="abaac-127">Chrome (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="abaac-127">Chrome (latest version)</span></span>
- <span data-ttu-id="abaac-128">Firefox (最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="abaac-128">Firefox (latest version)</span></span>

<span data-ttu-id="abaac-129">サポート対象のブラウザーに関する最新情報については、[Azure Portal に関するページ](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abaac-129">Check the [Azure portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) for the latest information about supported browsers.</span></span>

## <a name="whats-in-this-library"></a><span data-ttu-id="abaac-130">このライブラリの内容</span><span class="sxs-lookup"><span data-stu-id="abaac-130">What's in this library?</span></span>

<span data-ttu-id="abaac-131">必要な情報が見つけやすくなるように、ドキュメントには Azure Portal のレイアウトが反映されています。</span><span class="sxs-lookup"><span data-stu-id="abaac-131">The documentation reflects the layout of the Azure portal to make it easier to find the information you need.</span></span>

![Azure Portal のワークロード](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a><span data-ttu-id="abaac-133">概要と作業開始</span><span class="sxs-lookup"><span data-stu-id="abaac-133">Introduction and get started</span></span>
<span data-ttu-id="abaac-134">このセクションでは、Intune の使用開始にあたって役に立つ[概要情報](introduction-intune.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="abaac-134">This section contains [introductory information](introduction-intune.md) that helps you get started using Intune.</span></span>
### <a name="plan-and-design"></a><span data-ttu-id="abaac-135">計画と設計</span><span class="sxs-lookup"><span data-stu-id="abaac-135">Plan and design</span></span>
<span data-ttu-id="abaac-136">Intune 環境の[計画と設計](/intune-classic/plan-design/introduction)に役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="abaac-136">Information to help you [plan and design](/intune-classic/plan-design/introduction) your Intune environment.</span></span>
### <a name="device-enrollment"></a><span data-ttu-id="abaac-137">デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="abaac-137">Device enrollment</span></span>
<span data-ttu-id="abaac-138">[デバイスを Intune の管理対象にする方法](device-enrollment.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-138">[How to get your devices managed by Intune](device-enrollment.md).</span></span>
### <a name="device-compliance"></a><span data-ttu-id="abaac-139">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="abaac-139">Device compliance</span></span>
<span data-ttu-id="abaac-140">[デバイスのコンプライアンス レベルを定義し、準拠していないデバイスをレポートします](device-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-140">[Define a compliance level for your devices, then report any devices that are not compliant](device-compliance.md).</span></span>
### <a name="device-configuration"></a><span data-ttu-id="abaac-141">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="abaac-141">Device configuration</span></span>
<span data-ttu-id="abaac-142">[管理対象のデバイスで設定と機能を構成するために使用できるプロファイルについて理解します](device-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-142">[Understand the profiles you can use to configure settings and features on devices you manage](device-profiles.md).</span></span>
### <a name="devices"></a><span data-ttu-id="abaac-143">[デバイス]</span><span class="sxs-lookup"><span data-stu-id="abaac-143">Devices</span></span>
<span data-ttu-id="abaac-144">[インベントリとレポートによって管理対象デバイスの情報を把握します](device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-144">[Get to know the devices you manage with inventory and reports](device-management.md).</span></span>
### <a name="mobile-apps"></a><span data-ttu-id="abaac-145">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="abaac-145">Mobile apps</span></span>
<span data-ttu-id="abaac-146">[アプリの発行、管理、構成、および保護方法](app-management.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-146">[How to publish, manage, configure, and protect apps](app-management.md).</span></span>
### <a name="conditional-access"></a><span data-ttu-id="abaac-147">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="abaac-147">Conditional access</span></span>
<span data-ttu-id="abaac-148">[指定した条件に応じて Exchange サービスへのアクセスを制限します](conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-148">[Restrict access to Exchange services depending on conditions you specify](conditional-access.md).</span></span>
### <a name="on-premises-access"></a><span data-ttu-id="abaac-149">オンプレミスのアクセス</span><span class="sxs-lookup"><span data-stu-id="abaac-149">On-premises access</span></span>
[<span data-ttu-id="abaac-150">Exchange ActiveSync および Exchange On-premises へのアクセスを構成します</span><span class="sxs-lookup"><span data-stu-id="abaac-150">Configure access to Exchange ActiveSync, and Exchange on-premises</span></span>](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a><span data-ttu-id="abaac-151">Users</span><span class="sxs-lookup"><span data-stu-id="abaac-151">Users</span></span>
<span data-ttu-id="abaac-152">[リソースを管理し、グループに分類するデバイスのユーザーについて](users-add.md)説明します。</span><span class="sxs-lookup"><span data-stu-id="abaac-152">[Learn about the users of devices you manage and sort resources into groups](users-add.md).</span></span>
### <a name="groups"></a><span data-ttu-id="abaac-153">[グループ]</span><span class="sxs-lookup"><span data-stu-id="abaac-153">Groups</span></span>
[<span data-ttu-id="abaac-154">Intune で Azure Active Directory グループを使用する方法について説明します</span><span class="sxs-lookup"><span data-stu-id="abaac-154">Learn about how you can use Azure Active Directory groups with Intune</span></span>](groups-get-started.md)
### <a name="intune-roles"></a><span data-ttu-id="abaac-155">Intune ロール</span><span class="sxs-lookup"><span data-stu-id="abaac-155">Intune roles</span></span>
<span data-ttu-id="abaac-156">[Intune の各種アクションを実行できるユーザーと、それらのアクションの適用先となるユーザーを制御します](role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-156">[Control who can perform various Intune actions, and who those actions apply to](role-based-access-control.md).</span></span> <span data-ttu-id="abaac-157">一般的な Intune シナリオを対象とする組み込みロールを使用するか、独自のロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="abaac-157">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span>
### <a name="software-updates"></a><span data-ttu-id="abaac-158">ソフトウェア更新プログラム</span><span class="sxs-lookup"><span data-stu-id="abaac-158">Software updates</span></span>
<span data-ttu-id="abaac-159">[Windows 10 デバイスのソフトウェア更新を構成する方法について説明します](windows-update-for-business-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-159">[Learn about how to configure software updates for Windows 10 devices](windows-update-for-business-configure.md).</span></span>



## <a name="whats-new"></a><span data-ttu-id="abaac-160">新機能</span><span class="sxs-lookup"><span data-stu-id="abaac-160">What's new?</span></span>

<span data-ttu-id="abaac-161">[Intune の新機能をご確認ください](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="abaac-161">[Find out what's new in Intune](whats-new.md).</span></span>
