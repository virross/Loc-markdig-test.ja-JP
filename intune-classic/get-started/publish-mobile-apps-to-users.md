---
title: "ユーザーにモバイル アプリを発行する"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebdc5abba37cfd0e23f962434c2f654b4bc45312
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="quick-start-guide-publish-mobile-apps-to-your-users"></a><span data-ttu-id="d1486-102">クイック スタート ガイド: ユーザーにモバイル アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="d1486-102">Quick Start Guide: Publish mobile apps to your users</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d1486-103">Microsoft Intune では、エンド ユーザーが選択したデバイスから必要なモバイル アプリとデスクトップ アプリに簡単にアクセスできるようにすることで、エンド ユーザーの生産性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d1486-103">Microsoft Intune can help increase your end users’ productivity by quickly and easily giving them access to the mobile and desktop apps they need from the devices of their choice.</span></span> <span data-ttu-id="d1486-104">アプリを簡単に使用できるようにすることで、エンド ユーザーが適切なアプリを探してインストールする時間と労力を削減でき、ユーザーが必要なアプリを見つけられない場合のヘルプ デスクへの問い合わせを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d1486-104">Making apps easily available to end users reduces the time and effort users spend searching for and installing the correct apps, which reduces helpdesk calls when users cannot find the apps they need.</span></span>   

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="d1486-105">このクイック スタート ガイドの対象読者</span><span class="sxs-lookup"><span data-stu-id="d1486-105">Is this quick start guide right for me?</span></span>
<span data-ttu-id="d1486-106">ユーザーが生産的に仕事を進めるために必要なすべてのアプリを、ユーザーが使用しているデバイスの種類とは無関係に共通のポータルに提示することを望んでいますか。</span><span class="sxs-lookup"><span data-stu-id="d1486-106">Would you like your users to quickly have access to all the apps they need to be productive at work, presented in a common portal regardless of the type of device they use?</span></span>

<span data-ttu-id="d1486-107">そうであれば、Microsoft Intune で、1 つの共通のポータル ([Intune ポータル サイトまたは Web サイト](/intune-user-help/company-portal-frequently-asked-questions)) に、アプリ (Office モバイル、社内向けの基幹業務やその他のモバイルまたはデスクトップアプリ) を発行できます。</span><span class="sxs-lookup"><span data-stu-id="d1486-107">If yes, Microsoft Intune allows you to publish apps (Office mobile, internal line of business or other mobile and desktop apps) in a single common portal: the [Intune Company Portal app or website](/intune-user-help/company-portal-frequently-asked-questions).</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="d1486-108">実行方法</span><span class="sxs-lookup"><span data-stu-id="d1486-108">How do I do it?</span></span>
1.  <span data-ttu-id="d1486-109">Intune モバイルデバイス管理に[デバイスを登録](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)します。</span><span class="sxs-lookup"><span data-stu-id="d1486-109">[Enroll devices](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) into Intune mobile device management.</span></span>
2.  <span data-ttu-id="d1486-110">登録されたデバイスに展開する[アプリを Intuneに追加](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)します。</span><span class="sxs-lookup"><span data-stu-id="d1486-110">[Add apps to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) that you want to deploy to enrolled devices.</span></span>
3.  <span data-ttu-id="d1486-111">登録されたデバイスに[ Intune を使用してアプリを展開](/intune-classic/deploy-use/deploy-apps)します。</span><span class="sxs-lookup"><span data-stu-id="d1486-111">[Deploy apps using Intune](/intune-classic/deploy-use/deploy-apps) to enrolled devices.</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1486-112">追加情報:</span><span class="sxs-lookup"><span data-stu-id="d1486-112">Additional information:</span></span>
<span data-ttu-id="d1486-113">アプリのデータ損失保護を管理するために Intune の MAM 機能を使用して Office モバイル アプリを発行する場合は、MAM ポリシーを割り当てるエンド ユーザーに [Office 365 のユーザーライセンスを割り当てる](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1486-113">If publishing Office mobile apps is done with the intention of using Intune’s MAM capabilities to manage data loss protection for those apps, then each end user assigned MAM policies will need to be [assigned a user license for Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="what-should-i-do-next"></a><span data-ttu-id="d1486-114">次にすべきこと</span><span class="sxs-lookup"><span data-stu-id="d1486-114">What should I do next?</span></span>
- [<span data-ttu-id="d1486-115">Microsoft Intune でアプリの展開を監視する</span><span class="sxs-lookup"><span data-stu-id="d1486-115">Monitor app deployments in Microsoft Intune</span></span>](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)
- [<span data-ttu-id="d1486-116">モバイル デバイスで会社のデータのデータ損失保護を行う</span><span class="sxs-lookup"><span data-stu-id="d1486-116">Protect company data against data loss in mobile devices</span></span>](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
