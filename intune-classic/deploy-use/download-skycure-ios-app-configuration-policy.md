---
title: "Skycure iOS アプリ構成ポリシーをダウンロードする"
description: "エンドユーザーに展開した Skycure iOS アプリで使用する Skycure iOS アプリ構成ポリシーをダウンロードします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f6224d35dfa85cba89083d6a12f5490b994e558b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a><span data-ttu-id="d195f-103">Skycure iOS アプリ構成ポリシーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d195f-103">Download Skycure iOS app configuration policy</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a><span data-ttu-id="d195f-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="d195f-104">Before you begin</span></span>

<span data-ttu-id="d195f-105">次の手順を実行するには、Skycure 管理コンソールにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d195f-105">You need to log in to the Skycure Management Console to perform the next steps.</span></span>

> [!TIP] 
> <span data-ttu-id="d195f-106">Microsoft Internet Explorer 11 または Edge を利用しているときは、場合によっては、プライベート モードを利用して Skycure 管理コンソールを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d195f-106">If using Microsoft Internet explorer 11 or Edge, you might need to open the Skycure Management console using In-Private mode.</span></span>

## <a name="to-download-the-ios-app-configuration-policy"></a><span data-ttu-id="d195f-107">iOS アプリ構成ポリシーをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="d195f-107">To download the iOS app configuration policy</span></span>

1.  <span data-ttu-id="d195f-108">[Skycure 管理コンソール](https://aad.skycure.com)に進みます。</span><span class="sxs-lookup"><span data-stu-id="d195f-108">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="d195f-109">自分の **Skycure 管理者資格情報**を入力し、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d195f-109">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

    ![Skycure 管理コンソールのログイン](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="d195f-111">Skycure 管理者のユーザー名は電子メール アカウントですが、そのアカウントは Azure Active Directory の有効なアカウントでなければなりません。有効なユーザーではない場合、ログインは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d195f-111">The Skycure admin username is an e-mail account that must be a valid user account in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="d195f-112">Skycure は、シングル サインオン (SSO) を使用して、管理者ユーザー名の認証に Azure Active Directory を使用します。</span><span class="sxs-lookup"><span data-stu-id="d195f-112">Skycure uses Azure Active Directory to authenticate its admin username using Single Sign On (SSO).</span></span>

3.  <span data-ttu-id="d195f-113">**[設定]** &gt; **[Device Management Integrations (デバイス管理統合)]** &gt; **[EMM Integration Selection (EMM 統合選択)]** の順に進み、**[Microsoft Intune]** を選択し、選択を保存します。</span><span class="sxs-lookup"><span data-stu-id="d195f-113">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>

2.  <span data-ttu-id="d195f-114">**[Integration setup files (統合セットアップ ファイル)]** リンクをクリックし、生成された \*.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="d195f-114">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="d195f-115">この .zip ファイルには **skycure\_configuration.plist** ファイルが含まれます。このファイルを利用して、Intune クラシック ポータルで iOS アプリ構成ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d195f-115">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in the Intune classic portal.</span></span>

![Skycure 統合セットアップ ファイル](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a><span data-ttu-id="d195f-117">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d195f-117">Next steps</span></span>

[<span data-ttu-id="d195f-118">Skycure アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーの追加</span><span class="sxs-lookup"><span data-stu-id="d195f-118">Add Skycure apps, Microsoft Authenticator app and the iOS configuration policy</span></span>](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
