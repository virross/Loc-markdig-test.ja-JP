---
title: "Android デバイス向けの Intune カスタム設定"
titleSuffix: Azure portal
description: "Android カスタム プロファイルで使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0bbc5c82c349c8a3d19eeb4433763b53e7485bc0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a><span data-ttu-id="286b3-103">Microsoft Intune での Android デバイス向けのカスタム設定</span><span class="sxs-lookup"><span data-stu-id="286b3-103">Custom settings for Android devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="286b3-104">Microsoft Intune Android **カスタム** プロファイルを使用して、Android デバイスで各機能の制御に使用できる OMA-URI 設定を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="286b3-104">Use the Microsoft Intune Android **Custom** profile to assign OMA-URI settings that can be used to control features on Android devices.</span></span> <span data-ttu-id="286b3-105">これらの設定は、多くのデバイス製造元がデバイスの機能を制御するために使用する標準の設定です。</span><span class="sxs-lookup"><span data-stu-id="286b3-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="286b3-106">この機能は、Intune ポリシーで構成できない次の Android 設定を割り当てられるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="286b3-106">This capability is intended to allow you to assign the following Android settings that are not configurable with Intune policies:</span></span>

- [<span data-ttu-id="286b3-107">Microsoft Intune カスタム デバイス プロファイルを使用して、事前共有キーで Wi-Fi プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="286b3-107">Use a Microsoft Intune custom device profile to create a Wi-Fi profile with a pre-shared key</span></span>](/intune/wi-fi-profile-shared-key)
- [<span data-ttu-id="286b3-108">Microsoft Intune のカスタム プロファイルを使って、Android デバイス用にアプリごとの VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="286b3-108">Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices</span></span>](/intune/android-pulse-secure-per-app-vpn)
- [<span data-ttu-id="286b3-109">Microsoft Intune でカスタム ポリシーを使用して Samsung KNOX Standard デバイス用のアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="286b3-109">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
><span data-ttu-id="286b3-110">このプロファイルの種類は、現在、上に挙げた設定のみで構成できます。</span><span class="sxs-lookup"><span data-stu-id="286b3-110">Only the settings listed above can currently be configured by this profile type.</span></span> <span data-ttu-id="286b3-111">Android デバイスでは、構成できる OMA-URI 設定の完全な一覧が表示されません。</span><span class="sxs-lookup"><span data-stu-id="286b3-111">Android devices do not expose a complete list of OMA-URI settings you can configure.</span></span> <span data-ttu-id="286b3-112">追加されたその他の設定を表示するには、[Intune Uservoice サイト](https://microsoftintune.uservoice.com/forums/291681-ideas)から依頼してください。</span><span class="sxs-lookup"><span data-stu-id="286b3-112">If you want to see further settings added, please request these on the [Intune Uservoice site](https://microsoftintune.uservoice.com/forums/291681-ideas).</span></span>

## <a name="custom-profile-settings-for-android-devices"></a><span data-ttu-id="286b3-113">Android デバイス向けのカスタム プロファイル設定</span><span class="sxs-lookup"><span data-stu-id="286b3-113">Custom profile settings for Android devices</span></span>

1. <span data-ttu-id="286b3-114">「[How to configure custom device settings in Microsoft Intune (Microsoft Intune でカスタム デバイス設定を構成する方法)](custom-settings-configure.md)」の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="286b3-114">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="286b3-115">**[プロファイルを作成します]** ブレードで **[設定]** を選択し、1 つまたは複数の OMA-URI 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="286b3-115">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="286b3-116">**[行の編集]** ブレードで、設定ごとに次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="286b3-116">On the **Edit Row** blade, configure the following values for each setting:</span></span>
    - <span data-ttu-id="286b3-117">**[名前]** - OMA-URI 設定の一意の名前を入力すると、設定リスト内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="286b3-117">**Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="286b3-118">**[説明]** - 設定の概要と、それを特定するために役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="286b3-118">**Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>
    - <span data-ttu-id="286b3-119">**[データ型]** - この OMA-URI 設定を指定するデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="286b3-119">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="286b3-120">**[文字列]**、**[文字列 (XML)]**、**[日付と時刻]**、**[整数]**、**[浮動小数点]**、または **[ブール値]** から選択します。</span><span class="sxs-lookup"><span data-stu-id="286b3-120">Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.</span></span>
    - <span data-ttu-id="286b3-121">**[OMA-URI]** - 設定対象の OMA-URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="286b3-121">**OMA-URI** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="286b3-122">**[値]** - 入力した OMA-URI に関連付ける値を入力します。</span><span class="sxs-lookup"><span data-stu-id="286b3-122">**Value** - Enter the value you want to associate with the OMA-URI you entered.</span></span>
4. <span data-ttu-id="286b3-123">完了したら **[OK]** をクリックし、必要に応じて引き続き他の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="286b3-123">Click **OK** once you are done, then continue to add more settings as required.</span></span>

## <a name="next-steps"></a><span data-ttu-id="286b3-124">次のステップ</span><span class="sxs-lookup"><span data-stu-id="286b3-124">Next steps</span></span>

<span data-ttu-id="286b3-125">設定が完了するとプロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="286b3-125">When you complete the settings, the profile will be created and appears on the profiles list blade.</span></span> <span data-ttu-id="286b3-126">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="286b3-126">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>




