---
title: "Intune で Windows 10 エディションのアップグレードを構成する"
titlesuffix: Azure portal
description: "Intune を使用して、管理対象の Windows 10 デバイスを別のエディションにアップグレードする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 408cb88cabe96ad1226c4189bd1337ec95ba8d37
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a><span data-ttu-id="e741f-103">Microsoft Intune で Windows 10 エディションのアップグレードを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e741f-103">How to configure Windows 10 edition upgrades in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="e741f-104">このトピックでは、Windows 10 エディションのアップグレード プロファイルを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e741f-104">Use the information in this topic to learn how to configure a Windows 10 edition upgrade profile.</span></span> <span data-ttu-id="e741f-105">このプロファイルを使用して、次に挙げる Windows 10 のバージョンのいずれかを実行するデバイスを自動的に別のエディションにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="e741f-105">This profile lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>

- <span data-ttu-id="e741f-106">Windows 10 Home</span><span class="sxs-lookup"><span data-stu-id="e741f-106">Windows 10 Home</span></span>
- <span data-ttu-id="e741f-107">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="e741f-107">Windows 10 Holographic</span></span>
- <span data-ttu-id="e741f-108">[Windows] 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="e741f-108">Windows 10 Mobile</span></span>


<span data-ttu-id="e741f-109">次のアップグレード パスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e741f-109">The following upgrade paths are supported:</span></span>

- <span data-ttu-id="e741f-110">Windows 10 Pro から Windows 10 Enterprise へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="e741f-110">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="e741f-111">Windows 10 Home から Windows 10 Education へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="e741f-111">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="e741f-112">Windows 10 Mobile から Windows 10 Mobile Enterprise へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="e741f-112">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="e741f-113">Windows 10 Holographic windows 10 Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="e741f-113">From Windows 10 Holographic to Windows 10 Holographic for Business</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e741f-114">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="e741f-114">Before you start</span></span>
<span data-ttu-id="e741f-115">デバイスを最新バージョンにアップグレードし始める前に、次のいずれかを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e741f-115">Before you begin to upgrade devices to the latest version, you need one of:</span></span>

- <span data-ttu-id="e741f-116">ポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするための有効なプロダクト キー (Windows 10 Desktop エディションの場合)。</span><span class="sxs-lookup"><span data-stu-id="e741f-116">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="e741f-117">マルティプル アクティベーション キー (MAK)、キー マネジメント サーバー (KMS) キー、またはポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするためのライセンス情報を含む、Microsoft からのライセンス ファイル (Windows 10 Mobile エディションと Windows 10 Holographic エディションの場合) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e741f-117">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys or A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
- <span data-ttu-id="e741f-118">ポリシーを割り当てる Windows 10 デバイスが、Microsoft Intune に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e741f-118">The Windows 10 devices to which you assign the policy must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="e741f-119">エディションのアップグレード ポリシーは、Intune PC クライアント ソフトウェアを実行する PC で使用できません。</span><span class="sxs-lookup"><span data-stu-id="e741f-119">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <a name="create-a-device-profile-containing-device-restriction-settings"></a><span data-ttu-id="e741f-120">デバイスの制限設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e741f-120">Create a device profile containing device restriction settings</span></span>

1. <span data-ttu-id="e741f-121">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e741f-121">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="e741f-122">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-122">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="e741f-123">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-123">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="e741f-124">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-124">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="e741f-125">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-125">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="e741f-126">**[プロファイルを作成します]** ブレードで、エディションのアップグレード プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="e741f-126">On the **Create Profile** blade, enter a **Name** and **Description** for the edition upgrade profile.</span></span>
5. <span data-ttu-id="e741f-127">**[プラットフォーム]** ドロップダウン リストで、**[Windows 10 以降]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-127">From the **Platform** drop-down list, choose **Windows 10 and later**.</span></span>
6. <span data-ttu-id="e741f-128">**[プロファイルの種類]** ドロップダウン リストで、**[エディションのアップグレード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-128">From the **Profile type** drop-down list, choose **Edition upgrade**.</span></span>
7. <span data-ttu-id="e741f-129">**[エディションのアップグレード]** ブレードで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e741f-129">On the **Edition Upgrade** blade, configure the following settings:</span></span>
    - <span data-ttu-id="e741f-130">**[アップグレードのターゲット エディション]** - 対象のデバイスのアップグレード先となる Windows 10 Desktop、Windows 10 Holographic、または Windows 10 Mobile のバージョンをドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="e741f-130">**Edition to upgrade to** - From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
    - <span data-ttu-id="e741f-131">**[プロダクト キー]** - Microsoft から取得した、対象とするすべての Windows 10 デスクトップ デバイスをアップグレードするために使用できるプロダクト キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e741f-131">**Product Key** - Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="e741f-132">プロダクト キーを含むポリシーを作成した後でプロダクト キーを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="e741f-132">.After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="e741f-133">これは、セキュリティ上の理由からキーが隠されるためです。</span><span class="sxs-lookup"><span data-stu-id="e741f-133">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="e741f-134">プロダクト キーを変更するには、キー全体を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e741f-134">To change the product key, you must enter the entire key again.</span></span>
    - <span data-ttu-id="e741f-135">**[ライセンス ファイル]** - **[参照]** を選択し、Microsoft から取得した、対象とするデバイスのアップグレード後の Windows Holographic、または Windows 10 Mobile エディション用のライセンス情報を含むライセンス ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e741f-135">**License File** - Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>
8. <span data-ttu-id="e741f-136">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e741f-136">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="e741f-137">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e741f-137">The profile is created and appears on the profiles list blade.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e741f-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e741f-138">Next steps</span></span>

<span data-ttu-id="e741f-139">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e741f-139">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

>[!NOTE]
><span data-ttu-id="e741f-140">後でポリシーの割り当てを削除する場合、デバイス上の Windows のバージョンは元に戻されず、正常に機能を続けます。</span><span class="sxs-lookup"><span data-stu-id="e741f-140">If you later remove the policy assignment, the version of Windows on the device is not reverted, and continues to function normally.</span></span>

