---
title: "Managed Browser で Web アクセスを管理する"
description: "Managed Browser アプリケーションを展開して、Web 閲覧と他のアプリへの Web データ転送を制限します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b7eb2f9a48e2033dcac04e469e6dd2da55c5706
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a><span data-ttu-id="49b9b-103">Microsoft Intune と Managed Browser のポリシーを使用したインターネット アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="49b9b-103">Manage Internet access using managed browser policies with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="49b9b-104">Managed Browser は、Microsoft Intune を使用して組織で展開できる、Web を参照するためのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="49b9b-104">The managed browser is a web browsing application that you can deploy in your organization by using Microsoft Intune.</span></span> <span data-ttu-id="49b9b-105">Managed Browser ポリシーは、Managed Browser のユーザーがアクセスできる Web サイトを制限する許可リストまたはブロック リストを構成するものです。</span><span class="sxs-lookup"><span data-stu-id="49b9b-105">A managed browser policy configures an allow list or a block list that restricts the websites that users of the managed browser can visit.</span></span>

<span data-ttu-id="49b9b-106">このアプリは Intune SDK と統合されているので、アプリ保護ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-106">Because this app has integration with the Intune SDK, you can also apply app protection policies to it.</span></span> <span data-ttu-id="49b9b-107">これらのポリシーでは、切り取り、コピー、貼り付けの使用を制御したり、画面のキャプチャを禁止したり、ユーザーが選択したコンテンツへのリンクのみを他の管理対象アプリで開けるようにしたりします。</span><span class="sxs-lookup"><span data-stu-id="49b9b-107">These policies might include controlling the use of cut, copy, and paste, preventing screen captures, and ensuring that links to content that users select open only in other managed apps.</span></span> <span data-ttu-id="49b9b-108">詳細については、「[Microsoft Intune コンソールでモバイル アプリケーション管理ポリシーを構成して展開する](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)」で説明されている方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-108">For details, see [Configure and deploy mobile application management policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="49b9b-109">Managed Browser アプリは、デバイス上の別のアプリがアクセス保護ポリシーを取得した場合にのみ、Intune アクセス保護ポリシーを取得して適用します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-109">The Managed Browser app only retrieves and applies Intune app protection policies when another app on the device has retrieved an app protection policy.</span></span><br><br> <span data-ttu-id="49b9b-110">また、ユーザーがアプリ ストアから Managed Browser をインストールし、それが Intune で管理されていない場合は、次の動作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-110">Additionally, if users install the managed browser from the app store and Intune does not manage it, the following behavior applies:</span></span><br /><br />
><span data-ttu-id="49b9b-111">**iOS** : managed browser アプリは、基本的な web ブラウザーとして使用できますが、一部の機能を使用可能にすることはできませんし、他の Intune の管理対象アプリからデータにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-111">**iOS** – The managed browser app can be used as a basic web browser, but some features will not be available, and it will not be able to access data from other Intune-managed apps.</span></span><br />
<span data-ttu-id="49b9b-112">**Android** – managed browser アプリを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-112">**Android** – The managed browser app cannot be used.</span></span><br /><br />
<span data-ttu-id="49b9b-113">ユーザーが iOS 9 よりも前のバージョンが搭載された iOS デバイスに自分で Managed Browser をインストールした場合は、作成したポリシーで管理されません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-113">If users install the managed browser themselves on an iOS device with a version earlier than iOS 9, no policies that you create will manage the browser.</span></span> <span data-ttu-id="49b9b-114">ブラウザーを Intune で確実に管理するには、ユーザーにアプリをアンインストールしてもらった後に、管理対象アプリとして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b9b-114">To ensure that Intune manages the browser, users must uninstall the app before you can deploy it to them as a managed app.</span></span> <span data-ttu-id="49b9b-115">iOS 9 以降では、ユーザーは自分で Managed Browser をインストールした場合、それがポリシーの管理対象となることを認めるように求められます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-115">On iOS 9 and later, if users install the managed browser themselves, they will be prompted to allow it to become managed by policy.</span></span>

<span data-ttu-id="49b9b-116">次の種類のデバイス用に Managed Browser のポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-116">You can create managed browser policies for the following device types:</span></span>

-   <span data-ttu-id="49b9b-117">Android 4 以降が実行されているデバイス</span><span class="sxs-lookup"><span data-stu-id="49b9b-117">Devices that run Android 4 and later</span></span>

-   <span data-ttu-id="49b9b-118">iOS 8.0 以降を実行するデバイス</span><span class="sxs-lookup"><span data-stu-id="49b9b-118">Devices that run iOS 8.0 and later</span></span>

<span data-ttu-id="49b9b-119">Intune Managed Browser では、[Microsoft Intune アプリケーション パートナー](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)から Web コンテンツを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-119">The Intune managed browser supports opening web content from [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).</span></span>

## <a name="create-a-managed-browser-policy"></a><span data-ttu-id="49b9b-120">Managed Browser のポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="49b9b-120">Create a managed browser policy</span></span>

1.  <span data-ttu-id="49b9b-121">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[ポリシーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-121">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="49b9b-122">次のいずれかの種類の **ソフトウェア** ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-122">Configure one of the following **Software** policy types:</span></span>

    -   <span data-ttu-id="49b9b-123">**Managed Browser (Android 4 以降)**</span><span class="sxs-lookup"><span data-stu-id="49b9b-123">**Managed Browser (Android 4 and later)**</span></span>

    -   <span data-ttu-id="49b9b-124">**Managed Browser (iOS 8.0 以降)**</span><span class="sxs-lookup"><span data-stu-id="49b9b-124">**Managed Browser (iOS 8.0 and later)**</span></span>

    <span data-ttu-id="49b9b-125">ポリシーの作成および展開方法の詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-125">For more information about how to create and deploy policies, see the [Manage settings and features on your devices with Microsoft Intune Policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) topic.</span></span>

3.  <span data-ttu-id="49b9b-126">次を参考に、Managed Browser のポリシーの設定を構成してください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-126">Use the following to help you configure the managed browser policy settings:</span></span>

    - <span data-ttu-id="49b9b-127">**名前**。</span><span class="sxs-lookup"><span data-stu-id="49b9b-127">**Name**.</span></span> <span data-ttu-id="49b9b-128">Intune コンソール内で容易に識別できるように、Managed Browser ポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-128">Enter a unique name for the managed browser policy to help you identify it in the Intune console.</span></span>
    - <span data-ttu-id="49b9b-129">**説明**。</span><span class="sxs-lookup"><span data-stu-id="49b9b-129">**Description**.</span></span> <span data-ttu-id="49b9b-130">Managed Browser ポリシーの概要や、Managed Browser ポリシーを特定するのに役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-130">Provide a description that gives an overview of the managed browser policy and other relevant information that helps you to locate it.</span></span>
    - <span data-ttu-id="49b9b-131">**Managed Browser で開くことができる URL を許可リストまたはブロック リストで制限できるようにする**。</span><span class="sxs-lookup"><span data-stu-id="49b9b-131">**Enable an allow list or block list to restrict the URLs the Managed Browser can open**.</span></span> <span data-ttu-id="49b9b-132">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-132">Select one of the following options:</span></span>
        - <span data-ttu-id="49b9b-133">**管理対象ブラウザーで以下のリストにある URL だけを開くことを許可**。</span><span class="sxs-lookup"><span data-stu-id="49b9b-133">**Allow the managed browser to open only the URLs listed below**.</span></span> <span data-ttu-id="49b9b-134">Managed Browser で開くことができる URL のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-134">Specify a list of URLs that the managed browser can open.</span></span>
        - <span data-ttu-id="49b9b-135">**Managed Browser で以下のリストにある URL を開くことを禁止**。</span><span class="sxs-lookup"><span data-stu-id="49b9b-135">**Block the managed browser from opening the URLs listed below**.</span></span> <span data-ttu-id="49b9b-136">Managed Browser で開くことができないようにする URL のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-136">Specify a list of URLs that the managed browser will be blocked from opening.</span></span>
<span data-ttu-id="49b9b-137">**注:** 同じ Managed Browser ポリシーに、許可される URL とブロックされる URL の両方を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-137">**Note:** You cannot include both allowed and blocked URLs in the same managed browser policy.</span></span>
<span data-ttu-id="49b9b-138">指定できる URL の形式の詳細については、このトピックの「**許可される URL とブロックされる URL の形式**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-138">For more information about the URL formats you can specify, see **URL format for allowed and blocked URLs** in this topic.</span></span>

4.  <span data-ttu-id="49b9b-139">終了したら、**[ポリシーの保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-139">When you are finished, choose **Save Policy**.</span></span>

<span data-ttu-id="49b9b-140">**[ポリシー]** ワークスペースの **[構成ポリシー]** ノードに新しいポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-140">The new policy appears in the **Configuration Policies** node of the **Policy** workspace.</span></span>

## <a name="create-a-deployment-for-the-managed-browser-app"></a><span data-ttu-id="49b9b-141">Managed Browser アプリ向けに展開を作成する</span><span class="sxs-lookup"><span data-stu-id="49b9b-141">Create a deployment for the managed browser app</span></span>
<span data-ttu-id="49b9b-142">Managed Browser ポリシーの作成後、Managed Browser アプリ向けにソフトウェアの展開を作成し、作成した Managed Browser ポリシーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-142">After you have created the managed browser policy, you can then create a software deployment for the managed browser app, and associate it with the managed browser policy that you created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49b9b-143">Managed Browser ポリシーの展開方法は、他の Intune ポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="49b9b-143">Managed browser policies are not deployed in the same way as other Intune polices.</span></span> <span data-ttu-id="49b9b-144">この種類のポリシーは、Managed Browser ソフトウェア パッケージに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b9b-144">This type of policy must be associated with the managed browser software package.</span></span>

<span data-ttu-id="49b9b-145">アプリを展開し、必ず **[モバイル アプリの管理]** ページで Managed Browser ポリシーを選択してそのポリシーをアプリに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-145">Deploy the app, ensuring that you select the managed browser policy on the **Mobile App Management** page to associate the policy with the app.</span></span>

<span data-ttu-id="49b9b-146">アプリの展開方法の詳細については、「[Microsoft Intune でアプリを展開する](deploy-apps-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-146">For more information about how to deploy apps, see [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>

## <a name="security-and-privacy-for-the-managed-browser"></a><span data-ttu-id="49b9b-147">Managed Browser のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="49b9b-147">Security and privacy for the managed browser</span></span>

-   <span data-ttu-id="49b9b-148">iOS デバイスでは、証明書の有効期限が切れている Web サイトや証明書が信頼されていない Web サイトにユーザーがアクセスしても、開くことができません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-148">On iOS devices, websites that users visit that have an expired or untrusted certificate cannot be opened.</span></span>

-   <span data-ttu-id="49b9b-149">ユーザーが自分のデバイスの組み込みブラウザーに対して構成した設定は、Managed Browser では使用されません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-149">The managed browser does not use settings that users make for the built-in browser on their devices.</span></span> <span data-ttu-id="49b9b-150">これは、Managed Browser がこれらの設定にアクセスできないためです。</span><span class="sxs-lookup"><span data-stu-id="49b9b-150">This is because the managed browser does not have access to these settings.</span></span>

-   <span data-ttu-id="49b9b-151">Managed Browser に関連付けられているモバイル アプリケーション管理ポリシーで **[アクセスの際にシンプルな PIN を要求する]** オプションか **[アクセスの際に会社の資格情報を要求する]** オプションが構成されている場合は、ユーザーが認証ページのヘルプ リンクを選択すると、Managed Browser ポリシーのブロック リストに追加されているかどうかに関係なく、ユーザーはすべてのインターネット サイトを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-151">If you configure the option **Require simple PIN for access** or **Require corporate credentials for access** in a mobile application management policy associated with the managed browser, and a user selects the help link on the authentication page, they can then browse any Internet sites regardless of whether they were added to a block list in the managed browser policy.</span></span>

-   <span data-ttu-id="49b9b-152">Managed Browser では、直接アクセスされたときのみ、サイトへのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-152">The managed browser can block access to sites only when they are accessed directly.</span></span> <span data-ttu-id="49b9b-153">サイトへのアクセスに中間サービス (翻訳サービスなど) が使用されている場合は、アクセスをブロックすることができません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-153">It cannot block access when intermediate services (such as a translation service) are used to access the site.</span></span>

-   <span data-ttu-id="49b9b-154">認証を許可し、Intune のドキュメントにアクセスできるようにするため、**&#42;.microsoft.com** は許可リストとブロック リストの設定から除外されており、</span><span class="sxs-lookup"><span data-stu-id="49b9b-154">To allow authentication, and to ensure that the Intune documentation can be accessed,**&#42;.microsoft.com** is exempt from the allow or block list settings.</span></span> <span data-ttu-id="49b9b-155">常に許可されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-155">It is always allowed.</span></span>

### <a name="turn-off-usage-data"></a><span data-ttu-id="49b9b-156">使用状況データをオフにする</span><span class="sxs-lookup"><span data-stu-id="49b9b-156">Turn off usage data</span></span>
<span data-ttu-id="49b9b-157">Microsoft は、Microsoft の製品やサービスを改善するために、Managed Browser のパフォーマンスおよび使用に関する匿名データを自動的に収集します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-157">Microsoft automatically collects anonymous data about the performance and use of the managed browser to improve Microsoft products and services.</span></span> <span data-ttu-id="49b9b-158">ただし、ユーザーはデバイスの **[使用状況データ]** 設定を使用して、データの収集を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-158">Users can turn off data collection by using the **Usage Data** setting on their devices.</span></span> <span data-ttu-id="49b9b-159">このデータの収集方法は制御できません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-159">You have no control over the collection of this data.</span></span>

## <a name="reference-information"></a><span data-ttu-id="49b9b-160">参照情報</span><span class="sxs-lookup"><span data-stu-id="49b9b-160">Reference information</span></span>

### <a name="url-format-for-allowed-and-blocked-urls"></a><span data-ttu-id="49b9b-161">許可される URL とブロックされる URL の形式</span><span class="sxs-lookup"><span data-stu-id="49b9b-161">URL format for allowed and blocked URLs</span></span>
<span data-ttu-id="49b9b-162">許可リストとブロック リストで URL を指定するときに使用できる形式とワイルドカードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-162">Use the following information to learn about the allowed formats and wildcards that you can use when specifying URLs in the allowed and blocked lists:</span></span>

-   <span data-ttu-id="49b9b-163">ワイルドカード記号 (**&#42;**) は、以下の許可されているパターン リストの規則に従って使用できます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-163">You can use the wildcard symbol (**&#42;**) according to the rules in the following permitted patterns list.</span></span>

-   <span data-ttu-id="49b9b-164">リストに入力するときは、すべての URL の先頭に必ず **http** または **https** を付けてください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-164">Ensure that you prefix all URLs with **http** or **https** when entering them into the list.</span></span>

-   <span data-ttu-id="49b9b-165">アドレスにはポート番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-165">You can specify port numbers in the address.</span></span> <span data-ttu-id="49b9b-166">ポート番号を指定しない場合は、次の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-166">If you do not specify a port number, the values used will be:</span></span>

    -   <span data-ttu-id="49b9b-167">http の場合はポート 80</span><span class="sxs-lookup"><span data-stu-id="49b9b-167">Port 80 for http</span></span>

    -   <span data-ttu-id="49b9b-168">https の場合はポート 443</span><span class="sxs-lookup"><span data-stu-id="49b9b-168">Port 443 for https</span></span>

    <span data-ttu-id="49b9b-169">ポート番号にワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-169">Using wildcards for the port number is not supported.</span></span> <span data-ttu-id="49b9b-170">たとえば、**http&colon;//www&period;contoso&period;com:*;** や **http&colon;//www&period;contoso&period;com: /*;** はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-170">For example, **http&colon;//www&period;contoso&period;com:*;** and **http&colon;//www&period;contoso&period;com: /*;** are not supported.</span></span>

-   <span data-ttu-id="49b9b-171">URL を指定するときに使用できるパターンの詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b9b-171">Use the following table to learn about the permitted patterns that you can use when you specify URLs:</span></span>

|<span data-ttu-id="49b9b-172">[URL]</span><span class="sxs-lookup"><span data-stu-id="49b9b-172">URL</span></span>|<span data-ttu-id="49b9b-173">説明</span><span class="sxs-lookup"><span data-stu-id="49b9b-173">Details</span></span>|<span data-ttu-id="49b9b-174">［一致する］</span><span class="sxs-lookup"><span data-stu-id="49b9b-174">Matches</span></span>|<span data-ttu-id="49b9b-175">［次の値に一致しない］</span><span class="sxs-lookup"><span data-stu-id="49b9b-175">Does not match</span></span>|
    |-------|---------------|-----------|------------------|
    |<span data-ttu-id="49b9b-176">http://www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-176">http://www.contoso.com</span></span>|<span data-ttu-id="49b9b-177">単一のページと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-177">Matches a single page</span></span>|<span data-ttu-id="49b9b-178">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-178">www.contoso.com</span></span>|<span data-ttu-id="49b9b-179">host.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-179">host.contoso.com</span></span><br /><br /><span data-ttu-id="49b9b-180">www.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-180">www.contoso.com/images</span></span><br /><br /><span data-ttu-id="49b9b-181">contoso.com/</span><span class="sxs-lookup"><span data-stu-id="49b9b-181">contoso.com/</span></span>|
    |<span data-ttu-id="49b9b-182">http://contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-182">http://contoso.com</span></span>|<span data-ttu-id="49b9b-183">単一のページと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-183">Matches a single page</span></span>|<span data-ttu-id="49b9b-184">contoso.com/</span><span class="sxs-lookup"><span data-stu-id="49b9b-184">contoso.com/</span></span>|<span data-ttu-id="49b9b-185">host.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-185">host.contoso.com</span></span><br /><br /><span data-ttu-id="49b9b-186">www.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-186">www.contoso.com/images</span></span><br /><br /><span data-ttu-id="49b9b-187">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-187">www.contoso.com</span></span>|
    |<span data-ttu-id="49b9b-188">http://www.contoso.com/&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-188">http://www.contoso.com/&#42;</span></span>|<span data-ttu-id="49b9b-189">www.contoso.com で始まるすべての URL と一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-189">Matches all URLs that begin with www.contoso.com</span></span>|<span data-ttu-id="49b9b-190">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-190">www.contoso.com</span></span><br /><br /><span data-ttu-id="49b9b-191">www.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-191">www.contoso.com/images</span></span><br /><br /><span data-ttu-id="49b9b-192">www.contoso.com/videos/tvshows</span><span class="sxs-lookup"><span data-stu-id="49b9b-192">www.contoso.com/videos/tvshows</span></span>|<span data-ttu-id="49b9b-193">host.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-193">host.contoso.com</span></span><br /><br /><span data-ttu-id="49b9b-194">host.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-194">host.contoso.com/images</span></span>|
    |<span data-ttu-id="49b9b-195">http://&#42;.contoso.com/&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-195">http://&#42;.contoso.com/&#42;</span></span>|<span data-ttu-id="49b9b-196">contoso.com の下のすべてのサブドメインに一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-196">Matches all subdomains under contoso.com</span></span>|<span data-ttu-id="49b9b-197">developer.contoso.com/resources</span><span class="sxs-lookup"><span data-stu-id="49b9b-197">developer.contoso.com/resources</span></span><br /><br /><span data-ttu-id="49b9b-198">news.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-198">news.contoso.com/images</span></span><br /><br /><span data-ttu-id="49b9b-199">news.contoso.com/videos</span><span class="sxs-lookup"><span data-stu-id="49b9b-199">news.contoso.com/videos</span></span>|<span data-ttu-id="49b9b-200">contoso.host.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-200">contoso.host.com</span></span>|
    |<span data-ttu-id="49b9b-201">http://www.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-201">http://www.contoso.com/images</span></span>|<span data-ttu-id="49b9b-202">単一のフォルダーと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-202">Matches a single folder</span></span>|<span data-ttu-id="49b9b-203">www.contoso.com/images</span><span class="sxs-lookup"><span data-stu-id="49b9b-203">www.contoso.com/images</span></span>|<span data-ttu-id="49b9b-204">www.contoso.com/images/dogs</span><span class="sxs-lookup"><span data-stu-id="49b9b-204">www.contoso.com/images/dogs</span></span>|
    |<span data-ttu-id="49b9b-205">http://www.contoso.com:80</span><span class="sxs-lookup"><span data-stu-id="49b9b-205">http://www.contoso.com:80</span></span>|<span data-ttu-id="49b9b-206">ポート番号を使用し、単一のページと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-206">Matches a single page, by using a port number</span></span>|<span data-ttu-id="49b9b-207">http://www.contoso.com:80</span><span class="sxs-lookup"><span data-stu-id="49b9b-207">http://www.contoso.com:80</span></span>||
    |<span data-ttu-id="49b9b-208">https://www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-208">https://www.contoso.com</span></span>|<span data-ttu-id="49b9b-209">セキュリティで保護された単一のページと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-209">Matches a single, secure page</span></span>|<span data-ttu-id="49b9b-210">https://www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-210">https://www.contoso.com</span></span>|<span data-ttu-id="49b9b-211">http://www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-211">http://www.contoso.com</span></span>|
    |<span data-ttu-id="49b9b-212">http://www.contoso.com/images/&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-212">http://www.contoso.com/images/&#42;</span></span>|<span data-ttu-id="49b9b-213">1 つのフォルダーおよびすべてのサブフォルダーと一致する</span><span class="sxs-lookup"><span data-stu-id="49b9b-213">Matches a single folder and all subfolders</span></span>|<span data-ttu-id="49b9b-214">www.contoso.com/images/dogs</span><span class="sxs-lookup"><span data-stu-id="49b9b-214">www.contoso.com/images/dogs</span></span><br /><br /><span data-ttu-id="49b9b-215">www.contoso.com/images/cats</span><span class="sxs-lookup"><span data-stu-id="49b9b-215">www.contoso.com/images/cats</span></span>|<span data-ttu-id="49b9b-216">www.contoso.com/videos</span><span class="sxs-lookup"><span data-stu-id="49b9b-216">www.contoso.com/videos</span></span>|

-   <span data-ttu-id="49b9b-217">指定することができない入力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-217">The following are examples of some of the inputs that you cannot specify:</span></span>

    -   <span data-ttu-id="49b9b-218">&#42;.com</span><span class="sxs-lookup"><span data-stu-id="49b9b-218">&#42;.com</span></span>

    -   <span data-ttu-id="49b9b-219">&#42;.contoso/&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-219">&#42;.contoso/&#42;</span></span>

    -   <span data-ttu-id="49b9b-220">www.contoso.com/&#42;images</span><span class="sxs-lookup"><span data-stu-id="49b9b-220">www.contoso.com/&#42;images</span></span>

    -   <span data-ttu-id="49b9b-221">www.contoso.com/&#42;images&#42;pigs</span><span class="sxs-lookup"><span data-stu-id="49b9b-221">www.contoso.com/&#42;images&#42;pigs</span></span>

    -   <span data-ttu-id="49b9b-222">www.contoso.com/page&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-222">www.contoso.com/page&#42;</span></span>

    -   <span data-ttu-id="49b9b-223">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="49b9b-223">IP addresses</span></span>

    -   <span data-ttu-id="49b9b-224">https://&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-224">https://&#42;</span></span>

    -   <span data-ttu-id="49b9b-225">http://&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-225">http://&#42;</span></span>

    -   <span data-ttu-id="49b9b-226">http://www.contoso.com:&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-226">http://www.contoso.com:&#42;</span></span>

    -   <span data-ttu-id="49b9b-227">http://www.contoso.com: /&#42;</span><span class="sxs-lookup"><span data-stu-id="49b9b-227">http://www.contoso.com: /&#42;</span></span>

### <a name="how-conflicts-between-the-allow-and-block-list-are-resolved"></a><span data-ttu-id="49b9b-228">許可リストとブロック リストの競合を解決する方法</span><span class="sxs-lookup"><span data-stu-id="49b9b-228">How conflicts between the allow and block list are resolved</span></span>
<span data-ttu-id="49b9b-229">複数の Managed Browser ポリシーがデバイスに展開され、設定が競合する場合、モード (許可またはブロック) と URL の一覧の両方が競合していると判断されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-229">If multiple managed browser policies are deployed to a device and the settings conflict, both the mode (allow or block) and the URL lists are evaluated for conflicts.</span></span> <span data-ttu-id="49b9b-230">競合が発生した場合は、次の動作が適用されます。</span><span class="sxs-lookup"><span data-stu-id="49b9b-230">In case of a conflict, the following behavior applies:</span></span>

-   <span data-ttu-id="49b9b-231">各ポリシーのモードは同じで、URL の一覧が異なる場合、URL はデバイスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-231">If the modes in each policy are the same, but the URL lists are different, the URLs will not be enforced on the device.</span></span>

-   <span data-ttu-id="49b9b-232">各ポリシーのモードが異なり、URL の一覧は同じである場合、URL はデバイスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-232">If the modes in each policy are different, but the URL lists are the same, the URLs will not be enforced on the device.</span></span>

-   <span data-ttu-id="49b9b-233">デバイスが初めて Managed Browser ポリシーを受信するときに、2 つのポリシーが競合する場合、URL はデバイスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="49b9b-233">If a device is receiving managed browser policies for the first time and two policies conflict, the URLs will not be enforced on the device.</span></span> <span data-ttu-id="49b9b-234">**[ポリシー]** ワークスペースの **[ポリシーの競合]** ノードを使用して、競合を表示します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-234">Use the **Policy Conflicts** node of the **Policy** workspace to view the conflicts.</span></span>

-   <span data-ttu-id="49b9b-235">デバイスが Managed Browser ポリシーを既に受信していて、2 番目のポリシーが競合する設定で展開される場合、元の設定がデバイスに残ります。</span><span class="sxs-lookup"><span data-stu-id="49b9b-235">If a device has already received a managed browser policy and a second policy is deployed with conflicting settings, the original settings remain on the device.</span></span> <span data-ttu-id="49b9b-236">**[ポリシー]** ワークスペースの **[ポリシーの競合]** ノードを使用して、競合を表示します。</span><span class="sxs-lookup"><span data-stu-id="49b9b-236">Use the **Policy Conflicts** node of the **Policy** workspace to view the conflicts.</span></span>