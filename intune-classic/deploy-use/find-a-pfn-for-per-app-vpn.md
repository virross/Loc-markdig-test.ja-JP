---
title: "アプリごとの VPN のパッケージ ファミリ名 (PFN) の検索"
description: "アプリごとの VPN を構成できるように PFN を検索する。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 27979d2ad7715e51ca88ff911d728df588498875
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a><span data-ttu-id="4caf5-103">アプリごとの VPN 構成のパッケージ ファミリー名 (PFN) を検索する</span><span class="sxs-lookup"><span data-stu-id="4caf5-103">Find a package family name (PFN) for per-app VPN configuration</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4caf5-104">アプリごとの VPN をセットアップできるように PFN を検索する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="4caf5-104">There are two ways to find a PFN so that you can set up a per-app VPN.</span></span>

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a><span data-ttu-id="4caf5-105">Windows 10 コンピューターにインストールされているアプリの PFN を検索する</span><span class="sxs-lookup"><span data-stu-id="4caf5-105">Find a PFN for an app that's installed on a Windows 10 computer</span></span>

<span data-ttu-id="4caf5-106">使用しているアプリが既に Windows 10 コンピューターにインストールされている場合、[Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell コマンドレットを使用して PFN を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-106">If the app that you are working with is already installed on a Windows 10 computer, you can use the [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet to get the PFN.</span></span>

<span data-ttu-id="4caf5-107">Get-AppxPackage の構文:</span><span class="sxs-lookup"><span data-stu-id="4caf5-107">The syntax for Get-AppxPackage is:</span></span>

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
> <span data-ttu-id="4caf5-108">PFN を取得するには、状況に応じて管理者として PowerShell を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4caf5-108">You may have to run PowerShell as an admin to retrieve the PFN.</span></span>

<span data-ttu-id="4caf5-109">たとえば、コンピューターにインストールされているすべてのユニバーサル アプリに関する情報を取得するには、`Get-AppxPackage` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-109">For example, to get info about all the universal apps installed on the computer, use `Get-AppxPackage`.</span></span>

<span data-ttu-id="4caf5-110">名前がわかっているアプリに関する情報を取得するには、`Get-AppxPackage *<app_name>` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-110">To get info about an app when you know the name or part of the name, use `Get-AppxPackage *<app_name>`.</span></span> <span data-ttu-id="4caf5-111">アプリの正確な名前がわからない場合は、ワイルドカード文字を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="4caf5-111">Note the use of the wildcard character, which is particularly helpful if you're not sure of the full name of the app.</span></span> <span data-ttu-id="4caf5-112">たとえば、OneNote に関する情報を取得するには、`Get-AppxPackage *OneNote` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-112">For example, to get the info for OneNote, use `Get-AppxPackage *OneNote`.</span></span>


<span data-ttu-id="4caf5-113">OneNote について取得される情報の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-113">Here is the information retrieved for OneNote:</span></span>

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a><span data-ttu-id="4caf5-114">アプリがコンピューターにインストールされていない場合に PFN を検索する</span><span class="sxs-lookup"><span data-stu-id="4caf5-114">Find a PFN if the app is not installed on a computer</span></span>

1.  <span data-ttu-id="4caf5-115">https://www.microsoft.com/ja-jp/store/apps に移動します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-115">Go to https://www.microsoft.com/store/apps.</span></span>
2.  <span data-ttu-id="4caf5-116">検索バーにアプリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-116">Enter the name of the app in the search bar.</span></span> <span data-ttu-id="4caf5-117">この例では、OneNote を検索します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-117">In our example, search for OneNote.</span></span>
3.  <span data-ttu-id="4caf5-118">アプリのリンクを選びます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-118">Choose the link to the app.</span></span> <span data-ttu-id="4caf5-119">URL の末尾に一連の文字があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4caf5-119">Note that the URL has a series of letters at the end.</span></span> <span data-ttu-id="4caf5-120">この例では、URL は `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4caf5-120">In our example, the URL looks like this: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.</span></span>
4.  <span data-ttu-id="4caf5-121">別のタブに URL "`https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`" を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-121">In a different tab, paste the following URL, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`.</span></span> <span data-ttu-id="4caf5-122">`<app id>` の部分を、https://www.microsoft.com/ja-jp/store/apps から取得したアプリ ID (手順 3 の URL の末尾にある一連の文字) で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-122">Replace `<app id>` with the app id that you got from https://www.microsoft.com/store/apps - that series of letters at the end of the URL in step 3.</span></span> <span data-ttu-id="4caf5-123">この OneNote の例の場合、`https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata` を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-123">In our example of OneNote, you'd paste: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.</span></span>

<span data-ttu-id="4caf5-124">Microsoft Edge に目的の情報が表示されます。Internet Explorer で **[開く]** を選んで情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="4caf5-124">Microsoft Edge shows the information that you want; in Internet Explorer, choose **Open** to see the information.</span></span> <span data-ttu-id="4caf5-125">PFN 値は最初の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4caf5-125">The PFN value is given on the first line.</span></span> <span data-ttu-id="4caf5-126">この例の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4caf5-126">Here are the results for our example:</span></span>


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
