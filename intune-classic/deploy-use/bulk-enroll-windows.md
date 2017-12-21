---
title: "Windows 10 の一括登録"
description: "Microsoft Intune の一括登録パッケージを作成する"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0053e37a-f26e-452f-9524-5039a635b52e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.custom: intune-classic
ms.openlocfilehash: d72da42bec2d83abfe2572e34a3fb8bb79c3682a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="bulk-enrollment-for-windows-devices"></a><span data-ttu-id="d1ff4-103">Windows デバイスの一括登録</span><span class="sxs-lookup"><span data-stu-id="d1ff4-103">Bulk enrollment for Windows devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d1ff4-104">管理者として、Azure Active Directory と Intune に多数の新しい Windows デバイスを参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-104">As an administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune.</span></span> <span data-ttu-id="d1ff4-105">Azure AD テナントのデバイスを一括登録するには、Windows Configuration Designer (WCD) アプリでプロビジョニング パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-105">To bulk enroll devices for your Azure AD tenant, you create a provisioning package with the Windows Configuration Designer (WCD) app.</span></span> <span data-ttu-id="d1ff4-106">企業所有のデバイスにプロビジョニング パッケージを適用すると、Azure AD テナントにデバイスを参加させ、Intune 管理用に登録します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-106">Applying the provisioning package to corporate-owned devices joins the devices to your Azure AD tenant and enrolls them for Intune management.</span></span> <span data-ttu-id="d1ff4-107">パッケージが適用されると、Azure AD ユーザーがログオンするための準備は完了です。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-107">Once the package is applied, it's ready for your Azure AD users to log on.</span></span>

<span data-ttu-id="d1ff4-108">Azure AD ユーザーはこれらのデバイス上の標準ユーザーであり、割り当て済みの Intune ポリシーと必須アプリを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-108">Azure AD users are standard users on these devices and receive assigned Intune policies and required apps.</span></span> <span data-ttu-id="d1ff4-109">この時点では、セルフ サービスとポータル サイトのシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-109">Self-service and Company Portal scenarios are not supported at this time.</span></span>

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a><span data-ttu-id="d1ff4-110">Windows デバイスの一括登録の前提条件</span><span class="sxs-lookup"><span data-stu-id="d1ff4-110">Prerequisites for Windows devices bulk enrollment</span></span>

<span data-ttu-id="d1ff4-111">Windows デバイスの一括登録には、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-111">Bulk enrollment for Window devices requires the following:</span></span>

- <span data-ttu-id="d1ff4-112">Windows 10 Creator Update 以降が動作しているデバイス</span><span class="sxs-lookup"><span data-stu-id="d1ff4-112">Devices running Windows 10 Creator update or later</span></span>
- [<span data-ttu-id="d1ff4-113">Windows 自動登録</span><span class="sxs-lookup"><span data-stu-id="d1ff4-113">Windows automatic enrollment</span></span>](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a><span data-ttu-id="d1ff4-114">プロビジョニング パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="d1ff4-114">Create a provisioning package</span></span>

1. <span data-ttu-id="d1ff4-115">Microsoft ストアから [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-115">Download [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Microsoft Store.</span></span>
<span data-ttu-id="d1ff4-116">![Windows Configuration Designer アプリ ストアのスクリーン ショットと説明のスクリーン ショット](../media/bulk-enroll-store.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-116">![Screenshot of the Windows Configuration Designer app Store screenshots and description](../media/bulk-enroll-store.png)</span></span>

2. <span data-ttu-id="d1ff4-117">**Windows Configuration Designer** アプリを開き、**[Provision desktop devices]** (デスクトップ デバイスのプロビジョニング) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-117">Open the **Windows Configuration Designer** app and select **Provision desktop devices**.</span></span>
<span data-ttu-id="d1ff4-118">![Windows Configuration Designer アプリでデスクトップ デバイスのプロビジョニングを選択するスクリーン ショット](../media/bulk-enroll-select.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-118">![Screenshot of selecting Provision desktop devices in the Windows Configuration Designer app](../media/bulk-enroll-select.png)</span></span>

3. <span data-ttu-id="d1ff4-119">**[New project]\(新しいプロジェクト\)** ウィンドウが開くので、そこで次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-119">A **New project** window opens where you specify the following:</span></span>
  - <span data-ttu-id="d1ff4-120">**[名前]** - プロジェクトの名前</span><span class="sxs-lookup"><span data-stu-id="d1ff4-120">**Name** - A name for your project</span></span>
  - <span data-ttu-id="d1ff4-121">**[プロジェクト フォルダー]** - 新しいプロジェクトを保存する場所</span><span class="sxs-lookup"><span data-stu-id="d1ff4-121">**Project folder** - Where your new project will be saved</span></span>
  - <span data-ttu-id="d1ff4-122">**[説明]** - プロジェクトの説明 (オプション) ![Windows 構成デザイナー アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーンショット](../media/bulk-enroll-name.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-122">**Description** - An optional description of the project ![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-name.png)</span></span>

4.  <span data-ttu-id="d1ff4-123">デバイスの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-123">Enter a unique name for your devices.</span></span> <span data-ttu-id="d1ff4-124">名前には、シリアル番号 (%%SERIAL%%)、または文字のランダムなセットを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-124">Names can include a serial number (%%SERIAL%%) or a random set of characters.</span></span> <span data-ttu-id="d1ff4-125">必要に応じて、Windows のエディションをアップグレードする場合にプロダクト キーを入力したり、デバイスを共有使用のために構成したり、事前にインストールされたソフトウェアを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-125">Optionally, you can also enter a product key if you are upgrading the edition of Windows, configure the device for shared use, and remove pre-installed software.</span></span><BR>
<span data-ttu-id="d1ff4-126">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](../media/bulk-enroll-device.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-126">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-device.png)</span></span>

5.  <span data-ttu-id="d1ff4-127">必要に応じて、初回起動時にデバイスが接続する Wi-fi ネットワークを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-127">Optionally, you can configure the Wi-Fi network devices connect to when they first start.</span></span>  <span data-ttu-id="d1ff4-128">これが構成されていない場合は、デバイスの初回起動時にワイヤード (有線) ネットワーク接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-128">If this isn’t configured, a wired network connection is required when the device is first started.</span></span>
<span data-ttu-id="d1ff4-129">![Windows Configuration Designer アプリで、ネットワーク SSID やネットワークの種類のオプションを含む Wi-fi を有効にするスクリーン ショット](../media/bulk-enroll-network.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-129">![Screenshot of enabling Wi-Fi including Network SSID and Network type options in the Windows Configuration Designer app](../media/bulk-enroll-network.png)</span></span>

6.  <span data-ttu-id="d1ff4-130">**[Enroll in Azure AD]\(Azure AD に登録\)** を選択し、**[Bulk Token Expiry]\(一括トークンの有効期限\)** の日付を入力して、**[Get Bulk Token]\(一括トークンの取得\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-130">Select **Enroll in Azure AD**, enter a **Bulk Token Expiry** date, and then select **Get Bulk Token**.</span></span>
<span data-ttu-id="d1ff4-131">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](../media/bulk-enroll-account.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-131">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-account.png)</span></span>

7. <span data-ttu-id="d1ff4-132">一括トークンを取得するための Azure AD の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-132">Provide your Azure AD credentials to get a bulk token.</span></span>
<span data-ttu-id="d1ff4-133">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](../media/bulk-enroll-cred.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-133">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-cred.png)</span></span>

8.  <span data-ttu-id="d1ff4-134">**一括トークン**が正常にフェッチされたら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-134">Click **Next** when **Bulk Token** is fetched successfully.</span></span>

9. <span data-ttu-id="d1ff4-135">必要に応じて **[アプリケーションの追加]** や **[証明書の追加]** ができます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-135">Optionally, you can **Add applications** and **Add certificates**.</span></span> <span data-ttu-id="d1ff4-136">これらのアプリと証明書がデバイスでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-136">These apps and certificates are provisioned on the device.</span></span>

10. <span data-ttu-id="d1ff4-137">必要に応じて、プロビジョニング パッケージをパスワードで保護できます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-137">Optionally, you can password protect your provisioning package.</span></span>  <span data-ttu-id="d1ff4-138">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-138">Click **Create**.</span></span>
<span data-ttu-id="d1ff4-139">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](../media/bulk-enroll-create.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-139">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-create.png)</span></span>

## <a name="provision-devices"></a><span data-ttu-id="d1ff4-140">デバイスのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="d1ff4-140">Provision devices</span></span>

1. <span data-ttu-id="d1ff4-141">アプリで指定した**プロジェクト フォルダー**の場所にあるプロビジョニング パッケージにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-141">Access the provisioning package in the location specified in **Project folder** specified in the app.</span></span>

2. <span data-ttu-id="d1ff4-142">プロビジョニング パッケージをデバイスに適用する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-142">Choose how you’re going to apply the provisioning package to the device.</span></span>  <span data-ttu-id="d1ff4-143">プロビジョニング パッケージは、次のいずれかの方法でデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-143">A provisioning package can be applied to a device one of the following ways:</span></span>
 - <span data-ttu-id="d1ff4-144">USB ドライブにプロビジョニング パッケージを置いて、USB ドライブを一括登録するデバイスに挿入し、初期セットアップ時に適用する</span><span class="sxs-lookup"><span data-stu-id="d1ff4-144">Place the provisioning package on a USB drive, insert the USB drive into the device you’d like to bulk enroll, and apply it during initial setup</span></span>
 - <span data-ttu-id="d1ff4-145">ネットワーク フォルダーにプロビジョニング パッケージを置いて、初期セットアップ後に、一括登録するデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="d1ff4-145">Place the provisioning package on a network folder, and apply it insert on the device you’d like to bulk enroll after initial setup</span></span>

 <span data-ttu-id="d1ff4-146">スプロビジョニング パッケージを適用するステップ バイ ステップの手順については、「[プロビジョニング パッケージの適用](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-146">For step-by-step instruction on applying a provisioning package, see [Apply a provisioning package](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).</span></span>

3. <span data-ttu-id="d1ff4-147">パッケージを適用したら、デバイスは 1 分後に自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-147">After you apply the package, the device will automatically restart in 1 minute.</span></span>
 <span data-ttu-id="d1ff4-148">![Windows Configuration Designer アプリで、名前、プロジェクト フォルダー、説明を指定するスクリーン ショット](../media/bulk-enroll-add.png)</span><span class="sxs-lookup"><span data-stu-id="d1ff4-148">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](../media/bulk-enroll-add.png)</span></span>

4. <span data-ttu-id="d1ff4-149">デバイスが再起動すると、Azure Active Directory に接続して Microsoft Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-149">When the device restarts, it connects to the Azure Active Directory and enrolls in Microsoft Intune.</span></span>

## <a name="troubleshooting-windows-bulk-enrollment"></a><span data-ttu-id="d1ff4-150">Windows 一括登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d1ff4-150">Troubleshooting Windows bulk enrollment</span></span>

<span data-ttu-id="d1ff4-151">プロビジョニングは新しい Windows デバイスで使用することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-151">Provisioning is intended to be used on new Windows devices.</span></span> <span data-ttu-id="d1ff4-152">プロビジョニングのエラーが起きると、デバイスを出荷時の設定に戻すか、ブート イメージからのデバイスの回復が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-152">Provisioning failures might require a factory reset of the device or device recovery from a boot image.</span></span> <span data-ttu-id="d1ff4-153">プロビジョニングのエラーが起きるいくつかの理由について例を挙げます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-153">These examples describe some reasons for provisioning failures:</span></span>

- <span data-ttu-id="d1ff4-154">Active Directory ドメイン、またはローカル アカウントを作成していない Azure Active Directory テナントへの参加を試行するプロビジョニング パッケージでは、ネットワーク接続がないためにドメイン参加処理が失敗した場合、デバイスが到達不能になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-154">A provisioning package that attempts to join an Active Directory domain or Azure Active Directory tenant that does not create a local account could make the device unreachable if the domain-join process fails due to lack of network connectivity.</span></span>
- <span data-ttu-id="d1ff4-155">プロビジョニング パッケージによって実行されるスクリプトは、システム コンテキストで実行され、デバイス ファイル システムと構成に任意の変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-155">Scripts run by the provisioning package are run in system context, and are able to make arbitrary changes to the device file system and configurations.</span></span> <span data-ttu-id="d1ff4-156">悪意のある、または正しくないスクリプトを使用すると、デバイスは再イメージングまたは工場出荷時に戻すことでのみ回復できる状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1ff4-156">A malicious or bad script could put the device in a state that can only be recovered by reimaging or factory resetting the device.</span></span>
