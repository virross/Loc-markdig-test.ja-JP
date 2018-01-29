---
title: "Intune を使用した iOS および macOS デバイス向けの AirPrint 設定"
titlesuffix: Azure portal
description: "Intune を使用して、iOS デバイスと macOS デバイスを AirPrint 対応プリンターに自動接続する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc6dbe3c59495755aaab2a94e162833420ff658a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a><span data-ttu-id="0c7b8-103">iOS および macOS デバイス向けの AirPrint 設定</span><span class="sxs-lookup"><span data-stu-id="0c7b8-103">AirPrint settings for iOS and macOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0c7b8-104">これらの設定を利用し、ネットワーク上の AirPrint 対応プリンターに自動接続するように iOS デバイスまたは macOS デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-104">Use these settings to configure iOS or macOS devices to automatically connect to AirPrint compatible printers on your network.</span></span> <span data-ttu-id="0c7b8-105">始めるにはプリンターの IP アドレスとリソース パスを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-105">You need the IP address and resource path of your printers to proceed.</span></span>

## <a name="find-airprint-printer-information"></a><span data-ttu-id="0c7b8-106">AirPrint プリンター情報を調べる</span><span class="sxs-lookup"><span data-stu-id="0c7b8-106">Find AirPrint printer information</span></span>

<span data-ttu-id="0c7b8-107">iOS デバイス ユーザーが既知の AirPrint プリンターに印刷できるようにするには、この手順を実行して AirPrint 情報を AirPrint ペイロードに追加します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-107">Use this procedure to add AirPrint information to the AirPrint payload so that iOS device users can print to known AirPrint printers.</span></span>

1. <span data-ttu-id="0c7b8-108">AirPrint プリンターと同じローカル ネットワーク (サブネット) に接続している Mac で、(**/アプリケーション/ユーティリティ** フォルダーから) ターミナルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-108">On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open Terminal (from **/Applications/Utilities**)</span></span>
2. <span data-ttu-id="0c7b8-109">ターミナルで「**ippfind**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-109">In the Terminal, type **ippfind**, then press enter.</span></span>
3. <span data-ttu-id="0c7b8-110">コマンドによって返されたプリンター情報をメモします (例: **ipp://myprinter.local.:631/ipp/port1**)。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-110">Make a note of any printer information the command returns, for example: **ipp://myprinter.local.:631/ipp/port1**.</span></span> <span data-ttu-id="0c7b8-111">この情報の最初の部分がプリンター名で、後の部分がリソース パスです。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-111">The first part of the information is the name of your printer and the last part is the resource path.</span></span>
4. <span data-ttu-id="0c7b8-112">ターミナルで「**ping myprinter.local**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-112">In the Terminal, type **ping myprinter.local**, then press enter.</span></span>
5. <span data-ttu-id="0c7b8-113">コマンドによって返された IP アドレス情報をメモします (例: **PING myprinter.local (10.50.25.21)**)。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-113">Make a note of the IP address information returned by the command, for example, **PING myprinter.local (10.50.25.21)**.</span></span>
6. <span data-ttu-id="0c7b8-114">最後に、この IP アドレスとリソース パスを AirPrint ペイロード設定で使用します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-114">Finally, use the IP address and resource path in the AirPrint payload settings.</span></span> <span data-ttu-id="0c7b8-115">上記の例では、IP アドレスは **10.50.25.21**、リソース パスは **/ipp/port1** になります。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-115">An example IP address might be **10.50.25.21**, and an example resource path might be **/ipp/port1**.</span></span>

## <a name="configure-an-airprint-profile"></a><span data-ttu-id="0c7b8-116">AirPrint プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="0c7b8-116">Configure an AirPrint profile</span></span>

1. <span data-ttu-id="0c7b8-117">**[デバイス機能]** ブレードで **[AirPrint]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-117">On the **Device features** blade, choose **AirPrint**.</span></span>
2. <span data-ttu-id="0c7b8-118">**[AirPrint]** ブレードで、AirPrint の出力先を追加するには、**IP アドレス**と**リソース パス**を入力して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-118">On the **AirPrint** blade, to add an AirPrint destination, enter its **IP address** and **resource path**, and then click **Add**.</span></span>
3. <span data-ttu-id="0c7b8-119">必要な数の出力先を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-119">Continue to add as many destinations as you need.</span></span> <span data-ttu-id="0c7b8-120">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-120">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="0c7b8-121">コンマ区切り値 (.csv) ファイルからプリンターの一覧をインポートしたり、一覧をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-121">You can also import a list of printers from a comma-separated values (.csv) file or export the list.</span></span>


## <a name="next-steps"></a><span data-ttu-id="0c7b8-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="0c7b8-122">Next steps</span></span>

<span data-ttu-id="0c7b8-123">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-123">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="0c7b8-124">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0c7b8-124">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>