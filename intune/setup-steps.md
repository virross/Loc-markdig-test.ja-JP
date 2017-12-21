---
title: "Intune をセットアップする"
description: "Intune サブスクリプションの使用を開始するための要件と前提条件"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a95f05bb36746acbdd4824acd27ea2320d8f0177
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-intune"></a><span data-ttu-id="ed7c4-103">Intune をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ed7c4-103">Set up Intune</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="ed7c4-104">このセットアップで、モバイル デバイス管理 (MDM) を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-104">These set-up steps help you enable mobile device management (MDM).</span></span> <span data-ttu-id="ed7c4-105">会社のリソースにアクセスする許可をユーザーに与える前に、あるいはデバイスの設定を管理する前に、デバイスを管理対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-105">Devices must be managed before you can give users access to company resources or manage settings on those devices.</span></span>

<span data-ttu-id="ed7c4-106">Intune サブスクリプションの設定や MDM 権限の設定など、一部の手順はほとんどのシナリオで必須となります。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-106">Some steps, such as setting up an Intune subscription and setting the MDM authority, are required for most scenarios.</span></span> <span data-ttu-id="ed7c4-107">カスタム ドメインの構成やアプリの追加など、その他の手順が必要かどうかは会社次第です。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-107">Other steps, such as configuring a custom domain or adding apps, are optional depending upon your company's needs.</span></span>

<span data-ttu-id="ed7c4-108">現在コンピューターとサーバーの管理に Microsoft System Center Configuration Manager を使用している場合は、[Configuration Manager を拡張してモバイル デバイスを管理する](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)ことができます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-108">If you're currently using Microsoft System Center Configuration Manager to manage computers and servers, you can [extend Configuration Manager to manage mobile devices](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).</span></span>

>[!TIP]
><span data-ttu-id="ed7c4-109">対象となるプランで Intune のライセンスを 150 以上購入した場合は、*FastTrack センター特典*をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-109">If you purchase at least 150 licenses for Intune in an eligible plan, you can use the *FastTrack Center Benefit*.</span></span> <span data-ttu-id="ed7c4-110">このサービスでは、Microsoft のスペシャリストが Intune 用の環境の準備をお手伝いします。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-110">With this service, Microsoft specialists work with you to get your environment ready for Intune.</span></span> <span data-ttu-id="ed7c4-111">「[Enterprise Mobility + Security (EMS) 用の FastTrack センター特典](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-111">See [FastTrack Center Benefit for Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).</span></span>



| <span data-ttu-id="ed7c4-112">手順</span><span class="sxs-lookup"><span data-stu-id="ed7c4-112">Steps</span></span> | <span data-ttu-id="ed7c4-113">状態</span><span class="sxs-lookup"><span data-stu-id="ed7c4-113">Status</span></span>  |
| ------------- |-------------|
| <span data-ttu-id="ed7c4-114">1</span><span class="sxs-lookup"><span data-stu-id="ed7c4-114">1</span></span>  | <span data-ttu-id="ed7c4-115">[サポートされる構成](supported-devices-browsers.md) - 開始前に知っておく必要がある情報です。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-115">[Supported configurations](supported-devices-browsers.md) - Need-to-know info before you start.</span></span> <span data-ttu-id="ed7c4-116">サポートされる構成やネットワーク要件などです。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-116">This includes supported configurations and networking requirements.</span></span>|
| <span data-ttu-id="ed7c4-117">2</span><span class="sxs-lookup"><span data-stu-id="ed7c4-117">2</span></span> |  <span data-ttu-id="ed7c4-118">[Intune にサインインする](account-sign-up.md) - 試用版サブスクリプションにサインインするか、新しい Intune サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-118">[Sign in to Intune](account-sign-up.md) - Sign in to your trial subscription or create a new Intune subscription.</span></span> |  
| <span data-ttu-id="ed7c4-119">3</span><span class="sxs-lookup"><span data-stu-id="ed7c4-119">3</span></span> | <span data-ttu-id="ed7c4-120">[ドメイン名を構成する](custom-domain-name-configure.md) - 会社のドメイン名を Intune と接続するために DNS の登録を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-120">[Configure domain name](custom-domain-name-configure.md) - Set DNS registration to connect your company's domain name with Intune.</span></span> <span data-ttu-id="ed7c4-121">Intune に接続し、リソースを利用するとき、なじみのあるドメインがユーザーに与えられます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-121">This gives users a familiar domain when connecting to Intune and using resources.</span></span>  |
| <span data-ttu-id="ed7c4-122">4</span><span class="sxs-lookup"><span data-stu-id="ed7c4-122">4</span></span> | <span data-ttu-id="ed7c4-123">[ユーザーを追加する](users-add.md) - 手動でユーザーを追加するか、Active Directory を接続して Intune とユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-123">[Add users](users-add.md) - Manually add users or connect Active Directory to sync users with Intune.</span></span> <span data-ttu-id="ed7c4-124">デバイスがたとえば "ユーザーなし" のキオスク デバイスでない限り、必須となります。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-124">Required unless your devices are "userless" kiosk devices, for example.</span></span> |
| <span data-ttu-id="ed7c4-125">5</span><span class="sxs-lookup"><span data-stu-id="ed7c4-125">5</span></span> | <span data-ttu-id="ed7c4-126">[ライセンスを割り当てる](licenses-assign.md) - Intune を使用するためのアクセス許可をユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-126">[Assign licenses](licenses-assign.md) - Give users permission to use Intune.</span></span> <span data-ttu-id="ed7c4-127">サービスにアクセスするには、ユーザーまたはユーザーレス デバイスごとに Intune ライセンスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-127">Each user or userless device requires an Intune license to access the service.</span></span>|
| <span data-ttu-id="ed7c4-128">6</span><span class="sxs-lookup"><span data-stu-id="ed7c4-128">6</span></span> |  <span data-ttu-id="ed7c4-129">[グループを追加する](groups-add.md) - ユーザー グループとデバイス グループを使って管理タスクを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-129">[Add groups](groups-add.md) - Use user and device groups to simplify management tasks.</span></span> <span data-ttu-id="ed7c4-130">アプリ、設定、その他のリソースを割り当てるためにグループが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-130">Groups are used to assign apps, settings, and other resources.</span></span> |
| <span data-ttu-id="ed7c4-131">7</span><span class="sxs-lookup"><span data-stu-id="ed7c4-131">7</span></span> | <span data-ttu-id="ed7c4-132">[アプリを追加する](apps-add.md) - アプリはグループに割り当て、自動的に、あるいは任意でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-132">[Add apps](apps-add.md) - Apps can be assigned to groups and automatically or optionally installed.</span></span> |
| <span data-ttu-id="ed7c4-133">8</span><span class="sxs-lookup"><span data-stu-id="ed7c4-133">8</span></span> | <span data-ttu-id="ed7c4-134">[デバイスを構成する](device-profiles.md) - デバイス設定を管理するプロファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-134">[Configure devices](device-profiles.md) - Set up profiles that manage device settings.</span></span> <span data-ttu-id="ed7c4-135">デバイス プロファイルでは、電子メール、VPN、Wi-Fi、デバイス機能の設定を事前構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-135">Device profiles can preconfigure settings for email, VPN, Wi-Fi, and device features.</span></span> <span data-ttu-id="ed7c4-136">デバイスを制限し、デバイスとデータの両方を保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-136">They can also restrict devices to help protect both devices and data.</span></span>  |
| <span data-ttu-id="ed7c4-137">9</span><span class="sxs-lookup"><span data-stu-id="ed7c4-137">9</span></span> | <span data-ttu-id="ed7c4-138">[ポータル サイトをカスタマイズする](company-portal-app.md) - ユーザーがデバイスの登録とアプリのインストールに使用する Intune ポータル サイトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-138">[Customize Company Portal](company-portal-app.md) - Customize the Intune Company Portal that users use to enroll devices and install apps.</span></span> <span data-ttu-id="ed7c4-139">これらの設定は、ポータル サイト アプリと Intune ポータル サイト Web サイトの両方に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-139">These settings appear in both the Company Portal app and the Intune Company Portal website.</span></span> |
| <span data-ttu-id="ed7c4-140">10</span><span class="sxs-lookup"><span data-stu-id="ed7c4-140">10</span></span> | <span data-ttu-id="ed7c4-141">[デバイス登録を有効にする](mdm-authority-set.md) - MDM 権限を設定し、特定のプラットフォームを有効にすることで、iOS、Windows、Android、Mac デバイスの Intune 管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed7c4-141">[Enable device enrollment](mdm-authority-set.md) - Enable Intune management of iOS, Windows, Android, and Mac devices by setting the MDM authority and enabling specific platforms.</span></span> |
