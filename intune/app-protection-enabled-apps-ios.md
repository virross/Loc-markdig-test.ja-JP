---
title: "アプリ保護ポリシーのある iOS アプリ"
titlesuffix: Azure portal
description: "このトピックでは、アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点について説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 12e72482e83796c5e3771a2f9b39aec671eb36b5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="af72f-103">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="af72f-103">What to expect when your iOS app is managed by app protection policies</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="af72f-104">このトピックでは、アプリ保護ポリシーを使用する場合のアプリのユーザー エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="af72f-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="af72f-105">アプリ保護ポリシーが適用されるのは、作業アカウントを使用してアプリにアクセスしたり、会社の OneDrive 事業拠点に格納されたファイルにアクセスしたりするなどのワーク コンテキストでアプリが使用される場合に限定されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <a name="accessing-apps"></a><span data-ttu-id="af72f-106">アプリへのアクセス</span><span class="sxs-lookup"><span data-stu-id="af72f-106">Accessing apps</span></span>

<span data-ttu-id="af72f-107">デバイスが**Intune に登録されていない**場合、エンドユーザーはアプリを初めて使用すると、アプリの再起動を求められます。</span><span class="sxs-lookup"><span data-stu-id="af72f-107">If the device is **not enrolled in Intune**, the end-user will be asked to restart the app when they first use the app.</span></span>  <span data-ttu-id="af72f-108">再起動すると、アプリ保護ポリシーをアプリに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="af72f-108">A restart is required so app protection polices can be applied to the app.</span></span> <span data-ttu-id="af72f-109">次のスクリーンショットは、Skype アプリを使用した場合の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="af72f-109">The following screenshot illustrates this using the Skype app:</span></span>


![暗証番号 (PIN) を求めるプロンプトを表示している iOS のスクリーン ショット](./media/ios-pin-prompt.png)

<span data-ttu-id="af72f-111">**Intune の管理対象として登録された**デバイスの場合、エンドユーザーにはアプリが管理された状態にあることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-111">For devices that are **enrolled for management in Intune**, the end-user will see a message that their app is now managed:</span></span>

![会社によって管理された状態にあることを示すメッセージと、暗証番号 (PIN) を求めるプロンプトが表示されている iOS デバイスのスクリーンショット](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a><span data-ttu-id="af72f-113">複数の ID を使用するアプリのサポート</span><span class="sxs-lookup"><span data-stu-id="af72f-113">Using apps with multi-identity support</span></span>

<span data-ttu-id="af72f-114">アプリ保護ポリシーはアプリがワーク コンテキストで使用されている場合にのみ適用されます。そのため、ワーク コンテキストとパーソナル コンテキストでは、アプリの動作に違いが見られることがあります。</span><span class="sxs-lookup"><span data-stu-id="af72f-114">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>  

<span data-ttu-id="af72f-115">複数の ID をサポートするアプリに対しては、Intune は、エンドユーザーがアプリをワーク コンテキストで使用している場合にのみアプリ保護ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="af72f-115">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="af72f-116">たとえば、エンドユーザーが職場のデータにアクセスすると、暗証番号 (PIN) を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-116">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="af72f-117"><strong>Outlook アプリ</strong> の場合、エンドユーザーにはアプリの起動時に、暗証番号 (PIN) の入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-117">For the <strong>Outlook app</strong>, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="af72f-118"><strong>OneDrive アプリ</strong> の場合は、エンドユーザーが作業アカウントを入力すると、同様のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-118">For the <strong>OneDrive app</strong>, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="af72f-119">Microsoft の<strong>Word</strong>、 <strong>PowerPoint \* と \* \* Excel</strong>エンドユーザーが会社 OneDrive for Business の場所に格納されたドキュメントにアクセスするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="af72f-119">For Microsoft <strong>Word</strong>, <strong>PowerPoint\*, and \*\*Excel</strong>, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <a name="managing-user-accounts-on-the-device"></a><span data-ttu-id="af72f-120">デバイスのユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="af72f-120">Managing user accounts on the device</span></span>

<span data-ttu-id="af72f-121">Intune では、アプリ保護ポリシーをデバイスごとに 1 つのユーザー アカウントのみに展開することがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="af72f-121">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="af72f-122">2 つ目のユーザーがデバイスでブロックされるかどうかは、使用中のアプリによって決まります。</span><span class="sxs-lookup"><span data-stu-id="af72f-122">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="af72f-123">ただし、どの場合でも、ポリシーの影響を受けるのは、アプリ保護ポリシーが適用される最初のユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="af72f-123">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="af72f-124">**Microsoft Word**、**Excel**、**PowerPoint** では、2 つ目のユーザー アカウントがブロックされることはありませんが、2 つ目のユーザー アカウントがアプリ保護ポリシーの影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="af72f-124">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="af72f-125">**OneDrive アプリと Outlook アプリ**では、作業アカウントは 1 つだけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af72f-125">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="af72f-126">作業アカウントを複数追加しようとしても、これらのアプリでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="af72f-126">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="af72f-127">ただし、デバイス上のユーザーを削除して、別のユーザーを追加することはできます。</span><span class="sxs-lookup"><span data-stu-id="af72f-127">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="af72f-128">アプリ保護ポリシーを展開する前にデバイスに複数の既存のユーザー アカウントがある場合は、アプリ保護ポリシーが展開される最初のアカウントが Intune アプリ保護ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="af72f-128">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="af72f-129">次のサンプル シナリオを読んで、複数のユーザー アカウントがどのように処理されるかを深く理解してください。</span><span class="sxs-lookup"><span data-stu-id="af72f-129">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="af72f-130">ユーザー A は、**会社 X** と会社 **会社 Y** という 2 つの会社で働いています。ユーザー A は各会社の作業アカウントを持っており、どちらの会社も Intune を使用してアプリ保護ポリシーを展開しています。</span><span class="sxs-lookup"><span data-stu-id="af72f-130">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="af72f-131">**会社 X** は、**会社 Y** の**前に**アプリ保護ポリシーを展開しています。アプリ保護ポリシーは、**会社 X** に関連付けられたアカウントに適用され、会社 Y に関連付けられたアカウントには適用されません。会社 Y に関連付けられたユーザー アカウントをアプリ保護ポリシーで管理する場合は、会社 X に関連付けられたユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af72f-131">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <a name="adding-a-second-account"></a><span data-ttu-id="af72f-132">2 つ目のアカウントの追加</span><span class="sxs-lookup"><span data-stu-id="af72f-132">Adding a second account</span></span>

<span data-ttu-id="af72f-133">iOS デバイスを使用している場合は、同じデバイスに 2 つ目の作業アカウントを追加しようとすると、ブロック メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="af72f-133">If you are using an iOS device, when you try to add a second work account on the same device, you may see a blocking message.</span></span>  <span data-ttu-id="af72f-134">アカウントが表示され、削除するアカウントを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="af72f-134">The accounts will be displayed and you can choose the account you want to remove.</span></span>

![ブロック メッセージと、[はい] と [いいえ] オプショを表示しているダイアログ ボックスのスクリーンショット](./media/ios-switch-user.PNG)

## <a name="next-steps"></a><span data-ttu-id="af72f-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="af72f-136">Next steps</span></span>
[<span data-ttu-id="af72f-137">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="af72f-137">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
### <a name="see-also"></a><span data-ttu-id="af72f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="af72f-138">See also</span></span>
[<span data-ttu-id="af72f-139">Microsoft Intune でのアプリ保護ポリシーの作成と展開</span><span class="sxs-lookup"><span data-stu-id="af72f-139">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
