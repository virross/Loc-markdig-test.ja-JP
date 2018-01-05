---
title: "Windows 10 用の Intune Endpoint Protection 設定"
titlesuffix: Azure portal
description: "Windows 10 デバイスで Endpoint Protection 設定 ( BitLocker など) を制御するのに使用できる Intune 設定について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 66d13a5a5d4b74cc70696239514875fe0092a164
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a><span data-ttu-id="546c6-103">Microsoft Intune での Windows 10 以降用の Endpoint Protection 設定</span><span class="sxs-lookup"><span data-stu-id="546c6-103">Endpoint protection settings for Windows 10 and later in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="546c6-104">Endpoint Protection プロファイルを使用すると、Windows 10 デバイス上で BitLocker や Windows Defender のようなセキュリティ機能を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="546c6-104">The endpoint protection profile let you control security features on Windows 10 devices, like BitLocker, and Windows Defender.</span></span>

<span data-ttu-id="546c6-105">このトピックでは、Endpoint Protection プロファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="546c6-105">Use the information in this topic to learn how to create endpoint protection profiles.</span></span>

> [!Note]
> <span data-ttu-id="546c6-106">これらの設定は、Windows 10 の Home および Professional Edition ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="546c6-106">These settings are not supported on the Home and Professional editions of Windows 10.</span></span>

## <a name="create-an-endpoint-protection-profile"></a><span data-ttu-id="546c6-107">Endpoint Protection プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="546c6-107">Create an endpoint protection profile</span></span>

1. <span data-ttu-id="546c6-108">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="546c6-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="546c6-109">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="546c6-110">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-110">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="546c6-111">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="546c6-112">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="546c6-113">**[プロファイルを作成します]** ブレードで、デバイスの機能プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="546c6-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.</span></span>
5. <span data-ttu-id="546c6-114">**[プラットフォーム]** ドロップダウン リストで、**[Windows 10 以降]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-114">From the **Platform** drop-down list, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="546c6-115">**[プロファイルの種類]** ドロップダウン リストで、**[Endpoint Protection]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-115">From the **Profile type** drop-down list, choose **Endpoint protection**.</span></span>
7. <span data-ttu-id="546c6-116">**[Windows 暗号化]** ブレードで、目的の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-116">On the **Windows encryption** blade, configure the settings you want.</span></span> <span data-ttu-id="546c6-117">各設定の機能については、このトピックで詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="546c6-117">Use the details in this topic to help you understand what each setting does.</span></span> <span data-ttu-id="546c6-118">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-118">When you are finished, choose **OK**.</span></span>
8. <span data-ttu-id="546c6-119">**[プロファイルの作成]** ブレードに進み、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-119">Go back to the **Create Profile** blade, and choose **Create**.</span></span>

<span data-ttu-id="546c6-120">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="546c6-120">The profile is created and appears on the profiles list blade.</span></span>

## <a name="windows-defender-smartscreen-settings"></a><span data-ttu-id="546c6-121">Windows Defender SmartScreen 設定</span><span class="sxs-lookup"><span data-stu-id="546c6-121">Windows Defender SmartScreen settings</span></span>

- <span data-ttu-id="546c6-122">**アプリとファイルの SmartScreen** - ファイルやアプリの実行のために Windows SmartScreen を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-122">**SmartScreen for apps and files** - Enable Windows SmartScreen for file execution, and running apps.</span></span>
- <span data-ttu-id="546c6-123">**未確認ファイルの実行** - Windows SmartScreen で検証されていないファイルをエンド ユーザーが実行する行為を禁止します。</span><span class="sxs-lookup"><span data-stu-id="546c6-123">**Unverified files execution** - Block the end user from running files that have not been verified by Windows SmartScreen.</span></span>

## <a name="windows-encryption-settings"></a><span data-ttu-id="546c6-124">Windows 暗号化設定</span><span class="sxs-lookup"><span data-stu-id="546c6-124">Windows encryption settings</span></span>

### <a name="windows-settings"></a><span data-ttu-id="546c6-125">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="546c6-125">Windows Settings</span></span>

- <span data-ttu-id="546c6-126">**デバイスの暗号化が必須 (デスクトップのみ)** - 有効にすると、デバイスの暗号化を有効にするように求められます。</span><span class="sxs-lookup"><span data-stu-id="546c6-126">**Require devices to be encrypted (Desktop only)** - If enabled, users are prompted to enable device encryption.</span></span> <span data-ttu-id="546c6-127">さらに、別のプロバイダーによる暗号化が有効になっていないことを確認するように求められます。</span><span class="sxs-lookup"><span data-stu-id="546c6-127">Additionally, they are asked to confirm that encryption from another provider has not been enabled.</span></span> <span data-ttu-id="546c6-128">別の暗号化方式がアクティブになっている場合に Windows の暗号化を有効にすると、デバイスが不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="546c6-128">If Windows encryption is turned on while another encryption method is active, the device might become unstable.</span></span>
- <span data-ttu-id="546c6-129">**メモリ カードの暗号化が必須 (モバイルのみ)** - デバイスで使用するリムーバブル メモリ カードを暗号化するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-129">**Require Storage Card to be encrypted (mobile only)** - Enable this setting to encrypt any removable storage cards used by the device.</span></span>


### <a name="bitlocker-base-settings"></a><span data-ttu-id="546c6-130">BitLocker の基本設定</span><span class="sxs-lookup"><span data-stu-id="546c6-130">BitLocker base settings</span></span>

- <span data-ttu-id="546c6-131">**暗号化方法の構成** - オペレーティング システム、データ、およびリムーバブル ドライブ用の暗号化アルゴリズムを構成するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-131">**Configure encryption methods** - Enable this setting to configure encryption algorithms for operating system, data, and removable drives.</span></span>
    - <span data-ttu-id="546c6-132">**オペレーティング システム ドライブの暗号化** - オペレーティング システム ドライブ用の暗号化の方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-132">**Encryption for operating system drives** - Choose the encryption method for operating system drives.</span></span> <span data-ttu-id="546c6-133">XTS-AES アルゴリズムの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="546c6-133">We recommend you use the XTS-AES algorithm.</span></span>
    - <span data-ttu-id="546c6-134">**固定データ ドライブの暗号化** - 固定 (組み込み) のデータ ドライブ用の暗号化の方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-134">**Encryption for fixed data-drives** - Choose the encryption method for fixed (built-in) data drives.</span></span> <span data-ttu-id="546c6-135">XTS-AES アルゴリズムの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="546c6-135">We recommend you use the XTS-AES algorithm.</span></span>
    - <span data-ttu-id="546c6-136">**リムーバブル データドライブの暗号化** - リムーバブル データ ドライブ用の暗号化の方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-136">**Encryption for removable data-drives** - Choose the encryption method for removable data drives.</span></span> <span data-ttu-id="546c6-137">Windows 10 を実行していないデバイスでリムーバブル ドライブを使用する場合は、AES-CBC アルゴリズムの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="546c6-137">If the removable drive is used with devices that are not running Windows 10, we recommend you use the AES-CBC algorithm.</span></span>


### <a name="bitlocker-os-drive-settings"></a><span data-ttu-id="546c6-138">BitLocker OS ドライブ設定</span><span class="sxs-lookup"><span data-stu-id="546c6-138">BitLocker OS drive settings</span></span>

- <span data-ttu-id="546c6-139">**スタートアップ時に追加の認証を要求する** -</span><span class="sxs-lookup"><span data-stu-id="546c6-139">**Require additional authentication at startup** -</span></span>
    - <span data-ttu-id="546c6-140">**互換性のない TPM チップでの BitLocker** -</span><span class="sxs-lookup"><span data-stu-id="546c6-140">**BitLocker with non-compatible TPM chip** -</span></span>
    - <span data-ttu-id="546c6-141">**TPM スタートアップ** - TPM チップを許可するか、許可しないか、または必須とするかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-141">**TPM startup** - Configure whether the TPM chip is allowed, not allowed, or required.</span></span>
    - <span data-ttu-id="546c6-142">**TPM スタートアップ PIN** - TPM チップ搭載のスタートアップ PIN の使用を許可するか、許可しないか、または必須とするかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-142">**TPM startup PIN** - Configure whether using a startup PIN with the TPM chip is allowed, not allowed, or required.</span></span>
    - <span data-ttu-id="546c6-143">**TPM スタートアップ キー** - TPM チップ搭載のスタートアップ キーの使用を許可するか、許可しないか、または必須とするかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-143">**TPM startup key** - Configure whether using a startup key with the TPM chip is allowed, not allowed, or required.</span></span>
    - <span data-ttu-id="546c6-144">**TPM スタートアップ キーと PIN** - TPM チップ搭載のスタートアップ キーおよび PIN の使用を許可するか、許可しないか、または必須とするかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-144">**TPM startup key and PIN** - Configure whether using a startup key and PIN with the TPM chip is allowed, not allowed, or required.</span></span>
- <span data-ttu-id="546c6-145">**最小 PIN サイズ** - TPM スタートアップ PIN の最小長を構成するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-145">**Minimum PIN Length** - Enable this setting to configure a minimum length for the TPM startup PIN.</span></span>
    - <span data-ttu-id="546c6-146">**最小文字数** - スタートアップ PIN に必要な文字数を入力します。有効な値は **4**-**20** の範囲となります。</span><span class="sxs-lookup"><span data-stu-id="546c6-146">**Minimum characters** - Enter the number of characters required for the startup PIN from **4**-**20**.</span></span>
- <span data-ttu-id="546c6-147">**OS ドライブの回復を有効にする** - 必要なスタートアップ情報が利用できない場合に BitLocker で保護されたオペレーティング システム ドライブを回復する方法を制御するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-147">**Enable OS drive recovery** - Enable this setting to control how BitLocker-protected operating system drives are recovered when the required start-up information is not available.</span></span>
    - <span data-ttu-id="546c6-148">**証明書ベースのデータ回復エージェント** - BitLocker で保護されているオペレーティング システム ドライブでデータ回復エージェントを使用できるようにする場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-148">**Certificate-based data recovery agent** - Enable this setting if you want data recovery agents to be able to be used with BitLocker-protected operating system drives.</span></span>
    - <span data-ttu-id="546c6-149">**ユーザーによる回復パスワードの作成** - 48 桁の回復パスワードの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-149">**User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.</span></span>
    - <span data-ttu-id="546c6-150">**ユーザーによる回復キーの作成** - 256 ビットの回復キーの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-150">**User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.</span></span>
    - <span data-ttu-id="546c6-151">**BitLocker セットアップ ウィザードで回復オプションを非表示にする** - ユーザーが BitLocker を有効にした場合に、回復オプションをユーザーに表示しない、または回復オプションの変更をユーザーに許可しないためには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-151">**Hide recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.</span></span>
    - <span data-ttu-id="546c6-152">**BitLocker 回復情報を AD DS に保存する** - Active Directory の BitLocker 回復情報の保存を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-152">**Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.</span></span>
    - <span data-ttu-id="546c6-153">**AD DS への BitLocker 回復情報の保存を構成する** - BitLocker 回復情報のどの部分を Active Directory に格納するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-153">**Configure storage of BitLocker recovery Information to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory.</span></span> <span data-ttu-id="546c6-154">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-154">Choose from:</span></span>
        - <span data-ttu-id="546c6-155">**回復パスワードとキー パッケージをバックアップする**</span><span class="sxs-lookup"><span data-stu-id="546c6-155">**Backup recovery passwords and key packages**</span></span>
        - <span data-ttu-id="546c6-156">**回復パスワードのみバックアップする**</span><span class="sxs-lookup"><span data-stu-id="546c6-156">**Backup recovery passwords only**</span></span>
    - <span data-ttu-id="546c6-157">**BitLocker を有効にする前に回復情報が AD DS に保存される必要がある** - デバイスがドメインに不参加であり、かつ BitLocker 回復情報が Active Directory に正常に保存されていない場合、ユーザーが BitLocker を有効にするのを阻止するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-157">**Require recovery information to be stored in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information is successfully stored in Active Directory.</span></span>
- <span data-ttu-id="546c6-158">**プリブート回復メッセージと URL を有効にする** - ブート前のキー回復画面に表示されるメッセージと URL を構成するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-158">**Enable pre-boot recovery message and URL** - Enable this setting to configure the message and URL that are displayed on the pre-boot key recovery screen.</span></span>
    - <span data-ttu-id="546c6-159">**プリブート回復メッセージ** - プリブート回復メッセージをユーザーに表示する方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-159">**Pre-boot recovery message** - Configure how the pre-boot recovery message displays to users.</span></span> <span data-ttu-id="546c6-160">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-160">Choose from:</span></span>
        - <span data-ttu-id="546c6-161">**既定の回復メッセージと URL を使用する**</span><span class="sxs-lookup"><span data-stu-id="546c6-161">**Use default recovery message and URL**</span></span>
        - <span data-ttu-id="546c6-162">**空の回復メッセージと URL を使用する**</span><span class="sxs-lookup"><span data-stu-id="546c6-162">**Use empty recovery message and URL**</span></span>
        - <span data-ttu-id="546c6-163">**カスタム回復メッセージを使用する**</span><span class="sxs-lookup"><span data-stu-id="546c6-163">**Use custom recovery message**</span></span>
        - <span data-ttu-id="546c6-164">**カスタム回復 URL を使用する**</span><span class="sxs-lookup"><span data-stu-id="546c6-164">**Use custom recovery URL**</span></span>


### <a name="bitlocker-fixed-data-drive-settings"></a><span data-ttu-id="546c6-165">BitLocker 固定データ ドライブの設定</span><span class="sxs-lookup"><span data-stu-id="546c6-165">BitLocker fixed data-drive settings</span></span>

- <span data-ttu-id="546c6-166">**BitLocker によって保護されていない固定データ ドライブへの書き込みアクセスを拒否する** - 有効にした場合、固定データ ドライブまたは組み込みデータ ドライブへの書き込みを可能にするには、該当するすべてのドライブで BitLocker 保護を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="546c6-166">**Deny write access to fixed data-drive not protected by BitLocker** - If enabled, BitLocker protection must be enabled on all fixed, or built-in data drives to be able to write to them.</span></span>
- <span data-ttu-id="546c6-167">**固定ドライブの回復を有効にする** - 必要なスタートアップ情報が利用できない場合に BitLocker で保護された固定ドライブを回復する方法を制御するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-167">**Enable fixed drive recovery** - Enable this setting to control how BitLocker-protected fixed drives are recovered when the required start-up information is not available.</span></span>
    - <span data-ttu-id="546c6-168">**データ回復エージェント** - BitLocker で保護されている固定ドライブでデータ回復エージェントを使用する場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-168">**Data recovery agent** - Enable this setting if you want data recovery agents to be used with BitLocker-protected fixed drives.</span></span>
    - <span data-ttu-id="546c6-169">**ユーザーによる回復パスワードの作成** - 48 桁の回復パスワードの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-169">**User creation of recovery password** - Configure whether users are allowed, required, or not allowed to generate a 48-digit recovery password.</span></span>  
    - <span data-ttu-id="546c6-170">**ユーザーによる回復キーの作成** - 256 ビットの回復キーの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-170">**User creation of recovery key** - Configure whether users are allowed, required, or not allowed to generate a 256-bit recovery key.</span></span>
    - <span data-ttu-id="546c6-171">**BitLocker セットアップ ウィザードで回復オプションを非表示にする** - ユーザーが BitLocker を有効にした場合に、回復オプションをユーザーに表示しない、または回復オプションの変更をユーザーに許可しないためには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-171">**Hide recovery options in the BitLocker setup wizard** - Enable this setting to prevent users from seeing, or changing recovery options when they turn on BitLocker.</span></span>
    - <span data-ttu-id="546c6-172">**BitLocker 回復情報を AD DS に保存する** - Active Directory の BitLocker 回復情報の保存を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-172">**Save BitLocker recovery information to AD DS** - Enables the storage of BitLocker recovery information in Active Directory.</span></span>
    - <span data-ttu-id="546c6-173">**AD DS への BitLocker 回復情報の保存を構成する** - BitLocker 回復情報のどの部分を Active Directory に格納するかを構成します。</span><span class="sxs-lookup"><span data-stu-id="546c6-173">**Configure storage of BitLocker recovery Information to AD DS** - Configure what parts of BitLocker recovery information are stored in Active Directory.</span></span> <span data-ttu-id="546c6-174">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="546c6-174">Choose from:</span></span>
        - <span data-ttu-id="546c6-175">**回復パスワードとキー パッケージをバックアップする**</span><span class="sxs-lookup"><span data-stu-id="546c6-175">**Backup recovery passwords and key packages**</span></span>
        - <span data-ttu-id="546c6-176">**回復パスワードのみバックアップする**</span><span class="sxs-lookup"><span data-stu-id="546c6-176">**Backup recovery passwords only**</span></span>
    - <span data-ttu-id="546c6-177">**BitLocker を有効にする前に回復情報が AD DS に保存される必要がある** - デバイスがドメインに不参加であり、かつ BitLocker 回復情報が Active Directory に正常に保存されていない場合、ユーザーが BitLocker を有効にするのを阻止するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="546c6-177">**Require recovery information to be stored in AD DS before enabling BitLocker** - Enable this setting to stop users from turning on BitLocker unless the device is domain-joined, and BitLocker recovery information has been successfully stored in Active Directory.</span></span>


### <a name="bitlocker-removable-data-drive-settings"></a><span data-ttu-id="546c6-178">BitLocker リムーバブル データ ドライブの設定</span><span class="sxs-lookup"><span data-stu-id="546c6-178">BitLocker removable data-drive settings</span></span>

- <span data-ttu-id="546c6-179">**BitLocker によって保護されていないリムーバブル データ ドライブへの書き込みアクセスを拒否する** - BitLocker 暗号化がリムーバブル ストレージ ドライブに必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="546c6-179">**Deny write access to removable data-drive not protected by BitLocker** - Specify whether BitLocker encryption is required for removable storage drives.</span></span>
    - <span data-ttu-id="546c6-180">**別の組織で構成されたデバイスへの書き込みアクセスをブロックする** - 別の組織に属しているリムーバブル データ ドライブへの書き込みを可能にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="546c6-180">**Block write access to devices configured in another organization** - Specify whether removable data drives that belong to another organization can be written to.</span></span>



## <a name="next-steps"></a><span data-ttu-id="546c6-181">次の手順</span><span class="sxs-lookup"><span data-stu-id="546c6-181">Next steps</span></span>

<span data-ttu-id="546c6-182">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="546c6-182">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
