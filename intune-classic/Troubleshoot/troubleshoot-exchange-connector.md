---
title: "Exchange Connector に関するトラブルシューティング"
description: "Intune Exchange Connector に関連する問題のトラブルシューティングを行います。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 865ee7f18b7ad90b3d421f75534844587838158b
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshoot-the-exchange-connector"></a><span data-ttu-id="a10d2-103">Exchange Connector のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="a10d2-103">Troubleshoot the Exchange Connector</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a10d2-104">このトピックでは、Intune Exchange Connector に関連する可能性のある問題のトラブルシューティングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-104">This topic describes how to troubleshoot issues that may be related to the Intune Exchange Connector.</span></span>

## <a name="steps-for-checking-the-connector-configuration"></a><span data-ttu-id="a10d2-105">Connector の構成を確認する手順</span><span class="sxs-lookup"><span data-stu-id="a10d2-105">Steps for checking the Connector configuration</span></span> 

<span data-ttu-id="a10d2-106">Exchange Connector の構成を調べて、問題を解決できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-106">Check the configuration of the Exchange Connector and then see if the problem has been resolved.</span></span>

- <span data-ttu-id="a10d2-107">Exchange Connector の初期セットアップで、通知アカウントを指定したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-107">Be sure to specify a notification account in the initial setup of the Exchange Connector.</span></span>
- <span data-ttu-id="a10d2-108">Exchange Connector サービス アカウントに、Exchange Connector によって使用される PowerShell コマンドレットを実行するための適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a10d2-108">The Exchange Connector Service Account must have the appropriate permissions to execute the PowerShell cmdlets used by the Exchange Connector.</span></span>
- <span data-ttu-id="a10d2-109">Exchange Connector を構成するときに、Exchange Connector をホストするサーバーに近接するクライアント アクセス サーバー (CAS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-109">When configuring the Exchange Connector, specify a Client Access Server (CAS) that is as close as possible to the server hosting the Exchange Connector.</span></span> <span data-ttu-id="a10d2-110">特に O365 Dedicated を使用している場合は、CAS と Exchange Connector 間の通信の遅延によってデバイスの検出が遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a10d2-110">Communication latency between the CAS and the Exchange Connector could result in device discovery delays, particularly when using O365 Dedicated.</span></span>
- <span data-ttu-id="a10d2-111">Exchange Connector と Exchange CAS の同期にはタイム ラグがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a10d2-111">Be aware that there is a time lag between Exchange Connector synchronizations with the Exchange CAS.</span></span> <span data-ttu-id="a10d2-112">完全同期は 1 日に 1 回実行され、差分 (クイック) 同期は 2 時間間隔で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a10d2-112">A full sync takes place once a day, and a delta (quick) sync takes place every two hours.</span></span> <span data-ttu-id="a10d2-113">新しく登録されたデバイスを持つユーザーは、アクセスの取得が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a10d2-113">There is a likelihood that a user with a newly-enrolled device will experience a delay in getting access.</span></span>
- 
  ## <a name="exchange-activesync-device-not-discovered-from-exchange"></a><span data-ttu-id="a10d2-114">Exchange ActiveSync device not discovered from Exchange (Exchange ActiveSync デバイスが Exchange から検出されない)</span><span class="sxs-lookup"><span data-stu-id="a10d2-114">Exchange ActiveSync device not discovered from Exchange</span></span>
  <span data-ttu-id="a10d2-115">Exchange Connector が Exchange サーバーと同期しているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="a10d2-115">Check to see if the Exchange Connector is syncing with the Exchange server.</span></span> <span data-ttu-id="a10d2-116">これを行うには、ログで完全同期または差分同期を探します。Exchange Connector のログを確認します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-116">To do so, locate logs for a full sync or a delta sync. See Exchange Connector Logs.</span></span> <span data-ttu-id="a10d2-117">デバイスの参加以降、完全同期または差分同期が正常に完了している場合は、問題の原因から同期を排除します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-117">If a full sync or delta sync has completed successfully since the device joined, you've eliminated this as the source of the issue.</span></span> <span data-ttu-id="a10d2-118">同期が行われていない場合は、同期ログを収集し、サポート依頼に添付してください。</span><span class="sxs-lookup"><span data-stu-id="a10d2-118">If no sync has taken place, collect the sync logs and attach them to your support request.</span></span>

- <span data-ttu-id="a10d2-119">ユーザーが Intune ライセンスを持っていない場合、Exchange Connector は、それらのユーザーのデバイスを検出しません。</span><span class="sxs-lookup"><span data-stu-id="a10d2-119">If a user doesn't have an Intune license, the Exchange connector won’t discover their devices.</span></span>
- <span data-ttu-id="a10d2-120">ユーザーのプライマリ SMTP アドレスが AAD の UPN と異なる場合、Exchange Connector は、その Intune/AAD ユーザーのデバイスを検出しません。</span><span class="sxs-lookup"><span data-stu-id="a10d2-120">If a user’s Primary SMTP address is different than their UPN in AAD, the Exchange Connector will not discover any devices for that Intune/AAD user.</span></span> <span data-ttu-id="a10d2-121">プライマリ SMTP アドレスを修正してください。</span><span class="sxs-lookup"><span data-stu-id="a10d2-121">Fix the primary SMTP address.</span></span>
- <span data-ttu-id="a10d2-122">検出サイクル中に Exchange Connector が通信する CAS が Exchange 2010 CAS のときに、Exchange 2010 と 2013 のメールボックス サーバーの両方がある場合、Exchange Connector は、Exchange 2013 ユーザーのデバイスを検出しません。</span><span class="sxs-lookup"><span data-stu-id="a10d2-122">If the CAS that the Exchange Connector communicates with during a discovery cycle is an Exchange 2010 CAS and you have both Exchange 2010 and 2013 mailbox servers, the Exchange Connector will not discover any Exchange 2013 users’ devices.</span></span> <span data-ttu-id="a10d2-123">これを解決するには、Exchange 2013 CAS をポイントするように Exchange Connector を構成します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-123">To resolve this, configure the Exchange Connector to point to an Exchange 2013 CAS.</span></span>  <span data-ttu-id="a10d2-124">この問題は主に O365 Dedicated のトポロジに関係していますが、ベスト プラクティスとして、その他のトポロジでも Exchange 2013 CAS をポイントすることを勧めします。</span><span class="sxs-lookup"><span data-stu-id="a10d2-124">Though this issue primarily concerns O365 Dedicated topologies, we still recommend pointing to an Exchange 2013 CAS in other topologies as a best practice.</span></span>
- <span data-ttu-id="a10d2-125">Exchange Dedicated (O365 Dedicated) 環境では、初期セットアップ中に Exchange Connector が専用環境内の (2010 ではなく) Exchange 2013 CAS をポイントするように構成する必要があります。理由は、Exchange Connector は、Powershell コマンドレットを実行するときに、この CAS のみと通信するためです。</span><span class="sxs-lookup"><span data-stu-id="a10d2-125">For Exchange Dedicated (O365 dedicated) environments, you must point the Exchange Connector to an Exchange 2013 (not 2010) CAS in the dedicated environment during the initial setup as it will only communicate with this CAS when executing Powershell cmdlets.</span></span>


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a><span data-ttu-id="a10d2-126">Powershell を使用して Exchange Connector の問題に関するより多くのデータを取得する</span><span class="sxs-lookup"><span data-stu-id="a10d2-126">Using Powershell to get more data on Exchange Connector issues</span></span>
- <span data-ttu-id="a10d2-127">メールボックスのすべてのモバイル デバイスの一覧を取得するには、Get-ActiveSyncDeviceStatistics -mailbox mbx を使用します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-127">To get a list of all mobile devices for a mailbox use Get-ActiveSyncDeviceStatistics -mailbox mbx</span></span>
- <span data-ttu-id="a10d2-128">メールボックスの SMTP アドレスの一覧を取得するには、Get-Mailbox -Identity user | select emailaddresses | fl を使用します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-128">To get a list of SMTP addresses for a mailbox use Get-Mailbox -Identity user | select emailaddresses | fl.</span></span>
- <span data-ttu-id="a10d2-129">デバイスのアクセス状態に関する詳細情報を取得するには、Get-CASMailbox <upn> | fl を使用します。</span><span class="sxs-lookup"><span data-stu-id="a10d2-129">To get detailed information about a device's access state use Get-CASMailbox <upn> | fl</span></span>

### <a name="next-steps"></a><span data-ttu-id="a10d2-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="a10d2-130">Next steps</span></span>
<span data-ttu-id="a10d2-131">このトラブルシューティング情報を使っても問題が解決しない場合は、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」の説明に従って Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a10d2-131">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
