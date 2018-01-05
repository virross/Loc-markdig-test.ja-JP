---
title: "Microsoft Intune でカスタム VPN プロファイルを作成する方法"
titleSuffix: Azure portal
description: "Intune でカスタム構成を使用して VPN プロファイルを作成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec51848fb5145b8bf89370b78b62d8668fcb0092
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a><span data-ttu-id="cab6c-103">Microsoft Intune でカスタム VPN プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cab6c-103">How to create custom VPN profiles in Microsoft Intune</span></span>

## <a name="create-a-custom-configuration"></a><span data-ttu-id="cab6c-104">カスタム構成を作成する</span><span class="sxs-lookup"><span data-stu-id="cab6c-104">Create a custom configuration</span></span>
<span data-ttu-id="cab6c-105">Intune のカスタム構成ポリシーを使用して、以下の VPN プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cab6c-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="cab6c-106">Android 4 以降が実行されているデバイス</span><span class="sxs-lookup"><span data-stu-id="cab6c-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="cab6c-107">Windows 8.1 以降を実行する登録済みのデバイス</span><span class="sxs-lookup"><span data-stu-id="cab6c-107">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="cab6c-108">Windows Phone 8.1 以降が実行されているデバイス</span><span class="sxs-lookup"><span data-stu-id="cab6c-108">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="cab6c-109">Windows 10 デスクトップを実行する登録済みのデバイス</span><span class="sxs-lookup"><span data-stu-id="cab6c-109">Enrolled devices that run Windows 10 desktop</span></span> 
* <span data-ttu-id="cab6c-110">Windows 10 Mobile を実行するデバイス</span><span class="sxs-lookup"><span data-stu-id="cab6c-110">Devices that run Windows 10 Mobile</span></span>

<span data-ttu-id="cab6c-111">この種のポリシーは、標準的な Intune VPN ポリシーに、使用する設定が含まれていない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cab6c-111">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <a name="to-create-a-custom-configuration-policy"></a><span data-ttu-id="cab6c-112">カスタム構成ポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="cab6c-112">To create a custom configuration policy:</span></span>

1. <span data-ttu-id="cab6c-113">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cab6c-113">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="cab6c-114">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-114">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="cab6c-115">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-115">On the **Intune** blade, choose **Device configuration**.</span></span>
4. <span data-ttu-id="cab6c-116">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-116">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5. <span data-ttu-id="cab6c-117">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-117">On the profiles blade, choose **Create Profile**.</span></span>
6. <span data-ttu-id="cab6c-118">**[プロファイルを作成します]** ブレードで、VPN プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-118">On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.</span></span>
7. <span data-ttu-id="cab6c-119">**[プラットフォーム]** ドロップダウン リストで、VPN 設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-119">From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings.</span></span> <span data-ttu-id="cab6c-120">現時点では、カスタム デバイス設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cab6c-120">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="cab6c-121">**Android**</span><span class="sxs-lookup"><span data-stu-id="cab6c-121">**Android**</span></span>
    - <span data-ttu-id="cab6c-122">**iOS** (Apple Configurator からエクスポートしたファイルを使用して構成済み)。</span><span class="sxs-lookup"><span data-stu-id="cab6c-122">**iOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="cab6c-123">**macOS** (Apple Configurator からエクスポートしたファイルを使用して構成済み)。</span><span class="sxs-lookup"><span data-stu-id="cab6c-123">**macOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="cab6c-124">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="cab6c-124">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="cab6c-125">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="cab6c-125">**Windows 10 and later**</span></span>
6. <span data-ttu-id="cab6c-126">**[プロファイルの種類]** ドロップダウン リストで、**[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-126">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="cab6c-127">**[OMA-URI のカスタム設定]** ブレードで、指定する URI 設定ごとに **[追加]** を選択し、必要な情報を入力して、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-127">On the **Custom OMA-URI Settings** blade, for each URI setting you want to specify, choose **Add**, provide the requested information, then choose **OK**.</span></span> <span data-ttu-id="cab6c-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-128">Here's an example:</span></span>

   ![VPN プロファイルのカスタム構成ダイアログ ボックス](./media/Intune_Add_VPN_URI.png)

4.  <span data-ttu-id="cab6c-130">必要な URI 設定をすべて入力したら **[OK]** を選択し、**[プロファイルを作成します]** ブレードで **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cab6c-130">After you've entered all of URI settings you need, choose **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="cab6c-131">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cab6c-131">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="cab6c-132">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cab6c-132">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>




