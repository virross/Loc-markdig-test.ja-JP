---
title: "Intune での条件付きアクセス"
titlesuffix: Azure portal
description: "Intune での条件付きアクセスの一般的な使用方法"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3509dbf1bc0b415803bb003c342f5b5df69e235
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="common-ways-to-use-conditional-access-with-intune"></a><span data-ttu-id="14f9e-103">Intune での条件付きアクセスの一般的な使用方法</span><span class="sxs-lookup"><span data-stu-id="14f9e-103">Common ways to use conditional access with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="14f9e-104">組織における条件付きアクセスのコンプライアンスを推進するには、Intune モバイル デバイス コンプライアンス ポリシーと Intune モバイル アプリケーション管理 (MAM) の機能を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-104">You need to configure Intune mobile device compliance policy, and the Intune mobile application management (MAM) capabilities to drive conditional access compliance at your organization.</span></span> <span data-ttu-id="14f9e-105">Intune での条件付きアクセスの一般的な使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-105">Let’s talk about the common ways to use conditional access with Intune.</span></span>

## <a name="device-based-conditional-access"></a><span data-ttu-id="14f9e-106">デバイス ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-106">Device-based conditional access</span></span>

<span data-ttu-id="14f9e-107">Intune と Azure Active Directory が連携することで、管理されたデバイスと準拠デバイスのみが電子メール、Office 365 サービス、サービスとしてのソフトウェア (SaaS) アプリ、および[オンプレミス アプリ](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-107">Intune and Azure Active Directory work together to make sure only managed and compliant devices are allowed access to email, Office 365 services, Software as a service (SaaS) apps, and [on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).</span></span> <span data-ttu-id="14f9e-108">また、Azure Active Directory では、ドメインに参加しているコンピューターや、Intune に登録されているモバイル デバイスのみが Office 365 サービスにアクセスできるようにするポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-108">Additionally, you can set a policy in Azure Active Directory to only enable computers that are domain-joined, or mobile devices that are enrolled in Intune to access Office 365 services.</span></span>

<span data-ttu-id="14f9e-109">Intune には、デバイスのコンプライアンス対応状態を評価する、デバイス コンプライアンス ポリシーの機能があります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-109">Intune provides device compliance policy capabilities that evaluate the compliance status of the devices.</span></span> <span data-ttu-id="14f9e-110">コンプライアンス対応状態は Azure Active Directory に報告され、ユーザーが会社のリソースにアクセスしようとしたときに、Azure Active Directory で作成された条件付きアクセスのポリシーを適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-110">The compliance status is reported to Azure Active Directory that uses it to enforce the conditional access policy created in Azure Active Directory when the user tries to access company resources.</span></span>

<span data-ttu-id="14f9e-111">[新しい Azure Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)では、Exchange Online や他の Office 365 製品のデバイス ベースの条件付きアクセス ポリシーが Azure Portal で構成されるようになります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-111">Starting at the [new Azure portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), device-based conditional access policies for Exchange online and other Office 365 products are configured through the Azure portal.</span></span>

-   <span data-ttu-id="14f9e-112">Azure Active Directory の条件付きアクセスについて詳しくは、[こちら](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-112">Learn more about [conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span></span>

-   <span data-ttu-id="14f9e-113">Intune のデバイス コンプライアンスについて詳しくは、[こちら](device-compliance.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-113">Learn more about [what is Intune device compliance](device-compliance.md).</span></span>

-   <span data-ttu-id="14f9e-114">Intune で条件付きアクセスを使用した、電子メール、Office 365、およびその他のサービスの保護について詳しくは、[こちら](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-114">Learn more about [protecting e-mail, Office 365, and other services using conditional access with Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span></span>

### <a name="conditional-access-for-exchange-on-premises"></a><span data-ttu-id="14f9e-115">Exchange On-Premises の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-115">Conditional access for Exchange on-premises</span></span>

<span data-ttu-id="14f9e-116">条件付きアクセスを使用すると、デバイス コンプライアンス ポリシーと登録状態に基づいて、**Exchange On-Premises** へのアクセスを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-116">Conditional access can be used to allow or block access to **Exchange on-premises** based on the device compliance policies and enrollment state.</span></span> <span data-ttu-id="14f9e-117">条件付きアクセスをデバイス コンプライアンス ポリシーと組み合わせて使用した場合は、準拠デバイスのみが Exchange On-Premises へのアクセスを許可されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-117">When conditional access is used in combination with a device compliance policy, only compliant devices are allowed access to Exchange on-premises.</span></span>

<span data-ttu-id="14f9e-118">条件付きアクセスの詳細設定を構成して、次のような細かい制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-118">You can configure advanced settings in conditional access for more granular control such as:</span></span>

-   <span data-ttu-id="14f9e-119">特定のプラットフォームを許可またはブロックする。</span><span class="sxs-lookup"><span data-stu-id="14f9e-119">Allow or block certain platforms.</span></span>

-   <span data-ttu-id="14f9e-120">Intune で管理されていないデバイスを即時ブロックする。</span><span class="sxs-lookup"><span data-stu-id="14f9e-120">Immediately block devices that are not managed by Intune.</span></span>

<span data-ttu-id="14f9e-121">デバイス コンプライアンスと条件付きアクセス ポリシーが適用されると、Exchange On-Premises へのアクセスで使用されるデバイスがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-121">Any device used to access Exchange on-premises is checked for compliance when device compliance and conditional access policies are applied.</span></span>

<span data-ttu-id="14f9e-122">デバイスが条件を満たしていない場合、エンド ユーザーは、デバイス非準拠の原因である問題を修正するためのデバイス登録プロセスを提示されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-122">When devices do not meet the conditions set, the end user is guided through the process of enrolling the device to fix the issue that is making the device non-compliant.</span></span>

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a><span data-ttu-id="14f9e-123">Exchange On-Premises の条件付きアクセスのしくみ</span><span class="sxs-lookup"><span data-stu-id="14f9e-123">How conditional access for Exchange on-premises works</span></span>

<span data-ttu-id="14f9e-124">Intune Exchange Connector は Exchange サーバーに存在するすべての Exchange Active Sync (EAS) レコードを収集するため、Intune はこれらの EAS レコードを取得して、Intune デバイス レコードにマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-124">The Intune Exchange connector pulls in all the Exchange Active Sync (EAS) records that exist at the Exchange server so Intune can take these EAS records and map them to Intune device records.</span></span> <span data-ttu-id="14f9e-125">これらのレコードはデバイスに登録され、Intune によって認識されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-125">These records are devices enrolled and recognized by Intune.</span></span> <span data-ttu-id="14f9e-126">このプロセスにより、電子メールへのアクセスが許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-126">This process allows or blocks e-mail access.</span></span>

<span data-ttu-id="14f9e-127">EAS レコードが新しいために Intune が認識しない場合、Intune は電子メールへのアクセスをブロックするコマンドレットを発行します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-127">If the EAS record is brand new, and Intune is not aware of it, Intune issues a command-let that blocks access to e-mail.</span></span> <span data-ttu-id="14f9e-128">次の図で、このプロセスのしくみについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-128">Here are more details on how this process works:</span></span>

![Exchange On-premises と条件付きアクセス (CA) のフローチャート](./media/ca-intune-common-ways-1.png)

1.  <span data-ttu-id="14f9e-130">ユーザーは、Exchange On-premises 2010 SP1 以降でホストされている会社の電子メールにアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="14f9e-130">User tries to access corporate email, which is hosted on Exchange on-premises 2010 SP1 or later.</span></span>

2.  <span data-ttu-id="14f9e-131">デバイスが Intune で管理されていない場合は、電子メールへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-131">If the device is not managed by Intune, it will be blocked access to email.</span></span> <span data-ttu-id="14f9e-132">Intune は、EAS クライアントにブロック通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-132">Intune sends block notification to the EAS client.</span></span>

3.  <span data-ttu-id="14f9e-133">EAS はブロック通知を受信し、該当デバイスを検疫に移動して、検疫メールを送信します。このメールには、ユーザーがデバイスを登録するためのリンクを含む修復手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="14f9e-133">EAS receives block notification, moves the device to quarantine, and sends the quarantine email with remediation steps that contain links so the users can enroll their devices.</span></span>

4.  <span data-ttu-id="14f9e-134">Workplace Join プロセスが発生します。これは、Intune でデバイスを管理する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="14f9e-134">The Workplace join process happens, which is the first step to have the device managed by Intune.</span></span>

5.  <span data-ttu-id="14f9e-135">デバイスが Intune に登録されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-135">The device gets enrolled into Intune.</span></span>

6.  <span data-ttu-id="14f9e-136">Intune により EAS レコードとデバイス レコードがマップされ、デバイスのコンプライアンス対応状態が保存されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-136">Intune maps the EAS record to a device record, and saves the device compliance state.</span></span>

7.  <span data-ttu-id="14f9e-137">Azure AD Device Registration プロセスにより EAS クライアント ID が登録され、Intune デバイス レコードと EAS クライアント ID の間のリレーションシップが作成されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-137">The EAS client ID gets registered by the Azure AD Device Registration process, which creates a relationship between the Intune device record, and the EAS client ID.</span></span>

8.  <span data-ttu-id="14f9e-138">Azure AD Device Registration により、デバイスの状態に関する情報が保存されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-138">The Azure AD Device Registration saves the device state information.</span></span>

9.  <span data-ttu-id="14f9e-139">ユーザーが条件付きアクセス ポリシーを満たしている場合、Intune は Intune Exchange Connector を介して、メールボックスの同期を許可するコマンドレットを発行します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-139">If the user meets the conditional access policies, Intune issues a command-let through the Intune Exchange connector that allows the mailbox to sync.</span></span>

10. <span data-ttu-id="14f9e-140">Exchange サーバーが EAS クライアントに通知を送信し、ユーザーは電子メールにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-140">Exchange server sends the notification to EAS client so the user can access e-mail.</span></span>

#### <a name="whats-the-intune-role"></a><span data-ttu-id="14f9e-141">Intune ロールとは</span><span class="sxs-lookup"><span data-stu-id="14f9e-141">What’s the Intune role?</span></span>

<span data-ttu-id="14f9e-142">Intune はデバイスの状態を評価し、管理します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-142">Intune evaluates and manage the device state.</span></span>

#### <a name="whats-the-exchange-server-role"></a><span data-ttu-id="14f9e-143">Exchange サーバー ロールとは</span><span class="sxs-lookup"><span data-stu-id="14f9e-143">What’s the Exchange server role?</span></span>

<span data-ttu-id="14f9e-144">Exchange サーバーは、デバイスを検疫に移動するための API とインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-144">Exchange server provides API and infrastructure to move devices to its quarantine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14f9e-145">デバイスのコンプライアンスを評価するために、デバイスを使用するユーザーにコンプライアンス プロファイルを割り当てる必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-145">Keep in mind that the user who’s using the device must have a compliance profile assigned to them so the device to be evaluated for compliance.</span></span> <span data-ttu-id="14f9e-146">コンプライアンス ポリシーがユーザーに展開されていない場合、デバイスは準拠したものと見なされ、アクセス制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="14f9e-146">If no compliance policy is deployed to the user, the device is treated as compliant and no access restrictions are applied.</span></span>

### <a name="conditional-access-based-on-network-access-control"></a><span data-ttu-id="14f9e-147">ネットワーク アクセス制御に基づいた条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-147">Conditional access based on network access control</span></span>

<span data-ttu-id="14f9e-148">Cisco ISE、Aruba Clear Pass、Citrix NetScaler などのパートナーと統合された Intune は、Intune 登録とデバイスのコンプライアンス対応状態に基づいたアクセス制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-148">Intune integrated with partners like Cisco ISE, Aruba Clear Pass, and Citrix NetScaler to provide access controls based on the Intune enrollment and the device compliance state.</span></span>

<span data-ttu-id="14f9e-149">ユーザーが会社の Wi-Fi や VPN リソースにアクセスしようとすると、デバイスが管理されているか、Intune デバイス コンプライアンス ポリシーに準拠しているかどうかに基づいて、アクセスが許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-149">Users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources based on whether the device is managed and compliant with Intune device compliance policies.</span></span>

-   <span data-ttu-id="14f9e-150">NAC と Intune の統合について詳しくは、[こちら](network-access-control-integrate.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-150">Learn more about the [NAC integration with Intune](network-access-control-integrate.md).</span></span>

### <a name="conditional-access-based-on-device-risk"></a><span data-ttu-id="14f9e-151">デバイスのリスクに基づいた条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-151">Conditional access based on device risk</span></span>

<span data-ttu-id="14f9e-152">Intune は、モバイル デバイス上のマルウェア、トロイの木馬、およびその他の脅威を検出するためのセキュリティ ソリューションを提供する Mobile Threat Defense ベンダーと提携しました。</span><span class="sxs-lookup"><span data-stu-id="14f9e-152">Intune partnered with Mobile Threat Defense vendors that provides a security solution to detect malwares, Trojans, and other threats on mobile devices.</span></span>

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a><span data-ttu-id="14f9e-153">Intune と Mobile Threat Defense の統合のしくみ</span><span class="sxs-lookup"><span data-stu-id="14f9e-153">How the Intune and Mobile Threat Defense integration works</span></span>

<span data-ttu-id="14f9e-154">モバイル デバイスに Mobile Threat Defense エージェントがインストールされると、モバイル デバイスで脅威が検出されたかどうかに関するコンプライアンス対応状態のメッセージが、エージェントから Intune に返信されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-154">When mobile devices have the Mobile Threat Defense agent installed, the agent can send compliance state messages back to Intune reporting if a threat has been found in the mobile device itself.</span></span>

<span data-ttu-id="14f9e-155">Intune と Mobile Threat Defense の統合は、デバイスのリスクに基づいた条件付きアクセスの決定において重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="14f9e-155">The Intune and mobile threat defense integration plays a factor at the conditional access decisions based on device risk.</span></span>

-   <span data-ttu-id="14f9e-156">Intune Mobile Threat Defense について詳しくは、[こちら](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-156">Learn more about [Intune mobile threat defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).</span></span>

### <a name="conditional-access-for-windows-pcs"></a><span data-ttu-id="14f9e-157">Windows PC の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-157">Conditional access for Windows PCs</span></span>

<span data-ttu-id="14f9e-158">PC の条件付きアクセスでは、モバイル デバイスで利用できる機能と同様の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-158">Conditional access for PCs provide similar capabilities available for mobile devices.</span></span> <span data-ttu-id="14f9e-159">Intune で PC を管理する場合に条件付きアクセスを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-159">Let’s talk about the ways you can use conditional access when managing PCs with Intune.</span></span>

#### <a name="corporate-owned"></a><span data-ttu-id="14f9e-160">企業所有</span><span class="sxs-lookup"><span data-stu-id="14f9e-160">Corporate-owned</span></span>

-   <span data-ttu-id="14f9e-161">**オンプレミス AD ドメインへの参加:** AD のグループ ポリシーや System Center Configuration Manager を使用して PC をすでに管理しているという事実に満足している組織にとって、これはもっとも一般的な条件付きアクセスの展開オプションです。</span><span class="sxs-lookup"><span data-stu-id="14f9e-161">**On premises AD domain joined:** This has been the most common conditional access deployment option for organizations, whose are reasonable comfortable with the fact they’re already managing their PCs through AD group policies and/or with System Center Configuration Manager.</span></span>

-   <span data-ttu-id="14f9e-162">**Azure AD ドメインへの参加と Intune の管理:** このシナリオは、Choose Your Own Device (CYOD) と、ローミング ラップトップを会社のネットワークにほとんど接続しないシナリオを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="14f9e-162">**Azure AD domain joined and Intune management:** This scenario is typically geared to Choose Your Own Device (CYOD), and roaming laptop scenarios where these devices are rarely connected to corporate-network.</span></span> <span data-ttu-id="14f9e-163">デバイスは Azure AD に参加し、Intune に登録されます。これにより、オンプレミス AD とドメイン コントローラーへの依存が排除されます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-163">The device joins to the Azure AD and gets enrolled to Intune, which removes any dependency on on-premises AD, and domain controllers.</span></span> <span data-ttu-id="14f9e-164">会社のリソースにアクセスする場合は、これを条件付きアクセスの基準として使用できます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-164">This can be used as a conditional access criteria when accessing corporate resources.</span></span>

-   <span data-ttu-id="14f9e-165">**AD ドメインへの参加と System Center Configuration Manager:** 現在のブランチでは、System Center Configuration Manager は、ドメインに参加している PC とするのに加え、次の特定のコンプライアンス基準を評価できる条件付きアクセスの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="14f9e-165">**AD domain joined and System Center Configuration Manager:** As of current branch, System Center Configuration Manager provides conditional access capabilities that can evaluate specific compliance criteria, in addition to be a domain-joined PC:</span></span>

    -   <span data-ttu-id="14f9e-166">PC が暗号化されているか。</span><span class="sxs-lookup"><span data-stu-id="14f9e-166">Is the PC encrypted?</span></span>

    -   <span data-ttu-id="14f9e-167">マルウェアがインストールされているか。</span><span class="sxs-lookup"><span data-stu-id="14f9e-167">Is malware installed?</span></span> <span data-ttu-id="14f9e-168">PC は最新の状態か。</span><span class="sxs-lookup"><span data-stu-id="14f9e-168">Is it up-to-date?</span></span>

    -   <span data-ttu-id="14f9e-169">デバイスが脱獄またはルート化されているか。</span><span class="sxs-lookup"><span data-stu-id="14f9e-169">Is the device jailbroken or rooted?</span></span>

#### <a name="bring-your-own-device-byod"></a><span data-ttu-id="14f9e-170">Bring Your Own Device (BYOD)</span><span class="sxs-lookup"><span data-stu-id="14f9e-170">Bring your own device (BYOD)</span></span>

-   <span data-ttu-id="14f9e-171">**Workplace Join と Intune 管理:** この場合、ユーザーは個人のデバイスを参加させて、会社のリソースやサービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="14f9e-171">**Workplace join and Intune management:** Here the user can join their personal devices to access corporate resources and services.</span></span> <span data-ttu-id="14f9e-172">Workplace Join を使用し、デバイスを Intune に登録して、デバイスレベルのポリシーを受け取ることができます。これは、条件付きアクセスの基準を評価する別のオプションでもあります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-172">You can use Workplace join and enroll devices into Intune to receive device-level policies, which is also another option to evaluate conditional access criteria.</span></span>

## <a name="app-based-conditional-access"></a><span data-ttu-id="14f9e-173">アプリベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="14f9e-173">App-based conditional access</span></span>

<span data-ttu-id="14f9e-174">Intune と Azure Active Directory が連携することで、管理対象アプリのみが会社の電子メールやその他の Office 365 サービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="14f9e-174">Intune and Azure Active Directory work together to make sure only managed apps can access corporate e-mail or other Office 365 services.</span></span>

-   <span data-ttu-id="14f9e-175">Intune を使用したアプリ ベースの条件付きアクセスについて詳しくは、[こちら](app-based-conditional-access-intune.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14f9e-175">Learn more about [app-based conditional access with Intune](app-based-conditional-access-intune.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="14f9e-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="14f9e-176">Next steps</span></span>

[<span data-ttu-id="14f9e-177">Azure Active Directory で条件付きアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="14f9e-177">How to configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

<span data-ttu-id="14f9e-178">[Intune で On-Premises Exchange Connector をインストールする方法](https://docs.microsoft.com/intune/exchange-connector-install)</span><span class="sxs-lookup"><span data-stu-id="14f9e-178">[How to install on-premises Exchange connector with Intune](https://docs.microsoft.com/intune/exchange-connector-install).</span></span>

[<span data-ttu-id="14f9e-179">Exchange On-Premises の条件付きアクセス ポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="14f9e-179">How to create a conditional access policy for Exchange on-premises</span></span>](conditional-access-exchange-create.md)
