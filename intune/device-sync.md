---
title: "Intune を使用してデバイスを同期する"
titlesuffix: Azure portal
description: "デバイスを Intune と同期して最新のポリシーとアクションを取得する方法を説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 065c8e8f8403b96b7fad127abdd2c22d84e3e639
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a><span data-ttu-id="c3c20-103">デバイスを Intune と同期して最新のポリシーとアクションを取得する</span><span class="sxs-lookup"><span data-stu-id="c3c20-103">Sync devices with Intune to get the latest policies and actions</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c3c20-104">デバイスの**同期**のアクションは、選択したデバイスの Intune との即座の同期を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-104">The **Sync** device action forces the selected device to immediately check in with Intune.</span></span> <span data-ttu-id="c3c20-105">チェックインしたデバイスには、それに対して保留中のアクションまたはポリシーが即座に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c3c20-105">When a device checks in, it immediately receives any pending actions or policies that have been assigned to it.</span></span>  <span data-ttu-id="c3c20-106">このアクションにより、次のスケジュールされたチェックインを待つことなく、割り当てられたポリシーの検証およびトラブルシューティングを即座に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3c20-106">This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="c3c20-107">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c3c20-107">Supported platforms</span></span>

- <span data-ttu-id="c3c20-108">Windows</span><span class="sxs-lookup"><span data-stu-id="c3c20-108">Windows</span></span>
- <span data-ttu-id="c3c20-109">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c3c20-109">Windows Phone</span></span>
- <span data-ttu-id="c3c20-110">iOS</span><span class="sxs-lookup"><span data-stu-id="c3c20-110">iOS</span></span>
- <span data-ttu-id="c3c20-111">macOS</span><span class="sxs-lookup"><span data-stu-id="c3c20-111">macOS</span></span>
- <span data-ttu-id="c3c20-112">Android</span><span class="sxs-lookup"><span data-stu-id="c3c20-112">Android</span></span>

## <a name="how-to-sync-a-device"></a><span data-ttu-id="c3c20-113">デバイスを同期する方法</span><span class="sxs-lookup"><span data-stu-id="c3c20-113">How to sync a device</span></span>

1. <span data-ttu-id="c3c20-114">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c3c20-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c3c20-116">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="c3c20-117">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="c3c20-118">管理するデバイスの一覧からデバイスを選択し、その後 **[同期]** リモート操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-118">From the list of devices you manage, choose a device, and then choose the **Sync** remote action.</span></span>
7. <span data-ttu-id="c3c20-119">**[はい]** を選んで操作を確定します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-119">Choose **Yes** to confirm the action.</span></span>


## <a name="retriable-error-codes"></a><span data-ttu-id="c3c20-120">再試行可能なエラー コード</span><span class="sxs-lookup"><span data-stu-id="c3c20-120">Retriable error codes</span></span>

<span data-ttu-id="c3c20-121">管理者がデバイスの**同期**操作を行ったときに、失敗したものの再試行可能なエラー コードが生成された iOS アプリおよび Android アプリは、デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3c20-121">When an administrator runs the **Sync** device action, iOS and Androids apps that failed but  raised a retriable error code will be available to the device.</span></span> <span data-ttu-id="c3c20-122">ただし、再試行不可能なエラー コードが生成されたアプリは、デバイスで使用できるようになるまでに 7 日間待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c20-122">However, apps that raised a non-retriable error code must wait for seven days before they can be made available to the device.</span></span>


| <span data-ttu-id="c3c20-123">エラー コード</span><span class="sxs-lookup"><span data-stu-id="c3c20-123">Error Code</span></span>  | <span data-ttu-id="c3c20-124">提案された説明</span><span class="sxs-lookup"><span data-stu-id="c3c20-124">Suggested Description</span></span>                                                                                                                  | <span data-ttu-id="c3c20-125">再試行可能</span><span class="sxs-lookup"><span data-stu-id="c3c20-125">Retriable</span></span> |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| <span data-ttu-id="c3c20-126">2016330898</span><span class="sxs-lookup"><span data-stu-id="c3c20-126">2016330898</span></span> | <span data-ttu-id="c3c20-127">原因不明のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-127">An unknown error occurred.</span></span>                                                                                                             | <span data-ttu-id="c3c20-128">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="c3c20-128">No</span></span>        |
| <span data-ttu-id="c3c20-129">2016330897</span><span class="sxs-lookup"><span data-stu-id="c3c20-129">2016330897</span></span> | <span data-ttu-id="c3c20-130">Intune への接続がタイムアウトになりました。接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-130">Your connection to Intune timed out. Reset your connection</span></span>                                                                             | <span data-ttu-id="c3c20-131">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-131">Yes</span></span>       |
| <span data-ttu-id="c3c20-132">2016330896</span><span class="sxs-lookup"><span data-stu-id="c3c20-132">2016330896</span></span> | <span data-ttu-id="c3c20-133">インターネットへの接続が失われました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-133">You lost connection to the Internet.</span></span> <span data-ttu-id="c3c20-134">接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-134">Reset your connection.</span></span>                                                                            | <span data-ttu-id="c3c20-135">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-135">Yes</span></span>       |
| <span data-ttu-id="c3c20-136">2016330895</span><span class="sxs-lookup"><span data-stu-id="c3c20-136">2016330895</span></span> | <span data-ttu-id="c3c20-137">インターネットへの接続が失われました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-137">You lost connection to the Internet.</span></span> <span data-ttu-id="c3c20-138">接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-138">Reset your connection.</span></span>                                                                            | <span data-ttu-id="c3c20-139">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-139">Yes</span></span>       |
| <span data-ttu-id="c3c20-140">2016330894</span><span class="sxs-lookup"><span data-stu-id="c3c20-140">2016330894</span></span> | <span data-ttu-id="c3c20-141">インターネットへの接続が失われました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-141">You lost connection to the Internet.</span></span> <span data-ttu-id="c3c20-142">接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-142">Reset your connection.</span></span>                                                                            | <span data-ttu-id="c3c20-143">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-143">Yes</span></span>       |
| <span data-ttu-id="c3c20-144">2016330893</span><span class="sxs-lookup"><span data-stu-id="c3c20-144">2016330893</span></span> | <span data-ttu-id="c3c20-145">インターネットへの接続が失われました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-145">You lost connection to the Internet.</span></span> <span data-ttu-id="c3c20-146">接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-146">Reset your connection.</span></span>                                                                            | <span data-ttu-id="c3c20-147">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-147">Yes</span></span>       |
| <span data-ttu-id="c3c20-148">2016330892</span><span class="sxs-lookup"><span data-stu-id="c3c20-148">2016330892</span></span> | <span data-ttu-id="c3c20-149">海外ローミングが無効です。</span><span class="sxs-lookup"><span data-stu-id="c3c20-149">International roaming is disabled.</span></span>                                                                                                     | <span data-ttu-id="c3c20-150">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="c3c20-150">No</span></span>        |
| <span data-ttu-id="c3c20-151">2016330891</span><span class="sxs-lookup"><span data-stu-id="c3c20-151">2016330891</span></span> | <span data-ttu-id="c3c20-152">通話中は、このデバイスの携帯データ ネットワーク接続にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c3c20-152">The cellular data connection for this device cannot be accessed while a phone call is being made.</span></span> <span data-ttu-id="c3c20-153">通話が終了するまでお待ちください。</span><span class="sxs-lookup"><span data-stu-id="c3c20-153">Wait for the phone call to complete.</span></span> | <span data-ttu-id="c3c20-154">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-154">Yes</span></span>       |
| <span data-ttu-id="c3c20-155">2016330890</span><span class="sxs-lookup"><span data-stu-id="c3c20-155">2016330890</span></span> | <span data-ttu-id="c3c20-156">このデバイスの移動体通信ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="c3c20-156">The cellular network for this device.</span></span> <span data-ttu-id="c3c20-157">この時点で、これらのデバイスを使用できませんでした。</span><span class="sxs-lookup"><span data-stu-id="c3c20-157">These devices could not be used at this time.</span></span>                                                   | <span data-ttu-id="c3c20-158">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="c3c20-158">No</span></span>        |
| <span data-ttu-id="c3c20-159">2016330889</span><span class="sxs-lookup"><span data-stu-id="c3c20-159">2016330889</span></span> | <span data-ttu-id="c3c20-160">セキュリティで保護された接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-160">The secure connection failed.</span></span> <span data-ttu-id="c3c20-161">接続をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3c20-161">Reset your connection.</span></span>                                                                                   | <span data-ttu-id="c3c20-162">はい</span><span class="sxs-lookup"><span data-stu-id="c3c20-162">Yes</span></span>       |
| <span data-ttu-id="c3c20-163">2016330888</span><span class="sxs-lookup"><span data-stu-id="c3c20-163">2016330888</span></span> | <span data-ttu-id="c3c20-164">サーバーの信頼評価に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c3c20-164">The server trust evaluation has failed.</span></span>                                                                                                | <span data-ttu-id="c3c20-165">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="c3c20-165">No</span></span>        |

## <a name="next-steps"></a><span data-ttu-id="c3c20-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3c20-166">Next steps</span></span>

<span data-ttu-id="c3c20-167">**[デバイス アクション]** を選択して同期操作の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3c20-167">Choose **Device Actions** to see the status of the sync action.</span></span> 
