---
title: "アプリ保護ポリシーのある iOS アプリ"
description: "このトピックでは、アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5a7e736f01d43e4ef61f39da37086e5b58a9042c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="97696-103">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="97696-103">What to expect when your iOS app is managed by app protection policies</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 <span data-ttu-id="97696-104">このトピックでは、アプリ保護ポリシーが適用されているアプリを使用するときのユーザー エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="97696-104">This topic describes the user experience when using apps with app protection policies applied to.</span></span> <span data-ttu-id="97696-105">アプリ保護ポリシーが適用されるのは、仕事でアプリが使用される場合に限られます。たとえば、職場のアカウントを使用してアプリにアクセスしたり、会社の OneDrive 事業拠点に格納されたファイルにアクセスしたりする場合です。</span><span class="sxs-lookup"><span data-stu-id="97696-105">App protection policies are applied only when apps are used in the work context; for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive for business location.</span></span>

##  <a name="access-apps"></a><span data-ttu-id="97696-106">アプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="97696-106">Access apps</span></span>

<span data-ttu-id="97696-107">デバイスが**Intune に登録されていない**場合、ユーザーはアプリを初めて使用すると、アプリの再起動を求められます。</span><span class="sxs-lookup"><span data-stu-id="97696-107">If the device is **not enrolled in Intune**, the user is asked to restart the app when they first use it.</span></span> <span data-ttu-id="97696-108">再起動すると、アプリ保護ポリシーをアプリに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="97696-108">A restart is required so that app protection polices can be applied to the app.</span></span>

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

<span data-ttu-id="97696-109">**Intune の管理対象として登録された**デバイスの場合、ユーザーにはアプリが管理された状態にあることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97696-109">For devices that are **enrolled for management in Intune**, the user sees a message that their app is now managed.</span></span>

##  <a name="use-apps-with-multi-identity-support"></a><span data-ttu-id="97696-110">複数の ID に対応しているアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="97696-110">Use apps with multi-identity support</span></span>

<span data-ttu-id="97696-111">複数の ID をサポートするアプリの場合、アプリが作業コンテキストで利用されているときにアプリ保護ポリシーが適用されていれば、仕事用や個人用など、複数のアカウントを利用して同じアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97696-111">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="97696-112">たとえば、ユーザーが職場のデータにアクセスすると、暗証番号 (PIN) を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97696-112">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="97696-113">**Outlook アプリ**の場合、ユーザーにはアプリの起動時に、暗証番号 (PIN) の入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97696-113">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="97696-114">**OneDrive アプリ**の場合、ユーザーが職場のアカウントを入力するとき、PIN の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="97696-114">For the **OneDrive app**, the user is prompted for a pin when they type in the work account.</span></span>  <span data-ttu-id="97696-115">Microsoft **Word**、**PowerPoint**、**Excel** の場合、会社の OneDrive for Business 拠点に保存されているドキュメントにユーザーがアクセスするとき、PIN の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="97696-115">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for a pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

- <span data-ttu-id="97696-116">Intune で [アプリ保護と複数の ID](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) をサポートするアプリについての詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97696-116">Learn more about the apps that support [app protection and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

<span data-ttu-id="97696-117">アプリ保護ポリシーは仕事関連でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="97696-117">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="97696-118">そのため、仕事で使用する場合と個人的に使用する場合でアプリの動作が異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="97696-118">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

##  <a name="manage-user-accounts-on-the-device"></a><span data-ttu-id="97696-119">デバイスのユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="97696-119">Manage user accounts on the device</span></span>

<span data-ttu-id="97696-120">Intune では、アプリ保護ポリシーの展開は、デバイスごとに 1 ユーザー アカウントに限られます。</span><span class="sxs-lookup"><span data-stu-id="97696-120">Intune supports the deployment of app protection policies to  one user account per device only.</span></span>

* <span data-ttu-id="97696-121">2 つ目のユーザーがデバイスでブロックされるかどうかは、使用中のアプリによって決まります。</span><span class="sxs-lookup"><span data-stu-id="97696-121">Depending on the app that you are using, the second user might be blocked on the device.</span></span> <span data-ttu-id="97696-122">ただし、どの場合でも、ポリシーの影響を受けるのは、アプリ保護ポリシーが適用される最初のユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="97696-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="97696-123">**Microsoft Word**、**Excel**、**PowerPoint** では、2 つ目のユーザー アカウントがブロックされることはありませんが、2 つ目のユーザー アカウントがアプリ保護ポリシーの影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="97696-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="97696-124">**OneDrive アプリ**と **Outlook アプリ**では、職場のアカウントは 1 つだけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="97696-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span> <span data-ttu-id="97696-125">これらのアプリに複数の職場のアカウントを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="97696-125">You can't add multiple work accounts for these apps.</span></span> <span data-ttu-id="97696-126">ただし、デバイス上のユーザーを削除して、別のユーザーを追加することはできます。</span><span class="sxs-lookup"><span data-stu-id="97696-126">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="97696-127">アプリ保護ポリシーを展開する前にデバイスに複数の既存のユーザー アカウントがある場合は、アプリ保護ポリシーが展開される最初のアカウントが Intune アプリ保護ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="97696-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="97696-128">次のサンプル シナリオを読んで、複数のユーザー アカウントがどのように処理されるかを深く理解してください。</span><span class="sxs-lookup"><span data-stu-id="97696-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="97696-129">ユーザー A は、**会社 X** と会社 **会社 Y** という 2 つの会社で働いています。ユーザー A は各会社の作業アカウントを持っており、どちらの会社も Intune を使用してアプリ保護ポリシーを展開しています。</span><span class="sxs-lookup"><span data-stu-id="97696-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="97696-130">**会社 X** は、**会社 Y** の**前に**アプリ保護ポリシーを展開しています。アプリ保護ポリシーは、**会社 X** に関連付けられたアプリ保護ポリシーに適用され、会社 Y に関連付けられたアカウントには適用されません。会社 Y に関連付けられたユーザー アカウントをアプリ保護ポリシーで管理する場合は、会社 X に関連付けられたユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97696-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>

### <a name="add-a-second-account"></a><span data-ttu-id="97696-131">2 つ目のアカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="97696-131">Add a second account</span></span>

<span data-ttu-id="97696-132">iOS デバイスを使用している場合は、そのデバイスに 2 つ目の作業アカウントを追加しようとすると、ブロック メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97696-132">If you are using an iOS device, when you try to add a second work account on that device, you might see a blocking message.</span></span> <span data-ttu-id="97696-133">アカウントが表示され、削除するアカウントを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="97696-133">The accounts will be displayed, and then you can choose the account you want to remove.</span></span>

## <a name="next-steps"></a><span data-ttu-id="97696-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="97696-134">Next steps</span></span>
[<span data-ttu-id="97696-135">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="97696-135">What to expect when your Android app is managed by app protection policies</span></span>](end-user-mam-apps-android.md)
