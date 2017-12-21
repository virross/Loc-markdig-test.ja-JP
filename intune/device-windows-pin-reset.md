---
title: "Intune で Windows デバイスのパスコードをリセットする"
titlesuffix: Azure portal
description: "Microsoft PIN Reset Service が統合された Windows デバイスのパスコードを Intune を使用してリセットする方法を説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a><span data-ttu-id="2b2a7-103">Microsoft PIN Reset Service が統合された Windows デバイスのパスコードを Intune を使用してリセットする</span><span class="sxs-lookup"><span data-stu-id="2b2a7-103">Reset the passcode on Windows devices integrated with the Microsoft PIN Reset Service using Intune</span></span>

<span data-ttu-id="2b2a7-104">Windows デバイスのパスコード リセット機能に Microsoft PIN Reset Service を統合することにより、Windows 10 Mobile を実行するデバイスで新しいパスコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-104">The reset passcode capability for Windows devices integrates with the Microsoft Pin Reset Service to let you generate a new passcode for devices that run Windows 10 Mobile.</span></span> <span data-ttu-id="2b2a7-105">そのデバイスでは、Windows 10 Creators Update 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-105">The devices must be running the Windows 10 Creators Update, or later.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="2b2a7-106">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2b2a7-106">Supported platforms</span></span>

- <span data-ttu-id="2b2a7-107">Windows - Windows 10 Creators Update 以降 (Azure AD に参加) でサポートされています</span><span class="sxs-lookup"><span data-stu-id="2b2a7-107">Windows - Supported on Windows 10 Creators Update and later (Azure AD joined)</span></span>
- <span data-ttu-id="2b2a7-108">Windows Phone - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b2a7-108">Windows Phone - Not supported</span></span>
- <span data-ttu-id="2b2a7-109">iOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b2a7-109">iOS - Not supported</span></span>
- <span data-ttu-id="2b2a7-110">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b2a7-110">macOS - Not supported</span></span>
- <span data-ttu-id="2b2a7-111">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b2a7-111">Android - Not supported</span></span>


## <a name="before-you-start"></a><span data-ttu-id="2b2a7-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="2b2a7-112">Before you start</span></span>

<span data-ttu-id="2b2a7-113">管理する Windows デバイスのパスコードをリモートからリセットする前に、PIN のリセット サービスを Intune テナントに組み込み、管理するデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-113">Before you can remotely reset the passcode on Windows devices you can manage, you must onboard the PIN reset service to your Intune tenant, and configure devices you manage.</span></span> <span data-ttu-id="2b2a7-114">このように設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-114">Follow these instructions to get that set up:</span></span>

### <a name="connect-intune-with-the-pin-reset-service"></a><span data-ttu-id="2b2a7-115">PIN のリセット サービスを使用して Intune と接続する</span><span class="sxs-lookup"><span data-stu-id="2b2a7-115">Connect Intune with the PIN reset service</span></span>

1. <span data-ttu-id="2b2a7-116">[Microsoft PIN Reset Service Integration Web サイト](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent)に進み、Intune テナントを管理するテナント管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-116">Visit [Microsoft PIN Reset Service Integration website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), and sign in using the tenant administrator account you use to manage your Intune tenant.</span></span>
2. <span data-ttu-id="2b2a7-117">ログインしたら **[同意]** をクリックして、PIN リセット サービスがアカウントにアクセスするのに同意します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-117">After you log in, click **Accept** to give consent for the PIN reset service to access your account.</span></span><br>
<span data-ttu-id="2b2a7-118">![PIN をリセット サービスのアクセス許可 ページ](./media/pin-reset-service-application.png)</span><span class="sxs-lookup"><span data-stu-id="2b2a7-118">![PIN reset service permissions page](./media/pin-reset-service-application.png)</span></span>
3. <span data-ttu-id="2b2a7-119">Intune と PIN のリセット サービスが統合されたことは、Azure Portal で [Enterprise applications - All applications]/(エンタープライズ アプリケーション - すべてのアプリケーション)/ から確認できます。スクリーンショットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-119">In the Azure portal, you can verify that Intune and the PIN reset service were integrated from the Enterprise applications - All applications blade as shown in the following screenshot:</span></span><br>
<span data-ttu-id="2b2a7-120">![PIN のリセットで、Azure のサービス アプリケーション](./media/pin-reset-service-home-screen.png)</span><span class="sxs-lookup"><span data-stu-id="2b2a7-120">![PIN reset service application in Azure](./media/pin-reset-service-home-screen.png)</span></span>
4. <span data-ttu-id="2b2a7-121">Intune テナント管理資格情報を使用し、[この Web サイト](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent)にログインし、再度 **[同意]** してサービスがアクセスにアクセスすることに同意します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-121">Log in to [this website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) using your Intune tenant admin credentials and, again, choose **Accept** to give consent for the service to access your account.</span></span>

### <a name="configure-windows-devices-to-use-pin-reset"></a><span data-ttu-id="2b2a7-122">PIN のリセットを使用するよう Windows デバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="2b2a7-122">Configure Windows devices to use PIN reset</span></span>

<span data-ttu-id="2b2a7-123">管理する Windows デバイスで PIN のリセットを構成するには、その機能を有効にするために [Intune の Windows 10 カスタム デバイス ポリシー](custom-settings-windows-10.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-123">To configure PIN reset on Windows devices you manage, use an [Intune Windows 10 custom device policy](custom-settings-windows-10.md) to enable the feature.</span></span> <span data-ttu-id="2b2a7-124">次の Windows ポリシー構成サービス プロバイダー (CSP) を使用して、ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-124">Configure the policy using the following Windows policy configuration service provider (CSP):</span></span>


- <span data-ttu-id="2b2a7-125">**対象デバイス** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**</span><span class="sxs-lookup"><span data-stu-id="2b2a7-125">**For devices** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**</span></span>

<span data-ttu-id="2b2a7-126">*tenant ID* は、Azure Active Directory の **[プロパティ]** ページで取得できる Azure Active Directory ディレクトリ ID を示します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-126">*tenant ID* refers to your Azure Active Directory, Directory ID which you can obtain from the **Properties** page of Azure Active Directory.</span></span>

<span data-ttu-id="2b2a7-127">この CSP の値を **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-127">Set the value for this CSP to **True**.</span></span>

## <a name="steps-to-reset-the-passcode"></a><span data-ttu-id="2b2a7-128">パスコードをリセットする手順</span><span class="sxs-lookup"><span data-stu-id="2b2a7-128">Steps to reset the passcode</span></span>

1. <span data-ttu-id="2b2a7-129">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-129">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="2b2a7-130">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-130">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="2b2a7-131">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-131">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="2b2a7-132">**[デバイス]** ブレードで、**[管理]** > **[すべてのデバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-132">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="2b2a7-133">パスコードをリセットするデバイスを選択し、その後、デバイス プロパティ ブレードで **[New passcode]/(新しいパスコード)/** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-133">Select the device for which you want to reset the passcode, and then, on the device properties blade, choose **New passcode**.</span></span>
6. <span data-ttu-id="2b2a7-134">表示される確認メッセージの **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-134">From the confirmation that appears, choose **Yes**.</span></span> <span data-ttu-id="2b2a7-135">パスコードが生成され、以降 7 日間ポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-135">The passcode is generated, and is displayed in the portal for the next seven days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2b2a7-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2b2a7-136">Next steps</span></span>

<span data-ttu-id="2b2a7-137">パスコードのリセットに失敗した場合、詳細が記載されたリンクがポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b2a7-137">If the passcode reset fails, a link is provided in the portal to get more information.</span></span>


