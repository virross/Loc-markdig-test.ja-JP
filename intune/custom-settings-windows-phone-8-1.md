---
title: "Windows Phone 8.1 デバイスの Intune カスタム設定"
titleSuffix: Azure portal
description: "Windows Phone 8.1 カスタム プロファイルで使用できる Intune の設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a2ff0db3aebf2e043e137c96ce1bc6e73ff2f42a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="171a7-103">Microsoft Intune での Windows Phone 8.1 デバイス向けのカスタム設定</span><span class="sxs-lookup"><span data-stu-id="171a7-103">Custom settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="171a7-104">Microsoft Intune Windows Phone 8.1 **カスタム** プロファイルを使用して、Windows Phone 8.1 デバイスで各機能の制御に使用できる OMA-URI 設定を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="171a7-104">Use the Microsoft Intune Windows Phone 8.1 **Custom** profile to assign OMA-URI settings that can be used to control features on Windows Phone 8.1 devices.</span></span> <span data-ttu-id="171a7-105">これらの設定は、多くのデバイス製造元がデバイスの機能を制御するために使用する標準の設定です。</span><span class="sxs-lookup"><span data-stu-id="171a7-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="171a7-106">この機能は、他の Intune ポリシーで構成できない設定を割り当てられるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="171a7-106">This capability is intended to allow you to assign settings that are not configurable with other Intune policies.</span></span>

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a><span data-ttu-id="171a7-107">Windows Phone 8.1 デバイス向けのカスタム ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="171a7-107">Custom policy settings for Windows Phone 8.1 devices</span></span>

1. <span data-ttu-id="171a7-108">「[How to configure custom device settings in Microsoft Intune (Microsoft Intune でカスタム デバイス設定を構成する方法)](custom-settings-configure.md)」の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="171a7-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="171a7-109">**[プロファイルを作成します]** ブレードで **[設定]** を選択し、1 つまたは複数の OMA-URI 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="171a7-109">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="171a7-110">**[行の追加]** ブレードで、設定ごとに次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="171a7-110">On the **Add Row** blade, configure the following values for each setting:</span></span>
    - <span data-ttu-id="171a7-111">**[名前]** - OMA-URI 設定の一意の名前を入力すると、設定リスト内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="171a7-111">**Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="171a7-112">**[説明]** - 設定の概要と、それを特定するために役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="171a7-112">**Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>
    - <span data-ttu-id="171a7-113">**[OMA-URI]** - 設定対象の OMA-URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="171a7-113">**OMA-URI** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="171a7-114">**[データ型]** - この OMA-URI 設定を指定するデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="171a7-114">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="171a7-115">**[文字列]**、**[日付と時刻]**、**[整数]**、**[浮動小数点]**、または **[ブール値]** から選択します。</span><span class="sxs-lookup"><span data-stu-id="171a7-115">Choose from **String**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.</span></span>
    - <span data-ttu-id="171a7-116">**[値]** - 入力した OMA-URI に関連付ける値を入力します。</span><span class="sxs-lookup"><span data-stu-id="171a7-116">**Value** - Enter the value you want to associate with the OMA-URI you entered.</span></span>

4. <span data-ttu-id="171a7-117">完了したら **[OK]** をクリックし、必要に応じて引き続き他の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="171a7-117">Click **OK** once you are done, then continue to add more settings as required.</span></span>
