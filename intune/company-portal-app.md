---
title: "ポータル サイト アプリを構成する方法"
titleSuffix: Azure portal
description: "会社固有のブランドを Intune ポータル サイト アプリに適用する方法について説明します。 \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 303d4a4cbce9d63abc0809a27ae1e22dcd1e195b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a><span data-ttu-id="02b9a-104">Microsoft Intune ポータル サイト アプリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="02b9a-104">How to configure the Microsoft Intune Company Portal app</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="02b9a-105">ユーザーは、Microsoft Intune の会社のポータルを使用して、会社のデータにアクセスしたり、デバイスの登録、アプリケーションのインストール、IT 部門からのサポート情報の検索などの一般的なタスクを実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-105">The Microsoft Intune company portal is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.</span></span>        

> [!Tip]        
> <span data-ttu-id="02b9a-106">ポータル サイトをカスタマイズすると、構成がポータル サイトの Web サイトとポータル サイト アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-106">When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.</span></span>       

<span data-ttu-id="02b9a-107">ポータル サイトをカスタマイズすることで、エンド ユーザーの利便性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-107">Customizing the Company Portal helps provide a familiar and helpful experience for your end users.</span></span> <span data-ttu-id="02b9a-108">そのためには、**[モバイル アプリ]** ワークロードから **[セットアップ]** > **[ポータル サイトのブランド化]** の順に選び、必要な設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02b9a-108">To do it, from the **Mobile apps** workload, choose  **Setup** > **Company Portal Branding**, then configure the required settings.</span></span>      

## <a name="company-contact-information-and-privacy-statement"></a><span data-ttu-id="02b9a-109">会社の連絡先情報とプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="02b9a-109">Company contact information and privacy statement</span></span>        
<span data-ttu-id="02b9a-110">会社名は、ポータル サイトのタイトルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-110">The company name is displayed as the Company Portal title.</span></span> <span data-ttu-id="02b9a-111">連絡先情報と詳細は、ポータル サイトの **[IT に連絡]** 画面でユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-111">The contact information and details are displayed to users in the **Contact IT** screen of the Company Portal.</span></span> <span data-ttu-id="02b9a-112">プライバシーに関する声明は、ユーザーがプライバシー リンクをクリックすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-112">The privacy statement is displayed when a user clicks on the privacy link.</span></span>        


|<span data-ttu-id="02b9a-113">フィールド名</span><span class="sxs-lookup"><span data-stu-id="02b9a-113">Field name</span></span>|<span data-ttu-id="02b9a-114">最大長</span><span class="sxs-lookup"><span data-stu-id="02b9a-114">Max length</span></span>|<span data-ttu-id="02b9a-115">詳細情報</span><span class="sxs-lookup"><span data-stu-id="02b9a-115">More information</span></span>|        
|-|-|-|     
|<span data-ttu-id="02b9a-116">**会社名**</span><span class="sxs-lookup"><span data-stu-id="02b9a-116">**Company name**</span></span>|<span data-ttu-id="02b9a-117">40</span><span class="sxs-lookup"><span data-stu-id="02b9a-117">40</span></span>|<span data-ttu-id="02b9a-118">ポータル サイトのタイトルとして表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-118">This name is displayed as the title of the Company Portal.</span></span>|        
|<span data-ttu-id="02b9a-119">**IT 部門の担当者名**</span><span class="sxs-lookup"><span data-stu-id="02b9a-119">**IT department contact name**</span></span>|<span data-ttu-id="02b9a-120">40</span><span class="sxs-lookup"><span data-stu-id="02b9a-120">40</span></span>|<span data-ttu-id="02b9a-121">**[IT に連絡]** ページに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-121">This name is displayed on the **Contact IT** page.</span></span>|      
|<span data-ttu-id="02b9a-122">**IT 部門の電話番号**</span><span class="sxs-lookup"><span data-stu-id="02b9a-122">**IT department phone number**</span></span>|<span data-ttu-id="02b9a-123">20</span><span class="sxs-lookup"><span data-stu-id="02b9a-123">20</span></span>|<span data-ttu-id="02b9a-124">**[IT に連絡]** ページに表示される連絡先の電話番号です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-124">This contact number is displayed on the **Contact IT** page.</span></span>|        
|<span data-ttu-id="02b9a-125">IT 部門の電子メール アドレス</span><span class="sxs-lookup"><span data-stu-id="02b9a-125">IT department email address</span></span>|<span data-ttu-id="02b9a-126">40</span><span class="sxs-lookup"><span data-stu-id="02b9a-126">40</span></span>|<span data-ttu-id="02b9a-127">**[IT に連絡]** ページに表示される連絡先の電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="02b9a-127">This contact address is displayed on the **Contact IT** page.</span></span> <span data-ttu-id="02b9a-128">**alias@domainname.com** の形式で有効な電子メール アドレスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b9a-128">You must enter a valid email address in the format **alias@domainname.com**.</span></span>|     
|<span data-ttu-id="02b9a-129">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="02b9a-129">**Additional information**</span></span>|<span data-ttu-id="02b9a-130">120</span><span class="sxs-lookup"><span data-stu-id="02b9a-130">120</span></span>|<span data-ttu-id="02b9a-131">**[IT に連絡]** ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-131">Displayed on the **Contact IT** page.</span></span>|      
|<span data-ttu-id="02b9a-132">**会社のプライバシーに関する声明の URL**</span><span class="sxs-lookup"><span data-stu-id="02b9a-132">**Company privacy statement URL**</span></span>|<span data-ttu-id="02b9a-133">79</span><span class="sxs-lookup"><span data-stu-id="02b9a-133">79</span></span>|<span data-ttu-id="02b9a-134">ポータル サイトでユーザーがプライバシー リンクをクリックすると表示される、各社のプライバシーに関する声明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-134">You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal.</span></span> <span data-ttu-id="02b9a-135">**https://www.contoso.com** の形式で有効な URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="02b9a-135">You must enter a valid URL in the format **https://www.contoso.com**.</span></span>|        

## <a name="support-contacts"></a><span data-ttu-id="02b9a-136">サポートの連絡先</span><span class="sxs-lookup"><span data-stu-id="02b9a-136">Support contacts</span></span>     
<span data-ttu-id="02b9a-137">サポート Web サイトは、ポータル サイトに表示されます。ユーザーは、サポート サイトからオンライン サポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-137">The support website is displayed to users in the Company Portal to enable them to access online support.</span></span>        



|<span data-ttu-id="02b9a-138">フィールド名</span><span class="sxs-lookup"><span data-stu-id="02b9a-138">Field name</span></span>|<span data-ttu-id="02b9a-139">最大長</span><span class="sxs-lookup"><span data-stu-id="02b9a-139">Max length</span></span>|<span data-ttu-id="02b9a-140">詳細情報</span><span class="sxs-lookup"><span data-stu-id="02b9a-140">More information</span></span>|        
|-|-|-|     
|<span data-ttu-id="02b9a-141">**サポート Web サイトの URL**</span><span class="sxs-lookup"><span data-stu-id="02b9a-141">**Support website URL**</span></span>|<span data-ttu-id="02b9a-142">150</span><span class="sxs-lookup"><span data-stu-id="02b9a-142">150</span></span>|<span data-ttu-id="02b9a-143">ユーザーが使用するサポート Web サイトがある場合、その URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="02b9a-143">If you have a support website that you want your users to use, specify the URL here.</span></span> <span data-ttu-id="02b9a-144">URL は、**https://www.contoso.com** という形式にする必要があります。URL を指定しない場合、ポータル サイトの **[IT に連絡]** ページのサポート Web サイトには何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="02b9a-144">The URL must be in the format **https://www.contoso.com**. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal.</span></span>|        
|<span data-ttu-id="02b9a-145">**サポート Web サイトの名前**</span><span class="sxs-lookup"><span data-stu-id="02b9a-145">**Support website name**</span></span>|<span data-ttu-id="02b9a-146">40</span><span class="sxs-lookup"><span data-stu-id="02b9a-146">40</span></span>|<span data-ttu-id="02b9a-147">サポート Web サイトの URL に表示されるフレンドリ名です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-147">This name is the friendly name that is displayed for the URL to the support website.</span></span> <span data-ttu-id="02b9a-148">サポート Web サイトの URL を指定し、フレンドリ名を指定しない場合、ポータル サイトの **[IT に連絡]** ページに [IT Web サイトに移動する] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-148">If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Contact IT** page in the Company Portal.</span></span>       

## <a name="company-branding-customization"></a><span data-ttu-id="02b9a-149">会社のブランドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="02b9a-149">Company branding customization</span></span>       
<span data-ttu-id="02b9a-150">ポータル サイトのロゴや会社名、テーマの色や背景をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-150">You can customize your Company Portal with your company logo, company name, theme color and background.</span></span>     



|<span data-ttu-id="02b9a-151">フィールド名</span><span class="sxs-lookup"><span data-stu-id="02b9a-151">Field name</span></span>|<span data-ttu-id="02b9a-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="02b9a-152">More information</span></span>|       
|-|-|       
|<span data-ttu-id="02b9a-153">**テーマの色**</span><span class="sxs-lookup"><span data-stu-id="02b9a-153">**Theme color**</span></span>|<span data-ttu-id="02b9a-154">ポータル サイトに適用するテーマの色を選択します。</span><span class="sxs-lookup"><span data-stu-id="02b9a-154">Select a theme color to apply to the Company Portal.</span></span>|      
|<span data-ttu-id="02b9a-155">**会社のロゴを表示する**</span><span class="sxs-lookup"><span data-stu-id="02b9a-155">**Show company logo**</span></span>|<span data-ttu-id="02b9a-156">このオプションを有効にすると、ポータル サイトに表示する会社のロゴをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-156">When you enable this option, you can upload your company logo to show in your Company Portal.</span></span> <span data-ttu-id="02b9a-157">2 つのロゴをアップロードできます。1 つは、ポータル サイトの背景が白の場合に表示するロゴ、もう 1 つは、選択したテーマの色がポータル サイトの背景に使用されている場合に表示するロゴです。</span><span class="sxs-lookup"><span data-stu-id="02b9a-157">You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color.</span></span> <span data-ttu-id="02b9a-158">各ロゴは、.png または .jpg ファイルの種類にし、最大解像度が 400 x 100 ピクセルで、750 KB 以下のサイズにします。</span><span class="sxs-lookup"><span data-stu-id="02b9a-158">Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.</span></span><br><span data-ttu-id="02b9a-159">入力した会社名を、アップロードしたロゴの横に表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-159">You can also show the company name you entered next to the uploaded logo.</span></span>|      

<span data-ttu-id="02b9a-160">変更の保存後、**[Intune Web ポータルで設定をプレビューします]** を選択して、構成がどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-160">After you save your changes, you can choose **Preview your settings in the Intune Web Portal** to see how your configurations will look.</span></span>
