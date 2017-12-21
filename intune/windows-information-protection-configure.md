---
title: "Windows 情報保護を構成する - Intune"
titleSuffix: Azure portal
description: "Windows 情報保護の管理に使用できるIntune の設定について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8719e778c7f6b146625b82a63c1ff93c7936d294
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a><span data-ttu-id="10c0d-103">Microsoft Intune で Windows Information Protection を構成する方法</span><span class="sxs-lookup"><span data-stu-id="10c0d-103">How to configure Windows Information Protection in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="10c0d-104">企業内に従業員所有デバイスが増加するのに従い、企業のコントロールが届かない電子メール、ソーシャル メディア、パブリック クラウドなどのアプリやサービスを介して偶発的にデータが漏えいするリスクも増大しています。</span><span class="sxs-lookup"><span data-stu-id="10c0d-104">With the increase of employee-owned devices in the enterprise, there’s also an increasing risk of accidental data leaks through apps and services, like email, social media, and the public cloud, which are outside of the enterprise’s control.</span></span> <span data-ttu-id="10c0d-105">たとえば、従業員が個人用の電子メール アカウントから最新のエンジニアリング画像を送信したり、製品情報をコピーしてツイートに貼り付けたり、作成中の営業レポートをパブリック クラウドの記憶域に保存したりするときなどです。</span><span class="sxs-lookup"><span data-stu-id="10c0d-105">For example, an employee sends the latest engineering pictures from a personal email account, copies and pastes product info into a tweet, or saves an in-progress sales report to public cloud storage.</span></span>

<span data-ttu-id="10c0d-106">**Windows 情報保護**は、この潜在的なデータ漏えいの防止に役立ちます。それ以外の場合は従業員のエクスペリエンスを妨げることはありません。</span><span class="sxs-lookup"><span data-stu-id="10c0d-106">**Windows Information Protection** helps to protect against this potential data leakage without otherwise interfering with the employee experience.</span></span> <span data-ttu-id="10c0d-107">また、企業が所有するデバイスと従業員が作業のために持ち込む個人用デバイスでもエンタープライズ アプリとデータを偶発的なデータ漏えいから保護します。既存の環境や他のアプリを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10c0d-107">It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.</span></span>

<span data-ttu-id="10c0d-108">この Intune ポリシーは、Windows 情報保護によって保護されているアプリ、エンタープライズ ネットワークの場所、保護レベル、および暗号化設定の一覧を管理します。</span><span class="sxs-lookup"><span data-stu-id="10c0d-108">This Intune policy manages the list of apps protected by Windows Information Protection, enterprise network locations, protection level, and encryption settings.</span></span>

>[!NOTE]
> <span data-ttu-id="10c0d-109">Windows 10 ポータル サイト アプリを Windows Information Protection とともに使用するには、ポータル サイト アプリを Windows Information Protection モードの**除外対象**に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10c0d-109">To use the Windows 10 Company Portal app with Windows Information Protection, you must add the Company Portal app under the Windows Information Protection mode of **Exempt**.</span></span> 

### <a name="next-steps"></a><span data-ttu-id="10c0d-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="10c0d-110">Next steps</span></span>
<span data-ttu-id="10c0d-111">詳細については、「[Protect your enterprise data using Windows Information Protection (Windows 情報保護を使用してエンタープライズ データを保護する)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10c0d-111">For more information, see [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
