---
title: "Intune 電子メール設定を構成する方法"
titleSuffix: Azure portal
description: "管理するデバイスに会社の電子メールへの接続が作成されるように Intune を構成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5c4a0466e4de421a23b70a7beb4d1651d6caf7a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a><span data-ttu-id="948b4-103">Microsoft Intune で電子メールの設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="948b4-103">How to configure email settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="948b4-104">電子メール プロファイルを使用すると、会社の電子メールに接続し、同期するために必要な設定で管理対象デバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="948b4-104">Email profiles can be used to configure devices you manage with the settings necessary to connect to , and synchronize with company email.</span></span> <span data-ttu-id="948b4-105">こうすると、すべてのデバイスに標準の設定を適用し、正しい電子メールの設定がわからないエンド ユーザーからの問い合わせを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="948b4-105">This can help ensure that settings are standard across all of your devices, and also help to reduce support calls from end users who do not know the correct email settings.</span></span>

<span data-ttu-id="948b4-106">ほとんどのプラットフォームに組み込まれているメール クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="948b4-106">The built-in mail client is supported for most platforms.</span></span> <span data-ttu-id="948b4-107">ほとんどのサード パーティ製の電子メール アプリは現在サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="948b4-107">Most third-party email apps are not currently supported.</span></span>

<span data-ttu-id="948b4-108">電子メール プロファイルを使用して、次のデバイスの種類でネイティブ電子メール クライアントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="948b4-108">You can use email profiles to configure the native email client on the following device types:</span></span>

- <span data-ttu-id="948b4-109">Android Samsung KNOX Standard 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="948b4-109">Android Samsung KNOX Standard 4.0 and later</span></span>
- <span data-ttu-id="948b4-110">Android for Work</span><span class="sxs-lookup"><span data-stu-id="948b4-110">Android for Work</span></span>
- <span data-ttu-id="948b4-111">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="948b4-111">iOS 8.0 and later</span></span>
- <span data-ttu-id="948b4-112">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="948b4-112">Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="948b4-113">Windows 10 (デスクトップ) と Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="948b4-113">Windows 10 (desktop) and Windows 10 Mobile</span></span>

<span data-ttu-id="948b4-114">このトピックでは、電子メール プロファイルを構成する基本的な方法について説明します。その後、デバイスごとの詳細については、各プラットフォームのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="948b4-114">Use the information in this topic to learn the basics about configuring an email profile, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-email-settings"></a><span data-ttu-id="948b4-115">電子メール設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="948b4-115">Create a device profile containing email settings</span></span>

1. <span data-ttu-id="948b4-116">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="948b4-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="948b4-117">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="948b4-118">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-118">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="948b4-119">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-119">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="948b4-120">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-120">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="948b4-121">**[プロファイルを作成します]** ブレードで、電子メール プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="948b4-121">On the **Create Profile** blade, enter a **Name** and **Description** for the email profile.</span></span>
5. <span data-ttu-id="948b4-122">**[プラットフォーム]** ドロップダウン リストで、電子メール設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-122">From the **Platform** drop-down list, select the device platform to which you want to apply email settings.</span></span> <span data-ttu-id="948b4-123">現時点では、電子メール デバイス設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="948b4-123">Currently, you can choose one of the following platforms for email device settings:</span></span>
    - <span data-ttu-id="948b4-124">**Android** (Samsung Android KNOX Standard のみ)</span><span class="sxs-lookup"><span data-stu-id="948b4-124">**Android** (Samsung Android KNOX Standard only)</span></span>
    - <span data-ttu-id="948b4-125">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="948b4-125">**Android for Work**</span></span>
    - <span data-ttu-id="948b4-126">**Android**</span><span class="sxs-lookup"><span data-stu-id="948b4-126">**iOS**</span></span>
    - <span data-ttu-id="948b4-127">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="948b4-127">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="948b4-128">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="948b4-128">**Windows 10 and later**</span></span>
6. <span data-ttu-id="948b4-129">**[プロファイルの種類]** ドロップダウン リストで、**[電子メール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-129">From the **Profile** type drop-down list, choose **Email**.</span></span>
7. <span data-ttu-id="948b4-130">選択したプラットフォームによって構成できる設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="948b4-130">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="948b4-131">各プラットフォームの詳細な設定については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="948b4-131">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="948b4-132">Android for Work および Samsung KNOX Standard の設定</span><span class="sxs-lookup"><span data-stu-id="948b4-132">Android for Work and Samsung KNOX Standard settings</span></span>](email-settings-android.md)
    - [<span data-ttu-id="948b4-133">iOS の設定</span><span class="sxs-lookup"><span data-stu-id="948b4-133">iOS settings</span></span>](email-settings-ios.md)
    - [<span data-ttu-id="948b4-134">Windows Phone 8.1 の設定</span><span class="sxs-lookup"><span data-stu-id="948b4-134">Windows Phone 8.1 settings</span></span>](email-settings-windows-phone-8-1.md)
    - [<span data-ttu-id="948b4-135">Windows 10 の設定</span><span class="sxs-lookup"><span data-stu-id="948b4-135">Windows 10 settings</span></span>](email-settings-windows-10.md)
8. <span data-ttu-id="948b4-136">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="948b4-136">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="948b4-137">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="948b4-137">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="948b4-138">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="948b4-138">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

## <a name="further-information"></a><span data-ttu-id="948b4-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="948b4-139">Further information</span></span>

### <a name="remove-an-email-profile"></a><span data-ttu-id="948b4-140">電子メール プロファイルの削除</span><span class="sxs-lookup"><span data-stu-id="948b4-140">Remove an email profile</span></span>

<span data-ttu-id="948b4-141">デバイスから電子メール プロファイルを削除する場合、割り当てを編集し、デバイスがメンバーになっているすべてのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="948b4-141">If you want to remove an email profile from a device, edit the assignment and remove any groups of which the device is a member.</span></span> <span data-ttu-id="948b4-142">デバイスで唯一の電子メール プロファイルはこの方法で削除できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="948b4-142">Note that you cannot remove an email profile in this way if it is the only email profile on a device.</span></span>

### <a name="securing-email-access"></a><span data-ttu-id="948b4-143">電子メールへのアクセスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="948b4-143">Securing email access</span></span>

<span data-ttu-id="948b4-144">電子メール プロファイルは、2 つの方法のいずれかを使用して保護できます。</span><span class="sxs-lookup"><span data-stu-id="948b4-144">You can help secure email profiles using one of two methods:</span></span>

1. <span data-ttu-id="948b4-145">**[証明書]** - 電子メール プロファイルを作成する際に、事前に Intune で作成しておいた証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="948b4-145">**Certificates** - When you create the email profile, you choose a certificate profile that you have previously created in Intune.</span></span> <span data-ttu-id="948b4-146">これは ID 証明書と呼ばれ、ユーザーのデバイスが接続を許可されていることを示す信頼できる証明書プロファイル (または、ルート証明書) に対して認証を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="948b4-146">This is known as the identity certificate, and is used to authenticate against a trusted certificate profile (or a root certificate) to establish that the user’s device is allowed to connect.</span></span> <span data-ttu-id="948b4-147">信頼された証明書は、電子メールの接続を認証するコンピューター (通常はネイティブ電子メール サーバー) に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="948b4-147">The trusted certificate is assigned to the computer that authenticates the email connection, typically, the native mail server.</span></span>
<span data-ttu-id="948b4-148">Intune で証明書プロファイルを作成および使用する方法の詳細については、[Intune で証明書を構成する方法](certificates-configure.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="948b4-148">For more information about how to create and use certificate profiles in Intune, see [How to configure certificates with Intune](certificates-configure.md).</span></span>
2. <span data-ttu-id="948b4-149">**[ユーザー名とパスワード]** - ユーザーは、ユーザー名とパスワードを提供することにより、ネイティブ電子メール サーバーに対して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="948b4-149">**User name and password** - The user authenticates to the native mail server by providing their user name and password.</span></span>
<span data-ttu-id="948b4-150">パスワードは電子メール プロファイルに含まれていないため、電子メールに接続するときにユーザーが入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="948b4-150">The password is not contained in the email profile, so the user needs to supply this when they connect to email.</span></span>


### <a name="how-intune-handles-existing-email-accounts"></a><span data-ttu-id="948b4-151">Intune が既存の電子メール アカウントを処理する方法</span><span class="sxs-lookup"><span data-stu-id="948b4-151">How Intune handles existing email accounts</span></span>

<span data-ttu-id="948b4-152">ユーザーが電子メール アカウントを既に構成している場合、Intune 電子メール プロファイルの割り当ての結果はデバイス プラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="948b4-152">If the user has already configured an email account, the result of the Intune email profile assignment depends on the device platform:</span></span>

- <span data-ttu-id="948b4-153">**iOS:** ホスト名と電子メール アドレスに基づいて、既存の重複する電子メール プロファイルが検出されます。</span><span class="sxs-lookup"><span data-stu-id="948b4-153">**iOS:** An existing, duplicate email profile is detected based on host name and email address.</span></span> <span data-ttu-id="948b4-154">重複する電子メール プロファイルにより、Intune プロファイルの割り当てがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="948b4-154">The duplicate email profile will blocks the assignment of an Intune profile.</span></span> <span data-ttu-id="948b4-155">この場合、ポータル サイトはユーザーに、準拠していないことを通知し、手動で構成されたプロファイルを削除するようユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="948b4-155">In this case, the Company Portal informs the user that they are not compliant and prompts the user to remove the manually configured profile.</span></span> <span data-ttu-id="948b4-156">この問題を防ぐには、電子メール プロファイルをインストールする前に登録して、Intune によるプロファイルのセットアップを許可するようにユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="948b4-156">To help prevent this problem, instruct your users to enroll before installing an email profile, which allows Intune to set up the profile.</span></span>
- <span data-ttu-id="948b4-157">**Windows:** ホスト名と電子メール アドレスに基づいて、既存の重複する電子メール プロファイルが検出されます。</span><span class="sxs-lookup"><span data-stu-id="948b4-157">**Windows:** An existing, duplicate email profile is detected based on host name and email address.</span></span> <span data-ttu-id="948b4-158">Intune は、ユーザーによって作成された既存の電子メール プロファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="948b4-158">Intune overwrites the existing email profile created by the user.</span></span>
- <span data-ttu-id="948b4-159">**Android Samsung KNOX Standard** 電子メール アドレスに基づいて既存の重複する電子メール プロファイルが検出され、Intune プロファイルで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="948b4-159">**Android Samsung KNOX Standard** An existing, duplicate email profile is detected based on the email address, and overwrites it with the Intune profile.</span></span>
<span data-ttu-id="948b4-160">Android はプロファイルを識別するためにホスト名を使用しないため、複数の電子メール プロファイルを作成して異なるホスト上の同じ電子メール アドレスで使用することはお勧めしません。プロファイルが相互に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="948b4-160">Since Android does not use host name to identify the profile, we recommend that you not create multiple email profiles to use on the same email address on different hosts, as these overwrite each other.</span></span>
- <span data-ttu-id="948b4-161">**Android for Work** Intune には Android for Work 電子メール プロファイルが 2 つあります。Gmail 用と Nine Work 電子メール アプリ用です。</span><span class="sxs-lookup"><span data-stu-id="948b4-161">**Android for Work** Intune provides two Android for Work email profiles, one for each of the Gmail and Nine Work email apps.</span></span> <span data-ttu-id="948b4-162">これらのアプリは Google Play ストアで入手でき、デバイスの仕事用プロファイルにインストールされるため、プロファイルが重複することはありません。</span><span class="sxs-lookup"><span data-stu-id="948b4-162">These apps are available in the Google Play Store, and install in the device work profile, so they can't result in duplicate profiles.</span></span> <span data-ttu-id="948b4-163">いずれのアプリでも Exchange への接続がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="948b4-163">Both apps support connections to Exchange.</span></span> <span data-ttu-id="948b4-164">電子メール接続を有効にするには、いずれかの電子メール アプリをユーザーのデバイスに展開し、適切な電子メール プロファイルを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="948b4-164">To enable the email connectivity, deploy one of these email apps to your users' devices, and then create and deploy the appropriate email profile.</span></span> <span data-ttu-id="948b4-165">Nine Work などの電子メール アプリは無料とは限りません。</span><span class="sxs-lookup"><span data-stu-id="948b4-165">Email apps such as Nine Work might not be free.</span></span> <span data-ttu-id="948b4-166">アプリケーションのライセンスの詳細を確認するか、アプリの会社に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="948b4-166">Review the app’s licensing details or contact the app company with any questions.</span></span>

### <a name="update-an-email-profile"></a><span data-ttu-id="948b4-167">電子メール プロファイルの更新</span><span class="sxs-lookup"><span data-stu-id="948b4-167">Update an email profile</span></span>

<span data-ttu-id="948b4-168">以前に割り当てた電子メール プロファイルを変更すると、電子メールの設定の再構成を承認するかを確認するメッセージがエンド ユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="948b4-168">If you make changes to an email profile you previously assigned, end users might see a message asking them to approve the reconfiguration of their email settings.</span></span>
