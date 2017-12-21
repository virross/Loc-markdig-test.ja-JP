---
title: "ネットワーク アクセス制御と Intune の統合"
titlesuffix: Azure portal
description: "ネットワーク アクセス制御 (NAC) と Intune の統合"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d75d996f4166fb2a760d1ccb518ca7a228c1a0d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a><span data-ttu-id="0fa6c-103">ネットワーク アクセス制御 (NAC) と Intune の統合</span><span class="sxs-lookup"><span data-stu-id="0fa6c-103">Network access control (NAC) integration with Intune</span></span>

<span data-ttu-id="0fa6c-104">Intune はネットワーク アクセス制御パートナーと統合して、デバイスがオンプレミスのリソースにアクセスするときに、会社のデータが保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-104">Intune integrates with network access control partners to help organizations secure corporate data when devices try to access on-premises resources.</span></span>

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a><span data-ttu-id="0fa6c-105">Intune と NAC ソリューションが組織のリソースを保護する方法</span><span class="sxs-lookup"><span data-stu-id="0fa6c-105">How do Intune and NAC solutions help protect your organization resources?</span></span>

<span data-ttu-id="0fa6c-106">NAC ソリューションは、Intune でデバイスの登録とコンプライアンスの状態をチェックして、アクセス制御の決定を行います。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-106">NAC solutions are responsible for checking the device enrollment and compliance state with Intune to make access control decisions.</span></span> <span data-ttu-id="0fa6c-107">デバイスが登録されていない場合、または登録されていても Intune のデバイス コンプライアンス ポリシーに準拠していない場合は、登録およびデバイスのコンプライアンス チェックのために、デバイスを Intune にリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-107">If the device is not enrolled or is enrolled and not compliant with Intune device compliance policies, the device should be redirected to Intune for enrollment and/or for a device compliance check.</span></span>

### <a name="example"></a><span data-ttu-id="0fa6c-108">例</span><span class="sxs-lookup"><span data-stu-id="0fa6c-108">Example</span></span>

<span data-ttu-id="0fa6c-109">デバイスが登録されていて Intune に準拠している場合は、NAC ソリューションはデバイスによる会社リソースへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-109">If the device is enrolled and compliant with Intune, the NAC solution should allow the device access to corporate resources.</span></span> <span data-ttu-id="0fa6c-110">たとえば、会社の Wi-Fi リソースまたは VPN リソースにアクセスしようとするユーザーを許可または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-110">For example, users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources.</span></span>

## <a name="nac-and-conditional-access"></a><span data-ttu-id="0fa6c-111">NAC と条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0fa6c-111">NAC and conditional access</span></span>

<span data-ttu-id="0fa6c-112">NAC は条件付きアクセスと連携して、アクセス制御の決定を提供します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-112">NAC works with with conditional access to provide access control decisions.</span></span>

- <span data-ttu-id="0fa6c-113">詳しくは、「[Intune での条件付きアクセスの一般的な使用方法](conditional-access-intune-common-ways-use.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-113">See [common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md) for more details.</span></span>

## <a name="how-the-nac-integration-works"></a><span data-ttu-id="0fa6c-114">NAC 統合のしくみ</span><span class="sxs-lookup"><span data-stu-id="0fa6c-114">How the NAC integration works</span></span>

<span data-ttu-id="0fa6c-115">ここでは、NAC と Intune の統合のしくみの概要を説明します。最初の 3 つのステップは、オンボーディング プロセスの説明です。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-115">Here’s an overview on how the NAC integration works when integrated with Intune, the first three steps explain the onboarding process.</span></span> <span data-ttu-id="0fa6c-116">ステップ 4 ～ 9 では、NAC ソリューションが Intune と統合された後の継続的な動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-116">Once the NAC solution is integrated with Intune, steps 4-9 describe the on-going operation.</span></span>

![NAC が Intune と連携する方法](./media/ca-intune-common-ways-2.png)

1.  <span data-ttu-id="0fa6c-118">NAC パートナー ソリューションを Azure Active Directory (AAD) に登録し、Intune NAC API への委任されたアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-118">Register the NAC partner solution with Azure Active Directory (AAD), and grant delegated permissions to the Intune NAC API.</span></span>

2.  <span data-ttu-id="0fa6c-119">Intune 検出 URL などの適切な設定で、NAC パートナー ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-119">Configure the NAC partner solution with the appropriate settings including the Intune discovery URL.</span></span>

3.  <span data-ttu-id="0fa6c-120">証明書認証用に NAC パートナー ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-120">Configure the NAC partner solution for certificate authentication.</span></span>

4.  <span data-ttu-id="0fa6c-121">ユーザーが、会社の Wi-Fi アクセス ポイントに接続するか、VPN 接続要求を行います。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-121">User connects to corporate Wi-Fi access point or makes a VPN connection request.</span></span>

5.  <span data-ttu-id="0fa6c-122">NAC パートナー ソリューションは、Intune にデバイス情報を転送し、デバイスの登録とコンプライアンスの状態を Intune に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-122">NAC partner solution forwards the device information to Intune, and asks Intune about the device enrollment and compliance state.</span></span>

6.  <span data-ttu-id="0fa6c-123">デバイスが準拠していないか、登録されていない場合は、NAC パートナー ソリューションはユーザーに登録またはデバイスのコンプライアンスの修正を指示します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-123">If the device is not compliant or not enrolled, the NAC partner solution instructs the user to enroll or fix the device compliance.</span></span>

7.  <span data-ttu-id="0fa6c-124">デバイスは、コンプライアンスおよび登録状態の再検証を試みます。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-124">The device attempts to re-verify its compliance and/or the enrollment state.</span></span>

8.  <span data-ttu-id="0fa6c-125">デバイスが登録されて準拠するようになると、NAC パートナー ソリューションは Intune から状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-125">Once the device is enrolled and compliant, NAC partner solution gets the state from Intune.</span></span>

9.  <span data-ttu-id="0fa6c-126">接続が正常に確立されて、デバイスは会社のリソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="0fa6c-126">Connection is successfully established which allows the device access to corporate resources.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fa6c-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0fa6c-127">Next steps</span></span>

-   [<span data-ttu-id="0fa6c-128">Cisco ISE と Intune を統合する</span><span class="sxs-lookup"><span data-stu-id="0fa6c-128">Integrate Cisco ISE with Intune</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [<span data-ttu-id="0fa6c-129">Citrix NetScaler と Intune を統合する</span><span class="sxs-lookup"><span data-stu-id="0fa6c-129">Integrate Citrix NetScaler with Intune</span></span>](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [<span data-ttu-id="0fa6c-130">HP Aruba Clear Pass と Intune を統合する</span><span class="sxs-lookup"><span data-stu-id="0fa6c-130">Integrate HP Aruba Clear Pass with Intune</span></span>](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
