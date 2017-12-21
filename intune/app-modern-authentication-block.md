---
title: "最新の認証を使用していないアプリを Intune でブロックする"
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6a7cf3b73f4be195b4e07c8c72edeae9fbc9073
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a><span data-ttu-id="b146c-102">最新の認証を使用していないアプリをブロックする (ADAL)</span><span class="sxs-lookup"><span data-stu-id="b146c-102">Block apps that do not use modern authentication (ADAL)</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b146c-103">アプリ保護ポリシーを使用したアプリ ベースの条件付きアクセスは、OAuth2 の実装である[最新の認証](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)を使用するアプリケーションに依存しています。</span><span class="sxs-lookup"><span data-stu-id="b146c-103">App-based conditional access with app protection policies rely on applications using [modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) which is an implementation of OAuth2.</span></span> <span data-ttu-id="b146c-104">最新の Office モバイル アプリとデスクトップ アプリケーションは最新の認証を使用していますが、基本認証やフォームベースの認証など、他の認証方式を使用しているサードパーティ製アプリや古い Office アプリもあります。</span><span class="sxs-lookup"><span data-stu-id="b146c-104">Most current Office mobile and desktop applications use modern authentication, however there are third-party apps and older Office apps that user other authentication methods like basic authentication and forms based authentication.</span></span>

<span data-ttu-id="b146c-105">このようなアプリに対するアクセスをブロックするには、以下を推奨します。</span><span class="sxs-lookup"><span data-stu-id="b146c-105">To block access to these apps we recommend the following:</span></span>

* <span data-ttu-id="b146c-106">最新ではない認証プロトコルをブロックするように ADFS 要求規則を設定します。</span><span class="sxs-lookup"><span data-stu-id="b146c-106">Set up ADFS claims rules to block non-modern authentication protocols.</span></span> <span data-ttu-id="b146c-107">詳しい手順は、シナリオ 3 の[ブラウザー ベースのアプリケーションを除く Office 365 への外部アクセスをすべてブロックする方法](https://technet.microsoft.com/library/dn592182.aspx)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b146c-107">Detailed instructions are provided in scenario 3 - [block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>
* <span data-ttu-id="b146c-108">**SharePoint Online** では、PowerShell コマンドレット [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) を使用して従来の認証プロトコルのプロパティを false に設定することで、SharePoint Online サービスの最新ではない認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b146c-108">For **SharePoint Online**, disable non-modern authentication in the SharePoint Online service using the PowerShell commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) to set the legacy authentication protocols property to false:</span></span>

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
><span data-ttu-id="b146c-109">アプリ ベースの CA は、Azure Active Directory (Azure AD) 証明書ベースの認証と併用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b146c-109">App-based CA must not be used with Azure Active Directory (Azure AD) certificate based authentication.</span></span> <span data-ttu-id="b146c-110">同時に使用できるのは、いずれかの構成のみです。</span><span class="sxs-lookup"><span data-stu-id="b146c-110">You can only have one of these configured at a time.</span></span>

### <a name="see-also"></a><span data-ttu-id="b146c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b146c-111">See also</span></span>
[<span data-ttu-id="b146c-112">Intune を使用したアプリ ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="b146c-112">App-based conditional access with Intune</span></span>](app-based-conditional-access-intune.md)
