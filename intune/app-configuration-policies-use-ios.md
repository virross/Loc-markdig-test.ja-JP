---
title: "管理対象の iOS デバイス用アプリ構成ポリシーを追加する | Microsoft Docs"
titlesuffix: Azure portal
description: "アプリ構成ポリシーを使用して、実行時に構成データを iOS アプリに提供する方法について説明します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d63963af4b95d10abca8f90c86a3b28c5781da68
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a><span data-ttu-id="70c15-103">管理対象の iOS デバイス用アプリ構成ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="70c15-103">Add app configuration policies for managed iOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="70c15-104">Microsoft Intune のアプリ構成ポリシーを使用して、ユーザーが iOS アプリを実行するときに設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="70c15-104">Use app configuration policies in Microsoft Intune to supply settings when users run an iOS app.</span></span> <span data-ttu-id="70c15-105">これらのポリシーをユーザーとデバイスに直接割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="70c15-105">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="70c15-106">代わりに、ポリシーをアプリに関連付け、そのアプリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="70c15-106">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="70c15-107">ポリシー設定は、アプリがポリシーをチェックするとき (通常はアプリの初回実行時) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="70c15-107">The policy settings are used when the app checks for them, typically the first time it is run.</span></span>

> [!TIP]
> <span data-ttu-id="70c15-108">この種類のポリシーは現在、iOS 8.0 以降を実行しているデバイスでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="70c15-108">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="70c15-109">次の種類のアプリ インストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="70c15-109">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="70c15-110">**App Store の管理対象 iOS アプリ**</span><span class="sxs-lookup"><span data-stu-id="70c15-110">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="70c15-111">**iOS 用アプリ パッケージ**</span><span class="sxs-lookup"><span data-stu-id="70c15-111">**App package for iOS**</span></span>
>
> <span data-ttu-id="70c15-112">アプリのインストールの種類の詳細については、「[How to add an app to Microsoft Intune (Microsoft Intune にアプリを追加する方法)](apps-add.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c15-112">For more information about app installation types, see [How to add an app to Microsoft Intune](apps-add.md).</span></span>

## <a name="create-an-app-configuration-policy"></a><span data-ttu-id="70c15-113">アプリ構成ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="70c15-113">Create an app configuration policy</span></span>

1. <span data-ttu-id="70c15-114">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="70c15-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="70c15-115">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-115">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="70c15-116">**[モバイル アプリ]** ワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-116">Choose the **Mobile apps** workload.</span></span>
4. <span data-ttu-id="70c15-117">**[管理]** グループの **[アプリ構成ポリシー]** を選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-117">Choose **App configuration policies** in the **Manage** group, and then choose **Add**.</span></span>
5. <span data-ttu-id="70c15-118">次の詳細を設定します。</span><span class="sxs-lookup"><span data-stu-id="70c15-118">Set the following details:</span></span>
    - <span data-ttu-id="70c15-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="70c15-119">**Name**</span></span><br>
      <span data-ttu-id="70c15-120">Azure Portal に表示されるプロファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="70c15-120">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="70c15-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="70c15-121">**Description**</span></span><br>
      <span data-ttu-id="70c15-122">Azure Portal に表示されるプロファイルの説明。</span><span class="sxs-lookup"><span data-stu-id="70c15-122">The description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="70c15-123">**デバイス登録の種類**</span><span class="sxs-lookup"><span data-stu-id="70c15-123">**Device enrollment type**</span></span><br>
      <span data-ttu-id="70c15-124">**[管理対象デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-124">Choose **Managed devices**.</span></span>
6. <span data-ttu-id="70c15-125">**[プラットフォーム]** で **[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-125">Select **iOS** for **Platform**.</span></span>
7.  <span data-ttu-id="70c15-126">**[関連アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-126">Choose **Associated App**.</span></span> <span data-ttu-id="70c15-127">次に、**[関連アプリ]** ブレードで、構成を適用する管理対象アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-127">Then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.</span></span>
8.  <span data-ttu-id="70c15-128">**[構成ポリシーの追加]** ブレードで、**[構成設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-128">On the **Add Configuration Policy** blade, choose **Configuration settings**.</span></span>
9. <span data-ttu-id="70c15-129">**[構成設定の形式]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-129">Select **Configuration settings format**.</span></span> <span data-ttu-id="70c15-130">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-130">Select one of the following:</span></span>
    - <span data-ttu-id="70c15-131">**[[構成デザイナーを使用する]](#Use-the-configuration-designer)**</span><span class="sxs-lookup"><span data-stu-id="70c15-131">**[Use configuration designer](#Use-the-configuration-designer)**</span></span>
    - <span data-ttu-id="70c15-132">**[XML データを入力する](#enter-xml-data)**</span><span class="sxs-lookup"><span data-stu-id="70c15-132">**[Enter XML data](#enter-xml-data)**</span></span>
10. <span data-ttu-id="70c15-133">**[OK]** を選択してから、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-133">Choose **OK**, and then choose **Add**.</span></span>

## <a name="use-configuration-designer"></a><span data-ttu-id="70c15-134">構成デザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="70c15-134">Use configuration designer</span></span>

<span data-ttu-id="70c15-135">Intune に登録されているデバイスかどうかにかかわらず、アプリには構成デザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="70c15-135">You can use the configuration designer for apps on devices that are enrolled or not enrolled in Intune.</span></span> <span data-ttu-id="70c15-136">デザイナーでは、特定の構成キーと値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="70c15-136">The designer lets you configure specific configuration keys and values.</span></span> <span data-ttu-id="70c15-137">各値のデータ型も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70c15-137">You must also specify the data type for each value.</span></span> <span data-ttu-id="70c15-138">設定は、アプリのインストール時に自動で行われます。</span><span class="sxs-lookup"><span data-stu-id="70c15-138">Settings are supplied to apps automatically when they're installed.</span></span>

### <a name="add-a-setting"></a><span data-ttu-id="70c15-139">設定を追加する</span><span class="sxs-lookup"><span data-stu-id="70c15-139">Add a setting</span></span>

1. <span data-ttu-id="70c15-140">構成の各キーと値について、以下を設定します。</span><span class="sxs-lookup"><span data-stu-id="70c15-140">For each key and value in the configuration, set:</span></span>
   - <span data-ttu-id="70c15-141">**構成キー**</span><span class="sxs-lookup"><span data-stu-id="70c15-141">**Configuration key**</span></span><br>
     <span data-ttu-id="70c15-142">特定の設定構成を一意に識別するキー。</span><span class="sxs-lookup"><span data-stu-id="70c15-142">The key that uniquely identifies the specific setting configuration.</span></span>
   - <span data-ttu-id="70c15-143">**値の型**</span><span class="sxs-lookup"><span data-stu-id="70c15-143">**Value type**</span></span><br>
     <span data-ttu-id="70c15-144">構成値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="70c15-144">The data type of the configuration value.</span></span> <span data-ttu-id="70c15-145">整数型、実数型、文字列型、またはブール型があります。</span><span class="sxs-lookup"><span data-stu-id="70c15-145">Types include Integer, Real, String, or Boolean.</span></span>
   - <span data-ttu-id="70c15-146">**構成値**</span><span class="sxs-lookup"><span data-stu-id="70c15-146">**Configuration value**</span></span><br>
     <span data-ttu-id="70c15-147">構成の値。</span><span class="sxs-lookup"><span data-stu-id="70c15-147">The value for the configuration.</span></span>
2. <span data-ttu-id="70c15-148">**[OK]** を選択して構成の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="70c15-148">Choose **OK** to set your configuration settings.</span></span>

### <a name="delete-a-setting"></a><span data-ttu-id="70c15-149">設定の削除</span><span class="sxs-lookup"><span data-stu-id="70c15-149">Delete a setting</span></span>

1. <span data-ttu-id="70c15-150">設定の横の省略記号 (**[...]**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-150">Choose the ellipsis (**...**) next to the setting.</span></span>
2. <span data-ttu-id="70c15-151">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="70c15-151">Select **Delete**.</span></span>

<span data-ttu-id="70c15-152">\{\{ 文字と \}\} 文字を使用できるのはトークンの種類のみであり、他の目的には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="70c15-152">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="enter-xml-data"></a><span data-ttu-id="70c15-153">XML データを入力する</span><span class="sxs-lookup"><span data-stu-id="70c15-153">Enter XML data</span></span>

<span data-ttu-id="70c15-154">Intune に登録されているデバイスのアプリ構成設定を含む XML プロパティ リストを入力または貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="70c15-154">You can type or paste an XML property list that contains the app configuration settings for devices enrolled in Intune.</span></span> <span data-ttu-id="70c15-155">XML プロパティ リストの形式は、構成するアプリによって異なります。</span><span class="sxs-lookup"><span data-stu-id="70c15-155">The format of the XML property list varies depending on the app that you are configuring.</span></span> <span data-ttu-id="70c15-156">使用する正確な形式の詳細については、アプリの供給元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="70c15-156">For details about the exact format to use, contact the supplier of the app.</span></span>

<span data-ttu-id="70c15-157">Intune では XML 形式が検証されます。</span><span class="sxs-lookup"><span data-stu-id="70c15-157">Intune validates the XML format.</span></span> <span data-ttu-id="70c15-158">ただし、Intune では XML プロパティ リスト (PList) が対象アプリで動作するかどうかは確認されません。</span><span class="sxs-lookup"><span data-stu-id="70c15-158">However, Intune does not check that the XML property list (PList) will work with the target app.</span></span>

<span data-ttu-id="70c15-159">XML プロパティ リストの詳細情報:</span><span class="sxs-lookup"><span data-stu-id="70c15-159">To learn more about XML property lists:</span></span>

  -  <span data-ttu-id="70c15-160">「[Microsoft Intune でのモバイル アプリ構成ポリシーを使用した iOS アプリの構成](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c15-160">Read [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>
  -  <span data-ttu-id="70c15-161">iOS Developer Library の「[Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)」 (XML プロパティ リストの概要) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c15-161">Refer to [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>

### <a name="example-format-for-an-app-configuration-xml-file"></a><span data-ttu-id="70c15-162">アプリ構成 XML ファイルの形式の例</span><span class="sxs-lookup"><span data-stu-id="70c15-162">Example format for an app configuration XML file</span></span>

<span data-ttu-id="70c15-163">アプリ構成ファイルを作成する場合、この形式を使用して次の値を 1 つ以上指定できます。</span><span class="sxs-lookup"><span data-stu-id="70c15-163">When you create an app configuration file, you can specify one or more of the following values by using this format:</span></span>

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
### <a name="supported-xml-plist-data-types"></a><span data-ttu-id="70c15-164">サポートされている XML PList データ型</span><span class="sxs-lookup"><span data-stu-id="70c15-164">Supported XML PList data types</span></span>

<span data-ttu-id="70c15-165">Intune は、プロパティ リストで次のデータ型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="70c15-165">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="70c15-166">&lt;integer&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-166">&lt;integer&gt;</span></span>
- <span data-ttu-id="70c15-167">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-167">&lt;real&gt;</span></span>
- <span data-ttu-id="70c15-168">&lt;string&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-168">&lt;string&gt;</span></span>
- <span data-ttu-id="70c15-169">&lt;array&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-169">&lt;array&gt;</span></span>
- <span data-ttu-id="70c15-170">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-170">&lt;dict&gt;</span></span>
- <span data-ttu-id="70c15-171">&lt;true /&gt; または &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="70c15-171">&lt;true /&gt; or &lt;false /&gt;</span></span>

### <a name="tokens-used-in-the-property-list"></a><span data-ttu-id="70c15-172">プロパティ リストで使用されるトークン</span><span class="sxs-lookup"><span data-stu-id="70c15-172">Tokens used in the property list</span></span>

<span data-ttu-id="70c15-173">また、Intune は次のトークンの種類をプロパティ リストでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="70c15-173">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="70c15-174">\{\{userprincipalname\}\} — たとえば、**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="70c15-174">\{\{userprincipalname\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="70c15-175">\{\{mail\}\} — たとえば、**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="70c15-175">\{\{mail\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="70c15-176">\{\{partialupn\}\} — たとえば、**John**</span><span class="sxs-lookup"><span data-stu-id="70c15-176">\{\{partialupn\}\}—for example, **John**</span></span>
- <span data-ttu-id="70c15-177">\{\{accountid\}\} — たとえば、**fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span><span class="sxs-lookup"><span data-stu-id="70c15-177">\{\{accountid\}\}—for example, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span></span>
- <span data-ttu-id="70c15-178">\{\{deviceid\}\} — たとえば、**b9841cd9-9843-405f-be28-b2265c59ef97**</span><span class="sxs-lookup"><span data-stu-id="70c15-178">\{\{deviceid\}\}—for example, **b9841cd9-9843-405f-be28-b2265c59ef97**</span></span>
- <span data-ttu-id="70c15-179">\{\{userid\}\} — たとえば、**3ec2c00f-b125-4519-acf0-302ac3761822**</span><span class="sxs-lookup"><span data-stu-id="70c15-179">\{\{userid\}\}—for example, **3ec2c00f-b125-4519-acf0-302ac3761822**</span></span>
- <span data-ttu-id="70c15-180">\{\{username\}\} — たとえば、**John Doe**</span><span class="sxs-lookup"><span data-stu-id="70c15-180">\{\{username\}\}—for example, **John Doe**</span></span>
- <span data-ttu-id="70c15-181">\{\{serialnumber\}\} — たとえば、**F4KN99ZUG5V2** (iOS デバイスの場合)</span><span class="sxs-lookup"><span data-stu-id="70c15-181">\{\{serialnumber\}\}—for example, **F4KN99ZUG5V2** (for iOS devices)</span></span>
- <span data-ttu-id="70c15-182">\{\{serialnumberlast4digits\}\} — たとえば、**G5V2** (iOS デバイスの場合)</span><span class="sxs-lookup"><span data-stu-id="70c15-182">\{\{serialnumberlast4digits\}\}—for example, **G5V2** (for iOS devices)</span></span>

## <a name="next-steps"></a><span data-ttu-id="70c15-183">次の手順</span><span class="sxs-lookup"><span data-stu-id="70c15-183">Next steps</span></span>

<span data-ttu-id="70c15-184">通常どおり、アプリの[割り当て](apps-deploy.md)と[監視](apps-monitor.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="70c15-184">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>