---
title: "Windows PC を保護するためのポリシー"
description: "これらのポリシーを使用すると、Intune クライアント ソフトウェアで管理しているときに Windows PC のセキュリティを確保できます。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ddfe11dbe360577e5614f0909aae15fd89c3903d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a><span data-ttu-id="0372e-103">Intune クライアント ソフトウェアを実行する Windows PC の保護に有用なポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="0372e-103">Use policies to help protect Windows PCs that run the Intune client software</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="0372e-104">Microsoft Intune には 3 つのポリシーが用意されており、これらを使用すれば、[Intune クライアント ソフトウェア](manage-windows-pcs-with-microsoft-intune.md)が管理する Windows PC のセキュリティを容易に確保できます。</span><span class="sxs-lookup"><span data-stu-id="0372e-104">Microsoft Intune offers three policies that you can use to help ensure the security of Windows PCs that the [Intune client software](manage-windows-pcs-with-microsoft-intune.md) manages.</span></span>


## <a name="software-updates"></a><span data-ttu-id="0372e-105">ソフトウェア更新プログラム</span><span class="sxs-lookup"><span data-stu-id="0372e-105">Software updates</span></span>

<span data-ttu-id="0372e-106">Intune では、Microsoft および他社からソフトウェアの重要な更新プログラムが入手可能になるとその旨が通知されるため、[管理する Windows PC を最新の状態に保つ](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="0372e-106">Intune makes it easy for you to [keep Windows PCs that you manage up-to-date](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) by informing you when important software updates from Microsoft and other companies are available.</span></span> <span data-ttu-id="0372e-107">これらの更新プログラムは、承認または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="0372e-107">You can then approve or decline these updates.</span></span> <span data-ttu-id="0372e-108">承認した更新プログラムは、該当するすべての PC に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0372e-108">Approved updates will automatically be installed on all applicable PCs.</span></span>

## <a name="windows-firewall"></a><span data-ttu-id="0372e-109">Windows ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="0372e-109">Windows Firewall</span></span>

<span data-ttu-id="0372e-110">Windows ファイアウォールは、ハッカー、マルウェア、およびその他の脅威から Windows PC を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0372e-110">The Windows Firewall helps to keep hackers, malware, and other threats from Windows PCs.</span></span> <span data-ttu-id="0372e-111">Intune を使用すると、管理するすべての PC での [Windows ファイアウォールの設定および機能を管理する](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="0372e-111">With Intune, you can [manage settings and features for the Windows Firewall](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) on all PCs that you manage.</span></span>

## <a name="endpoint-protection"></a><span data-ttu-id="0372e-112">Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="0372e-112">Endpoint Protection</span></span>

<span data-ttu-id="0372e-113">IT 管理者として最も優先度が高い事項の 1 つは、[管理する Windows PC をマルウェアやウイルスのない状態に保つことです](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="0372e-113">As an IT admin, one of your top priorities is to [keep the Windows PCs that you manage free of malware and viruses](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).</span></span> <span data-ttu-id="0372e-114">Intune は Endpoint Protection と統合することで、マルウェアの脅威に対するリアルタイムの保護を実現し、マルウェア定義を最新の状態に保ち、自動的にコンピューターをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="0372e-114">Intune integrates with Endpoint Protection to provide real-time protection against malware threats, keep malware definitions up-to date, and automatically scan computers.</span></span> <span data-ttu-id="0372e-115">また、Endpoint Protection は、マルウェアの攻撃の管理と監視に役立つツールも提供します。</span><span class="sxs-lookup"><span data-stu-id="0372e-115">Endpoint Protection also provides tools that help you to manage and monitor malware attacks.</span></span>



### <a name="see-also"></a><span data-ttu-id="0372e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0372e-116">See also</span></span>
[<span data-ttu-id="0372e-117">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="0372e-117">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
