---
title: "通信手段の計画"
description: "この記事では、移行における情報伝達計画と戦略について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6a52506-2d29-41f7-a171-5d684a740dd4
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: f049abd260d014faa397d2f68e43d5f9d5465588
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="plan-communications"></a><span data-ttu-id="3b684-103">通信手段の計画</span><span class="sxs-lookup"><span data-stu-id="3b684-103">Plan communications</span></span>

<span data-ttu-id="3b684-104">情報伝達計画は、Intune 移行における重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="3b684-104">The communication plan is a key element in an Intune migration.</span></span> <span data-ttu-id="3b684-105">移行の各フェーズで、同じ情報伝達計画に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b684-105">You can follow the same communication plan for each phase of your migration.</span></span>

## <a name="email-templates"></a><span data-ttu-id="3b684-106">電子メール テンプレート</span><span class="sxs-lookup"><span data-stu-id="3b684-106">Email templates</span></span>

<span data-ttu-id="3b684-107">次のメール通信の計画をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b684-107">We recommend the following email communication plan.</span></span> <span data-ttu-id="3b684-108">情報伝達計画に適用できるテンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="3b684-108">We've provided templates for you to adapt for your communication plan:</span></span>

-   <span data-ttu-id="3b684-109">**電子メール \#1:** 利点、見込み、スケジュールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3b684-109">**Email \#1:** Explain the benefits, expectations, and schedule.</span></span> <span data-ttu-id="3b684-110">この機会を利用して、Intune によって管理されるデバイスでアクセスが許可される他の新しいサービスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="3b684-110">Take this opportunity to showcase any other new services whose access will be granted on devices managed by Intune.</span></span><br/><br/>


    -   [<span data-ttu-id="3b684-111">電子メールのダウンロード\#1 のテンプレート</span><span class="sxs-lookup"><span data-stu-id="3b684-111">Download email \#1 template</span></span>](https://gallery.technet.microsoft.com/Intune-migration-guide-end-e3209b35)
<br></br>

-   <span data-ttu-id="3b684-112">**電子メール \#2:** Intune からサービスにアクセスする準備が整ったことを発表します。</span><span class="sxs-lookup"><span data-stu-id="3b684-112">**Email \#2:** Announce that services are now ready for access through Intune.</span></span> <span data-ttu-id="3b684-113">ユーザーに早速登録するよう伝えます。</span><span class="sxs-lookup"><span data-stu-id="3b684-113">Tell users to enroll now.</span></span> <span data-ttu-id="3b684-114">移行の利点と戦略的な理由を再認識してもらいます。</span><span class="sxs-lookup"><span data-stu-id="3b684-114">Remind users of benefits and strategic reasons for migration.</span></span><br/><br/>


    -   [<span data-ttu-id="3b684-115">電子メールのダウンロード\#2 のテンプレート</span><span class="sxs-lookup"><span data-stu-id="3b684-115">Download email \#2 template</span></span>](https://gallery.technet.microsoft.com/Intune-migration-guide-end-a9d25eb5)
<br></br>

-   <span data-ttu-id="3b684-116">**電子メール \#3:** アクセスが影響を受ける前にタイムラインをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="3b684-116">**Email \#3:** Give users a timeline before their access is affected.</span></span> <span data-ttu-id="3b684-117">移行の利点と戦略的な理由を再認識してもらいます。</span><span class="sxs-lookup"><span data-stu-id="3b684-117">Again, remind users of benefits and strategic reasons for migration.</span></span> <span data-ttu-id="3b684-118">電子メールのタイミングには、フェーズに合わせたスライディング ウィンドウが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b684-118">Email timing should have a sliding window to match your phases.</span></span> <span data-ttu-id="3b684-119">たとえば、6 月に電子メール \#1 をフェーズ 1 のユーザーに送信し、電子メール \#2 をフェーズ 2 のユーザー、電子メール \#3 をフェーズ 3 のユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="3b684-119">For example, in June send email \#1 to phase 1 users, email \#2 to phase 2 users, and email \#3 to phase 3 users.</span></span><br/><br/>

    -   [<span data-ttu-id="3b684-120">電子メール \#3 テンプレートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="3b684-120">Download email \#3 template</span></span>](https://gallery.technet.microsoft.com/Intune-migration-guide-end-831521b5)

<span data-ttu-id="3b684-121">一定期間後に、条件付きアクセス ポリシーによるコンプライアンスの強制的な適用を開始し、企業データにアクセスする基準として使用します (「[条件付きアクセスを利用してエンド ユーザーの導入を推進する](migration-guide-drive-adoption.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3b684-121">After a certain period, you can begin enforcing compliance through conditional access policies and use it as criteria to access corporate data, as explained in [Drive end-user adoption with conditional access](migration-guide-drive-adoption.md).</span></span>

## <a name="additional-communication-templates"></a><span data-ttu-id="3b684-122">その他の情報伝達テンプレート</span><span class="sxs-lookup"><span data-stu-id="3b684-122">Additional communication templates</span></span>

<span data-ttu-id="3b684-123">Intune では、ユーザーのデバイス登録を推進するその他のテンプレートを用意しています。</span><span class="sxs-lookup"><span data-stu-id="3b684-123">Intune has additional templates you can use to promote device enrollment with your users:</span></span>

-   <span data-ttu-id="3b684-124">モバイル OS プラットフォームごとの登録手順について詳しくは、「[Microsoft Intune に関してエンド ユーザーを教育する方法](end-user-educate.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3b684-124">[How to educate your end users about Microsoft Intune](end-user-educate.md) breaks out enrollment steps by mobile OS platform.</span></span>

-   <span data-ttu-id="3b684-125">[IT 管理者向けの Intune エンド ユーザー登録テンプレート](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a)は、Intune で Android、iOS、および Mac デバイスを登録する方法を説明するカスタマイズ可能な Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="3b684-125">The [Intune end-user enrollment template for IT administrators](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) is customizable Word doc that explains how to enroll Android, iOS, and Mac devices in Intune.</span></span>

-   <span data-ttu-id="3b684-126">「[FastTrack for EMS how to guides & emails (EMS 用 FastTrack: 方法ガイドとメール)](https://gallery.technet.microsoft.com/FastTrack-for-EMS-How-To-f170da4c)」は、貴社のロゴでカスタマイズして、組織内での Intune と EMS の採用を促進できます。</span><span class="sxs-lookup"><span data-stu-id="3b684-126">The [FastTrack for EMS how to guides & emails](https://gallery.technet.microsoft.com/FastTrack-for-EMS-How-To-f170da4c) can be customized with your company’s logo to promote adoption of Intune and EMS within your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b684-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b684-127">Next steps</span></span>

<span data-ttu-id="3b684-128">[条件付きアクセスでエンド ユーザーの導入を推進します](migration-guide-drive-adoption.md)。</span><span class="sxs-lookup"><span data-stu-id="3b684-128">[Drive end-user adoption with conditional access](migration-guide-drive-adoption.md).</span></span>
