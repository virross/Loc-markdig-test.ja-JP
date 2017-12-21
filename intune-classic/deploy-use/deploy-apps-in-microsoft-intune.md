---
title: "アプリを展開する方法"
description: "このトピックの情報を使用して、Microsoft Intune でアプリを展開できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d147a53f283470feda83a66d3668aacc566cb81
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="deploy-apps-in-microsoft-intune"></a><span data-ttu-id="b9755-103">Deploy apps in Microsoft Intune (Microsoft Intune でアプリを展開する)</span><span class="sxs-lookup"><span data-stu-id="b9755-103">Deploy apps in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b9755-104">このトピックの情報を使用して、Microsoft Intune でアプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b9755-104">Use the information in this topic to help you deploy apps with Microsoft Intune.</span></span>


## <a name="deploy-an-app"></a><span data-ttu-id="b9755-105">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="b9755-105">Deploy an app</span></span>
<span data-ttu-id="b9755-106">この手順では、選択したデバイスまたはユーザーのグループにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b9755-106">In this procedure, you'll deploy an app to selected groups of devices or users.</span></span>

### <a name="to-deploy-an-app"></a><span data-ttu-id="b9755-107">アプリを展開するには</span><span class="sxs-lookup"><span data-stu-id="b9755-107">To deploy an app</span></span>

1. <span data-ttu-id="b9755-108">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順にクリックし、管理するアプリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="b9755-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Apps** &gt; **Apps** to view the list of apps that you manage.</span></span>

2.  <span data-ttu-id="b9755-109">展開するアプリを選択し、**[展開の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9755-109">Select the app that you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="b9755-110">*[&lt;アプリ名&gt;]* ダイアログ ボックスで、**[グループの選択]** ページで、アプリを展開するユーザー グループまたはデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9755-110">In the *&lt;app name&gt;* dialog box, on the **Select Groups** page, choose the user or device groups to which you want to deploy the app.</span></span>

4.  <span data-ttu-id="b9755-111">**[展開アクション]** ページで、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="b9755-111">On the **Deployment Action** page, configure the following:</span></span>

    - <span data-ttu-id="b9755-112">**承認** - 展開の詳細を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9755-112">**Approval** - Choose whether the deployment is:</span></span>
        - <span data-ttu-id="b9755-113">**[必須]** (インストール必須)</span><span class="sxs-lookup"><span data-stu-id="b9755-113">**Required** (mandatory install)</span></span>
        - <span data-ttu-id="b9755-114">**[使用可能]** (必要に応じて、ユーザーは会社のポータルからインストールします)</span><span class="sxs-lookup"><span data-stu-id="b9755-114">**Available** (users install from the company portal on demand)</span></span>
        - <span data-ttu-id="b9755-115">**[該当なし]** (アプリは会社のポータルにはインストールされていないか、表示されません)</span><span class="sxs-lookup"><span data-stu-id="b9755-115">**Not Applicable** (the app is not installed or shown in the company portal)</span></span>
        - <span data-ttu-id="b9755-116">**[アンインストール]** (アプリは対象となるデバイスからアンインストールされます)</span><span class="sxs-lookup"><span data-stu-id="b9755-116">**Uninstall** (the app is uninstalled from targeted devices)</span></span>
    - <span data-ttu-id="b9755-117">**期限** - 必要なインストールに対し、アプリをいつ展開するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9755-117">**Deadline** - For required installations, choose how soon to deploy the app.</span></span> <span data-ttu-id="b9755-118">定義済みの値から選択するか、**[カスタム]** を選択し、独自の期限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b9755-118">You can choose from the predefined values, or you can select **Custom** to configure your own deadline.</span></span>

5. <span data-ttu-id="b9755-119">展開するアプリがモバイル アプリケーション管理ポリシーで構成できる場合、**[モバイル アプリの管理]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9755-119">If the app you are deploying can be configured by a mobile application management policy, the **Mobile App Management** page is displayed.</span></span> <span data-ttu-id="b9755-120">このページで、このアプリに関連付けるモバイル アプリケーションの管理ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9755-120">On this page, choose the mobile application management policy that you want to associate with this app.</span></span>

    [<span data-ttu-id="b9755-121">モバイル アプリケーション管理ポリシーに対応する Microsoft アプリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9755-121">See which Microsoft apps are compatible with mobile application management policies.</span></span>](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. <span data-ttu-id="b9755-122">展開するアプリに Intune VPN プロファイルとの互換性がある場合、**[VPN プロファイル]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9755-122">If the app you are deploying is compatible with Intune VPN profiles, the **VPN Profile** page is displayed.</span></span> <span data-ttu-id="b9755-123">このページで、展開した VPN プロファイルに iOS アプリを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b9755-123">On this page, you can choose to associate iOS apps with a VPN profile that you have deployed.</span></span> <span data-ttu-id="b9755-124">アプリを起動すると、VPN 接続が自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="b9755-124">The VPN connection automatically opens when the app is launched.</span></span> <span data-ttu-id="b9755-125">VPN プロファイルを使用できるようにするには、**アプリごとの VPN** プロファイル設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9755-125">To make a VPN profile available, it must have the **Per-app VPN** profile setting enabled.</span></span>
 <span data-ttu-id="b9755-126">プロファイルをアプリと関連付ける方法に関する情報など、VPN プロファイルを構成する方法については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b9755-126">For information about how to configure VPN profiles, including information about how to associate profiles with apps, see [VPN connections in Microsoft Intune](vpn-connections-in-microsoft-intune.md).</span></span>

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a><span data-ttu-id="b9755-127">例</span><span class="sxs-lookup"><span data-stu-id="b9755-127">Example</span></span>

<span data-ttu-id="b9755-128">この例では、アプリを **[使用可能]** として iOS デバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="b9755-128">In this example, you deployed the app as **Available** to an iOS device.</span></span>
<span data-ttu-id="b9755-129">ユーザーのデバイスでポータル サイトにアプリが表示され、そこからアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b9755-129">The app displays on users' devices in the company portal, and users can install it from there.</span></span>

<span data-ttu-id="b9755-130">たとえば、このスクリーンショットでは、**[外部リンク]** インストール タイプとカスタム アイコンを使用して Bing for iOS アプリを展開しています。</span><span class="sxs-lookup"><span data-stu-id="b9755-130">For example, in this screenshot, the Bing for iOS app was deployed by using the **External Link** installation type with a custom icon.</span></span> <span data-ttu-id="b9755-131">**[このアプリをポータル サイトでおすすめアプリとして強調表示する]** オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="b9755-131">The option **Display this as a featured app and highlight it in the company portal** was selected.</span></span>  
<span data-ttu-id="b9755-132">![iOS の使用可能アプリ](./media/available-install-on-iOS.png)</span><span class="sxs-lookup"><span data-stu-id="b9755-132">![iOS available app](./media/available-install-on-iOS.png)</span></span>

<span data-ttu-id="b9755-133">アプリを **[必須]** として iOS デバイスに展開した場合は、アプリがインストール可能になったことを知らせる通知がユーザーに届きます。</span><span class="sxs-lookup"><span data-stu-id="b9755-133">If you deployed the app as **Required** to an iOS device, the user will get a notification that an app is ready to install.</span></span> <span data-ttu-id="b9755-134">たとえば、このスクリーンショットでは、種類が **[アプリ ストアの管理されている iOS アプリ]** のインストールで Work Folders for iOS アプリが展開されました。</span><span class="sxs-lookup"><span data-stu-id="b9755-134">For example, in this screenshot, the Work Folders for iOS app was deployed by using the **Managed iOS app from the app store** installation type.</span></span>  
<span data-ttu-id="b9755-135">![iOS の必須アプリ](./media/iOS-Required-install.PNG)</span><span class="sxs-lookup"><span data-stu-id="b9755-135">![iOS required app](./media/iOS-Required-install.PNG)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9755-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b9755-136">Next steps</span></span>

<span data-ttu-id="b9755-137">アプリケーションを展開した後、その進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="b9755-137">After you deploy an app, you'll want to monitor its progress.</span></span> <span data-ttu-id="b9755-138">詳細については、「[Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md)」 (Microsoft Intune でアプリを監視する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9755-138">For more information, see [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).</span></span>
