---
title: "Microsoft Intune VPN プロファイルのカスタム構成"
description: "Intune でカスタム構成を使用して VPN プロファイルを作成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3c04fcdadbc3ec2e121b4718b950a7e5e58700fe
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a><span data-ttu-id="e8a3b-103">Microsoft Intune VPN プロファイルのカスタム構成</span><span class="sxs-lookup"><span data-stu-id="e8a3b-103">Custom configurations for Microsoft Intune VPN profiles</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a><span data-ttu-id="e8a3b-104">カスタム構成を作成する</span><span class="sxs-lookup"><span data-stu-id="e8a3b-104">Create a custom configuration</span></span>
<span data-ttu-id="e8a3b-105">Intune のカスタム構成ポリシーを使用して、以下の VPN プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="e8a3b-106">Android 4 以降が実行されているデバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="e8a3b-107">Android for Work デバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-107">Android for Work devices</span></span>
* <span data-ttu-id="e8a3b-108">Windows 8.1 以降を実行する登録済みのデバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-108">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="e8a3b-109">Windows Phone 8.1 以降が実行されているデバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-109">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="e8a3b-110">Windows 10 デスクトップを実行する登録済みのデバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-110">Enrolled devices that run Windows 10 desktop</span></span>
* <span data-ttu-id="e8a3b-111">Windows 10 Mobile を実行するデバイス</span><span class="sxs-lookup"><span data-stu-id="e8a3b-111">Device that run Windows 10 Mobile</span></span>

<span data-ttu-id="e8a3b-112">この種のポリシーは、標準的な Intune VPN ポリシーに、使用する設定が含まれていない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-112">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <a name="to-create-a-custom-configuration-policy"></a><span data-ttu-id="e8a3b-113">カスタム構成ポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="e8a3b-113">To create a custom configuration policy:</span></span>

   1. <span data-ttu-id="e8a3b-114">[Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[ポリシーの追加]** > *<プラットフォームを展開>* > **[カスタム構成]** > **[ポリシーの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-114">In the [Intune admin console](https://manage.microsoft.com), choose **Policy** > **Add Policy** > *Expand platform* > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="e8a3b-115">ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-115">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="e8a3b-116">指定する必要がある URI の設定ごとに、**[追加]** を選択し、必要な情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-116">For each URI setting you want to specify, choose **Add**, and provide the requested information.</span></span> <span data-ttu-id="e8a3b-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-117">Here's an example:</span></span>

   ![VPN プロファイルのカスタム構成ダイアログ ボックス](./media/Intune_Add_VPN_URI.png)

   4.  <span data-ttu-id="e8a3b-119">すべての URI 設定を入力したら、**[ポリシーの保存]** を選択した後、ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-119">After you've entered all of URI settings, choose **Save policy**, and then deploy the policy.</span></span>

<span data-ttu-id="e8a3b-120">その後、通常どおり[ポリシーを展開](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)します。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-120">Then, [deploy the policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) as normal.</span></span>

## <a name="example-uri-settings"></a><span data-ttu-id="e8a3b-121">URI 設定の例</span><span class="sxs-lookup"><span data-stu-id="e8a3b-121">Example URI settings</span></span>

<span data-ttu-id="e8a3b-122">これらの設定は、Contoso という架空の会社で VPN のカスタム構成を作成する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-122">These settings can be used to create a custom configuration for a VPN in a fictitious company called Contoso.</span></span>
<span data-ttu-id="e8a3b-123">使用できるすべての設定の詳細については、「[VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-123">For full details about all the settings you can use, see [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).</span></span>

<span data-ttu-id="e8a3b-124">**Contoso のネイティブ VPN (IKEv2):**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-124">**Native Contoso VPN (IKEv2):**</span></span><br />
<span data-ttu-id="e8a3b-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span><span class="sxs-lookup"><span data-stu-id="e8a3b-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span></span>

<span data-ttu-id="e8a3b-126">**vpn.contoso.com**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-126">**vpn.contoso.com**</span></span><br />
<span data-ttu-id="e8a3b-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span><span class="sxs-lookup"><span data-stu-id="e8a3b-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span></span>

<span data-ttu-id="e8a3b-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span><span class="sxs-lookup"><span data-stu-id="e8a3b-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span></span>

<span data-ttu-id="e8a3b-129">**SplitTunnel**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-129">**SplitTunnel**</span></span><br />
<span data-ttu-id="e8a3b-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span><span class="sxs-lookup"><span data-stu-id="e8a3b-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span></span>

<span data-ttu-id="e8a3b-131">**Eap**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-131">**Eap**</span></span><br />
<span data-ttu-id="e8a3b-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span><span class="sxs-lookup"><span data-stu-id="e8a3b-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span></span>
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
<span data-ttu-id="e8a3b-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span></span><br />
<span data-ttu-id="e8a3b-134">True</span><span class="sxs-lookup"><span data-stu-id="e8a3b-134">True</span></span>

<span data-ttu-id="e8a3b-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span></span><br />
<span data-ttu-id="e8a3b-136">1</span><span class="sxs-lookup"><span data-stu-id="e8a3b-136">1</span></span>

<span data-ttu-id="e8a3b-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span></span><br />
<span data-ttu-id="e8a3b-138">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8a3b-138">Corp.Contoso.com</span></span>

<span data-ttu-id="e8a3b-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span></span><br />
<span data-ttu-id="e8a3b-140">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8a3b-140">Corp.Contoso.com</span></span>

<span data-ttu-id="e8a3b-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span></span><br />
<span data-ttu-id="e8a3b-142">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8a3b-142">Corp.Contoso.com</span></span>

<span data-ttu-id="e8a3b-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span></span><br />
<span data-ttu-id="e8a3b-144">10.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e8a3b-144">10.0.0.0</span></span>

<span data-ttu-id="e8a3b-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span></span><br />
<span data-ttu-id="e8a3b-146">8</span><span class="sxs-lookup"><span data-stu-id="e8a3b-146">8</span></span>

<span data-ttu-id="e8a3b-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span></span><br />
<span data-ttu-id="e8a3b-148">true</span><span class="sxs-lookup"><span data-stu-id="e8a3b-148">true</span></span>

<span data-ttu-id="e8a3b-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span></span><br />
<span data-ttu-id="e8a3b-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="e8a3b-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="e8a3b-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span></span><br />
<span data-ttu-id="e8a3b-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="e8a3b-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="e8a3b-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span></span><br />
<span data-ttu-id="e8a3b-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a3b-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="e8a3b-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span></span><br />
<span data-ttu-id="e8a3b-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="e8a3b-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="e8a3b-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="e8a3b-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span></span><br />
<span data-ttu-id="e8a3b-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a3b-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="e8a3b-159">これらの設定の使用方法に関するご質問、またはこれらの設定により行われることの詳細については、[構成サービス プロバイダー (CSP) に関するドキュメント](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8a3b-159">For any questions about how these settings should be used or more details about what they do, customers should refer to the [configuration service provider (CSP) documentation](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).</span></span>

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a><span data-ttu-id="e8a3b-160">PulseSecure での Android のアプリごとの VPN 用の URI 設定</span><span class="sxs-lookup"><span data-stu-id="e8a3b-160">URI settings for Android per-app VPN on PulseSecure</span></span>
### <a name="custom-uri-for-package-list"></a><span data-ttu-id="e8a3b-161">パッケージ リスト用のカスタム URI</span><span class="sxs-lookup"><span data-stu-id="e8a3b-161">CUSTOM URI FOR PACKAGE LIST</span></span>
-  <span data-ttu-id="e8a3b-162">データ型 = 文字列</span><span class="sxs-lookup"><span data-stu-id="e8a3b-162">Data type = String</span></span>
-  <span data-ttu-id="e8a3b-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span><span class="sxs-lookup"><span data-stu-id="e8a3b-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span></span>
-  <span data-ttu-id="e8a3b-164">値 = 区切り記号で区切られたパッケージ リスト</span><span class="sxs-lookup"><span data-stu-id="e8a3b-164">Value = Delimiter separated package list.</span></span>
   - <span data-ttu-id="e8a3b-165">区切り記号: セミコロン (;)、コロン (:)、コンマ (,)、パイプ (|)</span><span class="sxs-lookup"><span data-stu-id="e8a3b-165">Delimiters:  semicolon (;), colon (:), comma (,), Pipe (|)</span></span>

<span data-ttu-id="e8a3b-166">例:</span><span class="sxs-lookup"><span data-stu-id="e8a3b-166">Examples:</span></span>
- <span data-ttu-id="e8a3b-167">com.android.chrome</span><span class="sxs-lookup"><span data-stu-id="e8a3b-167">com.android.chrome</span></span>
- <span data-ttu-id="e8a3b-168">com.android.chrome;com.android.browser</span><span class="sxs-lookup"><span data-stu-id="e8a3b-168">com.android.chrome;com.android.browser</span></span>

### <a name="custom-uri-for-mode-optional"></a><span data-ttu-id="e8a3b-169">モード用のカスタム URI (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e8a3b-169">CUSTOM URI FOR MODE (OPTIONAL)</span></span>
- <span data-ttu-id="e8a3b-170">データ型 = 文字列</span><span class="sxs-lookup"><span data-stu-id="e8a3b-170">Data Type = String</span></span>
- <span data-ttu-id="e8a3b-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span><span class="sxs-lookup"><span data-stu-id="e8a3b-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span></span>

> <span data-ttu-id="e8a3b-172">注</span><span class="sxs-lookup"><span data-stu-id="e8a3b-172">Notes</span></span>
> - <span data-ttu-id="e8a3b-173">カスタム プロファイルに割り当てた*名前*を使用します</span><span class="sxs-lookup"><span data-stu-id="e8a3b-173">Use the same *name* that you assigned to the custom profile</span></span>
> - <span data-ttu-id="e8a3b-174">指定可能な値: *GLOBAL*、*WHITELIST*、*BLACKLIST*</span><span class="sxs-lookup"><span data-stu-id="e8a3b-174">Possible values: *GLOBAL*, *WHITELIST*, *BLACKLIST*</span></span>
> - <span data-ttu-id="e8a3b-175">PackageList が指定されていない場合の既定値は *GLOBAL* です (システム全体のプロファイルと下位互換)</span><span class="sxs-lookup"><span data-stu-id="e8a3b-175">Defaults to *GLOBAL* if no PackageList is provided (backward compatibility with system-wide profiles)</span></span>
> - <span data-ttu-id="e8a3b-176">PackageList が指定されている場合の既定値は *WHITELIST* です</span><span class="sxs-lookup"><span data-stu-id="e8a3b-176">Defaults to *WHITELIST* if a PackageList is provided</span></span>


### <a name="see-also"></a><span data-ttu-id="e8a3b-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8a3b-177">See also</span></span>
[<span data-ttu-id="e8a3b-178">Microsoft Intune での VPN 接続</span><span class="sxs-lookup"><span data-stu-id="e8a3b-178">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
