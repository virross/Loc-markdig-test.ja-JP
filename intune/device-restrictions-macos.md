---
title: "macOS の Intune デバイス制限設定"
titlesuffix: Azure portal
description: "macOS デバイスでデバイスの設定と機能を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d37b839bdd434c1a90d54e83f391e236205eb7d2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="27ebb-103">Microsoft Intune での macOS デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="27ebb-103">macOS device restriction settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="27ebb-104">この設定を使用して、デバイスの制限プロファイルの macOS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-104">Use these settings to manage macOS devices in a device restriction profile.</span></span>

## <a name="password"></a><span data-ttu-id="27ebb-105">パスワード</span><span class="sxs-lookup"><span data-stu-id="27ebb-105">Password</span></span>
-   <span data-ttu-id="27ebb-106">**[パスワード]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-106">**Password** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="27ebb-107">**[必要なパスワードの種類]** - パスワードを数字のみとすることができるかどうか、または英数字 (文字と数字を含む) にする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-107">**Required password type** - Specify whether the password can be Numeric only, or whether it must be Alphanumeric (contain letters and numbers).</span></span> <span data-ttu-id="27ebb-108">この設定は、Mac OS X バージョン 10.10.3 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="27ebb-108">This setting is supported only on Mac OS X version 10.10.3 and later.</span></span>
    -   <span data-ttu-id="27ebb-109">**[パスワードに使用する英数字以外の文字数]** - パスワードに必要な複雑な文字の数を指定します (**0** ～ **4** 文字)。</span><span class="sxs-lookup"><span data-stu-id="27ebb-109">**Number of non-alphanumeric characters in password** - Specify the number of complex characters required in the password (**0** to **4**).</span></span><br><span data-ttu-id="27ebb-110">複雑な文字とは、**?** のような記号です。</span><span class="sxs-lookup"><span data-stu-id="27ebb-110">A complex character is a symbol, like **?**</span></span>
    -   <span data-ttu-id="27ebb-111">**[パスワードの最小文字数]** - ユーザーが構成する必要があるパスワードの最小文字数 (**4** ～ **16** 文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-111">**Minimum password length** - Enter the minimum length of password a user must configure (between **4** and **16** characters).</span></span>
    -   <span data-ttu-id="27ebb-112">**[単純なパスワード]** - 単純なパスワードの使用を許可します (**0000**、**1234** など)。</span><span class="sxs-lookup"><span data-stu-id="27ebb-112">**Simple passwords** - Allow the use of simple passwords such as **0000** or **1234**.</span></span>
    -   <span data-ttu-id="27ebb-113">**[画面ロック後にパスワードが要求されるまでの最長時間 (分)]** - コンピューターの非アクティブ状態が許容される時間を指定します。この時間を超えると、ロックを解除するためにパスワードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="27ebb-113">**Maximum minutes after screen lock before password is required** - Specify how long the computer must be inactive before a password is required to unlock it.</span></span>
    -   <span data-ttu-id="27ebb-114">**[画面がロックされるまでの非アクティブな最長時間 (分)]** - コンピューターのアイドル状態が許容される時間を指定します。この時間を超えると、画面はロックされます。</span><span class="sxs-lookup"><span data-stu-id="27ebb-114">**Maximum minutes of inactivity until screen locks** - Specify the length of time that the computer must be idle before the screen locks.</span></span>
    -   <span data-ttu-id="27ebb-115">**[パスワードの有効期限 (日数)]** - どれだけの日数が経過すると、ユーザーがパスワードを変更する必要があるかを指定します **(1** から **255** 日)。</span><span class="sxs-lookup"><span data-stu-id="27ebb-115">**Password expiration (days)** - Specify how many days elapse before the user must change the password (**1** to **255** days).</span></span>
    -   <span data-ttu-id="27ebb-116">**[Prevent reuse of previous passwords (前のパスワードを再利用できないようにする)]** - 何回前までのパスワードを使用できないようにするかを指定します (**1** ～ **24**)。</span><span class="sxs-lookup"><span data-stu-id="27ebb-116">**Prevent reuse of previous passwords** - Specify the number of previously used passwords that cannot be reused (**1** to **24**).</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="27ebb-117">制限付きアプリ</span><span class="sxs-lookup"><span data-stu-id="27ebb-117">Restricted apps</span></span>

<span data-ttu-id="27ebb-118">制限付きアプリの一覧では、次の一覧のいずれかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="27ebb-118">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="27ebb-119">**[禁止されているアプリ]** の一覧 - ユーザーによるインストールと実行が許可されていないアプリ (Intune で管理されていない) アプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-119">A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="27ebb-120">**[承認済みアプリ]** の一覧 - ユーザーによるインストールが許可されているアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-120">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="27ebb-121">準拠性を維持するため、ユーザーは一覧表示されていないアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="27ebb-121">To remain compliant, users must not install apps that are not listed.</span></span> <span data-ttu-id="27ebb-122">管理対象アプリは Intune で自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="27ebb-122">Apps that are managed by Intune are automatically allowed.</span></span>

<span data-ttu-id="27ebb-123">一覧を構成するには、**[追加]** をクリックし、任意の名前、アプリの発行元 (省略可能)、アプリのバンドル ID (例: *com.apple.calculator*) を指定します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-123">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the bundle ID of the app (for example *com.apple.calculator*).</span></span>

## <a name="domains"></a><span data-ttu-id="27ebb-124">Domains</span><span class="sxs-lookup"><span data-stu-id="27ebb-124">Domains</span></span>

### <a name="unmarked-email-domains"></a><span data-ttu-id="27ebb-125">マークされていないメール ドメイン</span><span class="sxs-lookup"><span data-stu-id="27ebb-125">Unmarked email domains</span></span>

<span data-ttu-id="27ebb-126">**[メール ドメイン URL]** フィールドで、1 つ以上の URL を一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="27ebb-126">In the **Email Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="27ebb-127">構成したドメイン以外のドメインからのメールをエンド ユーザーが受信すると、そのメールは iOS のメール アプリで信頼されていないメールとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="27ebb-127">When end users receive an email from a domain other than one you configured, the email is marked as untrusted in the iOS Mail app.</span></span>

