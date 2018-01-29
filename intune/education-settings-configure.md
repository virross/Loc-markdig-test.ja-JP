---
title: "Windows 10 用に Intune 教育設定を構成する"
titleSuffix: Azure portal
description: "Intune を使用して、管理対象デバイスで Windows 10 の教育設定を構成する方法について説明します。\""
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9f69119e2b50f2e839fa31c1da47d2dafd932942
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a><span data-ttu-id="d04ab-103">Microsoft Intune で Windows 10 教育設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d04ab-103">How to configure Windows 10 education settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d04ab-104">教育プロファイルには、Windows テスト アプリを構成する詳細 (アカウント詳細を含む) とテスト URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d04ab-104">Education profiles let you specify details that configure the Windows Take a Test app including account details, and the test URL.</span></span> <span data-ttu-id="d04ab-105">これを構成するとき、テスト アプリが開き、指定したテストが表示されます。テストが完了するまで他のアプリはデバイスで実行できません。</span><span class="sxs-lookup"><span data-stu-id="d04ab-105">When you configure this, the Take a Test app opens with the test you specify, and no other apps can be run on the device until the test is complete.</span></span>

<span data-ttu-id="d04ab-106">テスト アプリに関する詳細については、「[Windows 10 でテストを受ける](https://docs.microsoft.com/education/windows/take-tests-in-windows-10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04ab-106">For details about the Take a Test app, see [Take tests in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).</span></span>

## <a name="create-a-device-profile-containing-education-profile-settings"></a><span data-ttu-id="d04ab-107">教育プロファイル設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d04ab-107">Create a device profile containing education profile settings</span></span>

1. <span data-ttu-id="d04ab-108">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d04ab-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="d04ab-109">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="d04ab-110">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-110">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="d04ab-111">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="d04ab-112">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="d04ab-113">**[プロファイルを作成します]** ブレードで、デバイスの制限プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="d04ab-114">**[プラットフォーム]** ドロップダウン リストで、**[Windows 10 以降]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-114">From the **Platform** drop-down list, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="d04ab-115">**[プロファイルの種類]** ドロップダウン リストで、**[教育プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-115">From the **Profile type** type drop-down list, choose **Education profile**.</span></span> 
7. <span data-ttu-id="d04ab-116">[設定]、[構成] の順に選択し、**[テスト]** ブレードで次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-116">Choose Settings > Configure, then, on the **Take a Test** blade, configure the following:</span></span>
    - <span data-ttu-id="d04ab-117">**アカウント ユーザー名** - テストで使用するアカウントのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-117">**Account user name** - Enter the user name of the account used with Take a Test.</span></span> <span data-ttu-id="d04ab-118">ユーザー名には、ドメイン アカウント、Azure Active Directory (AAD) アカウント、ローカルのコンピューター アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d04ab-118">This can be a domain account, an Azure Active Directory (AAD) account, or a local computer account.</span></span>
    - <span data-ttu-id="d04ab-119">**評価 URL** - ユーザーに受けさせるテストの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-119">**Assessment URL** - Provide the URL of the test you want users to take.</span></span> <span data-ttu-id="d04ab-120">詳細については、テストに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04ab-120">For more information, see the Take a Test documentation.</span></span>
    - <span data-ttu-id="d04ab-121">**画面の監視** - ユーザーがテストを受けている間、画面の行動を監視できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-121">**Screen monitoring** - Specify whether you want to be able to monitor screen activity while users are taking a test.</span></span>
    - <span data-ttu-id="d04ab-122">**テキストの候補** - ユーザーがテストを受けている間、テキスト候補の表示を許可するか、禁止します。</span><span class="sxs-lookup"><span data-stu-id="d04ab-122">**Text suggestion** - Allow or block text suggestions while users are taking a test.</span></span>
8. <span data-ttu-id="d04ab-123">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d04ab-123">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="d04ab-124">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04ab-124">The profile will be created and appears on the profiles list blade.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d04ab-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="d04ab-125">Next steps</span></span>

<span data-ttu-id="d04ab-126">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04ab-126">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



