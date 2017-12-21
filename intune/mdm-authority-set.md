---
title: "モバイル デバイス管理機関の設定"
titlesuffix: Azure portal
description: "Intune でモバイル デバイス管理機関を設定する方法について説明します。 \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 581cbc5ef9a6a02deb4e266b0845b95b65215c0f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-the-mobile-device-management-authority"></a><span data-ttu-id="b04f3-104">モバイル デバイス管理機関の設定</span><span class="sxs-lookup"><span data-stu-id="b04f3-104">Set the mobile device management authority</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b04f3-105">モバイル デバイス管理 (MDM) 機関の設定によって、デバイスの管理方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="b04f3-105">The mobile device management (MDM) authority setting determines how you manage your devices.</span></span> <span data-ttu-id="b04f3-106">IT 管理者が MDM 機関を設定してからでないと、ユーザーは管理対象のデバイスを登録できません。</span><span class="sxs-lookup"><span data-stu-id="b04f3-106">As an IT admin, you must set an MDM authority before users can enroll devices for management.</span></span>

<span data-ttu-id="b04f3-107">可能な構成は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b04f3-107">Possible configurations are:</span></span>

- <span data-ttu-id="b04f3-108">**Intune スタンドアロン** - Azure Portal を利用して構成する、クラウドのみの管理。</span><span class="sxs-lookup"><span data-stu-id="b04f3-108">**Intune Standalone** - cloud-only management, which you configure by using the Azure portal.</span></span> <span data-ttu-id="b04f3-109">Intune で提供される機能がすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-109">Includes the full set of capabilities that Intune offers.</span></span> <span data-ttu-id="b04f3-110">[Intune コンソールで MDM 機関を設定](#set-mdm-authority-to-intune)します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-110">[Set the MDM authority in the Intune console](#set-mdm-authority-to-intune).</span></span>

- <span data-ttu-id="b04f3-111">**Intune ハイブリッド** - Intune クラウド ソリューションと System Center Configuration Manager の統合。</span><span class="sxs-lookup"><span data-stu-id="b04f3-111">**Intune Hybrid** - integration of the Intune cloud solution with System Center Configuration Manager.</span></span> <span data-ttu-id="b04f3-112">Configuration Manager コンソールを使用して Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-112">You configure Intune by using the Configuration Manager console.</span></span> <span data-ttu-id="b04f3-113">[Configuration Manager で MDM 機関を設定](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-113">[Set the MDM authority in Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).</span></span>

- <span data-ttu-id="b04f3-114">**Office 365 のモバイル デバイス管理** - Office 365 と Intune クラウド ソリューションの統合。</span><span class="sxs-lookup"><span data-stu-id="b04f3-114">**Mobile Device Management for Office 365** - integration of Office 365 with the Intune cloud solution.</span></span> <span data-ttu-id="b04f3-115">Office 365 管理センターから Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-115">You configure Intune from your Office 365 Admin Center.</span></span> <span data-ttu-id="b04f3-116">Intune スタンドアロンで利用できる機能の一部が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-116">Includes a subset of the capabilities that are available with Intune Standalone.</span></span> <span data-ttu-id="b04f3-117">Office 365 管理センターで MDM 機関を設定します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-117">Set the MDM authority in Office 365 Admin Center.</span></span>

>[!IMPORTANT]    
<span data-ttu-id="b04f3-118">Configuration Manager 1610 以降のバージョンと Microsoft Intune バージョン 1705 では、MDM 機関の変更にあたって Microsoft サポートに問い合わせる必要はありません。また、既存の管理されたデバイスの登録を解除して再登録する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="b04f3-118">In Configuration Manager version 1610 or later and Microsoft Intune version 1705, you change the MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices.</span></span> <span data-ttu-id="b04f3-119">詳細については、「[不適切な MDM 機関の設定を選択した場合の対処方法](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b04f3-119">For details, see [What to do if you choose the wrong MDM authority setting](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span></span>

## <a name="set-mdm-authority-to-intune"></a><span data-ttu-id="b04f3-120">MDM 機関を Intune に設定する</span><span class="sxs-lookup"><span data-stu-id="b04f3-120">Set MDM authority to Intune</span></span>

1. <span data-ttu-id="b04f3-121">[Azure Portal](https://portal.azure.com) で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-121">In the [Azure portal](https://portal.azure.com), choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="b04f3-122">オレンジのバナーを選択し、**[モバイル デバイス管理機関]** 設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-122">Select the orange banner to open the **Mobile Device Management Authority** setting.</span></span>
3. <span data-ttu-id="b04f3-123">**[モバイル デバイス管理機関]** で、次の選択肢から MDM 機関を選択します。</span><span class="sxs-lookup"><span data-stu-id="b04f3-123">Under **Mobile Device Management Authority**, choose your MDM authority from the following options:</span></span>
  - <span data-ttu-id="b04f3-124">**Intune MDM 機関**</span><span class="sxs-lookup"><span data-stu-id="b04f3-124">**Intune MDM Authority**</span></span>
  - <span data-ttu-id="b04f3-125">**Configuration Manager MDM 機関**</span><span class="sxs-lookup"><span data-stu-id="b04f3-125">**Configuration Manager MDM Authority**</span></span>
  - <span data-ttu-id="b04f3-126">**なし**</span><span class="sxs-lookup"><span data-stu-id="b04f3-126">**None**</span></span>

  ![Intune のモバイル デバイス管理機関設定画面のスクリーンショット](media/set-mdm-auth.png)

  <span data-ttu-id="b04f3-128">MDM 機関が Intune に正しく設定されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-128">A message indicates that you have successfully set your MDM authority to Intune.</span></span>

## <a name="enable-device-enrollment"></a><span data-ttu-id="b04f3-129">デバイスの登録を可能にする</span><span class="sxs-lookup"><span data-stu-id="b04f3-129">Enable device enrollment</span></span>

<span data-ttu-id="b04f3-130">Intune が MDM 機関として設定されると、ユーザーは個人所有デバイスを登録し、メールなどのリソースにアクセスできます。それには、ポータル サイトをインストールするか (iOS と Android)、仕事の資格情報を追加するか (Windows)、会社のポータル Web サイトにアクセスします (iOS、Android、macOS)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-130">With Intune set as your MDM authority, users can enroll personally owned devices and gain access to resources like email in the following ways by installing the Company Portal (iOS and Android), adding work credentials (Windows), or accessing the Company Portal website (iOS, Android, macOS).</span></span>

<span data-ttu-id="b04f3-131">登録を有効に、または簡単にするために、各種プラットフォームで次のような要件があります。</span><span class="sxs-lookup"><span data-stu-id="b04f3-131">Different platforms have the following requirements to enable or simplify enrollment:</span></span>
- <span data-ttu-id="b04f3-132">**iOS** - (必須) [Apple MDM プッシュ証明書を取得し](apple-mdm-push-certificate-get.md)、[会社所有 iOS デバイスの登録を有効にします](ios-enroll.md) (任意)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-132">**iOS** - (required) [Get an Apple MDM push certificate](apple-mdm-push-certificate-get.md) and then [enable enrollment for company-owned iOS devices](ios-enroll.md) (optional).</span></span>
- <span data-ttu-id="b04f3-133">**Android** - (任意) [Android の仕事用プロファイルを有効にします](android-enroll.md)。</span><span class="sxs-lookup"><span data-stu-id="b04f3-133">**Android** - (optional) [Enable Android work profiles](android-enroll.md)</span></span>
- <span data-ttu-id="b04f3-134">**Windows** - (任意) [自動登録](windows-enroll.md)または[一括登録](windows-bulk-enroll.md)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b04f3-134">**Windows** - (optional) Enable [Automatic enrollment](windows-enroll.md) or [bulk enrollment](windows-bulk-enroll.md)</span></span>
- <span data-ttu-id="b04f3-135">**macOS** - 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b04f3-135">**macOS** - No requirements</span></span>


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a><span data-ttu-id="b04f3-136">MDM 証明書の有効期限が切れた後のモバイル デバイスのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="b04f3-136">Mobile device cleanup after MDM certificate expiration</span></span>

<span data-ttu-id="b04f3-137">MDM 証明書は、モバイル デバイスが Intune サービスと通信しているときに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-137">The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service.</span></span> <span data-ttu-id="b04f3-138">モバイル デバイスがワイプされたり、一定の時間 Intune サービスとモバイル デバイスが通信できなかったりすると、MDM 証明書は更新されません。</span><span class="sxs-lookup"><span data-stu-id="b04f3-138">If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed.</span></span> <span data-ttu-id="b04f3-139">デバイスは、MDM 証明書の有効期限が切れてから 180 日後に、Azure Portal から削除されます。</span><span class="sxs-lookup"><span data-stu-id="b04f3-139">The device is removed from the Azure portal 180 days after the MDM certificate expires.</span></span>
