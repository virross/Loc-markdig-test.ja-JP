---
title: "Intune ソフトウェア クライアントを実行している Windows PC にアプリを追加する"
description: "このトピックでは、Windows PC のアプリを展開する前に、それらのアプリを Intune に追加する方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cd213584780b5dc2e1d80dc51be3908ca444c54c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a><span data-ttu-id="397f3-103">Intune ソフトウェア クライアントを実行している Windows PC にアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="397f3-103">Add apps for Windows PCs that run the Intune software client</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="397f3-104">このトピックでは、アプリを展開する前に、それらのアプリを Intune に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="397f3-104">Use the information in this topic to learn how to add apps to Intune before you deploy them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="397f3-105">このトピックの情報は、Intune ソフトウェア クライアントで管理する Windows PC のアプリを追加するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="397f3-105">The information in this topic helps you add apps for Windows PCs that you manage by using the Intune software client.</span></span> <span data-ttu-id="397f3-106">登録済みの Windows PC やその他のモバイル デバイスにアプリを追加する場合は、「[Microsoft Intune でモバイル デバイスのアプリを追加する](add-apps-for-mobile-devices-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="397f3-106">If you want to add apps for enrolled Windows PCs and other mobile devices, see [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).</span></span>

<span data-ttu-id="397f3-107">PC にアプリをインストールするには、ユーザー操作なしで自動的にインストールできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="397f3-107">To install apps to PCs, they must be capable of being installed silently, with no user interaction.</span></span> <span data-ttu-id="397f3-108">そうでない場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="397f3-108">If this is not the case, the installation will fail.</span></span>


## <a name="add-the-app"></a><span data-ttu-id="397f3-109">アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="397f3-109">Add the app</span></span>
<span data-ttu-id="397f3-110">次の手順に従って、Intune ソフトウェア パブリッシャーでアプリのプロパティを構成し、クラウド ストレージ領域にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="397f3-110">You use the Intune Software Publisher to configure the properties of the app and upload it to your cloud storage space by using the following procedure:</span></span>

1.  <span data-ttu-id="397f3-111">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリの追加]** の順に選択し、Intune ソフトウェア パブリッシャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="397f3-111">In the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher.</span></span>

    > [!TIP]
    > <span data-ttu-id="397f3-112">パブリッシャーを開始する前に、場合によっては、Intune のユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="397f3-112">You might need to enter your Intune user name and password before the publisher starts.</span></span>

2.  <span data-ttu-id="397f3-113">パブリッシャーの **[ソフトウェア セットアップ]** ページの **[このソフトウェアをデバイスに配布する方法]** で、**[ソフトウェア インストーラー]** を選択して次を指定します。</span><span class="sxs-lookup"><span data-stu-id="397f3-113">On the **Software setup** page of the publisher, under **Select how this software is made available to devices**, choose **Software installer**, and then specify:</span></span>

    - <span data-ttu-id="397f3-114">**ソフトウェア インストーラー ファイルの種類を選択する**。</span><span class="sxs-lookup"><span data-stu-id="397f3-114">**Select the software installer file type**.</span></span> <span data-ttu-id="397f3-115">これは展開するソフトウェアの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="397f3-115">This indicates the type of software that you want to deploy.</span></span> <span data-ttu-id="397f3-116">Windows PC の場合、**[Windows インストーラー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-116">For a Windows PC, choose **Windows Installer**.</span></span>
    - <span data-ttu-id="397f3-117">**ソフトウェア セットアップ ファイルの場所を指定する**。</span><span class="sxs-lookup"><span data-stu-id="397f3-117">**Specify the location of the software setup files**.</span></span> <span data-ttu-id="397f3-118">インストール ファイルの場所を入力するか、**[参照]** を選択して一覧から場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-118">Enter the location of the installation files, or choose **Browse** to select the location from a list.</span></span>
    - <span data-ttu-id="397f3-119">**追加のファイルおよび同じフォルダーのサブフォルダーを含める**。</span><span class="sxs-lookup"><span data-stu-id="397f3-119">**Include additional files and subfolders from the same folder**.</span></span> <span data-ttu-id="397f3-120">Windows インストーラーを使用する一部のソフトウェアでは、サポート ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="397f3-120">Some software that uses Windows Installer requires supporting files.</span></span> <span data-ttu-id="397f3-121">これらは、インストール ファイルと同じフォルダーにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="397f3-121">These must be located in the same folder as the installation file.</span></span> <span data-ttu-id="397f3-122">これらのサポート ファイルも展開する場合、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-122">Select this option if you also want to deploy these supporting files.</span></span>

    <span data-ttu-id="397f3-123">たとえば、Intune に Application.msi という名前のアプリを発行する場合、ページは![発行元のソフトウェア セットアップ ページ](./media/publisher-for-pc.png)のようになります。</span><span class="sxs-lookup"><span data-stu-id="397f3-123">For example, if you want to publish an app named Application.msi to Intune, the page would look like this: ![Software setup page of the publisher](./media/publisher-for-pc.png)</span></span>

   <span data-ttu-id="397f3-124">このインストールの種類では、クラウド ストレージ領域がいくらか使用されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-124">This installation type uses some of your cloud storage space.</span></span>

3.  <span data-ttu-id="397f3-125">**[ソフトウェアの説明]** ページで、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="397f3-125">On the **Software description** page, configure the following.</span></span>

    > [!NOTE]
    > <span data-ttu-id="397f3-126">使用するインストーラー ファイルにもよりますが、これらの値の一部は自動的に入力されることもあれば、表示されないこともあります。</span><span class="sxs-lookup"><span data-stu-id="397f3-126">Depending on the installer file that you are using, some of these values might have been automatically entered, or they might not appear.</span></span>

    - <span data-ttu-id="397f3-127">**発行元**。</span><span class="sxs-lookup"><span data-stu-id="397f3-127">**Publisher**.</span></span> <span data-ttu-id="397f3-128">アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="397f3-128">Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="397f3-129">**名前**。</span><span class="sxs-lookup"><span data-stu-id="397f3-129">**Name**.</span></span> <span data-ttu-id="397f3-130">アプリの名前を入力します。この名前は会社のポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-130">Enter the name of the app as it will be displayed in the company portal.</span></span><br /><span data-ttu-id="397f3-131">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="397f3-131">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="397f3-132">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-132">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="397f3-133">**説明**。</span><span class="sxs-lookup"><span data-stu-id="397f3-133">**Description**.</span></span> <span data-ttu-id="397f3-134">アプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="397f3-134">Enter a description for the app.</span></span> <span data-ttu-id="397f3-135">これは会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-135">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="397f3-136">**ソフトウェア情報の URL** (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="397f3-136">**URL for software information** (optional).</span></span> <span data-ttu-id="397f3-137">このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="397f3-137">Enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="397f3-138">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-138">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="397f3-139">**プライバシー URL** (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="397f3-139">**Privacy URL** (optional).</span></span> <span data-ttu-id="397f3-140">このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="397f3-140">Enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="397f3-141">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-141">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="397f3-142">**カテゴリ** (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="397f3-142">**Category** (optional).</span></span> <span data-ttu-id="397f3-143">いずれかの組み込みアプリ カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-143">Select one of the built-in app categories.</span></span> <span data-ttu-id="397f3-144">会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="397f3-144">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="397f3-145">**アイコン** (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="397f3-145">**Icon** (optional).</span></span> <span data-ttu-id="397f3-146">アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="397f3-146">Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="397f3-147">ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-147">This is the icon that will be displayed with the app when users browse the company portal.</span></span>

4.  <span data-ttu-id="397f3-148">**[要件]** ページで、アプリをインストールする前に満たす必要がある要件を選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-148">On the **Requirements** page, select the requirements that must be met before the app can be installed.</span></span> <span data-ttu-id="397f3-149">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-149">Choose from:</span></span>

    - <span data-ttu-id="397f3-150">**アーキテクチャ**。</span><span class="sxs-lookup"><span data-stu-id="397f3-150">**Architecture**.</span></span> <span data-ttu-id="397f3-151">このアプリを 32 ビット版、64 ビット版、または両方のオペレーティング システムにインストールできるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-151">Select whether this app can be installed on 32-bit, 64-bit, or both operating systems.</span></span>
    - <span data-ttu-id="397f3-152">**オペレーティング システム**。</span><span class="sxs-lookup"><span data-stu-id="397f3-152">**Operating System**.</span></span> <span data-ttu-id="397f3-153">このアプリをインストールできる最低限のオペレーティング システムを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-153">Select the minimum operating system on which this app can be installed.</span></span>

5.  <span data-ttu-id="397f3-154">**検出規則** ページで、構成しているアプリが既に PC にインストールされているかどうかを検出する規則を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="397f3-154">On the **Detection rules** page, you can configure rules to detect whether the app that you are configuring is already installed on a PC.</span></span> <span data-ttu-id="397f3-155">または、既定の検出規則を使用して、以前にインストールされたバージョンのアプリを自動的に上書きします。</span><span class="sxs-lookup"><span data-stu-id="397f3-155">Or,  you can use the default detection rules to automatically overwrite any previously installed versions of the app.</span></span> <span data-ttu-id="397f3-156">このオプションは、Windows インストーラー (.exe ファイルのみ) 用です。</span><span class="sxs-lookup"><span data-stu-id="397f3-156">This option is for Windows Installer (.exe files only).</span></span>

    <span data-ttu-id="397f3-157">構成可能な規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="397f3-157">The rules that you can configure are:</span></span>
    - <span data-ttu-id="397f3-158">**ファイルが存在します**。</span><span class="sxs-lookup"><span data-stu-id="397f3-158">**File exists**.</span></span> <span data-ttu-id="397f3-159">検出するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="397f3-159">Specify the path to the file that you want to detect.</span></span> <span data-ttu-id="397f3-160">PC の **%ProgramFiles%** を検索するか (**Program Files**\&lt;path&gt; と **Program Files (x86)**\&lt;path&gt; が検索されます)、または **%SystemDrive%** を検索します (PC のルート ドライブ、通常は C ドライブから検索します)</span><span class="sxs-lookup"><span data-stu-id="397f3-160">You can search under **%ProgramFiles%** (which searches **Program Files**\&lt;path&gt; and **Program Files (x86)**\&lt;path&gt;) on the PC or **%SystemDrive%** (which searches from the root drive of the PC, typically drive C).</span></span>
    - <span data-ttu-id="397f3-161">**MSI 製品コードが存在しています**。</span><span class="sxs-lookup"><span data-stu-id="397f3-161">**MSI product code exists**.</span></span> <span data-ttu-id="397f3-162">**[参照]** を選択し、検索する Windows インストーラー (msi) ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-162">Choose **Browse** to choose the Windows Installer (.msi) file that you want to detect.</span></span>
    - <span data-ttu-id="397f3-163">**レジストリ キーが存在しています**。</span><span class="sxs-lookup"><span data-stu-id="397f3-163">**Registry key exists**.</span></span> <span data-ttu-id="397f3-164">**HKEY_LOCAL_MACHINE\** で始まるレジストリ キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="397f3-164">Specify a registry key that begins with **HKEY_LOCAL_MACHINE\**.</span></span> <span data-ttu-id="397f3-165">32 ビットと 64 ビットの両方のレジストリ パスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-165">Both 32-bit and 64-bit registry paths are searched.</span></span> <span data-ttu-id="397f3-166">指定したキーがいずれかの場所に存在する場合、検出規則が満たされます。</span><span class="sxs-lookup"><span data-stu-id="397f3-166">If the key that you specified exists in either location, the detection rule is satisfied.</span></span>

    <span data-ttu-id="397f3-167">構成した規則のいずれかをアプリが満たすと、それはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="397f3-167">If the app satisfies any of the rules that you have configured, it will not be installed.</span></span>

6.  <span data-ttu-id="397f3-168">**Windows インストーラー** ファイルの種類のみ (msi と exe): **[コマンド ライン引数]** ページで、インストーラーの任意のコマンドライン引数を指定するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-168">For the **Windows Installer** file type only (.msi and .exe): On the **Command line arguments** page, choose whether you want to supply optional command-line arguments for the installer.</span></span>
    <span data-ttu-id="397f3-169">次のパラメーターは、Intune によって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-169">The following parameters are added automatically by Intune:</span></span>
    - <span data-ttu-id="397f3-170">.exe ファイルの場合、**/install** が追加されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-170">For .exe files, **/install** is added.</span></span>
    - <span data-ttu-id="397f3-171">.msi ファイルの場合、**/quiet** が追加されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-171">For .msi files, **/quiet** is added.</span></span>
    <span data-ttu-id="397f3-172">これらのオプションは、アプリ パッケージの作成者がこの機能を有効にした場合のみ機能することにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="397f3-172">Note that these options will only work if the creator of the app package enabled functionality for this.</span></span>

7.  <span data-ttu-id="397f3-173">**Windows インストーラー** ファイルの種類のみ (exe のみ): **[リターン コード]** ページで、アプリが管理対象 Windows PC にインストールされるときに Intune で解釈される新しいエラー コードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="397f3-173">For the **Windows Installer** file type only (.exe only): On the **Return codes** page, you can add new error codes that Intune interprets when the app is installed on a managed Windows PC.</span></span>

    <span data-ttu-id="397f3-174">既定では、Intune は業界標準のリターン コードを使用して、アプリ パッケージが正常にインストールされたかどうかを示します (**0** - 成功。**3010** - 成功 (再起動が必要))。</span><span class="sxs-lookup"><span data-stu-id="397f3-174">By default, Intune uses industry-standard return codes to report the failure or success of an app package installation: **0** (Success) or **3010** (Success with restart).</span></span> <span data-ttu-id="397f3-175">この一覧に独自のリターン コードを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="397f3-175">You can also add your own return codes to this list.</span></span> <span data-ttu-id="397f3-176">リターン コードの一覧を指定し、アプリ インストールで一覧にないコードが返された場合、それはエラーとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-176">If you specify a list of return codes and the app installation returns a code that isn't on the list, it is interpreted as a failure.</span></span>

8.  <span data-ttu-id="397f3-177">**[概要]** ページで、指定した情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="397f3-177">On the **Summary** page, review the information that you specified.</span></span> <span data-ttu-id="397f3-178">準備ができたら、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="397f3-178">When you are ready, choose **Upload**.</span></span>

9. <span data-ttu-id="397f3-179">**[閉じる]** を選択して完了します。</span><span class="sxs-lookup"><span data-stu-id="397f3-179">Choose **Close** to finish.</span></span>

<span data-ttu-id="397f3-180">アプリは **[アプリ]** ワークスペースの **[アプリ]** ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="397f3-180">The app is displayed on the **Apps** node of the **Apps** workspace.</span></span>

## <a name="next-steps"></a><span data-ttu-id="397f3-181">次の手順</span><span class="sxs-lookup"><span data-stu-id="397f3-181">Next steps</span></span>

<span data-ttu-id="397f3-182">アプリを作成したら、次はアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="397f3-182">After you've created an app, the next step is to deploy it.</span></span> <span data-ttu-id="397f3-183">詳細については、「[Microsoft Intune でアプリを展開する](deploy-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="397f3-183">To find out more, see [Deploy apps in Microsoft Intune](deploy-apps.md).</span></span>

<span data-ttu-id="397f3-184">Windows PC にソフトウェアをデプロイする際のヒントとテクニックに関する詳細情報を読むには、「[Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/)」(サポートのヒント: PC への Intune ソフトウェア配布のベスト プラクティス) というブログの投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="397f3-184">If you want to read more information about tips and tricks to deploy software to Windows PCs, see the blog post [Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/).</span></span>
