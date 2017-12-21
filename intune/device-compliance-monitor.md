---
title: "デバイス コンプライアンスを監視する方法"
titlesuffix: Azure portal
description: "デバイス コンプライアンスを監視する方法を説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 65b156923a38d9b3d976604819ede300f063a88b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-monitor-device-compliance-in-intune"></a><span data-ttu-id="905e0-103">Intune でデバイス コンプライアンスを監視する方法</span><span class="sxs-lookup"><span data-stu-id="905e0-103">How to monitor device compliance in Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="905e0-104">**[概要]** ブレードでは、**コンプライアンス プロファイル**の状態の概要を確認できます。</span><span class="sxs-lookup"><span data-stu-id="905e0-104">You can view the summary of the status of your **compliance profiles** in the **Overview** blade.</span></span>
<span data-ttu-id="905e0-105">対話形式でグラフをクリックスルーして、詳細にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="905e0-105">You can interactively click through the charts to drill down into the details.</span></span> <span data-ttu-id="905e0-106">複数のコンプライアンス プロファイルを構成している場合は、ポリシー ブレードに移動し、**[管理]** セクションで **[レポート]** を選択して、各ポリシーの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="905e0-106">If you have multiple compliance profiles configured, you can also view the status for each policy by going to the policy blade and choosing **Reports** in the **Manage** section.</span></span>  <span data-ttu-id="905e0-107">表示できるレポートの詳細を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="905e0-107">The details of the reports available are listed below.</span></span>

##  <a name="device-compliance"></a><span data-ttu-id="905e0-108">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="905e0-108">Device compliance</span></span>

<span data-ttu-id="905e0-109">デバイス コンプライアンス レポートの概要ビューには、次のいずれかとして報告されたデバイスの数に関する集計情報がまず表示されます。</span><span class="sxs-lookup"><span data-stu-id="905e0-109">The summarized view of the device compliance report shows starts with showing you the aggregated information about the number of devices that are reporting as one of the following:</span></span>

- <span data-ttu-id="905e0-110">**[準拠]**: デバイスは最近コンプライアンスが評価され、指定したコンプライアンス プロファイル設定に準拠していると判断されました。</span><span class="sxs-lookup"><span data-stu-id="905e0-110">**Compliant**: Device has been evaluated for compliance recently and has been determined as compliant with the compliance profile settings you specified.</span></span>
- <span data-ttu-id="905e0-111">**[非準拠]**: デバイスは評価され、非準拠と判断されました。</span><span class="sxs-lookup"><span data-stu-id="905e0-111">**Noncompliant**: The device has been evaluated and determined as noncompliant.</span></span>  <span data-ttu-id="905e0-112">プロファイルで猶予期間が指定されていた場合、猶予期間が終了して、デバイスが非準拠状態になっています。</span><span class="sxs-lookup"><span data-stu-id="905e0-112">If there was a grace period specified in the profile, the grace period has expired putting the device in a noncompliant status.</span></span>
- <span data-ttu-id="905e0-113">**[猶予期間]**: デバイスは評価され、非準拠と判断されました。</span><span class="sxs-lookup"><span data-stu-id="905e0-113">**Grace period**: Device has been evaluated and determined as noncompliant.</span></span> <span data-ttu-id="905e0-114">ただし、デバイスが実際に非準拠としてマークされるまでの猶予期間がまだ適用されています。</span><span class="sxs-lookup"><span data-stu-id="905e0-114">However, the grace period still applies before the device is actually marked as noncompliant.</span></span>

<span data-ttu-id="905e0-115">各セクションにドリルダウンすると、個々のデバイスとユーザーの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="905e0-115">You can drill down on each section to see more details on the individual devices and users.</span></span>

## <a name="setting-compliance"></a><span data-ttu-id="905e0-116">コンプライアンスの設定</span><span class="sxs-lookup"><span data-stu-id="905e0-116">Setting compliance</span></span>

<span data-ttu-id="905e0-117">コンプライアンスの設定レポートには、次のような各コンプライアンス設定の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="905e0-117">The setting compliance report provides the details for each compliance settings such as:</span></span>

- <span data-ttu-id="905e0-118">設定に準拠していないデバイスの数。</span><span class="sxs-lookup"><span data-stu-id="905e0-118">Number of devices that are noncompliant with the setting.</span></span>
- <span data-ttu-id="905e0-119">設定が適用されているプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="905e0-119">The platform that the setting is applied to.</span></span>

<span data-ttu-id="905e0-120">各設定をドリルダウンすると、これらの設定が有効になっているプロファイルの詳細情報と設定の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="905e0-120">You can drill down on each of the setting to see more information about the profiles on which these settings have been enabled, and the value of the setting.</span></span>
