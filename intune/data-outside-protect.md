---
title: "会社のデータへの無許可のアクセスを防止する"
description: "企業ネットワーク外での共有時に、会社のデータへの無許可のアクセスを防止します。"
keywords: "Office 365 O365 Azure Information Protection データ保護 ネットワークの外部 会社のデータ"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6a88573a-aa60-455c-858c-74562798246b
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb748bc0a44b796dfb4ad07e404166d1d5c2ef19
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="prevent-unauthorized-access-to-company-data"></a><span data-ttu-id="5dbb2-104">会社のデータへの無許可のアクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="5dbb2-104">Prevent unauthorized access to company data</span></span> 

<span data-ttu-id="5dbb2-105">Office 365 のドキュメントと電子メールを分類し、ラベル付けし、保護することで、許可されたユーザーだけがデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-105">You can classify, label, and protect Office 365 documents and emails so only authorized users have access to the data.</span></span> <span data-ttu-id="5dbb2-106">設定は、IT 管理者またはユーザーが規則と条件を設定すると自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-106">The settings are managed automatically after IT administrators or users set the rules and conditions.</span></span> <span data-ttu-id="5dbb2-107">または、IT チームからユーザーに推奨される設定を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-107">Alternatively, the IT team can provide recommended settings for users to follow.</span></span> <span data-ttu-id="5dbb2-108">管理者とユーザーは、別の機関からの指示なく他のユーザーと既に共有されているデータへのアクセスを取り消すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-108">Administrators and users can also revoke access to data already shared with others without assistance from another authority.</span></span> <span data-ttu-id="5dbb2-109">この作業により、データが企業ネットワークから離れた後も、保護されているデータを開いたり更新したりするユーザーを制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-109">The result of this work is to control who opens or updates protected data, even when the data leaves the company's network.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="5dbb2-110">始める前に</span><span class="sxs-lookup"><span data-stu-id="5dbb2-110">Before you begin</span></span>

<span data-ttu-id="5dbb2-111">次の行動計画は、次の要件を満たすことで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-111">The following action plan can be used when you meet the following requirements:</span></span>
* <span data-ttu-id="5dbb2-112">会社が、クラウドに安全に移行する準備ができている。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-112">Your company is ready to transition securely to the cloud.</span></span>
* <span data-ttu-id="5dbb2-113">会社が Office 365 Exchange Online、SharePoint Online、OneDrive for Business、または Yammer を使用している。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-113">Your company uses Office 365 Exchange Online, SharePoint Online, OneDrive for Business, or Yammer.</span></span>
* <span data-ttu-id="5dbb2-114">会社が Microsoft 365、Enterprise Mobility + Security (EMS)、または Azure Information Protection のライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-114">Your company has licenses for Microsoft 365, Enterprise Mobility + Security (EMS), or Azure Information Protection.</span></span>
* <span data-ttu-id="5dbb2-115">会社が Windows 7 Service Pack 1 またはそれ以降が実行されているデバイスを使用している。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-115">Your company works with devices running Windows 7 Service Pack 1 or later.</span></span>
* <span data-ttu-id="5dbb2-116">会社が Office 365 ProPlus の 2016 または 2013 アプリ、Office Professional Plus 2016、Office Professional Plus 2013 Service Pack 1 または Office Professional Plus 2010 を使用している。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-116">Your company uses Office 365 ProPlus with 2016 apps or 2013 apps, Office Professional Plus 2016, Office Professional Plus 2013 with Service Pack 1, or Office Professional Plus 2010.</span></span>

## <a name="action-plan"></a><span data-ttu-id="5dbb2-117">行動計画</span><span class="sxs-lookup"><span data-stu-id="5dbb2-117">Action plan</span></span>

<span data-ttu-id="5dbb2-118">[Azure Information Protection のクイック スタート チュートリアル](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)を完了します。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-118">Complete the [quick start tutorial for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).</span></span>  

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="5dbb2-119">社員や学生に伝えること</span><span class="sxs-lookup"><span data-stu-id="5dbb2-119">What to tell employees and students</span></span>

<span data-ttu-id="5dbb2-120">[機密情報が含まれるドキュメントおよび電子メールを保護する方法とタイミング](https://docs.microsoft.com/information-protection/deploy-use/help-users)について詳細を共有できます。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-120">You can share details of [how and when to protect documents and emails that contain sensitive information](https://docs.microsoft.com/information-protection/deploy-use/help-users).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dbb2-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="5dbb2-121">Next steps</span></span>

<span data-ttu-id="5dbb2-122">次の手順として、会社データの保護機能を上げる他の方法について学習できます。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-122">As part of next steps, you can learn more about the other ways you can increase the protection of your company's data, including:</span></span> 

* <span data-ttu-id="5dbb2-123">[iOS および Android デバイスで Azure Information Protection] を使用する方法 (https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq)。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-123">Learn how to use [Azure Information Protection on iOS and Android devices](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq.</span></span>
* <span data-ttu-id="5dbb2-124">Windows Phone および Mac コンピューターの場合は、[Microsoft Rights Management 共有アプリケーション](https://technet.microsoft.com/dn451248)について詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5dbb2-124">For Windows Phone and Mac computers, learn about [Microsoft Rights Management Sharing Application](https://technet.microsoft.com/dn451248).</span></span>
