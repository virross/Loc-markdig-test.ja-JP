---
title: "Windows 10 デバイス向けの Intune カスタム設定"
titlesuffix: Azure portal
description: "Windows 10 カスタム プロファイルで使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa11591bf356165f57eb41db2d21b8f727e506d7
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="1e146-103">Microsoft Intune での Windows 10 デバイス向けのカスタム デバイス設定</span><span class="sxs-lookup"><span data-stu-id="1e146-103">Custom device settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 <span data-ttu-id="1e146-104">Windows 10 と Windows 10 Mobile 用の Microsoft Intune **カスタム** プロファイルを使用して、デバイスで各機能の制御に使用できる OMA-URI (Open Mobile Alliance Uniform Resource Identifier) 設定を展開します。</span><span class="sxs-lookup"><span data-stu-id="1e146-104">Use the Microsoft Intune **custom** profile for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices.</span></span> <span data-ttu-id="1e146-105">Windows 10 では、[Policy Configuration Service プロバイダー (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) など、多くの CSP 設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e146-105">Windows 10 makes many CSP settings available, for example, the [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).</span></span>
<span data-ttu-id="1e146-106">特定の設定を探しているのであれば、[Windows 10 デバイス制限プロファイル](device-restrictions-windows-10.md)には Intune に組み込まれているさまざまな設定があり、カスタム値の指定が要求されないことにご留意ください。</span><span class="sxs-lookup"><span data-stu-id="1e146-106">If you are looking for a particular setting, remember that the [Windows 10 device restriction profile](device-restrictions-windows-10.md) contains many settings that are built-in to Intune and do not require you to specify custom values.</span></span>

1. <span data-ttu-id="1e146-107">「[How to configure custom device settings in Microsoft Intune (Microsoft Intune でカスタム デバイス設定を構成する方法)](custom-settings-configure.md)」の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="1e146-107">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="1e146-108">**[プロファイルを作成します]** ブレードで **[設定]** を選択し、1 つまたは複数の OMA-URI 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e146-108">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="1e146-109">**[OMA-URI のカスタム設定]** ブレードで **[追加]** をクリックして、新しい値を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e146-109">On the **Custom OMA-URI Settings** blade, click **Add** to add a new value.</span></span> <span data-ttu-id="1e146-110">**[エクスポート]** をクリックして、コンマ区切り値 (.csv) ファイルで構成した値の一覧を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1e146-110">You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.</span></span>
4. <span data-ttu-id="1e146-111">各 OMA-URI 設定を追加するには、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e146-111">For each OMA-URI setting you want to add, enter the following information.</span></span> <span data-ttu-id="1e146-112">このトピックにあるリストを使用して、使用できる設定の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e146-112">Use the list in this topic to learn about the settings you can use:</span></span>
    - <span data-ttu-id="1e146-113">**設定名** - OMA-URI 設定の一意の名前を入力すると、設定リスト内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="1e146-113">**Setting name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="1e146-114">**設定の説明** - 必要に応じて、設定の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e146-114">**Setting description** - Optionally, enter a description for the setting.</span></span>
    - <span data-ttu-id="1e146-115">**データ型** - 以下から選択します。</span><span class="sxs-lookup"><span data-stu-id="1e146-115">**Data type** - Choose from:</span></span>
        - <span data-ttu-id="1e146-116">**文字列**</span><span class="sxs-lookup"><span data-stu-id="1e146-116">**String**</span></span>
        - <span data-ttu-id="1e146-117">**文字列型 (XML)**</span><span class="sxs-lookup"><span data-stu-id="1e146-117">**String (XML)**</span></span>
        - <span data-ttu-id="1e146-118">**日付と時刻**</span><span class="sxs-lookup"><span data-stu-id="1e146-118">**Date and time**</span></span>
        - <span data-ttu-id="1e146-119">**整数型**</span><span class="sxs-lookup"><span data-stu-id="1e146-119">**Integer**</span></span>
        - <span data-ttu-id="1e146-120">**浮動小数点**</span><span class="sxs-lookup"><span data-stu-id="1e146-120">**Floating point**</span></span>
        - <span data-ttu-id="1e146-121">**ブール型**</span><span class="sxs-lookup"><span data-stu-id="1e146-121">**Boolean**</span></span>
    - <span data-ttu-id="1e146-122">**OMA-URI (大文字と小文字を区別)** - 設定対象の OMA-URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e146-122">**OMA-URI (case sensitive)** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="1e146-123">**値** - 入力した OMA-URI に関連付ける値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e146-123">**Value** - Specify the value to associate with the OMA-URI you entered.</span></span>
5. <span data-ttu-id="1e146-124">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e146-124">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>
<span data-ttu-id="1e146-125">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e146-125">The profile will be created and appears on the profiles list blade.</span></span>

## <a name="example"></a><span data-ttu-id="1e146-126">例</span><span class="sxs-lookup"><span data-stu-id="1e146-126">Example</span></span>
<span data-ttu-id="1e146-127">以下のスクリーン ショットで、**Connectivity/AllowVPNOverCellular** 設定が有効になりました。</span><span class="sxs-lookup"><span data-stu-id="1e146-127">In the screenshot below, the setting **Connectivity/AllowVPNOverCellular** has been enabled.</span></span> <span data-ttu-id="1e146-128">これにより、移動体通信ネットワーク上の Windows 10 デバイスで OpenVPN 接続を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1e146-128">This lets a Windows 10 device open a VPN connection when on a cellular network.</span></span>

> ![VPN 設定を含むカスタム ポリシーの例](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a><span data-ttu-id="1e146-130">構成できるポリシーを見つける方法</span><span class="sxs-lookup"><span data-stu-id="1e146-130">How to find the policies you can configure</span></span>

<span data-ttu-id="1e146-131">Windows ドキュメント ライブラリの[構成サービス プロバイダー リファレンス](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference)に、Windows 10 でサポートされているすべての構成サービス プロバイダー (CSP) の完全一覧があります。</span><span class="sxs-lookup"><span data-stu-id="1e146-131">You’ll find a complete list of all configuration service providers (CSPs) that Windows 10 supports in the [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in the Windows documentation library.</span></span>

<span data-ttu-id="1e146-132">Windows 10 のバージョンによっては、一部の設定に互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="1e146-132">Not all settings are compatible with all Windows 10 versions.</span></span> <span data-ttu-id="1e146-133">Windows トピックの表を見れば、各 CSP でサポートされているバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1e146-133">The table in the Windows topic tells you which versions are supported for each CSP.</span></span>

<span data-ttu-id="1e146-134">また、トピックの一覧にある設定の一部は Intune でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e146-134">Additionally, Intune does not support all of the settings listed in the topic.</span></span> <span data-ttu-id="1e146-135">Intune で必要な設定がサポートされているかどうかを確認するには、その設定のトピックを開きます。</span><span class="sxs-lookup"><span data-stu-id="1e146-135">To find out if Intune supports the setting you want, open the topic for that setting.</span></span> <span data-ttu-id="1e146-136">各設定ページには、サポートされている操作が示されます。</span><span class="sxs-lookup"><span data-stu-id="1e146-136">Each setting page shows it’s supported operation.</span></span> <span data-ttu-id="1e146-137">Intune で利用するには、その設定で**追加**操作または**置換**操作がサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e146-137">To work with Intune, the setting must support the **Add** or **Replace** operations.</span></span>


