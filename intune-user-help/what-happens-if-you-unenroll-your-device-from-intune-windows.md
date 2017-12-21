---
title: "Windows デバイスの登録を解除するとどうなるか | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 710f91f72d9cf97acd0ac117b003eeb542449515
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a><span data-ttu-id="ac4c1-103">Intune から Windows デバイスの登録を解除するとどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-103">What happens if you unenroll your Windows device from Intune?</span></span>

<span data-ttu-id="ac4c1-104">お使いのデバイスの種類に関する情報については、このページの右側の**この記事内の項目**の下にあるリンクを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-104">Use the links at the right side of this page, under **In this article**, to find information about the type of device you're using.</span></span>


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a><span data-ttu-id="ac4c1-105">Windows 10、Windows 8.1、Windows 8、Windows 7、Windows Vista</span><span class="sxs-lookup"><span data-stu-id="ac4c1-105">Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista</span></span>

-   <span data-ttu-id="ac4c1-106">デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-106">Your device doesn't appear in the Company Portal anymore, and you can’t install apps from the Company Portal anymore.</span></span>

-   <span data-ttu-id="ac4c1-107">Intune クライアント ソフトウェアをインストールしていた場合、コンピューターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-107">If you installed the Intune client software, it’s removed from your computer.</span></span>

-   <span data-ttu-id="ac4c1-108">Intune Endpoint Protection ソフトウェアはコンピューターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-108">The Intune Endpoint Protection software is removed from your computer.</span></span> <span data-ttu-id="ac4c1-109">コンピューターに別のウイルス対策ソフトウェアがインストールされており、無効になっている場合は、Intune Endpoint Protection を削除した後で、そのアプリケーションを再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-109">If your computer has other virus protection software installed and it is disabled, that software can be re-enabled after Intune Endpoint Protection is removed.</span></span> <span data-ttu-id="ac4c1-110">ポータル サイトから削除した後は、コンピューターの確認を行ってください。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-110">Check your computer after removing it from the Company Portal.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac4c1-111">他のウイルス対策ソフトウェアを再び有効にしない場合、または他のウイルス対策ソフトウェアがインストールされていない場合、コンピューターはウイルスおよびマルウェアに対して脆弱になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-111">If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.</span></span>

-   <span data-ttu-id="ac4c1-112">追加時にデバイスで変更した設定がある場合 (カメラを無効にするなど)、その設定は適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-112">Any settings that were changed on your device when you added it (for example, disabling the camera) no longer apply.</span></span>

-   <span data-ttu-id="ac4c1-113">コンピューターは、Intune サービスから自動的なソフトウェア更新プログラムまたはウイルス対策ソフトウェア更新プログラムを受信しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-113">Your computer no longer receives automatic software updates or antivirus software updates from the Intune service.</span></span> <span data-ttu-id="ac4c1-114">ただし、コンピューターがどのようにセットアップされているかによって異なりますが、Windows Server Update Services、Windows Update、または Microsoft Update から、引き続き更新プログラムを受信できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-114">But, depending on how it is set up, your computer might still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

<span data-ttu-id="ac4c1-115">さらに Windows 8.1 の場合、</span><span class="sxs-lookup"><span data-stu-id="ac4c1-115">In addition, for Windows 8.1:</span></span>

-   <span data-ttu-id="ac4c1-116">お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-116">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-117">Windows Mail など、一部のメール アプリケーションは、デバイスに保存されている会社の電子メールにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-117">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-118">Wi-Fi または仮想プライベート ネットワークを使用して、社内ネットワークに接続できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-118">You might not be able to connect to your company network by using Wi-Fi or a virtual private network.</span></span>

-   <span data-ttu-id="ac4c1-119">お使いのデバイスで、ファイルの共有または内部 Web サイトなど、一部の会社リソースにアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-119">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

## <a name="windows-10-mobile-and-windows-phone-81"></a><span data-ttu-id="ac4c1-120">Windows 10 Mobile および Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="ac4c1-120">Windows 10 mobile and Windows Phone 8.1</span></span>

-   <span data-ttu-id="ac4c1-121">ポータル サイト アプリがデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-121">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="ac4c1-122">これにより、そのデバイスはポータル サイトに表示されなくなります。さらに、ポータル サイトまたはポータル Web サイトからアプリをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-122">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal app or the Company Portal website.</span></span>

-   <span data-ttu-id="ac4c1-123">お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-123">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-124">追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-124">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ac4c1-125">例外は暗号化のポリシーのみです。暗号化のポリシーは引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-125">The only exception to this is encryption policies, which still apply.</span></span> <span data-ttu-id="ac4c1-126">会社のポリシーで Windows Phone の暗号化が必須にされていた場合、電話の暗号化を解除するには、**[設定]** メニューを使用してリセットするしかありません。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-126">If your company policy required you to encrypt your Windows Phone, the only way to unencrypt your phone is to reset it by using the **Settings** menu.</span></span>

## <a name="windows-rt-running-windows-81"></a><span data-ttu-id="ac4c1-127">Windows 8.1 を実行している Windows RT</span><span class="sxs-lookup"><span data-stu-id="ac4c1-127">Windows RT running Windows 8.1</span></span>

-   <span data-ttu-id="ac4c1-128">ポータル サイト アプリがデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-128">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="ac4c1-129">これにより、デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-129">This means that your device doesn’t appear in the Company Portal anymore, and you can’t install apps from the Company Portal.</span></span>

-   <span data-ttu-id="ac4c1-130">お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-130">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-131">追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-131">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

-   <span data-ttu-id="ac4c1-132">Wi-Fi または仮想プライベート ネットワークを使用して、社内ネットワークに接続できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-132">You might not be able to connect to your company network by using Wi-Fi or a virtual private network anymore.</span></span>

-   <span data-ttu-id="ac4c1-133">お使いのデバイスで、ファイルの共有または内部 Web サイトなど、一部の会社リソースにアクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-133">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-134">Windows Mail など、一部のメール アプリケーションは、デバイスに保存されている会社の電子メールにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-134">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

<span data-ttu-id="ac4c1-135">Windows RT デバイスを削除すると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-135">When you remove your Windows RT device, the following happens:</span></span>

-   <span data-ttu-id="ac4c1-136">ポータル サイト アプリがデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-136">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="ac4c1-137">これにより、デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-137">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal.</span></span>

-   <span data-ttu-id="ac4c1-138">お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-138">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="ac4c1-139">追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-139">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

<span data-ttu-id="ac4c1-140">ご不明な点がある場合は、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-140">If you have questions, contact your company support.</span></span> <span data-ttu-id="ac4c1-141">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ac4c1-141">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
