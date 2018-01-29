---
title: "モバイル デバイスでの電子メールの構成を簡略化する"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 12/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1696c715-1e9a-401e-a530-77904fd189ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce3edb95bcb4211c4592887f9654ab77800e907e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="quick-start-guide-simplify-email-configuration-on-mobile-devices"></a><span data-ttu-id="512a6-102">クイック スタート ガイド: モバイル デバイスでの電子メールの構成を簡略化する</span><span class="sxs-lookup"><span data-stu-id="512a6-102">Quick Start Guide: Simplify email configuration on mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="512a6-103">Microsoft Intune は、Intune サービスによって管理される Windows、iOS、および Android モバイル デバイスに電子メール (および VPN と WiFi の) プロファイルを展開できるようにすることで、会社の時間とリソースを節約します。</span><span class="sxs-lookup"><span data-stu-id="512a6-103">Microsoft Intune saves your company time and resources by allowing you to deploy email (as well as VPN and WiFi) profiles to Windows, iOS and Android mobile devices managed by the Intune service.</span></span> <span data-ttu-id="512a6-104">電子メール プロファイルを自動的に構成することで、エンド ユーザー エクスペリエンスを大幅に向上させて満足度レベルを上昇させながら、ヘルプデスクのコストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="512a6-104">Automatically configuring email profiles can greatly improve the end-user experience and increase satisfaction levels while at the same time reduce your helpdesk costs.</span></span>

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="512a6-105">このクイック スタート ガイドの対象読者</span><span class="sxs-lookup"><span data-stu-id="512a6-105">Is this quick start guide right for me?</span></span>
<span data-ttu-id="512a6-106">エンド ユーザーがモバイル デバイスに新しい電子メール プロファイルを構成するために必要な時間と労力を削減することに加え、Intune によって管理されるモバイル デバイスのみが会社の電子メールにアクセスできるように会社のデータ セキュリティを強化したいと考えていますか。</span><span class="sxs-lookup"><span data-stu-id="512a6-106">Would like to reduce the time and effort required by your users to configure new email profiles on mobile devices from while also increasing your company’s data security by only allowing mobile devices managed by Intune to access your company email?</span></span>

<span data-ttu-id="512a6-107">そうであれば、Microsoft Intune は、電子メール プロファイルをデバイスに展開することで、従業員の Intune 管理デバイスの電子メールを自動的に構成できます。これにより、従業員が会社の電子メールにアクセスするために手動で構成を行う必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="512a6-107">If yes, Microsoft Intune can automatically configure email for your employees’ Intune-managed devices by deploying email profiles to their devices so that they don’t have to manually configure access to their company email.</span></span> <span data-ttu-id="512a6-108">この機能によって、Windows、iOS、および Android デバイスに関する電子メール構成問題の発生数を減少させることでユーザー エクスペリエンスが向上し、ヘルプデスクの全体的なコストが削減されます。</span><span class="sxs-lookup"><span data-stu-id="512a6-108">This capability provides a better end-user experience and reduces overall helpdesk costs by driving down the number of escalations for email configuration issues on your users Windows, iOS, and Android devices.</span></span>

<span data-ttu-id="512a6-109">電子メール プロファイルを構成した後、Intune の条件付きアクセス ポリシーを使用して、会社の電子メールと Office 365 サービスへのアクセスを簡単に制限できます。</span><span class="sxs-lookup"><span data-stu-id="512a6-109">After the email profile is configured, you can easily restrict access to company email and Office 365 services with Intune conditional access policies.</span></span> <span data-ttu-id="512a6-110">これらのポリシーによって、会社の電子メールと O365 サービスへのアクセスが、Intune に設定したルールを準拠しているデバイスに制限されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="512a6-110">These policies allow you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the rules that you set in Intune.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="512a6-111">実行方法</span><span class="sxs-lookup"><span data-stu-id="512a6-111">How do I do it?</span></span>
1.  <span data-ttu-id="512a6-112">Windows、iOS、および Android デバイスで自動的に[エンド ユーザーの電子メール プロファイルを構成](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)します。</span><span class="sxs-lookup"><span data-stu-id="512a6-112">Automatically [configure end-user email profiles](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) on Windows, iOS, and Android devices.</span></span>
2.  <span data-ttu-id="512a6-113">条件付きアクセス ポリシーを使用して、[会社の電子メールへのアクセスを制御](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)します。</span><span class="sxs-lookup"><span data-stu-id="512a6-113">[Control access to company email](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) using conditional access policies.</span></span>


### <a name="additional-information"></a><span data-ttu-id="512a6-114">追加情報:</span><span class="sxs-lookup"><span data-stu-id="512a6-114">Additional information:</span></span>
[<span data-ttu-id="512a6-115">Intune のデバイス設定とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="512a6-115">Intune device settings and security</span></span>](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)

## <a name="what-should-i-do-next"></a><span data-ttu-id="512a6-116">次にすべきこと</span><span class="sxs-lookup"><span data-stu-id="512a6-116">What should I do next?</span></span>
[<span data-ttu-id="512a6-117">管理対象デバイスに VPN プロファイルを展開する</span><span class="sxs-lookup"><span data-stu-id="512a6-117">Deploy VPN profiles to managed devices</span></span>](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)

[<span data-ttu-id="512a6-118">管理対象デバイスに Wi-Fi プロファイルを展開する</span><span class="sxs-lookup"><span data-stu-id="512a6-118">Deploy Wi-Fi profiles to managed devices</span></span>](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)

<span data-ttu-id="512a6-119">[Secure resource access with certificate profiles in Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) (Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する)</span><span class="sxs-lookup"><span data-stu-id="512a6-119">[Secure resource access with certificate profiles in Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)</span></span>
