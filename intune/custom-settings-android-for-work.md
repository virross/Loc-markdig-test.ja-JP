---
title: "Android for Work 向けの Intune カスタム プロファイル設定"
titlesuffix: Azure portal
description: "Android for Work デバイス用の Intune カスタム プロファイル設定を作成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f12d71b9477e3072b7952d3f9331ed0cefc33ac7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a><span data-ttu-id="df2b3-103">Android for Work デバイス向けの Intune カスタム プロファイル設定の作成</span><span class="sxs-lookup"><span data-stu-id="df2b3-103">Create Intune custom profile settings for Android for Work devices</span></span>

<span data-ttu-id="df2b3-104">Intune Android for Work カスタム構成ポリシーを使用して、Android for Work デバイスでの各機能の制御に使用できる OMA-URI 設定を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="df2b3-104">Use the Intune Android for Work custom configuration policy to assign OMA-URI settings that can be used to control features on Android for Work devices.</span></span> <span data-ttu-id="df2b3-105">これらの設定は、多くのデバイス製造元がデバイスの機能を制御するために使用する標準の設定です。</span><span class="sxs-lookup"><span data-stu-id="df2b3-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="df2b3-106">この機能は、Intune ポリシーで構成できない Android 設定を割り当てられるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="df2b3-106">This capability is intended to allow you to assign Android settings that are not configurable with Intune policies.</span></span> <span data-ttu-id="df2b3-107">現時点では、Intune でサポートされる Android カスタム ポリシーの数は限られています。</span><span class="sxs-lookup"><span data-stu-id="df2b3-107">Intune supports a limited number of Android custom policies at present.</span></span> <span data-ttu-id="df2b3-108">構成できるポリシーを見つける場合は、このトピックの例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2b3-108">See the examples in this topic to find out which policies you can configure.</span></span>

## <a name="create-a-custom-profile"></a><span data-ttu-id="df2b3-109">カスタム プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="df2b3-109">Create a custom profile</span></span>

1. <span data-ttu-id="df2b3-110">「[Microsoft Intune でカスタム デバイス設定を構成する方法](custom-settings-configure.md)」の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-110">Use the instructions in [How to configure custom device settings](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="df2b3-111">**[OMA-URI のカスタム設定]** ブレードで **[追加]** を選択して、新しい設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-111">On the **Custom OMA-URI Settings** blade, choose **Add** to add a new setting.</span></span>
3. <span data-ttu-id="df2b3-112">**[行の追加]** ブレードで、以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-112">On the **Add Row** blade, configure the following:</span></span>
    - <span data-ttu-id="df2b3-113">**[名前]** - Android for Work カスタム設定の一意の名前を入力すると、Azure Portal 内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="df2b3-113">**Name** - Enter a unique name for the Android for work custom settings to help you identify it in the Azure portal.</span></span>
    - <span data-ttu-id="df2b3-114">**[説明]** - Android カスタム ポリシーの概要や、ポリシーを特定するのに役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-114">**Description** - Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.</span></span>
    - <span data-ttu-id="df2b3-115">**[OMA-URI]** - 設定対象の OMA-URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-115">**OMA-URI** - Enter the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="df2b3-116">**[データ型]** - この OMA-URI 設定を指定するデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-116">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="df2b3-117">**[文字列]**、**[文字列 (XML ファイル)]**、**[日付と時刻]**、**[整数]**、**[浮動小数点]**、**[ブール値]**、または **[Base64 (ファイル)]** から選択します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-117">Choose from **String**, **String (XML file)**, **Date and time**, **Integer**, **Floating point**, **Boolean**, or **Base64 (file)**.</span></span>
    - <span data-ttu-id="df2b3-118">**[値]** - 以前に指定した OMA-URI に関連付ける値を指定します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-118">**Value** - Specify the value to associate with the OMA-URI that you specified previously.</span></span> <span data-ttu-id="df2b3-119">この値の指定に使用する方法は、選択したデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="df2b3-119">The method you use to supply this value will vary according to the data type you selected.</span></span> <span data-ttu-id="df2b3-120">たとえば、**[日付と時刻]** を選択した場合は、[日付の選択] から値を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-120">For example, if you chose **Date and time**, you'll select the value from a date picker.</span></span>
4. <span data-ttu-id="df2b3-121">完了したら、[OK] を選択して **[OMA-URI のカスタム設定]** に戻り、他の設定を追加するか、**[作成]** を選択してカスタム プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-121">When you have finished, choose OK to return to the **Custom OMA-URI Settings**, and then add more settings, or choose **Create** to create the custom profile.</span></span>


## <a name="example"></a><span data-ttu-id="df2b3-122">例</span><span class="sxs-lookup"><span data-stu-id="df2b3-122">Example</span></span>

<span data-ttu-id="df2b3-123">この例では、管理対象の Android for Work デバイスで、仕事用アプリと個人用アプリの間でのコピーと貼り付け操作の許可を制限するのに使用される、カスタム プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-123">In this example, you'll create a custom profile that can be used to restrict whether copy and paste actions between work and personal apps are allowed on managed Android for Work devices.</span></span>

1. <span data-ttu-id="df2b3-124">このトピックの手順を使用して、次の値を用い、Android for Work デバイス用のカスタム プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-124">Use the procedure in this topic to create a custom profile for Android for Work devices using the following values:</span></span>
    - <span data-ttu-id="df2b3-125">**[名前]** - 「コピーと貼り付けをブロック」または独自のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-125">**Name** - Enter "Block copy and paste" or text of your own choosing.</span></span>
    - <span data-ttu-id="df2b3-126">**[説明]** - 「仕事用アプリと個人用アプリの間でのコピーや貼り付けをブロック」または独自のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-126">**Description** - Enter "Blocks copy/paste between work and personal apps" or text of your own choosing.</span></span>
    - <span data-ttu-id="df2b3-127">**[OMA-URI]** - 「**./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-127">**OMA-URI** - Enter **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.</span></span>
    - <span data-ttu-id="df2b3-128">**[データ型]** - **[ブール]** を選択して、この OMA-URI の値が **True** または **False** のいずれかであるかを示します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-128">**Data type** - Select **Boolean** to indicate that the value for this OMA-URI is either **True** or **False**.</span></span>
    - <span data-ttu-id="df2b3-129">**[値]** - **True** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df2b3-129">**Value** - Select **True**.</span></span>
2. <span data-ttu-id="df2b3-130">最終的に、この画像のような設定になります。</span><span class="sxs-lookup"><span data-stu-id="df2b3-130">You should end up with a setting looking similar to this image.</span></span>
<span data-ttu-id="df2b3-131">![Android for Work でのコピーと貼り付けをブロック](./media/custom-policy-afw-copy-paste.png)</span><span class="sxs-lookup"><span data-stu-id="df2b3-131">![Block copy and paste for Android for Work.](./media/custom-policy-afw-copy-paste.png)</span></span>
3. <span data-ttu-id="df2b3-132">これで、このカスタム プロファイルを管理対象の Android for Work デバイスに割り当てると、仕事用アプリと個人用アプリの間でのコピーと貼り付けはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df2b3-132">Now, when you assign this custom profile to Android for Work devices you manage, copy and paste will be blocked between apps in the work, and personal profiles.</span></span>