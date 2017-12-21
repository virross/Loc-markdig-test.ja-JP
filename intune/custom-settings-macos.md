---
title: "macOS デバイス向けの Intune カスタム設定"
titleSuffix: Azure portal
description: "macOS カスタム プロファイルで使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e2c3fc3f95fb1f3f1bfea8b3b151ff774d6c2b46
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a><span data-ttu-id="f79f8-103">Microsoft Intune での macOS デバイス向けのカスタム設定</span><span class="sxs-lookup"><span data-stu-id="f79f8-103">Custom settings for macOS devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f79f8-104">Microsoft Intune の macOS カスタム プロファイルを使用して、[Apple Configurator ツール](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)で作成した設定を macOS デバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-104">Use the Microsoft Intune macOS custom profile to assign settings that you created by using the [Apple Configurator tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) to macOS devices.</span></span> <span data-ttu-id="f79f8-105">このツールを使用すると、これらのデバイスの動作を制御する多くの設定を作成し、構成プロファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-105">This tool lets you create many settings that control the operation of these devices and export them to a configuration profile.</span></span> <span data-ttu-id="f79f8-106">その後、この構成プロファイルを Intune macOS カスタム プロファイルにインポートし、組織内のユーザーとデバイスに設定を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-106">You can then import this configuration profile into an Intune macOS custom profile and assign the settings to users and devices in your organization.</span></span>

<span data-ttu-id="f79f8-107">この機能を使用すれば、他の Intune プロファイルの種類で構成できない macOS 設定を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-107">This capability allows you to assign macOS settings that are not configurable with other Intune profile types.</span></span>


1. <span data-ttu-id="f79f8-108">「[How to configure custom device settings in Microsoft Intune (Microsoft Intune でカスタム デバイス設定を構成する方法)](custom-settings-configure.md)」の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="f79f8-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="f79f8-109">**[プロファイルを作成します]** ブレードで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="f79f8-109">On the **Create Profile** blade, specify the following:</span></span>

- <span data-ttu-id="f79f8-110">**[カスタム構成プロファイル名]** - プロファイルの名前を指定します。この名前が、デバイスや Intune の状態に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-110">**Custom configuration profile name** - Provide a name for the policy as it will be displayed on the device, and in Intune status.</span></span>
- <span data-ttu-id="f79f8-111">**[構成プロファイル名]** - Apple Configurator を使用して作成した構成プロファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f79f8-111">**Configuration profile file** - Browse to the configuration profile that you created by using the Apple Configurator.</span></span>
<span data-ttu-id="f79f8-112">Apple Configurator ツールからエクスポートした設定に、macOS カスタム ポリシーを割り当てるデバイス上の macOS のバージョンとの互換性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f79f8-112">Ensure that the settings you export from the Apple Configurator tool are compatible with the version of macOS on the devices to which you assign the macOS custom policy.</span></span> <span data-ttu-id="f79f8-113">互換性のない設定を解決する方法については、[Apple 開発者](https://developer.apple.com/) Web サイトで「**Configuration Profile Reference**」 (構成プロファイル リファレンス) および「**Mobile Device Management Protocol Reference**」 (モバイル デバイス管理プロトコル リファレンス) を検索してください。</span><span class="sxs-lookup"><span data-stu-id="f79f8-113">For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.</span></span>

<span data-ttu-id="f79f8-114">インポートしたファイルは、ブレードの **[ファイルの内容]** 領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f79f8-114">The file you imported will be displayed in the **File contents** area of the blade.</span></span>
