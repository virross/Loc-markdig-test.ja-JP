---
title: "会社のリソースへのアクセスを有効にする"
description: "Wi-Fi、VPN、電子メール プロファイルを使用すると、ユーザーは必要なファイルとリソースにアクセスできます。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f15429fe61e08eb9a23123341b5ab8ce70a77e77
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enable-access-to-company-resources-with-microsoft-intune"></a><span data-ttu-id="97a11-103">Microsoft Intune を使用して、会社のリソースへのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="97a11-103">Enable access to company resources with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="97a11-104">Microsoft Intune Wi-Fi、VPN、電子メール プロファイルを使用すると、ユーザーはどこにいても仕事を遂行するために必要なファイルとリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97a11-104">Microsoft Intune Wi-Fi, VPN, and email profiles work together to help your users gain access to the files and resources that they need to do their work wherever they are.</span></span> <span data-ttu-id="97a11-105">証明書プロファイルは、そのようなアクセスをセキュリティで保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97a11-105">Certificate profiles help secure that access.</span></span>

## <a name="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="97a11-106">[Wi-Fi プロファイル](wi-fi-connections-in-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="97a11-106">[Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md) and supported platforms</span></span>

<span data-ttu-id="97a11-107">ワイヤレス ネットワークの設定をユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="97a11-107">Deploy wireless network settings to your users.</span></span> <span data-ttu-id="97a11-108">これらの設定により、ユーザーは企業ネットワークに簡単に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="97a11-108">These settings make it easy for your users to connect to the corporate network.</span></span>
#### <a name="supported-platforms"></a><span data-ttu-id="97a11-109">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="97a11-109">Supported platforms</span></span>

|<span data-ttu-id="97a11-110">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-110">Windows 8.1 and later</span></span>|<span data-ttu-id="97a11-111">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-111">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="97a11-112">iOS</span><span class="sxs-lookup"><span data-stu-id="97a11-112">iOS</span></span>|<span data-ttu-id="97a11-113">Android</span><span class="sxs-lookup"><span data-stu-id="97a11-113">Android</span></span>|<span data-ttu-id="97a11-114">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="97a11-114">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="97a11-115">○ (Windows Wi-Fi プロファイルをインポートできます)</span><span class="sxs-lookup"><span data-stu-id="97a11-115">Yes (You can import a Windows Wi-Fi profile.)</span></span>|<span data-ttu-id="97a11-116">○ (OMA-URI を構成できます)</span><span class="sxs-lookup"><span data-stu-id="97a11-116">Yes (You can configure OMA-URI.)</span></span> |<span data-ttu-id="97a11-117">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-117">Yes</span></span>|<span data-ttu-id="97a11-118">○</span><span class="sxs-lookup"><span data-stu-id="97a11-118">Yes</span></span>|<span data-ttu-id="97a11-119">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-119">Yes</span></span>|

## <a name="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="97a11-120">[VPN プロファイル](vpn-connections-in-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="97a11-120">[VPN profiles](vpn-connections-in-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="97a11-121">仮想プライベート ネットワーク (VPN) の設定をユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="97a11-121">Deploy virtual private network (VPN) settings to your users.</span></span> <span data-ttu-id="97a11-122">これらの設定により、ユーザーは企業ネットワーク上のリソースに簡単に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="97a11-122">These settings make it easy for users to connect to resources on the corporate network.</span></span>

|<span data-ttu-id="97a11-123">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-123">Windows 8.1 and later</span></span>|<span data-ttu-id="97a11-124">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-124">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="97a11-125">iOS</span><span class="sxs-lookup"><span data-stu-id="97a11-125">iOS</span></span>|<span data-ttu-id="97a11-126">Android</span><span class="sxs-lookup"><span data-stu-id="97a11-126">Android</span></span>|<span data-ttu-id="97a11-127">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="97a11-127">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="97a11-128">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-128">Yes</span></span>|<span data-ttu-id="97a11-129">○</span><span class="sxs-lookup"><span data-stu-id="97a11-129">Yes</span></span>|<span data-ttu-id="97a11-130">○</span><span class="sxs-lookup"><span data-stu-id="97a11-130">Yes</span></span>|<span data-ttu-id="97a11-131">○</span><span class="sxs-lookup"><span data-stu-id="97a11-131">Yes</span></span>|<span data-ttu-id="97a11-132">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-132">Yes</span></span>|

## <a name="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="97a11-133">[電子メール プロファイル](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="97a11-133">[Email profiles](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="97a11-134">組織のデバイスに対するネイティブ電子メール クライアント設定を作成、展開、監視します。</span><span class="sxs-lookup"><span data-stu-id="97a11-134">Create, deploy, and monitor native email client settings on devices in your organization.</span></span>

|<span data-ttu-id="97a11-135">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-135">Windows 8.1 and later</span></span>|<span data-ttu-id="97a11-136">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-136">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="97a11-137">iOS</span><span class="sxs-lookup"><span data-stu-id="97a11-137">iOS</span></span>|<span data-ttu-id="97a11-138">Android</span><span class="sxs-lookup"><span data-stu-id="97a11-138">Android</span></span>|<span data-ttu-id="97a11-139">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="97a11-139">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="97a11-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="97a11-140">No</span></span>|<span data-ttu-id="97a11-141">○</span><span class="sxs-lookup"><span data-stu-id="97a11-141">Yes</span></span>|<span data-ttu-id="97a11-142">○</span><span class="sxs-lookup"><span data-stu-id="97a11-142">Yes</span></span>|<span data-ttu-id="97a11-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="97a11-143">No</span></span>|<span data-ttu-id="97a11-144">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-144">Yes</span></span>|
> [!NOTE]
> <span data-ttu-id="97a11-145">OMA-URI を使用する Windows Phone 8.1 Wi-Fi プロファイルを構成する方法については、[この Intune チームのブログの投稿](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a11-145">[This Intune team blog post](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) gives information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.</span></span>

## <a name="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms"></a><span data-ttu-id="97a11-146">[証明書プロファイル](secure-resource-access-with-certificate-profiles.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="97a11-146">[Certificate profiles](secure-resource-access-with-certificate-profiles.md) and supported platforms</span></span>
<span data-ttu-id="97a11-147">ワイヤレス ネットワークや VPN 接続など、会社のリソースに対するアクセスをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="97a11-147">Help secure access to company resources including wireless networks and VPN connections.</span></span>

|<span data-ttu-id="97a11-148">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-148">Windows 8.1 and later</span></span>|<span data-ttu-id="97a11-149">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="97a11-149">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="97a11-150">iOS</span><span class="sxs-lookup"><span data-stu-id="97a11-150">iOS</span></span>|<span data-ttu-id="97a11-151">Android</span><span class="sxs-lookup"><span data-stu-id="97a11-151">Android</span></span>|<span data-ttu-id="97a11-152">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="97a11-152">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="97a11-153">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-153">Yes</span></span>|<span data-ttu-id="97a11-154">○</span><span class="sxs-lookup"><span data-stu-id="97a11-154">Yes</span></span>|<span data-ttu-id="97a11-155">○</span><span class="sxs-lookup"><span data-stu-id="97a11-155">Yes</span></span>|<span data-ttu-id="97a11-156">○</span><span class="sxs-lookup"><span data-stu-id="97a11-156">Yes</span></span>|<span data-ttu-id="97a11-157">Yes</span><span class="sxs-lookup"><span data-stu-id="97a11-157">Yes</span></span>|
