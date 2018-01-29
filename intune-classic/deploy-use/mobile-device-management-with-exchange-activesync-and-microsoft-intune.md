---
title: "Exchange ActiveSync デバイス管理"
description: "Exchange Connector を使用した Exchange ActiveSync (EAS) 管理によるモバイル デバイスの管理"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f5e9bd3dd2026096c323858fc7faa915895ed55d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a><span data-ttu-id="40037-103">Microsoft Intune を使用した Exchange ActiveSync モバイル デバイスの管理</span><span class="sxs-lookup"><span data-stu-id="40037-103">Exchange ActiveSync mobile device management with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="40037-104">Microsoft Intune でモバイル デバイスを直接管理するには、デバイスが [Intune に登録](prerequisites-for-enrollment.md)されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="40037-104">For Microsoft Intune to directly manage mobile devices, devices must be [enrolled in Intune](prerequisites-for-enrollment.md).</span></span> <span data-ttu-id="40037-105">別の方法として、管理者は Exchange Connector と Exchange ActiveSync (EAS) 管理を組み合わせて使用する、より限定的な管理ソリューションを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="40037-105">As an alternative, admins can enable a more limited management solution that uses Exchange ActiveSync (EAS) management with an Exchange connector.</span></span> <span data-ttu-id="40037-106">オンプレミスの Exchange サーバーで、または Office 365 を使用した Exchange Onlineで、デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="40037-106">Devices can be managed with either on-premises Exchange servers or Exchange Online using Office 365.</span></span> <span data-ttu-id="40037-107">Intune は、サブスクリプションごとに任意の種類の Exchange Connector 接続を 1 つだけサポートします。</span><span class="sxs-lookup"><span data-stu-id="40037-107">Intune supports only one Exchange connector connection of any type per subscription.</span></span>

## <a name="exchange-access-rules-for-mobile-devices"></a><span data-ttu-id="40037-108">モバイル デバイスの Exchange アクセス ルール</span><span class="sxs-lookup"><span data-stu-id="40037-108">Exchange access rules for mobile devices</span></span> ##

<span data-ttu-id="40037-109">Exchange では、モバイル デバイスが EAS への接続を試みたときの処理を定義する一連のルールが必要です。</span><span class="sxs-lookup"><span data-stu-id="40037-109">Exchange needs a set of rules that defines what happens when mobile devices attempt to connect to EAS.</span></span> <span data-ttu-id="40037-110">これらのルールは、Intune 管理コンソールで管理します。</span><span class="sxs-lookup"><span data-stu-id="40037-110">These rules are managed in the Intune administration console.</span></span>

[<span data-ttu-id="40037-111">モバイル デバイスの Exchange アクセス ルール</span><span class="sxs-lookup"><span data-stu-id="40037-111">Exchange access rules for mobile devices</span></span>](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a><span data-ttu-id="40037-112">Exchange Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="40037-112">Install the Exchange connector</span></span>
<span data-ttu-id="40037-113">Exchange Connector を使用すると、Intune コンソールで Exchange の展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="40037-113">The Exchange connector lets you manage your Exchange deployment in the Intune console.</span></span> <span data-ttu-id="40037-114">最初に、適切な Intune-to-Exchange Connector をインストールしてセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40037-114">You must first install and set up the appropriate Intune-to-Exchange connector.</span></span> <span data-ttu-id="40037-115">Exchange サーバーがオンプレミスか、クラウドにサービスとしてホストされているかに応じて、適切なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="40037-115">Choose the appropriate option based on whether your Exchange server is on-premises or hosted as a service in the cloud:</span></span>

-   [<span data-ttu-id="40037-116">Exchange Online または新しい Exchange Online Dedicated 環境に対して Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="40037-116">Configure the Intune for Exchange Online or new Exchange Online Dedicated environments</span></span>](intune-service-to-service-exchange-connector.md)
-   [<span data-ttu-id="40037-117">オンプレミスの Exchange サーバーおよび従来の Exchange Online Dedicated 環境で Intune コネクタをインストールする</span><span class="sxs-lookup"><span data-stu-id="40037-117">Install the Intune connector for on-premises Exchange servers and legacy Exchange Online Dedicated environments</span></span>](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a><span data-ttu-id="40037-118">Exchange で管理されているモバイル デバイスのポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="40037-118">Apply policy for Exchange-managed mobile devices</span></span>
<span data-ttu-id="40037-119">Intune コンソールを使用すれば、[EAS ポリシー設定](exchange-activesync-policy-settings-in-microsoft-intune.md)を管理し、[会社のリソースへのアクセスを制限](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="40037-119">The Intune console can be used to manage [EAS policy settings](exchange-activesync-policy-settings-in-microsoft-intune.md) and to [restrict access to company resources](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span> <span data-ttu-id="40037-120">各モバイル デバイスでサポートされる Exchange ActiveSync のポリシー設定と機能の一覧については、「[Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270)」 (Exchange ActiveSync クライアントの比較表) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40037-120">For a list of Exchange ActiveSync policy settings and features that specific mobile devices support, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).</span></span>

> [!NOTE]
> <span data-ttu-id="40037-121">Intune を Microsoft Exchange 環境に接続すると、Intune で管理されているすべてのユーザーの EAS ポリシーは、Intune 内で特定のポリシーが定義されていない限り、Microsoft Exchange サーバーの現在の既定のポリシーにリセットされます。</span><span class="sxs-lookup"><span data-stu-id="40037-121">After connecting Intune to a Microsoft Exchange environment, the EAS policy for all users managed through Intune will be reset to the current default policy on the Microsoft Exchange server, unless a more specific policy is defined within Intune.</span></span>

## <a name="wipe-company-data-from-mobile-devices"></a><span data-ttu-id="40037-122">会社のデータをモバイル デバイスから消去する</span><span class="sxs-lookup"><span data-stu-id="40037-122">Wipe company data from mobile devices</span></span>
<span data-ttu-id="40037-123">最後に、会社のデータが不要になったとき、またはデバイスをなくしたり盗まれたりしたときは、[EAS で管理されたモバイル デバイスから会社のデータを消去](wipe-for-exchange-managed-mobile-devices.md)できます。</span><span class="sxs-lookup"><span data-stu-id="40037-123">Finally, you can [wipe company data from EAS-managed mobile devices](wipe-for-exchange-managed-mobile-devices.md) when they are no longer in use, or if devices are lost or stolen.</span></span>
