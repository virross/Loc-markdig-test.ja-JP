---
title: "Android の Intune デバイス制限設定"
titlesuffix: Azure portal
description: "Android デバイスでデバイスの設定と機能を制御するために使用できる Intune の設定について説明します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0934e9f45cfee88fe12fac2ceda963c4afc2969c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="a0341-103">Microsoft Intune での Android および Samsung KNOX Standard デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="a0341-103">Android and Samsung KNOX Standard device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a0341-104">これらの設定を Android デバイス制限ポリシーとともに使用して、組織内のデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0341-104">Use these settings with an Android device restriction policy to configure devices in your organization.</span></span>

>[!TIP]
><span data-ttu-id="a0341-105">必要な設定が利用できない場合、[カスタム プロファイル](custom-settings-android.md)を使用して、デバイスを構成できることがあります。</span><span class="sxs-lookup"><span data-stu-id="a0341-105">If the settings you want are not available, you might be able to configure your devices using a [custom profile](custom-settings-android.md).</span></span>

## <a name="general"></a><span data-ttu-id="a0341-106">全般</span><span class="sxs-lookup"><span data-stu-id="a0341-106">General</span></span>

- <span data-ttu-id="a0341-107">**[カメラ]** - デバイスのカメラを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-107">**Camera** - Allows the use of the device camera.</span></span>
- <span data-ttu-id="a0341-108">**[コピー/貼り付け (Samsung KNOX のみ)]** - デバイスでコピー/貼り付け機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-108">**Copy and paste (Samsung KNOX only)** - Allows copy and paste functions on the device.</span></span>
- <span data-ttu-id="a0341-109">**[アプリ間のクリップボードの共有 (Samsung KNOX のみ)]** - クリップボードを使用してアプリ間でコピー/貼り付けを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-109">**Clipboard sharing between apps (Samsung KNOX only)** - Allows use of the clipboard to copy and paste between apps.</span></span>
- <span data-ttu-id="a0341-110">**[診断データの送信 (Samsung KNOX のみ)]** - ユーザーがデバイスから診断データを送信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-110">**Diagnostic data submission (Samsung KNOX only)** - Stops the user from submitting diagnostic data from the device.</span></span>
- <span data-ttu-id="a0341-111">**[工場出荷時の設定へのリセット (Samsung KNOX のみ)]** - ユーザーがデバイスを出荷時の設定に戻せるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-111">**Factory reset (Samsung KNOX only)** - Allows the user to perform a factory reset on the device.</span></span>
- <span data-ttu-id="a0341-112">**[位置情報 (Samsung KNOX のみ)]** - デバイスで位置情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-112">**Geolocation (Samsung KNOX only)** - Allows the device to utilize location information.</span></span>
- <span data-ttu-id="a0341-113">**[電源オフ (Samsung KNOX のみ)]** - ユーザーがデバイスの電源を切ることを許可します。</span><span class="sxs-lookup"><span data-stu-id="a0341-113">**Power off (Samsung KNOX only)** - Allows the user to power off the device.</span></span><br><span data-ttu-id="a0341-114">無効にすると、**デバイスがワイプされるまでのサインイン失敗回数**を設定できません。</span><span class="sxs-lookup"><span data-stu-id="a0341-114">If disabled, **Number of sign-in failures before wiping device** cannot be set.</span></span>
- <span data-ttu-id="a0341-115">**[画面キャプチャ (Samsung KNOX のみ)]** - ユーザーが画面のコンテンツを画像としてキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-115">**Screen capture (Samsung KNOX only)** - Lets the user capture the screen contents as an image.</span></span>
- <span data-ttu-id="a0341-116">**[音声アシスタント (Samsung KNOX のみ)]** - デバイスで音声アシスタント ソフトウェアを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-116">**Voice assistant (Samsung KNOX only)** - Allows the use of voice assistant software on the device.</span></span>
- <span data-ttu-id="a0341-117">**[YouTube (Samsung KNOX のみ)]** - デバイスで YouTube アプリを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-117">**YouTube (Samsung KNOX only)** - Allows the use of the YouTube app on the device.</span></span>
- <span data-ttu-id="a0341-118">**[共有デバイス] (Samsung KNOX のみ)** - 管理対象の Samsung KNOX Standard デバイスを共有デバイスとして構成します。</span><span class="sxs-lookup"><span data-stu-id="a0341-118">**Shared devices (Samsung KNOX only)** - Configure a managed Samsung KNOX Standard device as shared.</span></span> <span data-ttu-id="a0341-119">このモードでは、エンド ユーザーは Azure AD 資格情報を使用してデバイスにサインインおよびサインアウトできます。</span><span class="sxs-lookup"><span data-stu-id="a0341-119">In this mode, end users can sign in and out of the device with their Azure AD credentials.</span></span> <span data-ttu-id="a0341-120">使用中かどうかに関係なく、デバイスは常に管理対象です。</span><span class="sxs-lookup"><span data-stu-id="a0341-120">The device remains managed whether it’s in use or not.</span></span><br><span data-ttu-id="a0341-121">この機能を SCEP 証明書プロファイルと組み合わせて使用する場合、エンド ユーザーは、すべてのユーザーに対して同じアプリのセットを持つ一方、ユーザー独自の SCEP ユーザー証明書も持つデバイスを共有することができます。ユーザーがサインアウトすると、すべてのアプリ データがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="a0341-121">When used in conjunction with a SCEP certificate profile, this feature allows end users to share a device with the same set of apps for all users, but with their own SCEP user cert.  When users sign out, all app data is cleared.</span></span>  <span data-ttu-id="a0341-122">この機能は、LOB アプリのみに限定されています。</span><span class="sxs-lookup"><span data-stu-id="a0341-122">This feature is limited to LOB apps only.</span></span>
- <span data-ttu-id="a0341-123">**日付と時刻の変更 (Samsung KNOX) をブロック**- ユーザーが日付を変更することを防止し、時刻のデバイスに設定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-123">**Block date and time changes (Samsung KNOX)** - Prevent the user from changing the date and time settings on the device.</span></span> 

## <a name="password"></a><span data-ttu-id="a0341-124">パスワード</span><span class="sxs-lookup"><span data-stu-id="a0341-124">Password</span></span>

- <span data-ttu-id="a0341-125">**[パスワード]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。|はい|はい|</span><span class="sxs-lookup"><span data-stu-id="a0341-125">**Password** - Require the end user to enter a password to access the device.|Yes|Yes|</span></span>
- <span data-ttu-id="a0341-126">**[パスワードの最小文字数]** - ユーザーが構成する必要があるパスワードの最小文字数 (4 ～ 16 文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0341-126">**Minimum password length** - Enter the minimum length of password a user must configure (between 4 and 16 characters).</span></span>
- <span data-ttu-id="a0341-127">**[画面がロックされるまでの非アクティブな最長時間 (分)]** - デバイスの非アクティブ状態が許容される時間 (分) を指定します。この時間を超えると、デバイスは自動的にロックされます。</span><span class="sxs-lookup"><span data-stu-id="a0341-127">**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes of inactivity before the device automatically locks.</span></span>
- <span data-ttu-id="a0341-128">**[デバイスがワイプされるまでのサインイン失敗回数]** - デバイスをワイプするまでのサインイン エラーの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-128">**Number of sign-in failures before wiping device** - Specifies the number of sign-in failures to allow before the device is wiped.</span></span>
- <span data-ttu-id="a0341-129">**[パスワードの有効期限 (日数)]** - デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-129">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
-  <span data-ttu-id="a0341-130">**[必要なパスワードの種類]** - 必要なレベルのパスワードの複雑さと、生体認証デバイスを使用できるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0341-130">**Required password type** - Specifies the required password complexity level, and whether biometric devices can be used.</span></span> <span data-ttu-id="a0341-131">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="a0341-131">Choose from:</span></span>
    - <span data-ttu-id="a0341-132">**デバイスの既定**</span><span class="sxs-lookup"><span data-stu-id="a0341-132">**Device default**</span></span>
    - <span data-ttu-id="a0341-133">**低レベルのバイオメトリック セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="a0341-133">**Low security biometric**</span></span>
    - <span data-ttu-id="a0341-134">**最小数の数字**</span><span class="sxs-lookup"><span data-stu-id="a0341-134">**At least numeric**</span></span>
    - <span data-ttu-id="a0341-135">**[数値複素数]** - "1111" のような繰り返しの番号や、"1234" のような連続した番号は許可されません<sup>1</sup>。</span><span class="sxs-lookup"><span data-stu-id="a0341-135">**Numeric complex** - Repeating, or consecutive numbers like '1111' or '1234' are not allowed<sup>1</sup></span></span>
    - <span data-ttu-id="a0341-136">**最小数の英字**</span><span class="sxs-lookup"><span data-stu-id="a0341-136">**At least alphabetic**</span></span>
    - <span data-ttu-id="a0341-137">**最小数の英数字**</span><span class="sxs-lookup"><span data-stu-id="a0341-137">**At least alphanumeric**</span></span>
    - <span data-ttu-id="a0341-138">**英数字と記号を使用する**</span><span class="sxs-lookup"><span data-stu-id="a0341-138">**At least alphanumeric with symbols**</span></span>
- <span data-ttu-id="a0341-139">**[Prevent reuse of previous passwords (前のパスワードを再利用できないようにする)]** - エンド ユーザーが以前に使用したことのあるパスワードを作成できないようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-139">**Prevent reuse of previous passwords** - Stops the end user from creating a password they have used before.</span></span>
- <span data-ttu-id="a0341-140">**[指紋によるロック解除 (Samsung KNOX のみ)]** - 指紋を使用して、サポートされているデバイスのロックを解除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-140">**Fingerprint unlock (Samsung KNOX only)** - Allows the use of a fingerprint to unlock supported devices.</span></span>
- <span data-ttu-id="a0341-141">**[Smart Lock などの信頼できるエージェント]** - 互換性のある Android デバイス (Samsung KNOX Standard 5.0 以降) で Smart Lock 機能を制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-141">**Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible Android devices (Samsung KNOX Standard 5.0 and later).</span></span> <span data-ttu-id="a0341-142">信頼エージェントとも呼ばれるこの電話機能では、信頼できる場所にある場合、デバイスのロック画面のパスワードを無効化またはバイパスすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0341-142">This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location.</span></span> <span data-ttu-id="a0341-143">たとえば、デバイスが特定の Bluetooth デバイスに接続されているときや、NFC タグの近くにある場合にこれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0341-143">For example, this could be used when the device is connected to a specific Bluetooth device, or when it's close to an NFC tag.</span></span> <span data-ttu-id="a0341-144">この設定を使用して、ユーザーが SmartLock を構成することを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="a0341-144">You can use this setting to prevent users from configuring Smart Lock.</span></span>
- <span data-ttu-id="a0341-145">**[暗号化]** - デバイス上のファイルを暗号化することを要求します。</span><span class="sxs-lookup"><span data-stu-id="a0341-145">**Encryption** - Requires that files on the device are encrypted.</span></span>

<span data-ttu-id="a0341-146"><sup>1</sup> デバイス上のポータル サイト アプリを最新バージョンに更新してから、デバイスにこの設定を割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a0341-146"><sup>1</sup> Before you assign this setting to devices, ensure to update the Company Portal app to the latest version on those devices.</span></span>

<span data-ttu-id="a0341-147">**数値複素数**の設定を構成し、この設定を Android 5.0 よりも前のバージョンを実行するデバイスに割り当てると、次の動作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-147">If you configure the **Numeric complex** setting, and then assign it to a device running a version of Android earlier than 5.0, the following behavior applies.</span></span>
- <span data-ttu-id="a0341-148">ポータル サイト アプリで 1704 よりも前のバージョンが実行されている場合は、デバイスに PIN ポリシーが適用されず、Azure Portal でエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-148">If the Company Portal app is running a version earlier than 1704, no PIN policy is applied to the device and an error is displayed in the Azure portal.</span></span>
- <span data-ttu-id="a0341-149">ポータル サイト アプリが 1704 以降のバージョンを実行している場合は、単純な PIN のみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-149">If the Company Portal app runs the 1704 version or later, only a simple PIN can be applied.</span></span> <span data-ttu-id="a0341-150">Android 5.0 よりも前のバージョンでは、この設定はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a0341-150">Versions of Android earlier than 5.0 do not support this setting.</span></span> <span data-ttu-id="a0341-151">Azure Portal でエラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a0341-151">No error is displayed in the Azure portal.</span></span>


## <a name="google-play-store"></a><span data-ttu-id="a0341-152">Google Play ストア</span><span class="sxs-lookup"><span data-stu-id="a0341-152">Google Play Store</span></span>

- <span data-ttu-id="a0341-153">**[Google Play ストア (Samsung KNOX のみ)]** - ユーザーがデバイス上で Google Play ストアにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-153">**Google Play store (Samsung KNOX only)** - Allows the user to access the Google Play store on the device.</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="a0341-154">制限付きアプリ</span><span class="sxs-lookup"><span data-stu-id="a0341-154">Restricted apps</span></span>

<span data-ttu-id="a0341-155">制限付きアプリの一覧では、Android デバイスと Samsung KNOX Standard デバイスの両方に、次の一覧のいずれか 1 つを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0341-155">In the restricted apps list, you can configure one of the following lists for both Android, and Samsung KNOX Standard devices:</span></span>

<span data-ttu-id="a0341-156">**[禁止されているアプリ]** の一覧 - ユーザーがインストールおよび実行した場合に報告されるアプリ (Intune で管理されていない) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a0341-156">A **Prohibited apps** list - List the apps (not managed by Intune) that will be reported if users install and run.</span></span>
<span data-ttu-id="a0341-157">**[承認済みアプリ]** の一覧 - ユーザーによるインストールが許可されているアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a0341-157">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="a0341-158">準拠性を維持するため、ユーザーは他のアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="a0341-158">To remain compliant, users must not install other apps.</span></span> <span data-ttu-id="a0341-159">管理対象アプリは Intune で自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-159">Apps that are managed by Intune are automatically allowed.</span></span>
<span data-ttu-id="a0341-160">制限付きアプリの設定を含むデバイス プロファイルは、ユーザーのグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0341-160">Device profiles that contain restricted app settings must be assigned to groups of users.</span></span>

<span data-ttu-id="a0341-161">この一覧を構成するには、**[追加]** をクリックし、任意の名前、アプリの発行元 (省略可能)、アプリ ストアでのアプリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-161">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a><span data-ttu-id="a0341-162">ストアにおけるアプリの URL を指定する方法</span><span class="sxs-lookup"><span data-stu-id="a0341-162">How to specify the URL to an app in the store</span></span>

<span data-ttu-id="a0341-163">準拠アプリと非準拠アプリの一覧でアプリの URL を指定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0341-163">To specify an app URL in the compliant and noncompliant apps list, take the following steps:</span></span>

<span data-ttu-id="a0341-164">[Google Play の [アプリ] セクション](https://play.google.com/store/apps)で、使用するアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="a0341-164">In the [Apps section of Google Play](https://play.google.com/store/apps), search for the app you want to use.</span></span>

<span data-ttu-id="a0341-165">アプリのインストール ページを開き、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a0341-165">Open the installation page for the app, and then copy the URL to the clipboard.</span></span> <span data-ttu-id="a0341-166">準拠アプリおよび非準拠アプリの一覧でこの URL を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0341-166">You can now use this URL in either the compliant or noncompliant apps list.</span></span>

<span data-ttu-id="a0341-167">例: Google Play で Microsoft Office Mobile を検索します。</span><span class="sxs-lookup"><span data-stu-id="a0341-167">Example: Search Google Play for Microsoft Office Mobile.</span></span> <span data-ttu-id="a0341-168">**https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** という URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0341-168">Use the URL: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.</span></span>

### <a name="additional-options"></a><span data-ttu-id="a0341-169">追加オプション</span><span class="sxs-lookup"><span data-stu-id="a0341-169">Additional options</span></span>

<span data-ttu-id="a0341-170">**[インポート]** をクリックして、csv ファイルから一覧を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0341-170">You can also click **Import** to get the list from a csv file.</span></span> <span data-ttu-id="a0341-171">"<*アプリ URL*>, <*アプリ名*>, <*アプリの発行元*>" の形式を使用するか、または同じ形式で制限付きアプリの一覧の内容を含む csv ファイルで **[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0341-171">Use the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** in the csv file containing the contents of the restricted apps list in the same format.</span></span>      

## <a name="browser"></a><span data-ttu-id="a0341-172">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="a0341-172">Browser</span></span>

- <span data-ttu-id="a0341-173">**[Web ブラウザー (Samsung KNOX のみ)]** - デバイスの既定の Web ブラウザーを使用できるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-173">**Web browser (Samsung KNOX only)** - Specifies whether the device's default web browser can be used.</span></span>
- <span data-ttu-id="a0341-174">**[オートフィル (Samsung KNOX のみ)]** - Web ブラウザーのオートフィル機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-174">**Autofill (Samsung KNOX only)** - Allows the autofill function of the web browser to be used.</span></span>
- <span data-ttu-id="a0341-175">**[Cookie (Samsung KNOX のみ)]** - デバイスの Web ブラウザーで Cookie を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-175">**Cookies (Samsung KNOX only)** - Allows the device web browser to use cookies.</span></span>
- <span data-ttu-id="a0341-176">**[JavaScript (Samsung KNOX のみ)]** - デバイスの Web ブラウザーで Java スクリプトを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-176">**Javascript (Samsung KNOX only)** - Allows the device web browser to run Java scripts.</span></span>
- <span data-ttu-id="a0341-177">**[ポップアップ (Samsung KNOX のみ)]** - Web ブラウザーでポップアップ ブロックを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-177">**Pop-ups (Samsung KNOX only)** - Allows the use of the pop-up blocker in the web browser.</span></span>

## <a name="allow-or-block-apps"></a><span data-ttu-id="a0341-178">アプリの許可またはブロック</span><span class="sxs-lookup"><span data-stu-id="a0341-178">Allow or Block apps</span></span>

<span data-ttu-id="a0341-179">これらの設定を使用して、Samsung KNOX Standard のみが動作するデバイス上でインストールまたは起動できるアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-179">These settings can be used to specify apps that can be installed, or launched on devices that run Samsung KNOX Standard only.</span></span>
<span data-ttu-id="a0341-180">さらに、デバイスのユーザーに対して非表示にするインストール済みアプリを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0341-180">Additionally, you can also specify installed apps that will be hidden from the device user.</span></span> <span data-ttu-id="a0341-181">ユーザーは、これらのアプリを実行できません。</span><span class="sxs-lookup"><span data-stu-id="a0341-181">Users cannot run these apps.</span></span>

- <span data-ttu-id="a0341-182">**[インストールの許可されたアプリ (Samsung KNOX Standard のみ)]**</span><span class="sxs-lookup"><span data-stu-id="a0341-182">**Apps allowed to be installed (Samsung KNOX Standard only)**</span></span>
- <span data-ttu-id="a0341-183">**[起動がブロックされたアプリ (Samsung KNOX Standard のみ)]**</span><span class="sxs-lookup"><span data-stu-id="a0341-183">**Apps blocked from launching (Samsung KNOX Standard only)**</span></span>
- <span data-ttu-id="a0341-184">**[ユーザーに対して非表示のアプリ (Samsung KNOX Standard のみ)]**</span><span class="sxs-lookup"><span data-stu-id="a0341-184">**Apps hidden from user (Samsung KNOX Standard only)**</span></span>

<span data-ttu-id="a0341-185">各設定に対して、次のいずれかを使ってアプリの一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="a0341-185">For each setting, configure a list of apps using one of the following:</span></span>

- <span data-ttu-id="a0341-186">**[パッケージ名ごとにアプリを追加]** - 主に基幹業務アプリの場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-186">**Add apps by package name** - Primarily used for line of business apps.</span></span> <span data-ttu-id="a0341-187">アプリ名とアプリ パッケージ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0341-187">Enter the app name, and the name of the app package.</span></span>
- <span data-ttu-id="a0341-188">**[URL ごとにアプリを追加]** - アプリ名と、Google Play ストアの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0341-188">**Add apps by URL** - Enter the app name, and its URL in the Google Play store.</span></span>
- <span data-ttu-id="a0341-189">**[管理対象アプリを追加]** - Intune で管理するアプリの一覧から、対象のアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="a0341-189">**Add managed apps** - From the list of apps you manage with Intune, select the app you require.</span></span>

## <a name="cloud-and-storage"></a><span data-ttu-id="a0341-190">クラウドとストレージ</span><span class="sxs-lookup"><span data-stu-id="a0341-190">Cloud and Storage</span></span>

- <span data-ttu-id="a0341-191">**[Google バックアップ (Samsung KNOX のみ)]** - Google へのバックアップを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-191">**Google backup (Samsung KNOX only)** - Allows the use of Google backup.</span></span>
- <span data-ttu-id="a0341-192">**[Google アカウントの自動同期 (Samsung KNOX のみ)]** - Google アカウントの設定を自動的に同期できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-192">**Google account auto sync (Samsung KNOX only)** - Allows Google account settings to be automatically synchronized.</span></span>
- <span data-ttu-id="a0341-193">**[リムーバブル記憶域 (Samsung KNOX のみ)]** - デバイスで SD カードなどのリムーバブル記憶域を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-193">**Removable storage (Samsung KNOX only)** - Allows the device to use removable storage, like an SD card.</span></span>
- <span data-ttu-id="a0341-194">**[メモリ カードでの暗号化 (Samsung KNOX のみ)]** - デバイスのメモリ カードを暗号化する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0341-194">**Encryption on storage cards (Samsung KNOX only)** - Specifies whether the device storage card must be encrypted.</span></span>

## <a name="cellular-and-connectivity"></a><span data-ttu-id="a0341-195">携帯ネットワークと接続性</span><span class="sxs-lookup"><span data-stu-id="a0341-195">Cellular and Connectivity</span></span>

- <span data-ttu-id="a0341-196">**[データ ローミング (Samsung KNOX のみ)]** - デバイスが移動体通信ネットワーク上にある場合はデータ ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-196">**Data roaming (Samsung KNOX only)** - Allows data roaming when the device is on a cellular network).</span></span>
- <span data-ttu-id="a0341-197">**[SMS/MMS メッセージング (Samsung KNOX のみ)]** - デバイスで SMS と MMS メッセージングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-197">**SMS/MMS messaging (Samsung KNOX only)** - Allows the use of SMS and MMS messaging on the device.</span></span>
- <span data-ttu-id="a0341-198">**[音声ダイヤル (Samsung KNOX のみ)]** - デバイスの音声ダイヤル機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a0341-198">**Voice dialing (Samsung KNOX only)** - Enables or disables the voice dialing feature on the device.</span></span>
- <span data-ttu-id="a0341-199">**[音声通話ローミング (Samsung KNOX のみ)]** - デバイスが移動体通信ネットワーク上にある場合は音声通話ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-199">**Voice roaming (Samsung KNOX only)** - Allows voice roaming when the device is on a cellular network.</span></span>
- <span data-ttu-id="a0341-200">**[Bluetooth (Samsung KNOX のみ)]** - デバイスで Bluetooth を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-200">**Bluetooth (Samsung KNOX only)** - Allows the use of Bluetooth on the device.</span></span>
- <span data-ttu-id="a0341-201">**[NFC (Samsung KNOX のみ)]** - サポートされているデバイスで、近距離無線通信を使用する操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="a0341-201">**NFC (Samsung KNOX only)** - Allows operations that use near field communication on supported devices.</span></span>
- <span data-ttu-id="a0341-202">**[Wi-Fi (Samsung KNOX のみ)]** - デバイスで Wi-Fi 機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-202">**Wi-Fi (Samsung KNOX only)** - Allows the use of the Wi-Fi capabilities of the device.</span></span>
- <span data-ttu-id="a0341-203">**[Wi-Fi テザリング (Samsung KNOX のみ)]** - デバイスで Wi-Fi テザリングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a0341-203">**Wi-Fi tethering (Samsung KNOX only)** - Allows the use of Wi-Fi tethering on the device.</span></span>

## <a name="kiosk"></a><span data-ttu-id="a0341-204">キオスク</span><span class="sxs-lookup"><span data-stu-id="a0341-204">Kiosk</span></span>

<span data-ttu-id="a0341-205">キオスクの設定は、Samsung KNOX Standard デバイスのみの、Intune を使って管理するアプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0341-205">Kiosk settings apply only to Samsung KNOX Standard devices, and only to apps you manage using Intune.</span></span>

- <span data-ttu-id="a0341-206">**[管理対象アプリを選びます]** - 次のオプションのいずれかを選び、デバイスがキオスク モードのときに実行できる管理対象アプリを 1 つ以上追加します。</span><span class="sxs-lookup"><span data-stu-id="a0341-206">**Select a managed app** - Choose one of the following options to add one or more managed apps that can run when the device is in kiosk mode.</span></span> <span data-ttu-id="a0341-207">他のアプリはデバイスでの実行が許可されません。</span><span class="sxs-lookup"><span data-stu-id="a0341-207">No other apps are allowed to run on the device.</span></span>
    - <span data-ttu-id="a0341-208">**パッケージ名ごとにアプリを追加**</span><span class="sxs-lookup"><span data-stu-id="a0341-208">**Add apps by package name**</span></span>
    - <span data-ttu-id="a0341-209">**URL ごとにアプリを追加**</span><span class="sxs-lookup"><span data-stu-id="a0341-209">**Add apps by URL**</span></span>
    - <span data-ttu-id="a0341-210">**管理対象アプリを追加**</span><span class="sxs-lookup"><span data-stu-id="a0341-210">**Add managed apps**.</span></span>
- <span data-ttu-id="a0341-211">**[画面スリープ ボタン]** - デバイスの画面スリープ ウェイク ボタンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a0341-211">**Screen sleep button** - Enables or disables the screen sleep wake button on the device.</span></span>
- <span data-ttu-id="a0341-212">**ボリューム ボタン** - デバイスのボリューム ボタンの使用を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a0341-212">**Volume buttons** - Enables or disables the use of the volume buttons on the device.</span></span>


## <a name="next-steps"></a><span data-ttu-id="a0341-213">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a0341-213">Next steps</span></span>

<span data-ttu-id="a0341-214">引き続き「[デバイスの制限設定を構成する方法](device-restrictions-configure.md)」の手順を使用して作成し、デバイスの制限プロファイルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a0341-214">Continue using the instructions in [How to configure device restriction settings](device-restrictions-configure.md) to create, then assign the device restriction profile.</span></span>
