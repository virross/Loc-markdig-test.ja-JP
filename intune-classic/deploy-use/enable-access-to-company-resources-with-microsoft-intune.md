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
ms.openlocfilehash: 9f4860089d18369dfed5ec683f9bcf090398febe
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enable-access-to-company-resources-with-microsoft-intune"></a><span data-ttu-id="9885b-103">Microsoft Intune を使用して、会社のリソースへのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="9885b-103">Enable access to company resources with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="9885b-104">Microsoft Intune Wi-Fi、VPN、電子メール プロファイルを使用すると、ユーザーはどこにいても仕事を遂行するために必要なファイルとリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9885b-104">Microsoft Intune Wi-Fi, VPN, and email profiles work together to help your users gain access to the files and resources that they need to do their work wherever they are.</span></span> <span data-ttu-id="9885b-105">証明書プロファイルは、そのようなアクセスをセキュリティで保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9885b-105">Certificate profiles help secure that access.</span></span>

## <a name="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="9885b-106">[Wi-Fi プロファイル](wi-fi-connections-in-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9885b-106">[Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md) and supported platforms</span></span>

<span data-ttu-id="9885b-107">ワイヤレス ネットワークの設定をユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="9885b-107">Deploy wireless network settings to your users.</span></span> <span data-ttu-id="9885b-108">これらの設定により、ユーザーは企業ネットワークに簡単に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9885b-108">These settings make it easy for your users to connect to the corporate network.</span></span>
#### <a name="supported-platforms"></a><span data-ttu-id="9885b-109">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9885b-109">Supported platforms</span></span>

|<span data-ttu-id="9885b-110">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-110">Windows 8.1 and later</span></span>|<span data-ttu-id="9885b-111">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-111">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="9885b-112">iOS</span><span class="sxs-lookup"><span data-stu-id="9885b-112">iOS</span></span>|<span data-ttu-id="9885b-113">Android</span><span class="sxs-lookup"><span data-stu-id="9885b-113">Android</span></span>|<span data-ttu-id="9885b-114">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="9885b-114">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="9885b-115">○ (Windows Wi-Fi プロファイルをインポートできます)</span><span class="sxs-lookup"><span data-stu-id="9885b-115">Yes (You can import a Windows Wi-Fi profile.)</span></span>|<span data-ttu-id="9885b-116">○ (OMA-URI を構成できます)</span><span class="sxs-lookup"><span data-stu-id="9885b-116">Yes (You can configure OMA-URI.)</span></span> |<span data-ttu-id="9885b-117">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-117">Yes</span></span>|<span data-ttu-id="9885b-118">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-118">Yes</span></span>|<span data-ttu-id="9885b-119">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-119">Yes</span></span>|

## <a name="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="9885b-120">[VPN プロファイル](vpn-connections-in-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9885b-120">[VPN profiles](vpn-connections-in-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="9885b-121">仮想プライベート ネットワーク (VPN) の設定をユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="9885b-121">Deploy virtual private network (VPN) settings to your users.</span></span> <span data-ttu-id="9885b-122">これらの設定により、ユーザーは企業ネットワーク上のリソースに簡単に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9885b-122">These settings make it easy for users to connect to resources on the corporate network.</span></span>

|<span data-ttu-id="9885b-123">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-123">Windows 8.1 and later</span></span>|<span data-ttu-id="9885b-124">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-124">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="9885b-125">iOS</span><span class="sxs-lookup"><span data-stu-id="9885b-125">iOS</span></span>|<span data-ttu-id="9885b-126">Android</span><span class="sxs-lookup"><span data-stu-id="9885b-126">Android</span></span>|<span data-ttu-id="9885b-127">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="9885b-127">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="9885b-128">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-128">Yes</span></span>|<span data-ttu-id="9885b-129">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-129">Yes</span></span>|<span data-ttu-id="9885b-130">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-130">Yes</span></span>|<span data-ttu-id="9885b-131">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-131">Yes</span></span>|<span data-ttu-id="9885b-132">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-132">Yes</span></span>|

## <a name="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="9885b-133">[電子メール プロファイル](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9885b-133">[Email profiles](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="9885b-134">組織のデバイスに対するネイティブ電子メール クライアント設定を作成、展開、監視します。</span><span class="sxs-lookup"><span data-stu-id="9885b-134">Create, deploy, and monitor native email client settings on devices in your organization.</span></span>


| <span data-ttu-id="9885b-135">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-135">Windows 8.1 and later</span></span> | <span data-ttu-id="9885b-136">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-136">Windows Phone 8.1 and later</span></span> | <span data-ttu-id="9885b-137">iOS</span><span class="sxs-lookup"><span data-stu-id="9885b-137">iOS</span></span> | <span data-ttu-id="9885b-138">Android</span><span class="sxs-lookup"><span data-stu-id="9885b-138">Android</span></span> | <span data-ttu-id="9885b-139">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="9885b-139">Samsung KNOX Standard</span></span> |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          <span data-ttu-id="9885b-140">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="9885b-140">No</span></span>           |             <span data-ttu-id="9885b-141">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-141">Yes</span></span>             | <span data-ttu-id="9885b-142">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-142">Yes</span></span> |   <span data-ttu-id="9885b-143">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="9885b-143">No</span></span>    |          <span data-ttu-id="9885b-144">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-144">Yes</span></span>          |

> [!NOTE]
> <span data-ttu-id="9885b-145">OMA-URI を使用する Windows Phone 8.1 Wi-Fi プロファイルを構成する方法については、[この Intune チームのブログの投稿](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9885b-145">[This Intune team blog post](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) gives information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.</span></span>

## <a name="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms"></a><span data-ttu-id="9885b-146">[証明書プロファイル](secure-resource-access-with-certificate-profiles.md)とサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9885b-146">[Certificate profiles](secure-resource-access-with-certificate-profiles.md) and supported platforms</span></span>
<span data-ttu-id="9885b-147">ワイヤレス ネットワークや VPN 接続など、会社のリソースに対するアクセスをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="9885b-147">Help secure access to company resources including wireless networks and VPN connections.</span></span>


| <span data-ttu-id="9885b-148">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-148">Windows 8.1 and later</span></span> | <span data-ttu-id="9885b-149">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9885b-149">Windows Phone 8.1 and later</span></span> | <span data-ttu-id="9885b-150">iOS</span><span class="sxs-lookup"><span data-stu-id="9885b-150">iOS</span></span> | <span data-ttu-id="9885b-151">Android</span><span class="sxs-lookup"><span data-stu-id="9885b-151">Android</span></span> | <span data-ttu-id="9885b-152">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="9885b-152">Samsung KNOX Standard</span></span> |
|-----------------------|-----------------------------|-----|---------|-----------------------|
|          <span data-ttu-id="9885b-153">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-153">Yes</span></span>          |             <span data-ttu-id="9885b-154">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-154">Yes</span></span>             | <span data-ttu-id="9885b-155">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-155">Yes</span></span> |   <span data-ttu-id="9885b-156">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-156">Yes</span></span>   |          <span data-ttu-id="9885b-157">はい</span><span class="sxs-lookup"><span data-stu-id="9885b-157">Yes</span></span>          |

