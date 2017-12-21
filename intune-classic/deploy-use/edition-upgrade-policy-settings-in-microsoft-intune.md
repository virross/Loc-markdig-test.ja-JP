---
title: "Windows エディションのアップグレード ポリシー設定"
description: "Intune を使用して Windows 10 デバイスを別のバージョンに自動的にアップグレードする方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0e9b77ae9e6b58294d14c841c1ed32aaad501b18
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a><span data-ttu-id="ebaa0-103">Microsoft Intune のエディションのアップグレード ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="ebaa0-103">Windows edition upgrade policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ebaa0-104">Microsoft Intune の**エディションのアップグレード ポリシー**を使用して、次に挙げる Windows 10 のバージョンのいずれかを実行するデバイスを自動的に別のエディションにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-104">The Microsoft Intune **Edition Upgrade Policy** lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>
* <span data-ttu-id="ebaa0-105">[Windows] 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="ebaa0-105">Windows 10 Desktop</span></span>
* <span data-ttu-id="ebaa0-106">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="ebaa0-106">Windows 10 Holographic</span></span>
* <span data-ttu-id="ebaa0-107">[Windows] 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-107">Windows 10 Mobile</span></span>

<span data-ttu-id="ebaa0-108">次のアップグレード パスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-108">The following upgrade paths are supported:</span></span>
- <span data-ttu-id="ebaa0-109">Windows 10 Pro から Windows 10 Enterprise へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="ebaa0-109">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="ebaa0-110">Windows 10 Home から Windows 10 Education へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="ebaa0-110">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="ebaa0-111">Windows 10 Mobile から Windows 10 Mobile Enterprise へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="ebaa0-111">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="ebaa0-112">Windows 10 Holographic Pro から Windows 10 Holographic Enterprise へのアップグレード パス</span><span class="sxs-lookup"><span data-stu-id="ebaa0-112">From Windows 10 Holographic Pro to Windows 10 Holographic Enterprise</span></span>

## <a name="before-you-start"></a><span data-ttu-id="ebaa0-113">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="ebaa0-113">Before you start</span></span>
<span data-ttu-id="ebaa0-114">デバイスを最新バージョンにアップグレードし始める前に、次のいずれかを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-114">Before you begin to upgrade devices to the latest version, you will need one of the following:</span></span>
* <span data-ttu-id="ebaa0-115">ポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするための有効なプロダクト キー (Windows 10 Desktop エディションの場合)。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-115">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="ebaa0-116">マルチ ライセンス認証キー (MAK) またはキー マネジメント サーバー (KMS) キーのどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-116">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys.</span></span>
<span data-ttu-id="ebaa0-117">**または、**ポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするためのライセンス情報を含む、Microsoft からのライセンス ファイル (Windows 10 Mobile エディションと Windows 10 Holographic エディションの場合)。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-117">**or** A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
* <span data-ttu-id="ebaa0-118">対象とする Windows 10 デバイスが Microsoft Intune に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-118">The Windows 10 devices that you target must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="ebaa0-119">エディションのアップグレード ポリシーは、Intune PC クライアント ソフトウェアを実行する PC で使用できません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-119">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <a name="edition-upgrade-policy-settings"></a><span data-ttu-id="ebaa0-120">エディションのアップグレード ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="ebaa0-120">Edition upgrade policy settings</span></span>

|<span data-ttu-id="ebaa0-121">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ebaa0-121">Setting name</span></span>|<span data-ttu-id="ebaa0-122">説明</span><span class="sxs-lookup"><span data-stu-id="ebaa0-122">Details</span></span>|
|-|-|
|<span data-ttu-id="ebaa0-123">**名前**</span><span class="sxs-lookup"><span data-stu-id="ebaa0-123">**Name**</span></span>|<span data-ttu-id="ebaa0-124">エディションのアップグレード ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-124">Enter a name for the edition upgrade policy.</span></span>|
|<span data-ttu-id="ebaa0-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="ebaa0-125">**Description**</span></span>|<span data-ttu-id="ebaa0-126">必要に応じて、Intune コンソールでの識別に役立つポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-126">Optionally, enter a description for the policy that helps you identify it in the Intune console.</span></span>
|<span data-ttu-id="ebaa0-127">**アップグレード後のエディション**</span><span class="sxs-lookup"><span data-stu-id="ebaa0-127">**Edition to upgrade to**</span></span>|<span data-ttu-id="ebaa0-128">対象とするデバイスのアップグレード後の Windows 10 Desktop、Windows 10 Holographic、または Windows 10 Mobile のバージョンをドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-128">From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
|<span data-ttu-id="ebaa0-129">**プロダクト キー**</span><span class="sxs-lookup"><span data-stu-id="ebaa0-129">**Product Key**</span></span>|<span data-ttu-id="ebaa0-130">Microsoft から取得した、対象とするすべての Windows 10 デスクトップ デバイスをアップグレードするために使用できるプロダクト キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-130">Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="ebaa0-131">プロダクト キーを含むポリシーを作成した後でプロダクト キーを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-131">After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="ebaa0-132">これは、セキュリティ上の理由からキーが隠されるためです。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-132">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="ebaa0-133">プロダクト キーを変更するには、キー全体を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-133">To change the product key, you must enter the entire key again.</span></span>
|<span data-ttu-id="ebaa0-134">**ライセンス ファイル**</span><span class="sxs-lookup"><span data-stu-id="ebaa0-134">**License File**</span></span>|<span data-ttu-id="ebaa0-135">**[参照]** を選択し、Microsoft から取得した、対象とするデバイスのアップグレード後の Windows Holographic、または Windows 10 Mobile エディション用のライセンス情報を含むライセンス ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebaa0-135">Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>

### <a name="see-also"></a><span data-ttu-id="ebaa0-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebaa0-136">See also</span></span>
[<span data-ttu-id="ebaa0-137">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="ebaa0-137">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
