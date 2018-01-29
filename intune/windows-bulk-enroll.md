---
title: "Windows 10 の一括登録"
titlesuffix: Azure portal
description: "Microsoft Intune の一括登録パッケージを作成する"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: 941fcf1a0d1fed07576bfa0ae76b1125a5f0ebe1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="bulk-enrollment-for-windows-devices"></a><span data-ttu-id="5f611-103">Windows デバイスの一括登録</span><span class="sxs-lookup"><span data-stu-id="5f611-103">Bulk enrollment for Windows devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="5f611-104">管理者として、Azure Active Directory と Intune に多数の新しい Windows デバイスを参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="5f611-104">As an administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune.</span></span> <span data-ttu-id="5f611-105">Azure AD テナントのデバイスを一括登録するには、Windows Configuration Designer (WCD) アプリでプロビジョニング パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f611-105">To bulk enroll devices for your Azure AD tenant, you create a provisioning package with the Windows Configuration Designer (WCD) app.</span></span> <span data-ttu-id="5f611-106">企業所有のデバイスにプロビジョニング パッケージを適用すると、Azure AD テナントにデバイスを参加させ、Intune 管理用に登録します。</span><span class="sxs-lookup"><span data-stu-id="5f611-106">Applying the provisioning package to corporate-owned devices joins the devices to your Azure AD tenant and enrolls them for Intune management.</span></span> <span data-ttu-id="5f611-107">パッケージが適用されると、Azure AD ユーザーがログオンするための準備は完了です。</span><span class="sxs-lookup"><span data-stu-id="5f611-107">Once the package is applied, it's ready for your Azure AD users to log on.</span></span>

<span data-ttu-id="5f611-108">Azure AD ユーザーはこれらのデバイス上の標準ユーザーであり、割り当て済みの Intune ポリシーと必須アプリを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5f611-108">Azure AD users are standard users on these devices and receive assigned Intune policies and required apps.</span></span> <span data-ttu-id="5f611-109">この時点では、セルフ サービスとポータル サイトのシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f611-109">Self-service and Company Portal scenarios are not supported at this time.</span></span>

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a><span data-ttu-id="5f611-110">Windows デバイスの一括登録の前提条件</span><span class="sxs-lookup"><span data-stu-id="5f611-110">Prerequisites for Windows devices bulk enrollment</span></span>

<span data-ttu-id="5f611-111">Windows デバイスの一括登録には、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="5f611-111">Bulk enrollment for Window devices requires the following:</span></span>

- <span data-ttu-id="5f611-112">Windows 10 Creator Update 以降が動作しているデバイス</span><span class="sxs-lookup"><span data-stu-id="5f611-112">Devices running Windows 10 Creator update or later</span></span>
- [<span data-ttu-id="5f611-113">Windows 自動登録</span><span class="sxs-lookup"><span data-stu-id="5f611-113">Windows automatic enrollment</span></span>](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a><span data-ttu-id="5f611-114">プロビジョニング パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="5f611-114">Create a provisioning package</span></span>

1. <span data-ttu-id="5f611-115">Microsoft ストアから [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5f611-115">Download [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Microsoft Store.</span></span>
   <span data-ttu-id="5f611-116">![Windows Configuration Designer アプリ ストアのスクリーン ショットと説明のスクリーン ショット](media/bulk-enroll-store.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-116">![Screenshot of the Windows Configuration Designer app Store screenshots and description](media/bulk-enroll-store.png)</span></span>

2. <span data-ttu-id="5f611-117">**Windows Configuration Designer** アプリを開き、**[Provision desktop devices]** (デスクトップ デバイスのプロビジョニング) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f611-117">Open the **Windows Configuration Designer** app and select **Provision desktop devices**.</span></span>
   <span data-ttu-id="5f611-118">![Windows Configuration Designer アプリでデスクトップ デバイスのプロビジョニングを選択するスクリーン ショット](media/bulk-enroll-select.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-118">![Screenshot of selecting Provision desktop devices in the Windows Configuration Designer app](media/bulk-enroll-select.png)</span></span>

3. <span data-ttu-id="5f611-119">**[New project]\(新しいプロジェクト\)** ウィンドウが開くので、そこで次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f611-119">A **New project** window opens where you specify the following:</span></span>
   - <span data-ttu-id="5f611-120">**名前** - プロジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="5f611-120">**Name** - A name for your project</span></span>
   - <span data-ttu-id="5f611-121">**プロジェクト フォルダー** - プロジェクトを保存する場所</span><span class="sxs-lookup"><span data-stu-id="5f611-121">**Project folder** - Where your project will be saved</span></span>
   - <span data-ttu-id="5f611-122">**説明**-プロジェクトの説明 (オプション) ![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-name.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-122">**Description** - An optional description of the project ![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-name.png)</span></span>

4. <span data-ttu-id="5f611-123">デバイスの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f611-123">Enter a unique name for your devices.</span></span> <span data-ttu-id="5f611-124">名前には、シリアル番号 (%%SERIAL%%)、または文字のランダムなセットを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5f611-124">Names can include a serial number (%%SERIAL%%) or a random set of characters.</span></span> <span data-ttu-id="5f611-125">必要に応じて、Windows のエディションをアップグレードする場合にプロダクト キーを入力したり、デバイスを共有使用のために構成したり、事前にインストールされたソフトウェアを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f611-125">Optionally, you can also enter a product key if you are upgrading the edition of Windows, configure the device for shared use, and remove pre-installed software.</span></span>
   <span data-ttu-id="5f611-126">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-device.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-126">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-device.png)</span></span>

5. <span data-ttu-id="5f611-127">必要に応じて、初回起動時にデバイスが接続する Wi-fi ネットワークを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f611-127">Optionally, you can configure the Wi-Fi network devices connect to when they first start.</span></span>  <span data-ttu-id="5f611-128">これが構成されていない場合は、デバイスの初回起動時にワイヤード (有線) ネットワーク接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5f611-128">If this isn’t configured, a wired network connection is required when the device is first started.</span></span>
   <span data-ttu-id="5f611-129">![Windows Configuration Designer アプリで、ネットワーク SSID やネットワークの種類のオプションを含む Wi-fi を有効にするスクリーン ショット](media/bulk-enroll-network.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-129">![Screenshot of enabling Wi-Fi including Network SSID and Network type options in the Windows Configuration Designer app](media/bulk-enroll-network.png)</span></span>

6. <span data-ttu-id="5f611-130">**[Enroll in Azure AD]\(Azure AD に登録\)** を選択し、**[Bulk Token Expiry]\(一括トークンの有効期限\)** の日付を入力して、**[Get Bulk Token]\(一括トークンの取得\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f611-130">Select **Enroll in Azure AD**, enter a **Bulk Token Expiry** date, and then select **Get Bulk Token**.</span></span>
   <span data-ttu-id="5f611-131">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-account.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-131">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-account.png)</span></span>

7. <span data-ttu-id="5f611-132">一括トークンを取得するための Azure AD の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f611-132">Provide your Azure AD credentials to get a bulk token.</span></span>
   <span data-ttu-id="5f611-133">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-cred.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-133">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-cred.png)</span></span>

8. <span data-ttu-id="5f611-134">**一括トークン**が正常にフェッチされたら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f611-134">Click **Next** when **Bulk Token** is fetched successfully.</span></span>

9. <span data-ttu-id="5f611-135">必要に応じて **[アプリケーションの追加]** や **[証明書の追加]** ができます。</span><span class="sxs-lookup"><span data-stu-id="5f611-135">Optionally, you can **Add applications** and **Add certificates**.</span></span> <span data-ttu-id="5f611-136">これらのアプリと証明書がデバイスでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="5f611-136">These apps and certificates are provisioned on the device.</span></span>

10. <span data-ttu-id="5f611-137">必要に応じて、プロビジョニング パッケージをパスワードで保護できます。</span><span class="sxs-lookup"><span data-stu-id="5f611-137">Optionally, you can password protect your provisioning package.</span></span>  <span data-ttu-id="5f611-138">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f611-138">Click **Create**.</span></span>
    <span data-ttu-id="5f611-139">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-create.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-139">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-create.png)</span></span>

## <a name="provision-devices"></a><span data-ttu-id="5f611-140">デバイスのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="5f611-140">Provision devices</span></span>

1. <span data-ttu-id="5f611-141">アプリで指定した**プロジェクト フォルダー**の場所にあるプロビジョニング パッケージにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5f611-141">Access the provisioning package in the location specified in **Project folder** specified in the app.</span></span>

2. <span data-ttu-id="5f611-142">プロビジョニング パッケージをデバイスに適用する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f611-142">Choose how you’re going to apply the provisioning package to the device.</span></span>  <span data-ttu-id="5f611-143">プロビジョニング パッケージは、次のいずれかの方法でデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5f611-143">A provisioning package can be applied to a device one of the following ways:</span></span>
   - <span data-ttu-id="5f611-144">USB ドライブにプロビジョニング パッケージを置いて、USB ドライブを一括登録するデバイスに挿入し、初期セットアップ時に適用する</span><span class="sxs-lookup"><span data-stu-id="5f611-144">Place the provisioning package on a USB drive, insert the USB drive into the device you’d like to bulk enroll, and apply it during initial setup</span></span>
   - <span data-ttu-id="5f611-145">ネットワーク フォルダーにプロビジョニング パッケージを置いて、初期セットアップ後に、一括登録するデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="5f611-145">Place the provisioning package on a network folder, and apply it insert on the device you’d like to bulk enroll after initial setup</span></span>

   <span data-ttu-id="5f611-146">スプロビジョニング パッケージを適用するステップ バイ ステップの手順については、「[プロビジョニング パッケージの適用](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f611-146">For step-by-step instruction on applying a provisioning package, see [Apply a provisioning package](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).</span></span>

3. <span data-ttu-id="5f611-147">パッケージを適用したら、デバイスは 1 分後に自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="5f611-147">After you apply the package, the device will automatically restart in 1 minute.</span></span>
   <span data-ttu-id="5f611-148">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](media/bulk-enroll-add.png)</span><span class="sxs-lookup"><span data-stu-id="5f611-148">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-add.png)</span></span>

4. <span data-ttu-id="5f611-149">デバイスが再起動すると、Azure Active Directory に接続して Microsoft Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="5f611-149">When the device restarts, it connects to the Azure Active Directory and enrolls in Microsoft Intune.</span></span>

## <a name="troubleshooting-windows-bulk-enrollment"></a><span data-ttu-id="5f611-150">Windows 一括登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f611-150">Troubleshooting Windows bulk enrollment</span></span>

### <a name="provisioning-issues"></a><span data-ttu-id="5f611-151">プロビジョニングに関する問題</span><span class="sxs-lookup"><span data-stu-id="5f611-151">Provisioning issues</span></span>
<span data-ttu-id="5f611-152">プロビジョニングは新しい Windows デバイスで使用することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="5f611-152">Provisioning is intended to be used on new Windows devices.</span></span> <span data-ttu-id="5f611-153">プロビジョニングのエラーが起きると、デバイスを出荷時の設定に戻すか、ブート イメージからのデバイスの回復が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f611-153">Provisioning failures might require a factory reset of the device or device recovery from a boot image.</span></span> <span data-ttu-id="5f611-154">プロビジョニングのエラーが起きるいくつかの理由について例を挙げます。</span><span class="sxs-lookup"><span data-stu-id="5f611-154">These examples describe some reasons for provisioning failures:</span></span>

- <span data-ttu-id="5f611-155">Active Directory ドメイン、またはローカル アカウントを作成していない Azure Active Directory テナントへの参加を試行するプロビジョニング パッケージでは、ネットワーク接続がないためにドメイン参加処理が失敗した場合、デバイスが到達不能になることがあります。</span><span class="sxs-lookup"><span data-stu-id="5f611-155">A provisioning package that attempts to join an Active Directory domain or Azure Active Directory tenant that does not create a local account could make the device unreachable if the domain-join process fails due to lack of network connectivity.</span></span>
- <span data-ttu-id="5f611-156">プロビジョニング パッケージによって実行されるスクリプトは、システム コンテキストで実行され、デバイス ファイル システムと構成に任意の変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="5f611-156">Scripts run by the provisioning package are run in system context, and are able to make arbitrary changes to the device file system and configurations.</span></span> <span data-ttu-id="5f611-157">悪意のある、または正しくないスクリプトを使用すると、デバイスは再イメージングまたは工場出荷時に戻すことでのみ回復できる状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="5f611-157">A malicious or bad script could put the device in a state that can only be recovered by reimaging or factory resetting the device.</span></span>

### <a name="problems-with-bulk-enrollment-and-company-portal"></a><span data-ttu-id="5f611-158">一括登録およびポータル サイトに関する問題</span><span class="sxs-lookup"><span data-stu-id="5f611-158">Problems with bulk enrollment and Company Portal</span></span>
<span data-ttu-id="5f611-159">ユーザーが以前に一括登録したデバイスをポータル サイトで登録しようとすると、デバイスにセットアップまたは登録のどちらかの追加操作が必要なことを警告するメッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="5f611-159">If a user tries to enroll a previously bulk-enrolled device using the Company Portal, they will receive a warning that their device needs further actions, either setup or enrollment.</span></span> <span data-ttu-id="5f611-160">デバイスは登録されていますが、登録がポータル サイト アプリまたは Web サイトで認識されていません。</span><span class="sxs-lookup"><span data-stu-id="5f611-160">The device is enrolled, but the enrollment is not recognized by the Company Portal app or website.</span></span>

### <a name="bulk-enrollment-with-wi-fi"></a><span data-ttu-id="5f611-161">Wi-Fi で一括登録</span><span class="sxs-lookup"><span data-stu-id="5f611-161">Bulk enrollment with Wi-Fi</span></span> 

<span data-ttu-id="5f611-162">一括登録されたデバイスは、ユーザー対象の証明書と Wi-Fi 展開に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f611-162">Bulk enrolled devices are unable to use to user-targeted certificates and Wi-Fi deployment.</span></span> <span data-ttu-id="5f611-163">これらの接続を管理するために、[デバイス レベルの証明書](certificates-configure.md)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f611-163">You'll need to use [device-level certificates](certificates-configure.md) to manage these connections.</span></span> 

### <a name="conditional-access"></a><span data-ttu-id="5f611-164">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="5f611-164">Conditional access</span></span>
<span data-ttu-id="5f611-165">条件付きアクセスは、一括登録を使用して登録された Windows デバイスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5f611-165">Conditional access is not available for Windows devices enrolled using bulk enrollment.</span></span>
