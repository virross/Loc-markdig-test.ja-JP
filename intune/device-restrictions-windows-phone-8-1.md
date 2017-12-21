---
title: "Windows Phone 8.1 の Intune デバイス制限設定"
titleSuffix: Azure portal
description: "Windows Phone 8.1 デバイスでデバイスの設定と機能を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc0ff540bfacf16119cb5727458b42c0a7269c3a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="9737e-103">Microsoft Intune での Windows Phone 8.1 デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="9737e-103">Windows Phone 8.1 device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a><span data-ttu-id="9737e-104">全般</span><span class="sxs-lookup"><span data-stu-id="9737e-104">General</span></span>

-   <span data-ttu-id="9737e-105">**[カメラ]** - デバイスのカメラを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="9737e-105">**Camera** - Enables or blocks the device's camera.</span></span>
-   <span data-ttu-id="9737e-106">**[コピー/貼り付け]** - デバイスでコピー/貼り付け機能を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="9737e-106">**Copy and paste** - Enables or blocks copy and paste functionality on devices.</span></span>
-   <span data-ttu-id="9737e-107">**[リムーバブル記憶域]** - リムーバブル記憶域 (SD カードなど) の使用をデバイスに許可します。</span><span class="sxs-lookup"><span data-stu-id="9737e-107">**Removable storage** - Lets the device use removable storage such as SD cards.</span></span>
-   <span data-ttu-id="9737e-108">**[位置情報]** - デバイスで位置情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9737e-108">**Geolocation** - Enables the device to utilize location information.</span></span>
-   <span data-ttu-id="9737e-109">**[Microsoft アカウント]** - ユーザーが Microsoft アカウントをデバイスにリンクすることを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="9737e-109">**Microsoft account** - Enable or block the user from linking a Microsoft account to the device.</span></span>
-   <span data-ttu-id="9737e-110">**[画面キャプチャ]** - ユーザーが画面のコンテンツを画像ファイルとしてキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9737e-110">**Screen capture** - Lets the user capture the contents of the screen as an image file.</span></span>
-   <span data-ttu-id="9737e-111">**[診断データの送信]** - デバイスが Microsoft に診断情報を送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9737e-111">**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.</span></span>
-   <span data-ttu-id="9737e-112">**[カスタム メール アカウントの同期]** - Microsoft 以外の電子メール アカウントにデバイスが接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9737e-112">**Custom email accounts sync** - Enables the device to connect to non-Microsoft email accounts.</span></span>

## <a name="password"></a><span data-ttu-id="9737e-113">パスワード</span><span class="sxs-lookup"><span data-stu-id="9737e-113">Password</span></span>

-   <span data-ttu-id="9737e-114">**[パスワード]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。</span><span class="sxs-lookup"><span data-stu-id="9737e-114">**Password** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="9737e-115">**[必要なパスワードの種類]** - 英数字や数字のみなど、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-115">**Required password type** - Specifies the type of password that will be required, such as alphanumeric or numeric only.</span></span>
    -   <span data-ttu-id="9737e-116">**[パスワードの最小文字数]** - パスワードに必要な最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-116">**Minimum password length** - Specifies the minimum number of characters that are required in the password.</span></span>
    -   <span data-ttu-id="9737e-117">**[単純なパスワード]** - "0000" や "1234" などの単純なパスワードを使用できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-117">**Simple passwords** - Specifies that simple passwords such as ‘0000’ and ‘1234’ can be used.</span></span>
    -   <span data-ttu-id="9737e-118">**[デバイスがワイプされるまでのサインイン失敗回数]** - 間違ったパスワードをユーザーが何回入力すると、そのデバイスをワイプするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-118">**Number of sign-in failures before wiping device** - Specifies the number of times an incorrect password can be entered before the device is wiped.</span></span>
    -   <span data-ttu-id="9737e-119">**[画面がロックされるまでの非アクティブな最長時間 (分)]** - デバイスのアイドル状態が許容される時間を指定します。この時間を超えると、画面は自動的にロックされます。</span><span class="sxs-lookup"><span data-stu-id="9737e-119">**Maximum minutes of inactivity until screen locks** - Specifies the amount of time a device must remain idle before the screen is automatically locked.</span></span>
    -   <span data-ttu-id="9737e-120">**[パスワードの有効期限 (日数)]** - デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-120">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
    -   <span data-ttu-id="9737e-121">**[Prevent reuse of previous passwords (前のパスワードを再利用できないようにする)]** - 過去に使用されたパスワードの記憶件数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-121">**Prevent reuse of previous passwords** - Specifies how many previously used passwords are remembered.</span></span>
-   <span data-ttu-id="9737e-122">**[暗号化]** - サポートされているモバイル デバイス上のデータの暗号化を要求します。</span><span class="sxs-lookup"><span data-stu-id="9737e-122">**Encryption** - Requires that the data on supported mobile devices be encrypted.</span></span>

## <a name="app-store"></a><span data-ttu-id="9737e-123">アプリ ストア</span><span class="sxs-lookup"><span data-stu-id="9737e-123">App Store</span></span>

-   <span data-ttu-id="9737e-124">**[アプリ ストア]** - デバイスからアプリ ストアへの接続をユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="9737e-124">**App store** - Lets users connect to the app store from the device.</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="9737e-125">制限付きアプリ</span><span class="sxs-lookup"><span data-stu-id="9737e-125">Restricted apps</span></span>

<span data-ttu-id="9737e-126">制限付きアプリの一覧では、次の一覧のいずれかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9737e-126">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="9737e-127">**[ブロックされたアプリケーション]** の一覧 - ユーザーによるインストールと実行が許可されていないアプリ (Intune で管理されていない) アプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9737e-127">A **Blocked apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="9737e-128">**[許可されたアプリ]** の一覧 - ユーザーによるインストールが許可されているアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9737e-128">An **Allowed apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="9737e-129">管理対象アプリは Intune で自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="9737e-129">Apps that are managed by Intune are automatically allowed.</span></span>

<span data-ttu-id="9737e-130">この一覧を構成するには、**[追加]** をクリックし、任意の名前、アプリの発行元 (省略可能)、アプリ ストアでのアプリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="9737e-130">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a><span data-ttu-id="9737e-131">ストアにおけるアプリの URL を指定する方法</span><span class="sxs-lookup"><span data-stu-id="9737e-131">How to specify the URL to an app in the store</span></span>

<span data-ttu-id="9737e-132">許可されるアプリおよびブロックされるアプリの一覧でアプリの URL を指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="9737e-132">To specify an app URL in the allowed and blocked apps list, use the following format:</span></span>

<span data-ttu-id="9737e-133">[Windows Phone ストア](https://www.microsoft.com/store/apps/windows-phone)のページで、使用するアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="9737e-133">From the [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) page, search for the app that you want to use.</span></span>

<span data-ttu-id="9737e-134">アプリのページを開き、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9737e-134">Open the app’s page, and copy the URL to the clipboard.</span></span> <span data-ttu-id="9737e-135">許可されているアプリまたはブロックされているアプリの一覧で、これを URL として使用できます。</span><span class="sxs-lookup"><span data-stu-id="9737e-135">You can now use this as the URL in either the allowed or blocked apps list.</span></span>

<span data-ttu-id="9737e-136">例: ストアで Skype アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="9737e-136">Example: Search the store for the Skype app.</span></span> <span data-ttu-id="9737e-137">**http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** という URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="9737e-137">The URL you use will be **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.</span></span>



### <a name="additional-options"></a><span data-ttu-id="9737e-138">追加オプション</span><span class="sxs-lookup"><span data-stu-id="9737e-138">Additional options</span></span>

<span data-ttu-id="9737e-139">**[インポート]** をクリックして "<*アプリ URL*>, <*アプリ名*>, <*アプリの発行元*>" 形式の csv ファイルから一覧に値を設定したり、**[エクスポート]** をクリックして、制限付きアプリの一覧の内容を含む csv ファイルを同じ形式で作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9737e-139">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.</span></span>


## <a name="browser"></a><span data-ttu-id="9737e-140">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="9737e-140">Browser</span></span>

-   <span data-ttu-id="9737e-141">**[Web ブラウザー]** - デバイス上の組み込みの Web ブラウザーを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="9737e-141">**Web browser** - Enables or blocks the built-in web browser on devices.</span></span>

## <a name="cellular-and-connectivity"></a><span data-ttu-id="9737e-142">携帯ネットワークと接続性</span><span class="sxs-lookup"><span data-stu-id="9737e-142">Cellular and Connectivity</span></span>

-   <span data-ttu-id="9737e-143">**[Wi-Fi]** - デバイスの Wi-Fi 機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9737e-143">**Wi-Fi** - Enables or disables the Wi-Fi functionality of the device.</span></span>
-   <span data-ttu-id="9737e-144">**[Wi-Fi テザリング]** - デバイスで Wi-Fi テザリングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9737e-144">**Wi-Fi tethering** - Enables the use of Wi-Fi tethering on the device.</span></span>
-   <span data-ttu-id="9737e-145">**[自動的に Wi-Fi ホットスポットに接続します]** - 無料の Wi-Fi ホットスポットに自動的に接続し、使用条件に自動的に同意することをデバイスに許可します。</span><span class="sxs-lookup"><span data-stu-id="9737e-145">**Automatically connect to Wi-Fi hotspots** - Enables the device to automatically connect to free Wi-Fi hotspots and automatically accept any terms of use.</span></span>
-   <span data-ttu-id="9737e-146">**[Wi-Fi ホットスポットのレポート]** - ユーザーが近くにある接続を検出するのに役立つ、Wi-Fi 接続に関する情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="9737e-146">**Wi-Fi hotspot reporting** - Sends information about Wi-Fi connections to help the user discover nearby connections.</span></span>
-   <span data-ttu-id="9737e-147">**[NFC]** - 近距離無線通信をサポートするデバイスでこの機能を使用する操作を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9737e-147">**NFC** - Enables or disables operations that use near field communication on devices that support it.</span></span>
-   <span data-ttu-id="9737e-148">**[Bluetooth]** - デバイスの Bluetooth 機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9737e-148">**Bluetooth** - Enables or disables the Bluetooth functionality of the device.</span></span>
