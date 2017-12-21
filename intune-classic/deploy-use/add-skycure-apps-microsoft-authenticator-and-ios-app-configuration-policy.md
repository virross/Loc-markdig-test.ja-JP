---
title: "Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーの追加"
description: "Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーを Intune クラシック ポータルに追加します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cedf3db964c2a5c186af3033b44ee50a345c729e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a><span data-ttu-id="62278-103">Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーの追加</span><span class="sxs-lookup"><span data-stu-id="62278-103">Add Skycure apps, Microsoft Authenticator app and iOS configuration policy</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="62278-104">脅威がモバイル デバイスで特定されたときにエンドユーザーが通知を受け取れるように、また、脅威を除去するための手引きが受けられるように、Intune を利用して Skycure アプリを追加して展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62278-104">You need to use Intune to add and deploy the Skycure apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="62278-105">また、[Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) と iOS アプリ構成ポリシーが必要になります。Microsoft Authenticator を使用すると、Azure AD によってユーザーの ID の確認が行われます。iOS アプリ構成ポリシーは、Intune と Azure AD のシングル サインオン (SSO) を使用するように Skycure iOS アプリに信号を送るため、ユーザーは Skycure アプリにログインするたびにユーザー名とパスワードを入力する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="62278-105">Additionally, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD, and the iOS app configuration policy which signals the Skycure iOS app to use Intune and Azure AD Single Sign On (SSO) so users don’t need to type username and password every time they log in the Skycure app.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="62278-106">始める前に</span><span class="sxs-lookup"><span data-stu-id="62278-106">Before you begin</span></span>

-   <span data-ttu-id="62278-107">[Intune クラシック ポータル](https://manage.microsoft.com/)で以下の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62278-107">The below steps need to be completed in the [Intune classic portal](https://manage.microsoft.com/).</span></span>

-   <span data-ttu-id="62278-108">Skycure 管理コンソールで以前に構成したものと同じ Azure AD アカウントを使います。これは、Intune クラシック ポータルにログインするためのものと同じアカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62278-108">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic portal.</span></span>

-   <span data-ttu-id="62278-109">Skycure 統合ファイルを利用できる状態にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="62278-109">You need to have the Skycure integration file ready to use.</span></span> <span data-ttu-id="62278-110">これは以前、Skycure 管理コンソールからダウンロードしておいた .zip ファイルです。**skycure\_configuration.plist** というファイルと iOS アプリ構成ポリシー パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62278-110">This is the .zip file previously downloaded from the Skycure Management console, which contains the file **skycure\_configuration.plist** with the iOS app configuration policy parameters.</span></span>

-   <span data-ttu-id="62278-111">次のプロセスをよく理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="62278-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="62278-112">[Intune にアプリを追加する](/intune-classic/deploy-use/add-apps)。</span><span class="sxs-lookup"><span data-stu-id="62278-112">[Adding an app into Intune](/intune-classic/deploy-use/add-apps).</span></span>

    -   <span data-ttu-id="62278-113">[iOS アプリ構成ポリシーを Intune に追加する](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="62278-113">[Adding an iOS app configuration policy into Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-add-the-skycure-app-for-android"></a><span data-ttu-id="62278-114">Android 向け Skycure アプリを追加するには</span><span class="sxs-lookup"><span data-stu-id="62278-114">To add the Skycure app for Android</span></span>

1.  <span data-ttu-id="62278-115">Intune クラシック ポータルで、**[アプリ]** &gt; **[アプリの追加]** の順に選択して Intune ソフトウェア パブリッシャーを起動し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-115">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="62278-116">**[ソフトウェア セットアップ]** ページで **[外部リンク]** を選択し、**[URL の指定]** に [Android 向け Skycure アプリの URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="62278-116">On the **Software setup** page, choose **External link**, then paste the [Skycure app for Android url](https://play.google.com/store/apps/details?id=com.skycure.skycure) under **Specify the URL**.</span></span>

    ![Intune ソフトウェア パブリッシャーの [URL の指定]](../media/mtp/skycure-add-apps-1.png)

3.  <span data-ttu-id="62278-118">**[ソフトウェアの説明]** ページの **[発行元]**、**[名前]**、**[説明]** に入力し、**[このアプリをポータル サイトでおすすめアプリとして強調表示します]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-118">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune ソフトウェア パブリッシャーの [ソフトウェアの説明]](../media/mtp/skycure-add-apps-2.png)

4.  <span data-ttu-id="62278-120">**[アップロード]** をクリックし、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-120">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-skycure-app-for-ios"></a><span data-ttu-id="62278-121">iOS 向け Skycure アプリを追加するには</span><span class="sxs-lookup"><span data-stu-id="62278-121">To add the Skycure app for iOS</span></span>

1.  <span data-ttu-id="62278-122">Intune クラシック ポータルで、**[アプリ]** &gt; **[アプリの追加]** の順に選択して Intune ソフトウェア パブリッシャーを起動し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-122">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="62278-123">**[ソフトウェア セットアップ]** ページで **[App Store の管理されている iOS アプリ]** を選択し、**[URL の指定]** に [iOS 向け Skycure アプリの URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="62278-123">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Skycure app for iOS url](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) under **Specify the URL**.</span></span>

    ![Intune ソフトウェア パブリッシャーの管理対象 iOS アプリ](../media/mtp/skycure-add-apps-3.png)

3.  <span data-ttu-id="62278-125">**[ソフトウェアの説明]** ページの **[発行元]**、**[名前]**、**[説明]** に入力し、**[このアプリをポータル サイトでおすすめアプリとして強調表示します]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-125">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune ソフトウェア パブリッシャーのオプション](../media/mtp/skycure-add-apps-4.png)

4.  <span data-ttu-id="62278-127">**[要件]** ページの **[モバイル デバイスの種類]** で **[すべて]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-127">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="62278-128">**[アップロード]** をクリックし、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-128">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a><span data-ttu-id="62278-129">iOS 向けの Microsoft Authenticator アプリを追加するには</span><span class="sxs-lookup"><span data-stu-id="62278-129">To add the Microsoft Authenticator app for iOS</span></span>

1.  <span data-ttu-id="62278-130">Intune クラシック ポータルで、**[アプリ]** &gt; **[アプリの追加]** の順に選択して Intune ソフトウェア パブリッシャーを起動し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-130">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="62278-131">**[ソフトウェア セットアップ]** ページで **[App Store の管理されている iOS アプリ]** を選択し、**[URL の指定]** に [iOS 向け Microsoft Authenticator アプリの URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="62278-131">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Microsoft Authenticator app for iOS url](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) under **Specify the URL**.</span></span>

    ![Intune ソフトウェア パブリッシャーの管理対象 iOS アプリ 2](../media/mtp/skycure-add-apps-5.png)

3.  <span data-ttu-id="62278-133">**[ソフトウェアの説明]** ページの **[発行元]**、**[名前]**、**[説明]** に入力し、**[このアプリをポータル サイトでおすすめアプリとして強調表示します]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-133">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune ソフトウェア パブリッシャーの管理対象 iOS アプリ 3](../media/mtp/skycure-add-apps-6.png)

4.  <span data-ttu-id="62278-135">**[要件]** ページの **[モバイル デバイスの種類]** で **[すべて]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-135">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="62278-136">**[アップロード]** をクリックし、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62278-136">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a><span data-ttu-id="62278-137">Skycure iOS アプリ構成ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="62278-137">To add the Skycure iOS app configuration policy</span></span>

1.  <span data-ttu-id="62278-138">Intune クラシック ポータルで、**[ポリシー]** &gt; **[概要] &gt; [ポリシーの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="62278-138">In the Intune classic portal, choose **Policy** &gt; **Overview &gt; Add Policy**.</span></span>

2.  <span data-ttu-id="62278-139">ポリシーの一覧で、**[iOS]**を展開し、**[モバイル アプリ構成ポリシー (iOS 8.0 以降)]**、**[ポリシーの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="62278-139">In the list of policies, expand **iOS**, choose **Mobile App Configuration Policy (iOS 8.0 and later)**, then choose **Create Policy**.</span></span>

    ![iOS アプリ構成ポリシー](../media/mtp/skycure-add-apps-7.png)

3.  <span data-ttu-id="62278-141">**[ポリシーの作成]** ページの **[全般]** セクションで、iOS アプリ構成ポリシーの名前と説明を指定します。説明は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="62278-141">In the **General** section of the **Create Policy** page, supply a name and an optional description for the iOS app configuration policy.</span></span>

    <span data-ttu-id="62278-142">a.</span><span class="sxs-lookup"><span data-stu-id="62278-142">a.</span></span>  <span data-ttu-id="62278-143">メモ帳のようなテキスト エディターで **skycure\_configuration.plist** ファイルを開き、その内容をコピーして**モバイル アプリ構成ポリシー**の本文に貼り付け、**[検証]**、**[ポリシーの保存]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="62278-143">Open the **skycure\_configuration.plist** file using a text editor like notepad, copy the content and paste it into the **Mobile App Configuration Policy** body, choose **Validate**, then choose **Save Policy**.</span></span>

       ![iOS アプリ構成ポリシー 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a><span data-ttu-id="62278-145">次のステップ</span><span class="sxs-lookup"><span data-stu-id="62278-145">Next steps</span></span>

[<span data-ttu-id="62278-146">Skycure アプリ、Microsoft Authenticator アプリ、iOS アプリ構成ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="62278-146">Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy</span></span>](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
