---
title: "PSK を使用する Wi-Fi"
description: "カスタム構成を使用して、事前共有キーを使用した Wi-Fi プロファイルを作成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6cb2fc1948aa87e1b0f37070ed119e1bceef874f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a><span data-ttu-id="4ce54-103">カスタム ポリシーを使用して、事前共有キーを使用した Wi-Fi プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4ce54-103">Use a custom policy to create a Wi-Fi profile with a pre-shared key</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4ce54-104">Intune の**カスタム構成**を使用して、事前共有キーを使用した Wi-Fi プロファイルを作成する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-104">Here's how to use Intune’s **Custom Configuration** to create a Wi-Fi profile with a pre-shared key.</span></span> <span data-ttu-id="4ce54-105">このトピックでは、EAP ベースの Wi-Fi プロファイルを作成する方法の例も示します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-105">This topic also has an example of how to create an EAP-based Wi-Fi profile.</span></span>

> [!NOTE]
> -   <span data-ttu-id="4ce54-106">以下のように、そのネットワークに接続しているコンピューターからコードをコピーした方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ce54-106">You might find it easier to copy the code from a computer that connects to that network, as described below.</span></span>
> - <span data-ttu-id="4ce54-107">Android では、Johnathon Biersack 氏が提供しているこの [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) を使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="4ce54-107">For Android, you also have the option of using this [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) provided by Johnathon Biersack.</span></span>
> -   <span data-ttu-id="4ce54-108">OMA-URI 設定をさらに追加することにより、複数のネットワークとキーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-108">You can add multiple networks and keys by adding more OMA-URI settings.</span></span>
> -  <span data-ttu-id="4ce54-109">iOS でプロファイルを構成するには、Mac ステーションで Apple Configurator を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-109">For iOS, use Apple Configurator on a Mac station to set up the profile.</span></span> <span data-ttu-id="4ce54-110">また、Johnathon Biersack 氏が提供する [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-110">Alternatively, use this [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) provided by Johnathon Biersack.</span></span>


1. <span data-ttu-id="4ce54-111">Android または Windows 用に事前共有キーを使用した Wi-Fi プロファイル、または EAP ベースの Wi-Fi プロファイルを作成する場合、ポリシーを作成するときに、Wi-Fi プロファイルではなく、そのデバイスのプラットフォーム用の**カスタム構成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-111">To create a Wi-Fi profile with a pre-shared key for Android or Windows or an EAP-based Wi-Fi profile, when you create a policy choose **Custom Configuration** for that device platform rather than a Wi-Fi profile.</span></span>

2. <span data-ttu-id="4ce54-112">名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-112">Provide a name and description.</span></span>
3. <span data-ttu-id="4ce54-113">新しい OMA-URI 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-113">Add a new OMA-URI setting:</span></span>

   <span data-ttu-id="4ce54-114">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-114">a.</span></span>   <span data-ttu-id="4ce54-115">この Wi-Fi ネットワーク設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-115">Enter a name for this Wi-Fi network setting.</span></span>

   <span data-ttu-id="4ce54-116">b.</span><span class="sxs-lookup"><span data-stu-id="4ce54-116">b.</span></span>   <span data-ttu-id="4ce54-117">OMA-URI 設定の説明を入力するか、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4ce54-117">Enter a description of the OMA-URI setting or leave blank.</span></span>

   <span data-ttu-id="4ce54-118">c.</span><span class="sxs-lookup"><span data-stu-id="4ce54-118">c.</span></span>   <span data-ttu-id="4ce54-119">**データ型**: "String(XML)" に設定</span><span class="sxs-lookup"><span data-stu-id="4ce54-119">**Data Type**: Set to "String(XML)"</span></span>

   <span data-ttu-id="4ce54-120">d.</span><span class="sxs-lookup"><span data-stu-id="4ce54-120">d.</span></span>   <span data-ttu-id="4ce54-121">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="4ce54-121">**OMA-URI**:</span></span>

   - <span data-ttu-id="4ce54-122">**Android の場合**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span><span class="sxs-lookup"><span data-stu-id="4ce54-122">**For Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span></span>
   - <span data-ttu-id="4ce54-123">**Windows の場合**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span><span class="sxs-lookup"><span data-stu-id="4ce54-123">**For Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ce54-124">先頭にピリオドを必ず入力してください。</span><span class="sxs-lookup"><span data-stu-id="4ce54-124">Be sure to include the dot character at the beginning.</span></span>

   <span data-ttu-id="4ce54-125">SSID は、作成しているポリシーの SSID です。</span><span class="sxs-lookup"><span data-stu-id="4ce54-125">SSID is the SSID for which you’re creating the policy.</span></span> <span data-ttu-id="4ce54-126">たとえば、`./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings` と記述します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-126">For example, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span></span>

   <span data-ttu-id="4ce54-127">e.</span><span class="sxs-lookup"><span data-stu-id="4ce54-127">e.</span></span> <span data-ttu-id="4ce54-128">**値フィールド**に、XML コードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-128">**Value Field** is where you paste your XML code.</span></span> <span data-ttu-id="4ce54-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-129">Here’s an example.</span></span> <span data-ttu-id="4ce54-130">それぞれの値は、ネットワーク設定に適したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce54-130">Each value should be adapted to your network settings.</span></span> <span data-ttu-id="4ce54-131">一部のポインターのコードについては、コメント セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ce54-131">See the comments section of the code for some pointers.</span></span>
4. <span data-ttu-id="4ce54-132">**[OK]** を選択して、保存し、ポリシーをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="4ce54-132">Choose **OK**, save, and then deploy the policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ce54-133">このポリシーは、ユーザー グループにのみデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-133">This policy can only be deployed to user groups.</span></span>

<span data-ttu-id="4ce54-134">次回各デバイスがチェックインするときに、ポリシーは適用され、そのデバイスに Wi-Fi プロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-134">The next time each device checks in, the policy will be applied, and a Wi-Fi profile will be created on the device.</span></span> <span data-ttu-id="4ce54-135">デバイスは自動的にネットワークに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ce54-135">The device will be able to connect to the network automatically.</span></span>
## <a name="android-or-windows-wi-fi-profile"></a><span data-ttu-id="4ce54-136">Android または Windows の Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="4ce54-136">Android or Windows Wi-Fi profile</span></span>

<span data-ttu-id="4ce54-137">次に、Android または Windows の Wi-Fi プロファイルの XML コードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-137">Here’s an example of the XML code for an Android or Windows Wi-Fi profile:</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="4ce54-138">`<protected>false</protected>` を **false** に設定する必要があります。**true** に設定すると、デバイスはパスワードが暗号化されていると見なし、暗号化の解除を試みます。その結果、接続が失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ce54-138">`<protected>false</protected>`must be set to **false**, as **true** could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.</span></span>
> 
>  <span data-ttu-id="4ce54-139">`<hex>53534944</hex>` は、`<name><SSID of wifi profile></name>` の 16 進値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ce54-139">`<hex>53534944</hex>` should be set to the hexadecimal value of `<name><SSID of wifi profile></name>`.</span></span>
>  <span data-ttu-id="4ce54-140">Windows 10 デバイスは、"*0x87D1FDE8 修復できませんでした*" という間違ったエラーを返す場合があります。それでも、これまでどおり、プロファイルでプロビジョニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-140">Windows 10 devices may return a false *0x87D1FDE8 Remediation failed* error, but will still be provisioned with the profile.</span></span>

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
<hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>        </SSID>
        <nonBroadcast>false</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication><Type of authentication></authentication>
            <encryption><Type of encryption></encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a><span data-ttu-id="4ce54-141">EAP ベースの Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="4ce54-141">EAP-based Wi-Fi profile</span></span>
<span data-ttu-id="4ce54-142">次に、EAP ベースの Wi-Fi プロファイルの XML コードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-142">Here’s  an example of the XML code for an EAP-based Wi-Fi profile:</span></span>

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a><span data-ttu-id="4ce54-143">既存の Wi-Fi 接続からの XML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="4ce54-143">Create the XML file from an existing Wi-Fi connection</span></span>
<span data-ttu-id="4ce54-144">次のように、既存の Wi-Fi 接続から XML ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-144">You can also create an XML file from an existing Wi-Fi connection:</span></span>
1. <span data-ttu-id="4ce54-145">ワイヤレス ネットワークに接続中のコンピューターまたは最近接続されたコンピューターの、C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid} のフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-145">On a computer that is connected to or has recently connected to the wireless network, open the following folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span></span>

    <span data-ttu-id="4ce54-146">すべての中から正しいプロファイルを探す必要があるため、多数のワイヤレス ネットワークに接続したことのないコンピューターを使用するのが最良です。</span><span class="sxs-lookup"><span data-stu-id="4ce54-146">It’s best to use a computer that has not connected to many wireless networks, because you’ll have to search through each profile to find the right one.</span></span>
2. <span data-ttu-id="4ce54-147">XML ファイルを検索し、正しい名前のファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-147">Search through the XML files to locate the one with the right name.</span></span>
3. <span data-ttu-id="4ce54-148">正しい XML ファイルを見つけたら、OMA-URI の設定ページの [データ] フィールドに、XML コードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-148">After you have located the correct XML file, copy and paste the XML code into the Data field of the OMA-URI settings page.</span></span>

## <a name="deploy-the-policy"></a><span data-ttu-id="4ce54-149">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="4ce54-149">Deploy the policy</span></span>

1.  <span data-ttu-id="4ce54-150">**[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-150">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>

2.  <span data-ttu-id="4ce54-151">**[展開の管理]** ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-151">In the **Manage Deployment** dialog box:</span></span>

    -   <span data-ttu-id="4ce54-152">**ポリシーを展開するには** - ポリシーを展開する対象となる 1 つ以上のグループを選択して、**[追加]** &gt; **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-152">**To deploy the policy** - Select one or more groups to which you want to deploy the policy, and then choose **Add** &gt; **OK**.</span></span>

    -   <span data-ttu-id="4ce54-153">**ポリシーを展開せずにダイアログ ボックスを閉じるには**、**[キャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ce54-153">**To close the dialog box without deploying it** - Choose **Cancel**.</span></span>

<span data-ttu-id="4ce54-154">デプロイ済みポリシーを選択すると、ポリシー一覧の下部にデプロイについての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ce54-154">When you select a deployed policy, you can view more information about the deployment in the lower part of the policies list.</span></span>

### <a name="see-also"></a><span data-ttu-id="4ce54-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ce54-155">See also</span></span>
[<span data-ttu-id="4ce54-156">Microsoft Intune での Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="4ce54-156">Wi-Fi connections in Microsoft Intune</span></span>](wi-fi-connections-in-microsoft-intune.md)
