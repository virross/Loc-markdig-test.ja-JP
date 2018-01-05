---
title: "事前共有キーを使用した Wi-Fi プロファイルの作成"
titleSuffix: Azure portal
description: "Intune カスタム プロファイルを使用して、事前共有キーで Wi-Fi プロファイルを作成します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8930c574f083b58ed5f1bdbabc3fe0daad545301
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="use-a-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a><span data-ttu-id="2de77-103">カスタム デバイス プロファイルを使用し、事前共有キーを使用した Wi-Fi プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2de77-103">Use a custom device profile to create a Wi-Fi profile with a pre-shared key</span></span>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="2de77-104">Intune の**カスタム デバイス プロファイル**を使用して、事前共有キーを使用して Wi-Fi プロファイルを作成する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2de77-104">Here's how to use Intune’s **Custom device profiles** to create a Wi-Fi profile with a pre-shared key.</span></span> <span data-ttu-id="2de77-105">このトピックでは、EAP ベースの Wi-Fi プロファイルを作成する方法の例も示します。</span><span class="sxs-lookup"><span data-stu-id="2de77-105">This topic also has an example of how to create an EAP-based Wi-Fi profile.</span></span>

> [!NOTE]
> -   <span data-ttu-id="2de77-106">以下のように、そのネットワークに接続しているコンピューターからコードをコピーした方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2de77-106">You might find it easier to copy the code from a computer that connects to that network, as described below.</span></span>
> - <span data-ttu-id="2de77-107">Android では、Johnathon Biersack 氏が提供しているこの [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) を使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="2de77-107">For Android, you also have the option of using this [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) provided by Johnathon Biersack.</span></span>
> -   <span data-ttu-id="2de77-108">OMA-URI 設定をさらに追加することにより、複数のネットワークとキーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2de77-108">You can add multiple networks and keys by adding more OMA-URI settings.</span></span>
> -  <span data-ttu-id="2de77-109">iOS でプロファイルを構成するには、Mac ステーションで Apple Configurator を使用します。</span><span class="sxs-lookup"><span data-stu-id="2de77-109">For iOS, use Apple Configurator on a Mac station to set up the profile.</span></span> <span data-ttu-id="2de77-110">また、Johnathon Biersack 氏が提供する [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2de77-110">Alternatively, use this [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) provided by Johnathon Biersack.</span></span>


1. <span data-ttu-id="2de77-111">Android または Windows 用に事前共有キーを使用した Wi-Fi プロファイル、または EAP ベースの Wi-Fi プロファイルを作成するには、デバイス プロファイルを作成するときに、Wi-Fi プロファイルではなく、そのデバイス プラットフォームの**カスタム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2de77-111">To create a Wi-Fi profile with a pre-shared key for Android or Windows or an EAP-based Wi-Fi profile, when you create a device profile choose **Custom** for that device platform rather than a Wi-Fi profile.</span></span>

2. <span data-ttu-id="2de77-112">名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="2de77-112">Provide a name and description.</span></span>
3. <span data-ttu-id="2de77-113">新しい OMA-URI 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="2de77-113">Add a new OMA-URI setting:</span></span>

   <span data-ttu-id="2de77-114">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="2de77-114">a.</span></span>   <span data-ttu-id="2de77-115">この Wi-Fi ネットワーク設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2de77-115">Enter a name for this Wi-Fi network setting.</span></span>

   <span data-ttu-id="2de77-116">b.</span><span class="sxs-lookup"><span data-stu-id="2de77-116">b.</span></span>   <span data-ttu-id="2de77-117">OMA-URI 設定の説明を入力するか、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="2de77-117">Enter a description of the OMA-URI setting or leave blank.</span></span>

   <span data-ttu-id="2de77-118">c.</span><span class="sxs-lookup"><span data-stu-id="2de77-118">c.</span></span>   <span data-ttu-id="2de77-119">**[データ型]**: **String** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2de77-119">**Data Type**: Set to **String**.</span></span>

   <span data-ttu-id="2de77-120">d.</span><span class="sxs-lookup"><span data-stu-id="2de77-120">d.</span></span>   <span data-ttu-id="2de77-121">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="2de77-121">**OMA-URI**:</span></span>

   - <span data-ttu-id="2de77-122">**Android の場合**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span><span class="sxs-lookup"><span data-stu-id="2de77-122">**For Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span></span>
   - <span data-ttu-id="2de77-123">**Windows の場合**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span><span class="sxs-lookup"><span data-stu-id="2de77-123">**For Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span></span>

   > [!NOTE]
   > <span data-ttu-id="2de77-124">先頭にピリオドを必ず入力してください。</span><span class="sxs-lookup"><span data-stu-id="2de77-124">Be sure to include the dot character at the beginning.</span></span>

   <span data-ttu-id="2de77-125">SSID は、作成しているポリシーの SSID です。</span><span class="sxs-lookup"><span data-stu-id="2de77-125">SSID is the SSID for which you’re creating the policy.</span></span> <span data-ttu-id="2de77-126">たとえば、`./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings` と記述します。</span><span class="sxs-lookup"><span data-stu-id="2de77-126">For example, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span></span>

   <span data-ttu-id="2de77-127">e.</span><span class="sxs-lookup"><span data-stu-id="2de77-127">e.</span></span> <span data-ttu-id="2de77-128">**値フィールド**に、XML コードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2de77-128">**Value Field** is where you paste your XML code.</span></span> <span data-ttu-id="2de77-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2de77-129">Here’s an example.</span></span> <span data-ttu-id="2de77-130">それぞれの値は、ネットワーク設定に適したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2de77-130">Each value should be adapted to your network settings.</span></span> <span data-ttu-id="2de77-131">一部のポインターのコードについては、コメント セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2de77-131">See the comments section of the code for some pointers.</span></span>
4. <span data-ttu-id="2de77-132">**[OK]** を選択して保存し、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2de77-132">Choose **OK**, save, and then assign the policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2de77-133">このポリシーは、ユーザー グループにのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2de77-133">This policy can only be assigned to user groups.</span></span>

<span data-ttu-id="2de77-134">次回各デバイスがチェックインするときに、ポリシーは適用され、そのデバイスに Wi-Fi プロファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2de77-134">The next time each device checks in, the policy will be applied, and a Wi-Fi profile will be created on the device.</span></span> <span data-ttu-id="2de77-135">デバイスは自動的にネットワークに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2de77-135">The device will be able to connect to the network automatically.</span></span>

## <a name="android-or-windows-wi-fi-profile"></a><span data-ttu-id="2de77-136">Android または Windows の Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="2de77-136">Android or Windows Wi-Fi profile</span></span>

<span data-ttu-id="2de77-137">次に、Android または Windows の Wi-Fi プロファイルの XML コードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="2de77-137">Here’s an example of the XML code for an Android or Windows Wi-Fi profile:</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="2de77-138">`<protected>false</protected>` を **false** に設定する必要があります。**true** に設定すると、デバイスはパスワードが暗号化されていると見なし、暗号化の解除を試みます。その結果、接続が失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2de77-138">`<protected>false</protected>`must be set to **false**, as **true** could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.</span></span>
>
>  <span data-ttu-id="2de77-139">`<hex>53534944</hex>` は、`<name><SSID of wifi profile></name>` の 16 進値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2de77-139">`<hex>53534944</hex>` should be set to the hexadecimal value of `<name><SSID of wifi profile></name>`.</span></span>
>  <span data-ttu-id="2de77-140">Windows 10 デバイスは、"*0x87D1FDE8 修復できませんでした*" という間違ったエラーを返す場合があります。それでも、これまでどおり、プロファイルでプロビジョニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2de77-140">Windows 10 devices may return a false *0x87D1FDE8 Remediation failed* error, but will still be provisioned with the profile.</span></span>

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
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

## <a name="eap-based-wi-fi-profile"></a><span data-ttu-id="2de77-141">EAP ベースの Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="2de77-141">EAP-based Wi-Fi profile</span></span>
<span data-ttu-id="2de77-142">次に、EAP ベースの Wi-Fi プロファイルの XML コードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="2de77-142">Here’s  an example of the XML code for an EAP-based Wi-Fi profile:</span></span>

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

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a><span data-ttu-id="2de77-143">既存の Wi-Fi 接続からの XML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2de77-143">Create the XML file from an existing Wi-Fi connection</span></span>
<span data-ttu-id="2de77-144">次のように、既存の Wi-Fi 接続から XML ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2de77-144">You can also create an XML file from an existing Wi-Fi connection:</span></span>
1. <span data-ttu-id="2de77-145">ワイヤレス ネットワークに接続中のコンピューターまたは最近接続されたコンピューターの、C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid} のフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2de77-145">On a computer that is connected to or has recently connected to the wireless network, open the following folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span></span>

    <span data-ttu-id="2de77-146">すべての中から正しいプロファイルを探す必要があるため、多数のワイヤレス ネットワークに接続したことのないコンピューターを使用するのが最良です。</span><span class="sxs-lookup"><span data-stu-id="2de77-146">It’s best to use a computer that has not connected to many wireless networks, because you’ll have to search through each profile to find the right one.</span></span>
2. <span data-ttu-id="2de77-147">XML ファイルを検索し、正しい名前のファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="2de77-147">Search through the XML files to locate the one with the right name.</span></span>
3. <span data-ttu-id="2de77-148">正しい XML ファイルを見つけたら、OMA-URI の設定ページの [データ] フィールドに、XML コードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2de77-148">After you have located the correct XML file, copy and paste the XML code into the Data field of the OMA-URI settings page.</span></span>

## <a name="best-practices"></a><span data-ttu-id="2de77-149">ヒント集</span><span class="sxs-lookup"><span data-stu-id="2de77-149">Best practices</span></span>
<span data-ttu-id="2de77-150">PSK で Wi-Fi プロファイルを展開する前に、デバイスがエンドポイントに直接接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2de77-150">Before you deploy a Wi-Fi profile with PSK, verify that the device can connect to the endpoint directly.</span></span>

<span data-ttu-id="2de77-151">キー (パスワードまたはパスフレーズ) をローテーションで使用するときは、ダウンタウンを予想し、展開を適宜計画します。</span><span class="sxs-lookup"><span data-stu-id="2de77-151">When rotating keys (passwords or passphrases), expect downtime and plan deployments accordingly.</span></span> <span data-ttu-id="2de77-152">新しい Wi-Fi プロファイルは非稼働時間中にプッシュすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2de77-152">Consider pushing new Wi-Fi profiles during non-working hours.</span></span> <span data-ttu-id="2de77-153">また、接続に影響が出る可能性をユーザーに知らせます。</span><span class="sxs-lookup"><span data-stu-id="2de77-153">Also, warn users that connectivity may be impacted.</span></span>
 
<span data-ttu-id="2de77-154">円滑に移行と、適切なタイミングでのポリシー更新の配信を実現するために、デバイスの通信チャネルを 1 つ以上 Intune に対して常に開いておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2de77-154">To ensure a smooth transition experience and deliver timely policy updates, devices must keep at least one open communication channel to Intune.</span></span> <span data-ttu-id="2de77-155">これを行うには、セルラー接続を使用するか、Intune エンドポイントにのみユーザーを接続するゲスト Wi-Fi アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2de77-155">To do this, use cellular connectivity or provide guest Wi-Fi access that connects users only to Intune endpoints.</span></span>


