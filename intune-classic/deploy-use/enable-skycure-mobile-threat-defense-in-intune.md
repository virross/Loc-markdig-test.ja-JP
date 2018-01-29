---
title: "Intune で Skycure Mobile Threat Defense を有効にする"
description: "Intune クラシック ポータルで Skycure Mobile Threat Defense を有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 73a2a8748f219bfc68b7e112c2003b9c31060c71
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a><span data-ttu-id="f90dc-103">Intune で Skycure Mobile Threat Defense を有効にする</span><span class="sxs-lookup"><span data-stu-id="f90dc-103">Enable Skycure Mobile Threat Defense in Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f90dc-104">Skycure モバイルの脅威に対する防御を有効にする必要がありますを構成しておく、 [Skycure コンソールで Intune コネクタ](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)です。</span><span class="sxs-lookup"><span data-stu-id="f90dc-104">To enable the Skycure mobile threat defense, you should have already configured the [Intune Connector in the Skycure console](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).</span></span>

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a><span data-ttu-id="f90dc-105">Intune で Skycure MTD の接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="f90dc-105">To enable the Skycure MTD connection in Intune</span></span>

1.  <span data-ttu-id="f90dc-106">[Intune クラシック ポータル](https://manage.microsoft.com/)に進み、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f90dc-106">Go to the [Intune classic portal](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="f90dc-107">**[管理]** &gt; **[Third Party Service Integration (サード パーティ サービスの統合)]** の順に選択し、**[Skycure の状態]** を選択し、切り替えボタンで **[Synchronization with MTD (MTD と同期)]** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f90dc-107">Choose **Admin** &gt; **Third Party Service Integration**, then choose **Skycure Status** and enable **Synchronization with MTD** using the toggle button.</span></span>

    ![Intune クラシック ポータルで Skycure 切り替えを有効にする](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> <span data-ttu-id="f90dc-109">コンプライアンス ポリシー ルールを作成して条件付きアクセスを構成する前に、Skycure アプリを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f90dc-109">You must configure the Skycure apps before creating compliance policy rules and configuring conditional access.</span></span> <span data-ttu-id="f90dc-110">これにより、アプリはエンド ユーザーがインストールできる状態になり、アプリをインストールするとエンド ユーザーは電子メールや他の会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f90dc-110">This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

<span data-ttu-id="f90dc-111">以上で、Intune 管理者コンソールでの Skycure と Intune の統合のセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="f90dc-111">This completes the setup of the Skycure and Intune integration in the Intune administrator console.</span></span> <span data-ttu-id="f90dc-112">このソリューションを実装するこの後の手順では、Skycure for Work アプリを展開し、コンプライアンス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f90dc-112">The next few steps to implement this solution involve deploying the Skycure for Work apps and setting up the compliance policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f90dc-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="f90dc-113">Next steps</span></span>

[<span data-ttu-id="f90dc-114">Skycure Mobile Threat Defense コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f90dc-114">Create Skycure Mobile Threat Defense compliance policy</span></span>](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
