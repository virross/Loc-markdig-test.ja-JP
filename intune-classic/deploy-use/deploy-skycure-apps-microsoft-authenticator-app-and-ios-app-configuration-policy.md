---
title: "Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーを展開する"
description: "Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーを Intune クラシック ポータルに展開します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: eddabdd8f0588d6f27b5ddcc6b959d3203a7cf44
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a><span data-ttu-id="1dcc2-103">Skycure アプリ、Microsoft Authenticator アプリ、iOS アプリ構成ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="1dcc2-103">Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a><span data-ttu-id="1dcc2-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="1dcc2-104">Before you begin</span></span>

-   <span data-ttu-id="1dcc2-105">[Intune クラシック ポータル](https://manage.microsoft.com/)で以下の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-105">The below steps need to be completed in the [Intune classic portal](https://manage.microsoft.com/).</span></span>

-   <span data-ttu-id="1dcc2-106">Skycure 管理コンソールで以前に構成したものと同じ Azure AD アカウントを使います。これは、Intune クラシック ポータルにログインするためのものと同じアカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-106">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic portal.</span></span>

-   <span data-ttu-id="1dcc2-107">次のプロセスをよく理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-107">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="1dcc2-108">[Intune でアプリを展開する](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-108">[Deploying an app with Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="1dcc2-109">[iOS アプリ構成ポリシーを展開する](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-109">[Deploying an iOS app configuration policy](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a><span data-ttu-id="1dcc2-110">Skycure アプリ、Microsoft Authenticator アプリ、iOS アプリ構成ポリシーを展開するには</span><span class="sxs-lookup"><span data-stu-id="1dcc2-110">To deploy Skycure apps, Microsoft Authenticator app and the iOS app configuration policy</span></span>

1.  <span data-ttu-id="1dcc2-111">Intune クラシック ポータルで **[アプリ]** &gt; **[アプリ]** の順に選び、管理できるアプリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-111">In the Intune classic portal, choose **Apps** &gt; **Apps** to view the list of apps that you can manage.</span></span>

2.  <span data-ttu-id="1dcc2-112">次のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-112">Select the following apps:</span></span>

    <span data-ttu-id="1dcc2-113">a.</span><span class="sxs-lookup"><span data-stu-id="1dcc2-113">a.</span></span>  <span data-ttu-id="1dcc2-114">Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="1dcc2-114">Microsoft Authenticator</span></span>

    <span data-ttu-id="1dcc2-115">b.</span><span class="sxs-lookup"><span data-stu-id="1dcc2-115">b.</span></span>  <span data-ttu-id="1dcc2-116">Android 向け Skycure アプリ</span><span class="sxs-lookup"><span data-stu-id="1dcc2-116">Skycure app for Android</span></span>

    <span data-ttu-id="1dcc2-117">c.</span><span class="sxs-lookup"><span data-stu-id="1dcc2-117">c.</span></span>  <span data-ttu-id="1dcc2-118">iOS 向け Skycure アプリ</span><span class="sxs-lookup"><span data-stu-id="1dcc2-118">Skycure app for iOS</span></span>

       ![Intune クラシック ポータルの展開するすべてのアプリ](../media/mtp/skycure-deploy-app-1.png)

3.  <span data-ttu-id="1dcc2-120">**[展開の管理]** を選択し、Skycure ユーザーが含まれる Azure AD セキュリティ グループを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-120">Choose **Manage Deployments,** select the Azure AD security group that has the Skycure users, then click **Next**.</span></span>

4.  <span data-ttu-id="1dcc2-121">**[展開アクション]** ページで、**[承認]** ドロップダウン リストから **[必須のインストール]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-121">On the **Deployment Action** page, select the option **Required Install** from the **Approval** drop-down list, then click **Next**.</span></span>

    ![Intune クラシック ポータルの展開アクション](../media/mtp/skycure-deploy-app-2.png)

5.  <span data-ttu-id="1dcc2-123">**[VPN プロファイル]** ページで、**[VPN ポリシー]** ドロップダウン リストから **[なし]** オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-123">On the **VPN profile** page, select the option **None** from the **VPN Policy** drop-down list, then click **Next**.</span></span>

6.  <span data-ttu-id="1dcc2-124">**[モバイル アプリ構成]** ページで、**[アプリ構成ポリシー]** ドロップダウン リストから、前に作成した iOS アプリ構成ポリシーを選択し、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1dcc2-124">On the **Mobile App Configuration** page, select the iOS App Configuration Policy previously created from the **App Configuration Policy** drop-down list, then click **Finish**.</span></span>

    ![Intune クラシック ポータルのモバイル アプリ構成](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a><span data-ttu-id="1dcc2-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1dcc2-126">Next steps</span></span>

[<span data-ttu-id="1dcc2-127">Skycure と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1dcc2-127">Set up the Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
