---
title: "Windows 8.1 以降の Wi-Fi 設定のインポート"
titleSuffix: Azure portal
description: "Wi-Fi 設定を Windows から Intune Wi-Fi プロファイルにインポートする方法。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b9fd64449c94636040de1692c0fb6e30b3a551b
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a><span data-ttu-id="1af05-103">Microsoft Intune で Windows 8.1 以降のデバイス向け Wi-Fi 設定をインポートする方法</span><span class="sxs-lookup"><span data-stu-id="1af05-103">How to import Wi-Fi settings for Windows 8.1 and later devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1af05-104">Windows 8.1 または Windows 10 デスクトップまたはモバイルを実行するデバイスの場合は、以前エクスポートされた Wi-Fi 構成プロファイルをファイルにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1af05-104">For devices that run Windows 8.1 or Windows 10 desktop or mobile, you can import a Wi-Fi configuration profile that was previously exported to a file.</span></span>

## <a name="export-wi-fi-settings-from-a-windows-device"></a><span data-ttu-id="1af05-105">Windows デバイスからの Wi-Fi 設定のエクスポート</span><span class="sxs-lookup"><span data-stu-id="1af05-105">Export Wi-Fi settings from a Windows device</span></span>

<span data-ttu-id="1af05-106">Windows で、**netsh wlan** ユーティリティを使用して、既存の Wi-Fi プロファイルを Intune で読み取れる XML ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1af05-106">In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune.</span></span> <span data-ttu-id="1af05-107">必要な Wi-Fi プロファイルが既にインストールされている Windows コンピューターでは、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1af05-107">On a Windows computer that already has the required WiFi profile installed, follow this following procedure.</span></span>
1. <span data-ttu-id="1af05-108">エクスポートされた Wi-Fi プロファイル用のローカル フォルダー (**c:\WiFi** など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1af05-108">Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.</span></span>
1. <span data-ttu-id="1af05-109">コマンド プロンプトを管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="1af05-109">Open up a Command Prompt as an administrator.</span></span>
1. <span data-ttu-id="1af05-110">**netsh wlan show profiles** コマンドを実行し、エクスポートするプロファイルの名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="1af05-110">Run the command **netsh wlan show profiles**, and note the name of the profile you'd like to export.</span></span> <span data-ttu-id="1af05-111">この例では、プロファイル名は **WiFiName** です。</span><span class="sxs-lookup"><span data-stu-id="1af05-111">In this example, the profile name is **WiFiName**.</span></span>
1. <span data-ttu-id="1af05-112">**netsh wlan export profile name="ProfileName" folder=c:\Wifi** コマンドを実行します。これにより、**Wi-Fi-WiFiName.xml** という名前の Wi-Fi プロファイル ファイルがターゲット フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="1af05-112">Run this command: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**.This will create a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.</span></span>

## <a name="import-the-wi-fi-settings-into-intune"></a><span data-ttu-id="1af05-113">Intune への Wi-Fi 設定のインポート</span><span class="sxs-lookup"><span data-stu-id="1af05-113">Import the Wi-Fi settings into Intune</span></span>

1. <span data-ttu-id="1af05-114">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1af05-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="1af05-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="1af05-116">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-116">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="1af05-117">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-117">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="1af05-118">[プロファイル] ブレードで、**[プロファイルを作成します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1af05-118">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="1af05-119">**[プロファイルを作成します]** ブレードで、デバイスの制限プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="1af05-119">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="1af05-120">**[プラットフォーム]** ドロップダウン リストで、**[Windows 8.1 以降]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-120">From the **Platform** drop-down list, choose **Windows 8.1 and later**.</span></span>
6. <span data-ttu-id="1af05-121">**[プロファイルの種類]** ドロップダウン リストで、**[Wi-Fi インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-121">From the **Profile** type drop-down list, choose **Wi-Fi import**.</span></span>
7. <span data-ttu-id="1af05-122">**[Wi-fi Basic]** ブレードで、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="1af05-122">On the **Wi-Fi Basic** blade, configure the following:</span></span>
    - <span data-ttu-id="1af05-123">**[接続名]**: Wi-Fi 接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1af05-123">**Connection name** Enter the name of the Wi-Fi connection.</span></span> <span data-ttu-id="1af05-124">この名前は、使用可能な Wi-Fi ネットワークを参照しているエンド ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1af05-124">This name will be displayed to end users when they browse available Wi-Fi networks.</span></span>
    - <span data-ttu-id="1af05-125">**[プロファイル XML]**: 参照ボタンをクリックして、Intune にインポートする Wi-Fi プロファイル設定を含む XML ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1af05-125">**Profile XML** Click the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.</span></span>
    - <span data-ttu-id="1af05-126">**[ファイルの内容]**: 選択した構成プロファイルの XML コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1af05-126">**File contents** Displays the XML code for the configuration profile you selected.</span></span>
8. <span data-ttu-id="1af05-127">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1af05-127">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="1af05-128">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1af05-128">The profile will be created and appears on the profiles list blade.</span></span>
