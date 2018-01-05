---
title: "Intune Wi-Fi 設定を構成する方法"
titleSuffix: Azure portal
description: "Intune を使用して、管理対象デバイスの Wi-Fi 接続を構成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f42d12ddcfc0e2eef8d99102cebae460cdcb29bb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a><span data-ttu-id="18b4b-103">Microsoft Intune で Wi-Fi の設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="18b4b-103">How to configure Wi-Fi settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="18b4b-104">Microsoft Intune の Wi-Fi プロファイルを使用して、ワイヤレス ネットワーク設定を組織のユーザーとデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-104">Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization.</span></span> <span data-ttu-id="18b4b-105">Wi-Fi プロファイルを割り当てた場合、ユーザーはプロファイルを構成することなく、会社の Wi-Fi ネットワークにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-105">When you assign a Wi-Fi profile, your users will have access to your corporate Wi-Fi network without having to configure it themselves.</span></span>

<span data-ttu-id="18b4b-106">たとえば、Contoso Wi-Fi という名前の新しい Wi-Fi ネットワークをインストールし、すべての iOS デバイスがこのネットワークに接続するように設定するとします。</span><span class="sxs-lookup"><span data-stu-id="18b4b-106">For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network.</span></span> <span data-ttu-id="18b4b-107">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18b4b-107">Here's the process:</span></span>

1. <span data-ttu-id="18b4b-108">Contoso Wi-Fi ワイヤレス ネットワークへの接続に必要な設定が含まれている Wi-Fi プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-108">Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.</span></span>
2. <span data-ttu-id="18b4b-109">iOS デバイスのすべてのユーザーを含むグループにそのプロファイルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-109">Assign the profile to a group containing all users of iOS devices.</span></span>
3. <span data-ttu-id="18b4b-110">ユーザーは、自分のデバイスでワイヤレス ネットワークの一覧にある新しい Contoso Wi-Fi ネットワークを見つけ、このネットワークに簡単に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="18b4b-110">Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.</span></span>

<span data-ttu-id="18b4b-111">Wi-Fi プロファイルでは次のデバイス プラットフォームをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="18b4b-111">Wi-Fi profiles support the following device platforms:</span></span>

- <span data-ttu-id="18b4b-112">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="18b4b-112">Android 4 and later</span></span>
- <span data-ttu-id="18b4b-113">Android for Work</span><span class="sxs-lookup"><span data-stu-id="18b4b-113">Android for Work</span></span>
- <span data-ttu-id="18b4b-114">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="18b4b-114">iOS 8.0 and later</span></span>
- <span data-ttu-id="18b4b-115">macOS (Mac OS X 10.9 以降)</span><span class="sxs-lookup"><span data-stu-id="18b4b-115">macOS (Mac OS X 10.9 and later)</span></span>

<span data-ttu-id="18b4b-116">Windows 8.1、Windows 10、および Windows 10 Mobile を実行しているデバイスの場合は、以前に別のデバイスからエクスポートした Wi-Fi 構成をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-116">For devices running Windows 8.1, Windows 10, and Windows 10 Mobile, you can import a Wi-Fi configuration that was previously exported from another device.</span></span>

<span data-ttu-id="18b4b-117">このトピックでは、Wi-Fi プロファイルを構成する基本的な方法について説明します。その後、デバイスごとの詳細については、各プラットフォームのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4b-117">Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-wi-fi-settings"></a><span data-ttu-id="18b4b-118">Wi-Fi 設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="18b4b-118">Create a device profile containing Wi-Fi settings</span></span>

1. <span data-ttu-id="18b4b-119">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="18b4b-119">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="18b4b-120">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-120">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="18b4b-121">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-121">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="18b4b-122">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-122">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="18b4b-123">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-123">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="18b4b-124">**[プロファイルを作成します]** ブレードで、Wi-Fi プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-124">On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.</span></span>
5. <span data-ttu-id="18b4b-125">**[プラットフォーム]** ドロップダウン リストで、Wi-Fi 設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-125">From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings.</span></span> <span data-ttu-id="18b4b-126">現時点では、Wi-Fi 設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-126">Currently, you can choose one of the following platforms for Wi-Fi settings:</span></span>
    - <span data-ttu-id="18b4b-127">**Android**</span><span class="sxs-lookup"><span data-stu-id="18b4b-127">**Android**</span></span>
    - <span data-ttu-id="18b4b-128">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="18b4b-128">**Android for Work**</span></span>
    - <span data-ttu-id="18b4b-129">**iOS**</span><span class="sxs-lookup"><span data-stu-id="18b4b-129">**iOS**</span></span>
    - <span data-ttu-id="18b4b-130">**macOS**</span><span class="sxs-lookup"><span data-stu-id="18b4b-130">**macOS**</span></span>
    - <span data-ttu-id="18b4b-131">**Windows 8.1 以降 (プロファイルのインポート)**</span><span class="sxs-lookup"><span data-stu-id="18b4b-131">**Windows 8.1 and later (import a profile)**</span></span>
6. <span data-ttu-id="18b4b-132">**[プロファイルの種類]** ドロップダウン リストで、**[Wi-Fi Basic]** または **[Wi-Fi Enterprise]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18b4b-132">From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.</span></span> <span data-ttu-id="18b4b-133">**[Wi-Fi Basic]** を使用し、ネットワーク名や SSID などの基本的な機能を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-133">You can use **Wi-fi basic** to supply basic features like the network name, and the SSID.</span></span> <span data-ttu-id="18b4b-134">**[Wi-Fi Enterprise]** を使用すると、詳細情報 (たとえば、Wi-Fi ネットワークで拡張認証プロトコル (EAP) を使用している場合は EPA) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-134">**Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this.</span></span> <span data-ttu-id="18b4b-135">**[Wi-Fi インポート]** (Windows 8.1 および Windows 10) を使用すると、以前に別のデバイスからエクスポートした Wi-Fi 設定を XML ファイルとしてインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-135">**Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previously exported from a different device.</span></span>
7. <span data-ttu-id="18b4b-136">選択したプラットフォームによって構成できる設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="18b4b-136">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="18b4b-137">各プラットフォームの詳細な設定については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4b-137">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="18b4b-138">Android と Android for Work の設定</span><span class="sxs-lookup"><span data-stu-id="18b4b-138">Android and Android for Work settings</span></span>](wi-fi-settings-android.md)
    - [<span data-ttu-id="18b4b-139">iOS の設定</span><span class="sxs-lookup"><span data-stu-id="18b4b-139">iOS settings</span></span>](wi-fi-settings-ios.md)
    - [<span data-ttu-id="18b4b-140">macOS の設定</span><span class="sxs-lookup"><span data-stu-id="18b4b-140">macOS settings</span></span>](wi-fi-settings-macos.md)
    - [<span data-ttu-id="18b4b-141">Windows Phone 8.1 の設定</span><span class="sxs-lookup"><span data-stu-id="18b4b-141">Windows Phone 8.1 settings</span></span>](wi-fi-settings-import-windows-8-1.md)
8. <span data-ttu-id="18b4b-142">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18b4b-142">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="18b4b-143">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="18b4b-143">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="18b4b-144">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18b4b-144">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
