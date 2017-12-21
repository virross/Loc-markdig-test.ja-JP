---
title: "Intune 移行中にアプリ保護ポリシーを構成する"
description: "この記事では、Intune 移行中にアプリ保護ポリシーを設定するために必要な手順について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: c58ce51731b476cfca71851430297aff3edc5cd6
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-app-protection-policies-optional"></a><span data-ttu-id="69c39-103">アプリ保護ポリシーを構成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="69c39-103">Configure app protection policies (optional)</span></span>


<span data-ttu-id="69c39-104">アプリ保護ポリシーでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="69c39-104">App protection policies allow you to:</span></span>
* <span data-ttu-id="69c39-105">アプリの暗号化</span><span class="sxs-lookup"><span data-stu-id="69c39-105">Encrypt apps</span></span>
* <span data-ttu-id="69c39-106">アプリにアクセスするときの PIN の定義</span><span class="sxs-lookup"><span data-stu-id="69c39-106">Define a PIN when the app is accessed</span></span>
* <span data-ttu-id="69c39-107">脱獄またはルート化されたデバイスでのアプリの実行のブロック、および他の多くの保護</span><span class="sxs-lookup"><span data-stu-id="69c39-107">Block apps from running on jail-broken or rooted devices, and many other protections.</span></span>

<span data-ttu-id="69c39-108">携帯電話を紛失したり盗難に遭ったりした場合は、個人データは保持したまま会社のデータに対して選択的にリモート ワイプを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="69c39-108">If the user's phone is lost or stolen, you can selectively wipe the corporate data remotely while leaving the personal data intact.</span></span>

<span data-ttu-id="69c39-109">アプリ保護ポリシーではアプリ レベルでセキュリティを適用し、デバイスの登録を必要としません。</span><span class="sxs-lookup"><span data-stu-id="69c39-109">App protection policies apply security at the app level and do not require device enrollment.</span></span> <span data-ttu-id="69c39-110">Intune 登録の有無に関係なく、アプリ保護ポリシーをデバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="69c39-110">You can use them with devices enrolled into Intune or not.</span></span> <span data-ttu-id="69c39-111">また、サードパーティの MDM プロバイダーに登録されたデバイスにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="69c39-111">Additionally, you can apply them to devices enrolled into a third-party MDM provider.</span></span>

## <a name="app-protection-policies-with-lob-apps"></a><span data-ttu-id="69c39-112">LOB アプリでのアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="69c39-112">App protection policies with LOB apps</span></span>

<span data-ttu-id="69c39-113">[IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) および [Android](https://www.microsoft.com/download/details.aspx?id=47267) プラットフォーム用の [Microsoft Intune App SDK](app-sdk-get-started.md) や Microsoft Intune アプリ ラッピング ツールを利用して、基幹業務 (LOB) アプリに対してモバイル アプリ保護ポリシーを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="69c39-113">You can also extend the mobile app protection policies to your line-of-business (LOB) apps by using the [Microsoft Intune App SDK](app-sdk-get-started.md) or the Microsoft Intune App Wrapping Tool for both [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) and [Android](https://www.microsoft.com/download/details.aspx?id=47267) platforms.</span></span>

## <a name="how-do-app-protection-policies-help-during-migration"></a><span data-ttu-id="69c39-114">アプリ保護ポリシーは移行中にどのように役立つか</span><span class="sxs-lookup"><span data-stu-id="69c39-114">How do app protection policies help during migration?</span></span>

<span data-ttu-id="69c39-115">移行では、デバイスを以前の MDM プロバイダーから削除して、Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c39-115">In a migration, you must remove devices from the old MDM provider and enroll them into Intune.</span></span> <span data-ttu-id="69c39-116">この計画を立てて、エンド ユーザーに以前の MDM プロバイダーの利用をやめて、速やかに Intune に登録するよう働きかけます。</span><span class="sxs-lookup"><span data-stu-id="69c39-116">You should plan for this and encourage your end-users to leave the old MDM provider and immediately enroll into Intune.</span></span> <span data-ttu-id="69c39-117">移行中は一部のユーザーの登録プロセスの完了が遅れて、デバイスがどちらの MDM プロバイダーでも管理されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="69c39-117">However, during the migration there may be users who delay completing the enrollment process and whose devices are not managed by either MDM provider.</span></span>

<span data-ttu-id="69c39-118">この期間に会社のリソースへのアクセスを引き続き許可すると、デバイスの盗難や会社のデータの損失に対する脆弱性が高まります。</span><span class="sxs-lookup"><span data-stu-id="69c39-118">This period can leave your organization more vulnerable to device theft and corporate data loss if corporate resource access is still allowed.</span></span> <span data-ttu-id="69c39-119">また、会社のリソースへのアクセスをブロックすると、ユーザーの生産性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69c39-119">It may also lead to lower user productivity if corporate resource access is blocked.</span></span>

<span data-ttu-id="69c39-120">Intune では移行中の企業データの保護が提供されるため、デバイス レベルの管理が行われない期間も、引き続き会社のデータをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="69c39-120">Intune can offer corporate data protections during the migration so you can still have security coverage for your corporate data when there’s no device-level management.</span></span>

<span data-ttu-id="69c39-121">以前の MDM プロバイダーで条件付きアクセスを無効にしても、Intune に登録すればユーザーの生産性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="69c39-121">As you disable conditional access in the old MDM provider, users can still be productive while you on-board them into Intune.</span></span>

## <a name="task-list-for-app-protection-policies"></a><span data-ttu-id="69c39-122">アプリ保護ポリシーのタスク一覧</span><span class="sxs-lookup"><span data-stu-id="69c39-122">Task list for app protection policies</span></span>

1. [<span data-ttu-id="69c39-123">アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="69c39-123">Create an app protection policy</span></span>](app-protection-policies.md#create-an-app-protection-policy)
2. [<span data-ttu-id="69c39-124">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="69c39-124">Deploy a policy</span></span>](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a><span data-ttu-id="69c39-125">次のステップ</span><span class="sxs-lookup"><span data-stu-id="69c39-125">Next steps</span></span>

[<span data-ttu-id="69c39-126">特殊な移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="69c39-126">Special migration considerations</span></span>](migration-guide-considerations.md)
