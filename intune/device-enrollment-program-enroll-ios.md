---
title: "iOS デバイスの登録 - Device Enrollment Program"
titlesuffix: Azure portal
description: "Device Enrollment Program を使用して会社所有の iOS デバイスを登録する方法を説明します。\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ddf23ba8557c0cc2dedc232e6fbe574e2d25a69
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a><span data-ttu-id="bb50c-103">Apple の Device Enrollment Program を使用して iOS デバイスを自動登録する</span><span class="sxs-lookup"><span data-stu-id="bb50c-103">Automatically enroll iOS devices with Apple's Device Enrollment Program</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="bb50c-104">このトピックは、Apple の [Device Enrollment Program (DEP)](https://deploy.apple.com) で購入したデバイスの iOS デバイス登録を有効にする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-104">This topic helps you enable iOS device enrollment for devices purchased through Apple's [Device Enrollment Program (DEP)](https://deploy.apple.com).</span></span> <span data-ttu-id="bb50c-105">自動で多数のデバイスの DEP 登録を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-105">You can enable DEP enrollment for large numbers of devices without ever touching them.</span></span> <span data-ttu-id="bb50c-106">iPhone や iPad などのデバイスを直接ユーザーに配信できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-106">You can ship devices like iPhones and iPads directly to users.</span></span> <span data-ttu-id="bb50c-107">ユーザーがデバイスの電源をオンにすると、セットアップ アシスタントが構成済み設定で実行され、デバイスが管理対象として登録されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-107">When the user turns on the device, Setup Assistant runs with preconfigured settings and the device enrolls into management.</span></span>

<span data-ttu-id="bb50c-108">DEP 登録を有効にするには、Intune ポータルと Apple DEP ポータルの両方を使います。</span><span class="sxs-lookup"><span data-stu-id="bb50c-108">To enable DEP enrollment, you use both the Intune and Apple DEP portals.</span></span> <span data-ttu-id="bb50c-109">管理するために Intune にデバイスを割り当てられるように、シリアル番号のリストまたは注文番号が必要になります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-109">A list of serial numbers or a purchase order number is required so you can assign devices to Intune for management.</span></span> <span data-ttu-id="bb50c-110">登録時にデバイスに適用された設定を含む DEP 登録プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-110">You create DEP enrollment profiles containing settings that applied to devices during enrollment.</span></span>

<span data-ttu-id="bb50c-111">なお、DEP 登録は[デバイス登録マネージャー](device-enrollment-manager-enroll.md)では動作しません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-111">By the way, DEP enrollment does not work with the [device enrollment manager](device-enrollment-manager-enroll.md).</span></span>

## <a name="what-is-supervised-mode"></a><span data-ttu-id="bb50c-112">監視モードとは何か。</span><span class="sxs-lookup"><span data-stu-id="bb50c-112">What is supervised mode?</span></span>
<span data-ttu-id="bb50c-113">Apple は iOS 5 で監視モードを導入しました。</span><span class="sxs-lookup"><span data-stu-id="bb50c-113">Apple introduced supervised mode in iOS 5.</span></span> <span data-ttu-id="bb50c-114">監視モードの iOS デバイスは、さらに細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-114">An iOS device in supervised mode can be managed with more controls.</span></span> <span data-ttu-id="bb50c-115">そのため、企業所有のデバイスで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-115">As such, it is especially useful for corporate-owned devices.</span></span> <span data-ttu-id="bb50c-116">Intune は Apple Device Enrollment Program (DEP) の一部としてデバイスの監視モードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-116">Intune supports configuring devices for supervised mode as part the Apple Device Enrollment Program (DEP).</span></span> 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a><span data-ttu-id="bb50c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb50c-117">Prerequisites</span></span>
- <span data-ttu-id="bb50c-118">[Apple の Device Enrollment Program](http://deploy.apple.com) で購入したデバイス</span><span class="sxs-lookup"><span data-stu-id="bb50c-118">Devices purchased in [Apple's Device Enrollment Program](http://deploy.apple.com)</span></span>
- [<span data-ttu-id="bb50c-119">MDM 機関</span><span class="sxs-lookup"><span data-stu-id="bb50c-119">MDM Authority</span></span>](mdm-authority-set.md)
- [<span data-ttu-id="bb50c-120">Apple MDM プッシュ証明書</span><span class="sxs-lookup"><span data-stu-id="bb50c-120">Apple MDM Push certificate</span></span>](apple-mdm-push-certificate-get.md)

> [!NOTE]
> <span data-ttu-id="bb50c-121">多要素認証 (MFA) は、ユーザー アフィニティの DEP 登録セットアップ中は動作しません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-121">Multifactor authentication (MFA) doesn't work during DEP enrollment set up for user affinity.</span></span> <span data-ttu-id="bb50c-122">登録後、MFA はデバイスで期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-122">After enrollment, MFA works as expected on devices.</span></span> <span data-ttu-id="bb50c-123">デバイスでは、最初のサインイン時にパスワードの変更が必要なユーザーにプロンプトを表示することができません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-123">Devices can't prompt users who need to change their password when they first sign in.</span></span> <span data-ttu-id="bb50c-124">さらに、パスワードの有効期限が切れているユーザーには、登録時にパスワードのリセットは求められません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-124">Additionally, users with expired passwords aren't prompted to reset their password during enrollment.</span></span> <span data-ttu-id="bb50c-125">ユーザーは別のデバイスを使用してパスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-125">Users must use a different device to reset the password.</span></span>

## <a name="get-the-apple-dep-token"></a><span data-ttu-id="bb50c-126">Apple DEP トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="bb50c-126">Get the Apple DEP token</span></span>

<span data-ttu-id="bb50c-127">DEP に iOS デバイスを登録するには、Apple の DEP トークン (.p7m) ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb50c-127">Before you can enroll iOS devices with DEP, you need a DEP token (.p7m) file from Apple.</span></span> <span data-ttu-id="bb50c-128">このトークンにより、Intune は企業所有の DEP デバイスに関する情報を同期できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-128">This token lets Intune sync information about DEP devices that your corporation owns.</span></span> <span data-ttu-id="bb50c-129">また、Intune は Apple に登録プロファイルをアップロードして、デバイスをそれらのプロファイルに割り当てられるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-129">It also permits Intune to upload enrollment profiles to Apple and to assign devices to those profiles.</span></span>

<span data-ttu-id="bb50c-130">DEP トークンを作成する場合は、Apple DEP ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-130">You use the Apple DEP portal to create a DEP token.</span></span> <span data-ttu-id="bb50c-131">また、管理のためにデバイスを Intune に割り当てる場合にも DEP ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-131">You also use the DEP portal to assign devices to Intune for management.</span></span>

> [!NOTE]
> <span data-ttu-id="bb50c-132">Azure に移行する前に Intune クラシック ポータルからトークンを削除すると、削除された Apple DEP トークンが Intune で復元される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-132">If you delete the token from the Intune classic portal before migrating to Azure, Intune might restore a deleted Apple DEP token.</span></span> <span data-ttu-id="bb50c-133">Azure Portal から DEP トークンを再び削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-133">You can delete the DEP token again from the Azure portal.</span></span> <span data-ttu-id="bb50c-134">Azure Portal から DEP トークンを再び削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-134">You can delete the DEP token again from the Azure portal.</span></span>

<span data-ttu-id="bb50c-135"><strong>手順 1: Apple DEP トークンを作成するために必要な Intune 公開キー証明書をダウンロードします。</strong></span><span class="sxs-lookup"><span data-stu-id="bb50c-135"><strong>Step 1. Download an Intune public key certificate required to create an Apple DEP token.</strong></span></span><br>


1. <span data-ttu-id="bb50c-136">Azure ポータルの Intune で、**[デバイスの登録]** > **[Apple の登録]** > **[Enrollment Program トークン]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-136">In Intune in the Azure portal, choose **Device enrollment** > **Apple enrollment** > **Enrollment Program Token**.</span></span>

   ![[Apple 証明書] ワークスペースの [Enrollment Program トークン] のスクリーンショット。](./media/enrollment-program-token-add.png)

2. <span data-ttu-id="bb50c-138">**[公開キーをダウンロードします]** を選択し、暗号化キー (.pem) ファイルをダウンロードしてローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-138">Choose **Download your public key** to download and save the encryption key (.pem) file locally.</span></span> <span data-ttu-id="bb50c-139">.pem ファイルは、Apple Device Enrollment Program ポータルから信頼関係証明書を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-139">The .pem file is used to request a trust-relationship certificate from the Apple Device Enrollment Program portal.</span></span>

   ![公開キーをダウンロードするための [Apple 証明書] ワークスペースの [Enrollment Program トークン] のスクリーンショット。](./media/enrollment-program-token-download.png)

<span data-ttu-id="bb50c-141"><strong>手順 2:Apple DEP トークンを作成し、ダウンロードします。</strong></span><span class="sxs-lookup"><span data-stu-id="bb50c-141"><strong>Step 2. Create and download an Apple DEP token.</strong></span></span><br>

1. <span data-ttu-id="bb50c-142">**[Apple Device Enrollment Program を使用してトークンを作成します]** を選択して Apple の Deployment Program ポータルを開き、会社の Apple ID でサインインします。</span><span class="sxs-lookup"><span data-stu-id="bb50c-142">Choose **Create a token via Apple's Device Enrollment Program** to open Apple's Deployment Program portal, and sign in with your company Apple ID.</span></span> <span data-ttu-id="bb50c-143">この Apple ID を使って、DEP トークンを更新できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-143">You can use this Apple ID to renew your DEP token.</span></span>
2.  <span data-ttu-id="bb50c-144">Apple の [Deployment Programs ポータル](https://deploy.apple.com) で、**[Device Enrollment Program]** の **[開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-144">In Apple's [Deployment Programs portal](https://deploy.apple.com), choose **Get Started** for **Device Enrollment Program**.</span></span>

3. <span data-ttu-id="bb50c-145">**[Manage Servers\(サーバーの管理\)]** ページで、**[Add MDM Server\(MDM サーバーの追加\)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-145">On the **Manage Servers** page, choose **Add MDM Server**.</span></span>
4. <span data-ttu-id="bb50c-146">**MDM サーバー名**を入力し、**[Next]** (次へ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb50c-146">Enter the **MDM Server Name**, and then choose **Next**.</span></span> <span data-ttu-id="bb50c-147">サーバー名は、自分がモバイル デバイス管理 (MDM) サーバーを識別できるようにするための名前です。</span><span class="sxs-lookup"><span data-stu-id="bb50c-147">The server name is for your reference to identify the mobile device management (MDM) server.</span></span> <span data-ttu-id="bb50c-148">Microsoft Intune サーバーの名前または URL ではありません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-148">It is not the name or URL of the Microsoft Intune server.</span></span>

   ![DEP の MDM サーバー名を追加して [次へ] をクリックしたスクリーンショット。](./media/enrollment-program-token-add-server.png)

5. <span data-ttu-id="bb50c-150">**[Add &lt;ServerName&gt;\(<サーバー名> の追加\)]** ダイアログ ボックスが開き、**[Upload Your Public Key\(公開キーをアップロードする\)]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-150">The **Add &lt;ServerName&gt;** dialog box opens, stating **Upload Your Public Key**.</span></span> <span data-ttu-id="bb50c-151">**[Choose File]** (ファイルを選択) をクリックして</span><span class="sxs-lookup"><span data-stu-id="bb50c-151">Choose **Choose File…**</span></span> <span data-ttu-id="bb50c-152">.pem ファイルをアップロードし、**[Next]** (次へ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-152">to upload the .pem file, and then choose **Next**.</span></span>  


7. <span data-ttu-id="bb50c-153">**[Deployment Programs](展開プログラム)** &gt; **[Device Enrollment Program]** &gt; **[Manage Devices](デバイスの管理)** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-153">Go to  **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Manage Devices**.</span></span>
8. <span data-ttu-id="bb50c-154">**[Choose Devices By\(デバイスの選択方法\)]** で、デバイスを識別する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-154">Under **Choose Devices By**, specify how devices are identified:</span></span>
    - <span data-ttu-id="bb50c-155">**Serial Number\(シリアル番号\)**</span><span class="sxs-lookup"><span data-stu-id="bb50c-155">**Serial Number**</span></span>
    - <span data-ttu-id="bb50c-156">**Order Number\(注文番号\)**</span><span class="sxs-lookup"><span data-stu-id="bb50c-156">**Order Number**</span></span>
    - <span data-ttu-id="bb50c-157">**Upload CSV File\(CSV ファイルのアップロード\)**</span><span class="sxs-lookup"><span data-stu-id="bb50c-157">**Upload CSV File**.</span></span>

   ![シリアル番号でデバイスを選択するように指定し、アクションの選択でサーバーへの割り当てを設定し、サーバー名を選択したスクリーンショット。](./media/enrollment-program-token-specify-serial.png)

9. <span data-ttu-id="bb50c-159">**[アクションの選択]** で **[Assign to Server]\(サーバーに割り当てる\)** を選択し、Microsoft Intune に指定した **ServerName** を選択して、&lt;[OK]&gt; を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-159">For **Choose Action**, choose **Assign to Server**, choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.</span></span> <span data-ttu-id="bb50c-160">指定したデバイスが管理用に Intune サーバーに割り当てられて、**[Assignment Complete\(割り当て完了\)]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-160">The Apple portal assigns the specified devices to the Intune server for management and then displays **Assignment Complete**.</span></span>

   <span data-ttu-id="bb50c-161">Apple ポータルで、**[Deployment Programs\(配備プログラム\)]** &gt; **[Device Enrollment Program\(Device Enrollment Program\)]** &gt; **[View Assignment History\(割り当て履歴の表示\)]** の順に移動して、デバイスとその MDM サーバーの割り当てのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-161">In the Apple portal, go to **Deployment Programs** &gt; **Device Enrollment Program** &gt; **View Assignment History** to see a list of devices and their MDM server assignment.</span></span>

<span data-ttu-id="bb50c-162">**手順 3:Enrollment Program トークンの作成に使った Apple ID を入力します。**</span><span class="sxs-lookup"><span data-stu-id="bb50c-162">**Step 3. Enter the Apple ID used to create your enrollment program token.**</span></span><br><span data-ttu-id="bb50c-163">Azure ポータルの Intune で、後で参照するための Apple ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-163">In Intune in the Azure portal, provide the Apple ID for future reference.</span></span> <span data-ttu-id="bb50c-164">すべてのデバイスを再登録しなくて済むように、今後、Enrollment Program トークンを更新するときはこの ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-164">Use this ID to renew your enrollment program token in the future to avoid needing to re-enroll all your devices.</span></span>

![Enrollment Program トークンの作成に使った Apple ID の指定と、Enrollment Program トークンの参照のスクリーンショット。](./media/enrollment-program-token-apple-id.png)

<span data-ttu-id="bb50c-166">**手順 4:アップロードする Enrollment Program トークンを参照します。**</span><span class="sxs-lookup"><span data-stu-id="bb50c-166">**Step 4. Browse to your enrollment program token to upload.**</span></span><br>
<span data-ttu-id="bb50c-167">証明書 (.pem) ファイルに移動し、**[開く]** を選択して、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-167">Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**.</span></span> <span data-ttu-id="bb50c-168">このプッシュ証明書を使用して、Intune はモバイル デバイスを登録し、登録したモバイル デバイスにポリシーを適用して iOS デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-168">With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span> <span data-ttu-id="bb50c-169">Intune は、Apple と自動的に同期して、Enrollment Program アカウントを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-169">Intune automatically synchronizes with Apple to see your enrollment program account.</span></span>

## <a name="create-an-apple-enrollment-profile"></a><span data-ttu-id="bb50c-170">Apple 登録プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bb50c-170">Create an Apple enrollment profile</span></span>

<span data-ttu-id="bb50c-171">これでトークンがインストールされました。DEP デバイスの登録プロファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-171">Now that you've installed your token, you can create an enrollment profile for DEP devices.</span></span> <span data-ttu-id="bb50c-172">デバイス登録プロファイルで、デバイス グループに対して登録時に適用する設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-172">A device enrollment profile defines the settings applied to a group of devices during enrollment.</span></span>

1. <span data-ttu-id="bb50c-173">Azure ポータルの Intune で、**[デバイスの登録]** > **[Apple の登録]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-173">In Intune in the Azure portal, choose **Device enrollment** > **Apple Enrollment**.</span></span>
2. <span data-ttu-id="bb50c-174">**[Apple の Enrollment Program]** で、**[Enrollment Program プロファイル]** > **[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-174">Under **Enrollment Program for Apple**, choose **Enrollment Program Profiles** > **Create**.</span></span>
3. <span data-ttu-id="bb50c-175">**[登録プロファイルの作成]** で、管理用にプロファイルの **[名前]** と **[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-175">On **Create Enrollment Profile**, enter a **Name** and **Description** for the profile for administrative purposes.</span></span> <span data-ttu-id="bb50c-176">ユーザーにはこれらの詳細は表示されません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-176">Users do not see these details.</span></span> <span data-ttu-id="bb50c-177">この **[名前]** フィールドを使用して、Azure Active Directory で動的グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-177">You can use this **Name** field to create a dynamic group in Azure Active Directory.</span></span> <span data-ttu-id="bb50c-178">この登録プロファイルに対応するデバイスを割り当てるために enrollmentProfileName パラメーターを定義する場合はプロファイル名を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-178">Use the profile name to define the enrollmentProfileName parameter to assign devices with this enrollment profile.</span></span> <span data-ttu-id="bb50c-179">Azure Active Directory の動的グループの詳細については[こちら](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb50c-179">Learn more about [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).</span></span>

   <span data-ttu-id="bb50c-180">**[ユーザー アフィニティ]** で、このプロファイルに対応するデバイスを割り当て済みユーザーとともに登録するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-180">For **User Affinity**, choose whether devices with this profile enroll with or without an assigned user.</span></span>

   - <span data-ttu-id="bb50c-181">**[ユーザー アフィニティとともに登録する]** - ユーザーに属していて、アプリのインストールなどのサービスにポータル サイトを使用する必要があるデバイスの場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-181">**Enroll with user affinity** - Choose for devices that belong to users and that need to use the company portal for services like installing apps.</span></span> <span data-ttu-id="bb50c-182">ユーザー アフィニティには [WS-Trust 1.3 Username/Mixed エンドポイント](https://technet.microsoft.com/library/adfs2-help-endpoints)が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb50c-182">User affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints).</span></span> <span data-ttu-id="bb50c-183">[詳細については、ここをクリック](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint)してください。</span><span class="sxs-lookup"><span data-stu-id="bb50c-183">[Learn more](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).</span></span>

   - <span data-ttu-id="bb50c-184">**[ユーザー アフィニティなしで登録する]** - 1 人のユーザーに関連付けられていないデバイスの場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-184">**Enroll without user affinity** - Choose for device unaffiliated with a single user.</span></span> <span data-ttu-id="bb50c-185">ローカルのユーザー データにアクセスせずにタスクを実行するデバイスで使用します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-185">Use for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="bb50c-186">ポータル サイト アプリなどのアプリは動作しません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-186">Apps like the Company Portal app don’t work.</span></span>

4. <span data-ttu-id="bb50c-187">**[デバイス管理の設定]** を選択し、次のプロファイル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-187">Choose **Device Management Settings** to configure the following profile settings:</span></span>

   ![管理モードが選択されているスクリーン ショット。](./media/enrollment-program-profile-mode.png)
    - <span data-ttu-id="bb50c-191">**[監督下]** - より多くの管理オプションが使用可能な管理モードです。既定でアクティベーション ロックは無効になります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-191">**Supervised** - a management mode that enables more management options and disabled Activation Lock by default.</span></span> <span data-ttu-id="bb50c-192">このチェック ボックスをオフのままにすると、管理機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-192">If you leave the check box blank, you have limited management capabilities.</span></span> <span data-ttu-id="bb50c-193">Microsoft は、多数の iOS デバイスを展開する組織に対して特に、監視モードを有効にするメカニズムとして DPE の利用を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="bb50c-193">Microsoft recommends using DEP as the mechanism for enabling supervised mode, especially for organizations that are deploying large numbers of iOS devices.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb50c-194">デバイスの登録後、Intune を利用してデバイスの監視モードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-194">Configuring a device for supervised mode cannot be done using Intune after a device has been enrolled.</span></span> <span data-ttu-id="bb50c-195">登録後に監視モードを有効にする唯一の方法は、USB ケーブルで iOS デバイスを Mac に接続し、Apple Configurator を使用することです。</span><span class="sxs-lookup"><span data-stu-id="bb50c-195">After enrollment, the only way to enable supervised mode is to connect an iOS device to a Mac with a USB cable and use Apple Configurator.</span></span> <span data-ttu-id="bb50c-196">デバイスがリセットされ、監視モードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-196">This will reset the device and configure it in supervised mode.</span></span> <span data-ttu-id="bb50c-197">詳細については、[Apple Configurator ドキュメント](http://help.apple.com/configurator/mac/2.3)を参照してください。監視対象となったデバイスのロック画面には、"この iPhone は Contoso が管理しています" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-197">Learn more about this on [Apple Configurator docs](http://help.apple.com/configurator/mac/2.3). A supervised device will say that "This iPhone is managed by Contoso."</span></span> <span data-ttu-id="bb50c-198">また、"この iPhone は監視されています。</span><span class="sxs-lookup"><span data-stu-id="bb50c-198">on the lock screen, and "This iPhone is supervised.</span></span> <span data-ttu-id="bb50c-199">Contoso はインターネット トラフィックを監視し、このデバイスの位置を特定できます。" と、</span><span class="sxs-lookup"><span data-stu-id="bb50c-199">Contoso can monitor your Internet traffic and locate this device."</span></span> <span data-ttu-id="bb50c-200">**[設定]**、**[全般]**、**[情報]** の順に選択すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-200">in **Settings** > **General** > **About**.</span></span>

    - <span data-ttu-id="bb50c-201">**[ロックされた登録]** - ([管理モード] を [監督下] にする必要があります) 管理プロファイルの削除を許可する iOS 設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="bb50c-201">**Locked enrollment** - (Requires Management Mode = supervised) Disables iOS settings that could allow removal of the management profile.</span></span> <span data-ttu-id="bb50c-202">このチェック ボックスをオフのままにすると、[設定] メニューから管理プロファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-202">If you leave the check box blank, it allows the management profile to be removed from the Settings menu.</span></span> <span data-ttu-id="bb50c-203">デバイスの登録後は、デバイスを出荷時の設定にリセットしないと、この設定を変更することができません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-203">After device enrollment, you cannot change this setting without factory resetting the device.</span></span>

   - <span data-ttu-id="bb50c-204">**[有効な Shared iPad]** - Apple の Device Enrollment Program は共有の iPad をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-204">**Enable Shared iPad** - Apple's Device Enrollment Program does not support shared iPad.</span></span>

     - <span data-ttu-id="bb50c-205">**[ペアリングの許可]** - iOS デバイスをコンピューターと同期できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-205">**Allow Pairing** - Specifies whether iOS devices can sync with computers.</span></span> <span data-ttu-id="bb50c-206">**[証明書による Apple Configurator の許可]** を選択した場合は、**[Apple Configurator の証明書]** で証明書を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-206">If you chose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**.</span></span>

     - <span data-ttu-id="bb50c-207">**[Apple Configurator の証明書]** - **[ペアリングの許可]** で **[証明書による Apple Configurator の許可]** を選択した場合は、インポートする Apple Configurator の証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-207">**Apple Configurator Certificates** - If you chose **Allow Apple Configurator by certificate** under **Allow Pairing**, choose an Apple Configurator Certificate to import.</span></span>

   <span data-ttu-id="bb50c-208">**[保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-208">Choose **Save**.</span></span>

5. <span data-ttu-id="bb50c-209">**[セットアップ アシスタントの設定]** を選択し、次のプロファイル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-209">Choose **Setup Assistant Settings** to configure the following profile settings:</span></span>

   ![新しい Enrollment Program プロファイルで使用可能な設定が選択されている構成設定のスクリーンショット。](./media/enrollment-program-profile-settings.png)
   - <span data-ttu-id="bb50c-211">**[部署名]** - アクティブ化中にユーザーが **[About Configuration (構成について)]** をタップすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-211">**Department Name** - Appears when users tap **About Configuration** during activation.</span></span>

   - <span data-ttu-id="bb50c-212">**[部署の電話番号]** - アクティブ化中にユーザーが **[ヘルプが必要ですか]** ボタンをクリックすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-212">**Department Phone** - Appears when the user clicks the **Need Help** button during activation.</span></span>
   - <span data-ttu-id="bb50c-213">**セットアップ アシスタントのオプション** - これらの省略可能な設定は、後で iOS の **[設定]** メニューで設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-213">**Setup Assistant Options** - These optional settings can be set up later in the iOS **Settings** menu.</span></span>
       - <span data-ttu-id="bb50c-214">**パスコード**</span><span class="sxs-lookup"><span data-stu-id="bb50c-214">**Passcode**</span></span>
       - <span data-ttu-id="bb50c-215">**ロケーション サービス**</span><span class="sxs-lookup"><span data-stu-id="bb50c-215">**Location Services**</span></span>
       - <span data-ttu-id="bb50c-216">**復元**</span><span class="sxs-lookup"><span data-stu-id="bb50c-216">**Restore**</span></span>
       - <span data-ttu-id="bb50c-217">**Apple ID**</span><span class="sxs-lookup"><span data-stu-id="bb50c-217">**Apple ID**</span></span>
       - <span data-ttu-id="bb50c-218">**使用条件**</span><span class="sxs-lookup"><span data-stu-id="bb50c-218">**Terms and Conditions**</span></span>
       - <span data-ttu-id="bb50c-219">**Touch ID**</span><span class="sxs-lookup"><span data-stu-id="bb50c-219">**Touch ID**</span></span>
       - <span data-ttu-id="bb50c-220">**Apple Pay**</span><span class="sxs-lookup"><span data-stu-id="bb50c-220">**Apple Pay**</span></span>
       - <span data-ttu-id="bb50c-221">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="bb50c-221">**Zoom**</span></span>
       - <span data-ttu-id="bb50c-222">**Siri**</span><span class="sxs-lookup"><span data-stu-id="bb50c-222">**Siri**</span></span>
       - <span data-ttu-id="bb50c-223">**診断データ**</span><span class="sxs-lookup"><span data-stu-id="bb50c-223">**Diagnostic Data**</span></span>

     <span data-ttu-id="bb50c-224">**[保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-224">Choose **Save**.</span></span>

6. <span data-ttu-id="bb50c-225">プロファイルの設定を保存するには、**[登録プロファイルの作成]** ブレードで **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-225">To save the profile settings, choose **Create** on the **Create Enrollment Profile** blade.</span></span> <span data-ttu-id="bb50c-226">登録プロファイルが、[Apple Enrollment Program 登録プロファイル] の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-226">The enrollment profile appears in the Apple Enrollment Program Enrollment Profiles list.</span></span>

## <a name="sync-managed-devices"></a><span data-ttu-id="bb50c-227">管理対象デバイスを同期する</span><span class="sxs-lookup"><span data-stu-id="bb50c-227">Sync managed devices</span></span>
<span data-ttu-id="bb50c-228">デバイスを管理するアクセス許可を Intune に割り当てたので、Intune と Apple を同期して、管理対象デバイスを Azure ポータルの Intune に表示できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-228">Now that Intune has permission to manage your devices, you can synchronize Intune with Apple to see your managed devices in Intune in the Azure portal.</span></span>

1. <span data-ttu-id="bb50c-229">Azure Portal の Intune で、**[デバイスの登録]** > **[Apple の登録]** > **[Enrollment Program デバイス]** > **[同期]** の順に選択します。進行状況バーには、もう一度同期が要求されるまでの待ち時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-229">In Intune in the Azure portal, choose **Device enrollment** > **Apple Enrollment** > **Enrollment Program Devices** > **Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.</span></span>

   ![[Enrollment Program デバイス] ノードと [同期] リンクが選ばれているスクリーンショット。](./media/enrollment-program-device-sync.png)

2. <span data-ttu-id="bb50c-231">**[同期]** ブレードで、**[同期を要求]** を選択します。進行状況バーには、もう一度同期が要求されるまでの待ち時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-231">On the **Sync** blade, choose **Request Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.</span></span>

   ![[同期を要求] リンクが選ばれている [同期] ブレードのスクリーンショット。](./media/enrollment-program-device-request-sync.png)

   <span data-ttu-id="bb50c-233">許容される Enrollment Program トラフィックについての Apple の規約に準拠するため、Intune では次の制限が課せられます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-233">To comply with Apple’s terms for acceptable enrollment program traffic, Intune imposes the following restrictions:</span></span>
     -  <span data-ttu-id="bb50c-234">完全な同期は 7 日に 1 回だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-234">A full sync can run no more than once every seven days.</span></span> <span data-ttu-id="bb50c-235">Intune は、完全な同期中に、Intune に割り当てられているすべての Apple シリアル番号を更新します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-235">During a full sync, Intune refreshes every Apple serial number assigned to Intune.</span></span> <span data-ttu-id="bb50c-236">前回の完全同期の 7 日以内に完全同期が試みられると、Intune は Intune にまだ一覧表示されていないシリアル番号のみを更新します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-236">If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.</span></span>
     -  <span data-ttu-id="bb50c-237">すべての同期要求は、完了までに 15 分与えられます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-237">Any sync request is given 15 minutes to finish.</span></span> <span data-ttu-id="bb50c-238">この時間中または要求が成功するまで、**[同期]** ボタンは無効にされます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-238">During this time or until the request succeeds, the **Sync** button is disabled.</span></span>
     - <span data-ttu-id="bb50c-239">Intune は、24 時間ごとに新規のデバイスと削除されたデバイスを Apple と同期します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-239">Intune syncs new and removed devices with Apple every 24 hours.</span></span>

3. <span data-ttu-id="bb50c-240">[Enrollment Program デバイス] ワークスペースで、**[更新]** を選んでデバイスを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-240">In the Enrollment Program Devices workspace, choose **Refresh** to see your devices.</span></span>

## <a name="assign-an-enrollment-profile-to-devices"></a><span data-ttu-id="bb50c-241">登録プロファイルをデバイスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="bb50c-241">Assign an enrollment profile to devices</span></span>
<span data-ttu-id="bb50c-242">登録する前に、Enrollment Program プロファイルをデバイスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-242">You must assign an enrollment program profile to devices before they can enroll.</span></span>

>[!NOTE]
><span data-ttu-id="bb50c-243">**[Apple Serial Numbers\(Apple シリアル番号\)]** ブレードでプロファイルにシリアル番号を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-243">You can also assign serial numbers to profiles from the **Apple Serial Numbers** blade.</span></span>

1. <span data-ttu-id="bb50c-244">Azure ポータルの Intune で **[デバイスの登録]** > **[Apple の登録]** の順に選択し、**[Enrollment Program プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-244">In Intune in the Azure portal, choose **Device enrollment** > **Apple Enrollment**, and then choose **Enrollment Program Profiles**.</span></span>
2. <span data-ttu-id="bb50c-245">**[Enrollment Program プロファイル]** の一覧から、デバイスに割り当てるプロファイルを選択し、**[デバイスの割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-245">From the list of **Enrollment Program Profiles**, choose the profile you want to assign to devices and then choose **Assign devices**.</span></span>

   ![[割り当て] が選択されている [デバイスの割り当て] のスクリーンショット。](./media/enrollment-program-device-assign.png)

3. <span data-ttu-id="bb50c-247">**[割り当て]** を選択し、このプロファイルを割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-247">Choose **Assign** and then choose the devices you want to assign this profile.</span></span> <span data-ttu-id="bb50c-248">フィルターを適用して使用可能なデバイスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="bb50c-248">You can filter to view available devices:</span></span>
   - <span data-ttu-id="bb50c-249">**未割り当て**</span><span class="sxs-lookup"><span data-stu-id="bb50c-249">**unassigned**</span></span>
   - <span data-ttu-id="bb50c-250">**任意**</span><span class="sxs-lookup"><span data-stu-id="bb50c-250">**any**</span></span>
   - <span data-ttu-id="bb50c-251">**&lt;プロファイル名&gt;**</span><span class="sxs-lookup"><span data-stu-id="bb50c-251">**&lt;profile name&gt;**</span></span>
4. <span data-ttu-id="bb50c-252">割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-252">Choose the devices you want to assign.</span></span> <span data-ttu-id="bb50c-253">列の上のチェック ボックスで最大 1,000 のデバイスを選び、**[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb50c-253">The checkbox above the column selects up to 1000 listed devices, and then click **Assign**.</span></span> <span data-ttu-id="bb50c-254">1,000 を超えるデバイスを登録するには、すべてのデバイスに登録プロファイルを割り当てるまで割り当て手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bb50c-254">To enroll more than 1000 devices, repeat the assignment steps until all devices are assigned an enrollment profile.</span></span>

   ![Intune で Enrollment Program プロファイルを割り当てるための [割り当て] ボタンのスクリーンショット](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a><span data-ttu-id="bb50c-256">デバイスを配布する</span><span class="sxs-lookup"><span data-stu-id="bb50c-256">Distribute devices</span></span>
<span data-ttu-id="bb50c-257">Apple と Intune の間の同期と管理を有効にし、DEP デバイスを登録できるようにプロファイルを割り当てました。</span><span class="sxs-lookup"><span data-stu-id="bb50c-257">You have enabled management and syncing between Apple and Intune, and assigned a profile to  let your DEP devices enroll.</span></span> <span data-ttu-id="bb50c-258">ユーザーにデバイスを配布できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bb50c-258">You can now distribute devices to users.</span></span> <span data-ttu-id="bb50c-259">ユーザー アフィニティがあるデバイスでは、各ユーザーに Intune ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb50c-259">Devices with user affinity require each user be assigned an Intune license.</span></span> <span data-ttu-id="bb50c-260">ユーザー アフィニティがないデバイスでは、デバイスのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb50c-260">Devices without user affinity require a device license.</span></span> <span data-ttu-id="bb50c-261">デバイスが出荷時の設定にリセットされるまで、アクティブ化されたデバイスは登録プロファイルを適用できません。</span><span class="sxs-lookup"><span data-stu-id="bb50c-261">An activated device cannot apply an enrollment profile until the device is factory reset.</span></span>

<span data-ttu-id="bb50c-262">「[Intune で iOS デバイスを Device Enrollment Program に登録する](/intune-user-help/enroll-your-device-dep-ios)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb50c-262">See [Enroll your iOS device in Intune with the Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).</span></span> 
