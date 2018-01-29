---
title: "iOS モバイル アプリ構成ポリシーを使用する"
description: "Intune のモバイル アプリ構成ポリシーを使用して、ユーザーが iOS アプリを実行するときに必要となる可能性がある設定を指定できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8abf6a84227c640838bfbb1f454dca7fe321f08c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a><span data-ttu-id="f924a-103">Microsoft Intune でのモバイル アプリ構成ポリシーを使用した iOS アプリの構成</span><span class="sxs-lookup"><span data-stu-id="f924a-103">Configure iOS apps with mobile app configuration policies in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f924a-104">Microsoft Intune のモバイル アプリ構成ポリシーを使用して、ユーザーがアプリを実行するときに必要となる可能性がある設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f924a-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="f924a-105">たとえば、アプリは次の内容を指定することをユーザーに要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="f924a-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="f924a-106">カスタム ポート番号。</span><span class="sxs-lookup"><span data-stu-id="f924a-106">A custom port number.</span></span>

-   <span data-ttu-id="f924a-107">言語設定。</span><span class="sxs-lookup"><span data-stu-id="f924a-107">Language settings.</span></span>

-   <span data-ttu-id="f924a-108">セキュリティ設定。</span><span class="sxs-lookup"><span data-stu-id="f924a-108">Security settings.</span></span>

-   <span data-ttu-id="f924a-109">会社のロゴなどのブランドの設定。</span><span class="sxs-lookup"><span data-stu-id="f924a-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="f924a-110">ユーザーがこれらの設定を誤って入力すると、ヘルプ デスクの負荷が増加し、新しいアプリの採用が遅くなる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="f924a-110">If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="f924a-111">モバイル アプリ構成ポリシーを使用すると、アプリを実行する前にこれらの設定をポリシー内のユーザーに展開することで、これらの問題を排除できます。</span><span class="sxs-lookup"><span data-stu-id="f924a-111">Mobile app configuration policies can help you eliminate these problems by letting you deploy these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="f924a-112">設定が自動的に指定されるため、ユーザーの操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="f924a-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="f924a-113">これらのポリシーをユーザーやデバイスに直接展開しないでください。</span><span class="sxs-lookup"><span data-stu-id="f924a-113">You do not deploy these policies directly to users and devices.</span></span> <span data-ttu-id="f924a-114">代わりに、ポリシーをアプリに関連付け、そのアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="f924a-114">Instead, you associate a policy with an app, and then deploy the app.</span></span> <span data-ttu-id="f924a-115">ポリシー設定は、アプリがポリシーを確認する際に (通常は初めて実行したときに) 必ず使用されます。</span><span class="sxs-lookup"><span data-stu-id="f924a-115">The policy settings will be used whenever the app checks for them (typically, the first time it is run).</span></span>

> [!TIP]
> <span data-ttu-id="f924a-116">この種類のポリシーは現在、iOS 8.0 以降を実行しているデバイスでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f924a-116">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="f924a-117">次の種類のアプリ インストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f924a-117">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="f924a-118">**App Store の管理対象 iOS アプリ**</span><span class="sxs-lookup"><span data-stu-id="f924a-118">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="f924a-119">**iOS 用アプリ パッケージ**</span><span class="sxs-lookup"><span data-stu-id="f924a-119">**App package for iOS**</span></span>
>
> <span data-ttu-id="f924a-120">アプリのインストールの種類の詳細については、「[Deploy apps with Microsoft Intune](deploy-apps.md)」(Microsoft Intune でアプリを展開する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f924a-120">For more information about app installation types, see [Deploy apps with Microsoft Intune](deploy-apps.md).</span></span>

## <a name="configure-a-mobile-app-configuration-policy"></a><span data-ttu-id="f924a-121">モバイル アプリ構成ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f924a-121">Configure a mobile app configuration policy</span></span>

1.  <span data-ttu-id="f924a-122">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[概要]** &gt; **[ポリシーの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f924a-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="f924a-123">ポリシーの一覧で、**[iOS]**を展開し、**[モバイル アプリの構成]**、**[ポリシーの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f924a-123">In the list of policies, expand **iOS**, choose **Mobile App Configuration**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f924a-124">この種類のポリシーではカスタム設定のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f924a-124">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="f924a-125">推奨設定はありません。</span><span class="sxs-lookup"><span data-stu-id="f924a-125">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="f924a-126">**[ポリシーの作成]** ページの **[全般]** セクションで、名前とモバイル アプリ構成ポリシーのオプションの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="f924a-126">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4.  <span data-ttu-id="f924a-127">このページの **[モバイル アプリ構成ポリシー]** セクションで、必要なアプリの構成設定を含む XML プロパティ リストをボックスに入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f924a-127">In the **Mobile App Configuration Policy** section of the page, in the box, enter or paste an  XML property list that contains the app configuration settings that you want.</span></span> <span data-ttu-id="f924a-128">XML プロパティ リストの形式は、構成するアプリによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f924a-128">The format of the XML property list will vary depending on the app you are configuring.</span></span> <span data-ttu-id="f924a-129">使用する形式の詳細については、アプリの供給元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f924a-129">Contact the supplier of the app for details about the exact format to use.</span></span>

    > [!TIP]
    > <span data-ttu-id="f924a-130">XML プロパティ リストの詳細については、iOS 開発者ライブラリの [XML プロパティ リスト](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f924a-130">To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>

5.  <span data-ttu-id="f924a-131">**[検証]** をクリックして、入力した XML が有効なプロパティ リスト形式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f924a-131">Click **Validate** to ensure that the XML that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f924a-132">**[検証]** をクリックすると、Intune によって、入力した XML が有効な形式であるかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f924a-132">When you click **Validate**, Intune checks that the XML you entered is in a valid format.</span></span> <span data-ttu-id="f924a-133">XML プロパティ リストが関連付けられているアプリで動作するかどうかはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="f924a-133">It does not check that the XML property list will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="f924a-134">終了したら、 **[ポリシーの保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f924a-134">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="f924a-135">新しいポリシーは、 **[構成ポリシー]** ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f924a-135">The new policy is displayed in the **Configuration Policies** node.</span></span>

## <a name="information-about-the-xml-file-format"></a><span data-ttu-id="f924a-136">XML ファイル形式に関する情報</span><span class="sxs-lookup"><span data-stu-id="f924a-136">Information about the XML file format</span></span>

<span data-ttu-id="f924a-137">Intune は、プロパティ リストで次のデータ型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f924a-137">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="f924a-138">&lt;integer&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-138">&lt;integer&gt;</span></span>
- <span data-ttu-id="f924a-139">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-139">&lt;real&gt;</span></span>
- <span data-ttu-id="f924a-140">&lt;string&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-140">&lt;string&gt;</span></span>
- <span data-ttu-id="f924a-141">&lt;array&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-141">&lt;array&gt;</span></span>
- <span data-ttu-id="f924a-142">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-142">&lt;dict&gt;</span></span>
- <span data-ttu-id="f924a-143">&lt;true /&gt; または &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="f924a-143">&lt;true /&gt; or &lt;false /&gt;</span></span>

<span data-ttu-id="f924a-144">データ型の詳細については、iOS 開発者ライブラリの [プロパティ リスト](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f924a-144">For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.</span></span>

<span data-ttu-id="f924a-145">また、Intune は次のトークンの種類をプロパティ リストでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f924a-145">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="f924a-146">\{\{userprincipalname\}\} - (例: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="f924a-146">\{\{userprincipalname\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="f924a-147">\{\{mail\}\} - (例: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="f924a-147">\{\{mail\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="f924a-148">\{\{partialupn\}\} - (例: **John**)</span><span class="sxs-lookup"><span data-stu-id="f924a-148">\{\{partialupn\}\} - (Example: **John**)</span></span>
- <span data-ttu-id="f924a-149">\{\{accountid\}\} - (例: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span><span class="sxs-lookup"><span data-stu-id="f924a-149">\{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span></span>
- <span data-ttu-id="f924a-150">\{\{deviceid\}\} - (例: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span><span class="sxs-lookup"><span data-stu-id="f924a-150">\{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span></span>
- <span data-ttu-id="f924a-151">\{\{userid\}\} - (例: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span><span class="sxs-lookup"><span data-stu-id="f924a-151">\{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span></span>
- <span data-ttu-id="f924a-152">\{\{username\}\} - (例: **John Doe**)</span><span class="sxs-lookup"><span data-stu-id="f924a-152">\{\{username\}\} - (Example: **John Doe**)</span></span>
- <span data-ttu-id="f924a-153">\{\{serialnumber\}\} - (例: **F4KN99ZUG5V2**) iOS デバイスの場合</span><span class="sxs-lookup"><span data-stu-id="f924a-153">\{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices</span></span>
- <span data-ttu-id="f924a-154">\{\{serialnumberlast4digits\}\} - (例: **G5V2**) iOS デバイスの場合</span><span class="sxs-lookup"><span data-stu-id="f924a-154">\{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices</span></span>

<span data-ttu-id="f924a-155">\{\{ 文字と \}\} 文字を使用できるのはトークンの種類のみであり、他の目的には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f924a-155">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a><span data-ttu-id="f924a-156">モバイル アプリ構成ポリシーをアプリに関連付ける</span><span class="sxs-lookup"><span data-stu-id="f924a-156">Associate a mobile app configuration policy with an app</span></span>
<span data-ttu-id="f924a-157">モバイル アプリ構成ポリシーを作成したら、この構成ポリシーの設定を適用する iOS アプリに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f924a-157">After you have created a mobile app configuration policy, you must associate it with the iOS app to which you want the settings in the configuration policy to apply.</span></span>

<span data-ttu-id="f924a-158">これを行うには、「[Microsoft Intune でモバイル デバイスにアプリを展開する](add-apps-for-mobile-devices-in-microsoft-intune.md)」と「[Microsoft Intune を使用してアプリを展開する](deploy-apps-in-microsoft-intune.md)」で説明されているアプリの展開を作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f924a-158">To do this, follow the steps to create an app deployment in [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) and [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span> <span data-ttu-id="f924a-159">ウィザードの **[モバイル アプリの構成]** ページに達したら、**[アプリ構成ポリシー]** ドロップダウン リストからアプリに関連付けるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f924a-159">When you reach the **Mobile App Configuration** page of the wizard, select the policy that you want to associate with the app from the **App Configuration Policy** drop-down list.</span></span>

<span data-ttu-id="f924a-160">その後、引き続き展開し、通常どおりアプリの展開をモニタリングしてください。</span><span class="sxs-lookup"><span data-stu-id="f924a-160">Then, continue to deploy and monitor the app deployment as usual.</span></span>

<span data-ttu-id="f924a-161">展開したアプリをデバイスで実行すると、モバイル アプリ構成ポリシーで構成した設定を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="f924a-161">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="f924a-162">1 つまたは複数のモバイル アプリ構成ポリシーが競合する場合は、どちらのポリシーも適用されません。</span><span class="sxs-lookup"><span data-stu-id="f924a-162">If one or more mobile app configuration policies conflict, neither policy is enforced.</span></span> <span data-ttu-id="f924a-163">競合は Intune 管理コンソールの**ダッシュボード**に報告されます。</span><span class="sxs-lookup"><span data-stu-id="f924a-163">The conflict will be reported in the Intune administration console **Dashboard**.</span></span>

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a><span data-ttu-id="f924a-164">モバイル アプリ構成 XML ファイルの形式の例</span><span class="sxs-lookup"><span data-stu-id="f924a-164">Example format for a mobile app configuration XML file</span></span>

<span data-ttu-id="f924a-165">モバイル アプリ構成ファイルを作成する場合、この形式を使用して次の値を 1 つ以上指定できます。</span><span class="sxs-lookup"><span data-stu-id="f924a-165">When you create a mobile app configuration file, you can specify one or more of the following values by using this format:</span></span>

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>
```
