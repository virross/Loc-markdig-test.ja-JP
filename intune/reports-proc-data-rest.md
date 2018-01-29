---
title: "REST クライアントを使用してデータ ウェアハウス API からデータを取得する"
description: "RESTful API を使用し、Intune データ ウェアハウスからデータを取得します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 73db6d2c2fb493bd12dc1ee8538ee117eea7203f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a><span data-ttu-id="ce355-103">REST クライアントを使用して Intune データ ウェアハウス API からデータを取得する</span><span class="sxs-lookup"><span data-stu-id="ce355-103">Get data from the Intune Data Warehouse API with a REST client</span></span>

<span data-ttu-id="ce355-104">RESTful エンドポイント経由で Intune データ ウェアハウスのデータ モデルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ce355-104">You can access the Intune Data Warehouse data model through RESTful endpoints.</span></span> <span data-ttu-id="ce355-105">データにアクセスするには、OAuth 2.0 を利用し、Microsoft Azure Active Directory (Azure AD) でクライアントを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce355-105">To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0.</span></span> <span data-ttu-id="ce355-106">アクセスを有効にするには、最初に Azure でネイティブ アプリを設定し、Microsoft Intune API へのアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="ce355-106">To enable access, first set up a native app in Azure and grant permissions to the Microsoft Intune API.</span></span> <span data-ttu-id="ce355-107">ローカル クライアントに許可が与えられます。そのクライアントはネイティブ アプリ経由でデータ ウェアハウス エンドポイントと通信できます。</span><span class="sxs-lookup"><span data-stu-id="ce355-107">Your local client gets authorization, and then the client can communicate with the Data Warehouse endpoints through the native app.</span></span>

<span data-ttu-id="ce355-108">データ ウェアハウス API からデータを取得するようにクライアントを設定する手順では、次の作業が必要になります。</span><span class="sxs-lookup"><span data-stu-id="ce355-108">The steps to set up a client to get data from the  Data Warehouse API require you to:</span></span>

1. <span data-ttu-id="ce355-109">Azure でネイティブ アプリとしてクライアント アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="ce355-109">Create a client app as a native app in Azure</span></span>
3. <span data-ttu-id="ce355-110">Microsoft Intune API へのアクセスをクライアント アプリに与える</span><span class="sxs-lookup"><span data-stu-id="ce355-110">Grant the client app access to the Microsoft Intune API</span></span>
3. <span data-ttu-id="ce355-111">データを取得するための REST クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="ce355-111">Create a local REST client to get the data</span></span>

<span data-ttu-id="ce355-112">次の手順を使用して、REST クライアントでの認証および API へのアクセス方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ce355-112">Use the following steps to learn how to authorize and access the API with a REST client.</span></span> <span data-ttu-id="ce355-113">まず、Postman を利用する汎用 REST クライアントの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce355-113">First, you will look at using a generic REST client using Postman.</span></span> <span data-ttu-id="ce355-114">Postman は、API と連動する REST クライアントを開発およびトラブルシューティングするために一般的に利用されているツールです。</span><span class="sxs-lookup"><span data-stu-id="ce355-114">Postman is a commonly used tool troubleshooting and developing REST clients to work with APIs.</span></span> <span data-ttu-id="ce355-115">Postman の詳細については、「[Postman](https://www.getpostman.com)」のサイトをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ce355-115">For more information about Postman, see the [Postman](https://www.getpostman.com) site.</span></span> <span data-ttu-id="ce355-116">次に、C# コード サンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="ce355-116">Then you can look at a C# code sample.</span></span> <span data-ttu-id="ce355-117">そのサンプルは、クライアントを認証し、API からデータを取得するコードの例を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce355-117">The sample provides an example for authorizing a client and getting data from the API.</span></span>

## <a name="create-a-client-app-as-a-native-app-in-azure"></a><span data-ttu-id="ce355-118">Azure でネイティブ アプリとしてクライアント アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="ce355-118">Create a client app as a native app in Azure</span></span>

<span data-ttu-id="ce355-119">Azure でネイティブ アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce355-119">Create a native app in Azure.</span></span> <span data-ttu-id="ce355-120">このネイティブ アプリはクライアント アプリです。</span><span class="sxs-lookup"><span data-stu-id="ce355-120">This native app is the client app.</span></span> <span data-ttu-id="ce355-121">ローカル コンピューターで実行されるクライアントは、ローカル クライアントが資格情報を要求するとき、Intune データ ウェアハウス API を参照します。</span><span class="sxs-lookup"><span data-stu-id="ce355-121">The client running on your local machine references the Intune Data Warehouse API when the local client requests credentials.</span></span> 

1. <span data-ttu-id="ce355-122">テナントの Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ce355-122">Sign in to the Azure portal for your tenant.</span></span> <span data-ttu-id="ce355-123">**[Azure Active Directory]** > **[アプリの登録]** の順に選択し、**[アプリの登録]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce355-123">Choose **Azure Active Directory** > **App Registrations** to open the **App registrations** blade.</span></span>
2. <span data-ttu-id="ce355-124">**[New app registration]\(新しいアプリの登録\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-124">Select **New app registration**.</span></span>
3. <span data-ttu-id="ce355-125">アプリの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-125">Type the app details.</span></span>
    1.  <span data-ttu-id="ce355-126">「Intune データ ウェアハウス クライアント」など、わかりやすい名前を **[名前]** に入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-126">Type a friendly name, such as Intune Data Warehouse Client, for the **Name**.</span></span>
    2.  <span data-ttu-id="ce355-127">**[アプリケーションの種類]** の **[ネイティブ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-127">Select **Native** for the **Application type**.</span></span>
    3.  <span data-ttu-id="ce355-128">**[サインオン URL]** に URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-128">Type a URL for the **Sign-on URL**.</span></span> <span data-ttu-id="ce355-129">サインオン URL は特定のシナリオによって代わります。ただし、Postman を利用する予定の場合、「`https://www.getpostman.com/oauth2/callback`」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="ce355-129">The Sign-on URL will depend on the specific scenario, however if you plan on using Postman, type `https://www.getpostman.com/oauth2/callback`.</span></span> <span data-ttu-id="ce355-130">Azure AD に認証するとき、クライアント認証手順のコールバックを利用します。</span><span class="sxs-lookup"><span data-stu-id="ce355-130">You will use the callback for client authentication step when authenticating to Azure AD.</span></span>
4.  <span data-ttu-id="ce355-131">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-131">Select **Create**.</span></span>

     ![Intune データ ウェアハウス API](media\reports-get_rest_data_client_overview.png)

5. <span data-ttu-id="ce355-133">このアプリの **[アプリケーション ID]** をメモします。</span><span class="sxs-lookup"><span data-stu-id="ce355-133">Note the **Application ID** of this app.</span></span> <span data-ttu-id="ce355-134">この ID は次のセクションで使用します。</span><span class="sxs-lookup"><span data-stu-id="ce355-134">You will use the ID in the next section.</span></span>

## <a name="grant-the-client-app-access-to-the-microsoft-intune-api"></a><span data-ttu-id="ce355-135">Microsoft Intune API へのアクセスをクライアント アプリに与える</span><span class="sxs-lookup"><span data-stu-id="ce355-135">Grant the client app access to the Microsoft Intune API</span></span>

<span data-ttu-id="ce355-136">これでアプリが Azure に定義されました。</span><span class="sxs-lookup"><span data-stu-id="ce355-136">You now have an app defined in Azure.</span></span> <span data-ttu-id="ce355-137">ネイティブ アプリから Microsoft Intune API にアクセスするための許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="ce355-137">Grant access from the native app to the Microsoft Intune API.</span></span>

1.  <span data-ttu-id="ce355-138">ネイティブ アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-138">Select the native app.</span></span> <span data-ttu-id="ce355-139">アプリには **Intune Data Warehouse Client** などの名前が付けてあります。</span><span class="sxs-lookup"><span data-stu-id="ce355-139">You named the app something such as **Intune Data Warehouse Client**.</span></span>
2.  <span data-ttu-id="ce355-140">**[設定]** ブレードから **[必要なアクセス許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-140">Select **Required permissions** from the **Settings** blade</span></span>
3.  <span data-ttu-id="ce355-141">**[必要なアクセス許可]** ブレードで **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-141">Select **Add** in the **Required permissions** blade.</span></span>
4.  <span data-ttu-id="ce355-142">**[API を選択します]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ce355-142">Select **Select an API**.</span></span>
5.  <span data-ttu-id="ce355-143">Web アプリ名を検索します。</span><span class="sxs-lookup"><span data-stu-id="ce355-143">Search for the web app name.</span></span> <span data-ttu-id="ce355-144">**Microsoft Intune API** という名前です。</span><span class="sxs-lookup"><span data-stu-id="ce355-144">It is named **Microsoft Intune API**.</span></span>
6.  <span data-ttu-id="ce355-145">一覧でアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="ce355-145">Select the app in the list.</span></span>
7.  <span data-ttu-id="ce355-146">**[選択]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ce355-146">Select **Select**.</span></span>
8.  <span data-ttu-id="ce355-147">**[委任されたアクセス許可]** ボックスにチェックマークを入れ、**[Get data warehouse information from Microsoft Intune]\(Microsoft Intune からデータ ウェアハウス情報を取得する\)** を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce355-147">Check the **Delegated Permissions** box to add **Get data warehouse information from Microsoft Intune**.</span></span>

    ![アクセスを有効にする](media\reports-get_rest_data_client_access.png)

9.  <span data-ttu-id="ce355-149">**[選択]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ce355-149">Select **Select**.</span></span>
10.  <span data-ttu-id="ce355-150">**[完了]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ce355-150">Select **Done**.</span></span>
11.  <span data-ttu-id="ce355-151">必要に応じて、[必要なアクセス許可] ブレードで **[アクセス許可の付与]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-151">Optionally, Select **Grant Permissions** in the Required permissions blade.</span></span> <span data-ttu-id="ce355-152">これで、現在のディレクトリのすべてのアカウントへのアクセスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="ce355-152">This will grant access to all accounts in the current directory.</span></span> <span data-ttu-id="ce355-153">テナントのすべてのユーザーに対して同意を求めるダイアログ ボックスが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ce355-153">This will prevent the consent dialog box from appearing for every user in the tenant.</span></span> <span data-ttu-id="ce355-154">詳細については、「[Azure Active Directory とアプリケーションの統合](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce355-154">For more information, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).</span></span>
12.  <span data-ttu-id="ce355-155">**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-155">Select **Yes**.</span></span>

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a><span data-ttu-id="ce355-156">Microsoft Intune API と Postman からデータを取得する</span><span class="sxs-lookup"><span data-stu-id="ce355-156">Get data from the Microsoft Intune API with Postman</span></span>

<span data-ttu-id="ce355-157">Intune データ ウェアハウス API と、Postman など、汎用 REST クライアントを連動させることができます。</span><span class="sxs-lookup"><span data-stu-id="ce355-157">You can work with the Intune Data Warehouse API with a generic REST client such as Postman.</span></span> <span data-ttu-id="ce355-158">Postman を利用することで、API の機能、つまり、基礎となる OData データ モデルを詳しく理解できます。また、API リソースへの接続で発生した問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="ce355-158">Postman can  provide insight into the features of the API, the underlying OData data model, and troubleshoot your  connection to the API resources.</span></span> <span data-ttu-id="ce355-159">このセクションでは、ローカル クライアントに Auth2.0 トークンを生成する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ce355-159">In this section, you can find information about generating an Auth2.0 token for your local client.</span></span> <span data-ttu-id="ce355-160">クライアントが Azure AD で認証したり、API リソースにアクセスしたりするには、トークンが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce355-160">The client will need the token to authenticate with Azure AD and access the API resources.</span></span>

### <a name="information-you-will-need-to-make-the-call"></a><span data-ttu-id="ce355-161">呼び出しに必要な情報</span><span class="sxs-lookup"><span data-stu-id="ce355-161">Information you will need to make the call</span></span>

<span data-ttu-id="ce355-162">Postman を使用して REST 呼び出しを行うには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce355-162">You need the following information to make a REST call using Postman:</span></span>

| <span data-ttu-id="ce355-163">属性</span><span class="sxs-lookup"><span data-stu-id="ce355-163">Attribute</span></span>        | <span data-ttu-id="ce355-164">説明</span><span class="sxs-lookup"><span data-stu-id="ce355-164">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="ce355-165">例</span><span class="sxs-lookup"><span data-stu-id="ce355-165">Example</span></span>                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| <span data-ttu-id="ce355-166">コールバック URL</span><span class="sxs-lookup"><span data-stu-id="ce355-166">Callback URL</span></span>     | <span data-ttu-id="ce355-167">アプリ設定ページでこれをコールバック URL として設定します。</span><span class="sxs-lookup"><span data-stu-id="ce355-167">Set this as the callback URL in your app settings page.</span></span>                                                                                                                              | <span data-ttu-id="ce355-168">https://www.getpostman.com/oauth2/callback</span><span class="sxs-lookup"><span data-stu-id="ce355-168">https://www.getpostman.com/oauth2/callback</span></span>                                                    |
| <span data-ttu-id="ce355-169">トークン名</span><span class="sxs-lookup"><span data-stu-id="ce355-169">Token Name</span></span>       | <span data-ttu-id="ce355-170">Azure アプリに資格情報を渡すために使用する文字列。</span><span class="sxs-lookup"><span data-stu-id="ce355-170">A string used to pass the credentials to the Azure app.</span></span> <span data-ttu-id="ce355-171">この過程で生成されたトークンにより、データ ウェアハウス API を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ce355-171">The process generates your token so you can make a call to the Data Warehouse API.</span></span>                          | <span data-ttu-id="ce355-172">Bearer</span><span class="sxs-lookup"><span data-stu-id="ce355-172">Bearer</span></span>                                                                                        |
| <span data-ttu-id="ce355-173">認証 URL</span><span class="sxs-lookup"><span data-stu-id="ce355-173">Auth URL</span></span>         | <span data-ttu-id="ce355-174">これは認証に使用する URL です。</span><span class="sxs-lookup"><span data-stu-id="ce355-174">This is the URL used to authenticate.</span></span> | <span data-ttu-id="ce355-175">https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="ce355-175">https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/</span></span> |
| <span data-ttu-id="ce355-176">アクセス トークン URL</span><span class="sxs-lookup"><span data-stu-id="ce355-176">Access Token URL</span></span> | <span data-ttu-id="ce355-177">これはトークンの付与に使用する URL です。</span><span class="sxs-lookup"><span data-stu-id="ce355-177">This is the URL used to grant the token.</span></span>                                                                                                                                              | <span data-ttu-id="ce355-178">https://login.microsoftonline.com/common/oauth2/token</span><span class="sxs-lookup"><span data-stu-id="ce355-178">https://login.microsoftonline.com/common/oauth2/token</span></span> |
| <span data-ttu-id="ce355-179">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="ce355-179">Client ID</span></span>        | <span data-ttu-id="ce355-180">Azure でネイティブ アプリを作成したとき、これを作成し、メモしました。</span><span class="sxs-lookup"><span data-stu-id="ce355-180">You created, and noted this when creating the native app in Azure.</span></span>                                                                                               | <span data-ttu-id="ce355-181">4184c61a-e324-4f51-83d7-022b6a81b991</span><span class="sxs-lookup"><span data-stu-id="ce355-181">4184c61a-e324-4f51-83d7-022b6a81b991</span></span>                                                          |
| <span data-ttu-id="ce355-182">スコープ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ce355-182">Scope (Optional)</span></span> | <span data-ttu-id="ce355-183">新規</span><span class="sxs-lookup"><span data-stu-id="ce355-183">Blank</span></span>                                                                                                                                                                               | <span data-ttu-id="ce355-184">このフィールドは空白にできます。</span><span class="sxs-lookup"><span data-stu-id="ce355-184">You can leave the field blank.</span></span>                                                                     |
| <span data-ttu-id="ce355-185">付与タイプ</span><span class="sxs-lookup"><span data-stu-id="ce355-185">Grant Type</span></span>       | <span data-ttu-id="ce355-186">このトークンは認証コードです。</span><span class="sxs-lookup"><span data-stu-id="ce355-186">The token is an authorization code.</span></span>                                                                                                                                                  | <span data-ttu-id="ce355-187">認証コード</span><span class="sxs-lookup"><span data-stu-id="ce355-187">Authorization code</span></span>                                                                            |

### <a name="odata-endpoint"></a><span data-ttu-id="ce355-188">OData エンドポイント</span><span class="sxs-lookup"><span data-stu-id="ce355-188">OData endpoint</span></span>

<span data-ttu-id="ce355-189">エンドポイントも必要です。</span><span class="sxs-lookup"><span data-stu-id="ce355-189">You also need the endpoint.</span></span> <span data-ttu-id="ce355-190">データ ウェアハウス エンドポイントを取得するには、カスタム フィード URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce355-190">To get your Data Warehouse endpoint, you will need the custom feed URL.</span></span> <span data-ttu-id="ce355-191">OData エンドポイントはデータ ウェアハウス ブレードから取得できます。</span><span class="sxs-lookup"><span data-stu-id="ce355-191">You can get the OData endpoint from the Data Warehouse blade.</span></span>

1. <span data-ttu-id="ce355-192">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ce355-192">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="ce355-193">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-193">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="ce355-194">**[その他のタスク]** の **[Intune データ ウェアハウスの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-194">Select **Set up Intune Data Warehouse** under **Other tasks**.</span></span>
4. <span data-ttu-id="ce355-195">**[サード パーティのレポート サービスを使用する]** のカスタム フィード URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ce355-195">Copy the custom feed url under **Use third-party reporting services**.</span></span> <span data-ttu-id="ce355-196">これは次のようになります。`https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="ce355-196">It should look something like: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span></span>

<span data-ttu-id="ce355-197">エンドポイントは次の形式に従います。`https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`</span><span class="sxs-lookup"><span data-stu-id="ce355-197">The endpoint follows the following format: `https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`.</span></span> 

<span data-ttu-id="ce355-198">たとえば、**dates** エンティティは次のようになります。`https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="ce355-198">For example, the **dates** entity looks like: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`</span></span>

<span data-ttu-id="ce355-199">詳細については、「[Intune データ ウェアハウス API エンドポイント](reports-api-url.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce355-199">For more information, see [Intune Data Warehouse API endpoint](reports-api-url.md).</span></span>

### <a name="make-the-rest-call"></a><span data-ttu-id="ce355-200">REST 呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="ce355-200">Make the REST call</span></span>

<span data-ttu-id="ce355-201">Postman のために新しいアクセス トークンを取得するには、Azure AD 認証 URL、クライアント ID、クライアント シークレットを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce355-201">To get a new access token for Postman, you must add the Azure AD authorization URL, add your Client ID, and Client Secret.</span></span> <span data-ttu-id="ce355-202">Postman は、資格情報が入力された認証ページを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ce355-202">Postman will load the authorization page where you will type your credentials.</span></span>

#### <a name="add-the-information-used-to-request-the-token"></a><span data-ttu-id="ce355-203">トークンの要求に必要な情報を追加する</span><span class="sxs-lookup"><span data-stu-id="ce355-203">Add the information used to request the token</span></span>

1.  <span data-ttu-id="ce355-204">まだインストールしていない場合、Postman をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ce355-204">Download Postman if you do not already have it installed.</span></span> <span data-ttu-id="ce355-205">Postman をダウンロードする方法は、[www.getpostman](https://www.getpostman.com) でご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ce355-205">To download Postman, see [www.getpostman](https://www.getpostman.com).</span></span>
2.  <span data-ttu-id="ce355-206">Postman を開きます。</span><span class="sxs-lookup"><span data-stu-id="ce355-206">Open Postman.</span></span> <span data-ttu-id="ce355-207">HTTP 操作の **GET** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-207">Choose the HTTP operation **GET**.</span></span>
3.  <span data-ttu-id="ce355-208">アドレスにエンドポイント URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ce355-208">Paste the endpoint URL into the address.</span></span> <span data-ttu-id="ce355-209">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ce355-209">It should look something like:</span></span>  

    `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  <span data-ttu-id="ce355-210">**[認証]** タブを選択し、**[種類]** 一覧から **[OAuth 2.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-210">Choose the **Authorization** tab, and select **OAuth 2.0** from the **Type** list.</span></span>
5.  <span data-ttu-id="ce355-211">**[Get New Access Token]\(新しいアクセス トークンを取得する\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-211">Select **Get New Access Token**.</span></span>
6.  <span data-ttu-id="ce355-212">Azure でアプリにコールバック URL が追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce355-212">Verify that you have already added the Callback URL to your app in Azure.</span></span> <span data-ttu-id="ce355-213">コールバック URL は `https://www.getpostman.com/oauth2/callback` です。</span><span class="sxs-lookup"><span data-stu-id="ce355-213">The Callback URL is `https://www.getpostman.com/oauth2/callback`.</span></span>
7.  <span data-ttu-id="ce355-214">**[トークン名]** のベアラーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-214">Type Bearer for the **Token Name**.</span></span>
8.  <span data-ttu-id="ce355-215">**[認証 URL]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce355-215">Add the **Auth URL**.</span></span> <span data-ttu-id="ce355-216">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ce355-216">It should look something like:</span></span>  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/`
9.  <span data-ttu-id="ce355-217">**[アクセス トークン URL]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce355-217">Add the **Access Token URL**.</span></span> <span data-ttu-id="ce355-218">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ce355-218">It should look something like:</span></span>  

     `https://login.microsoftonline.com/common/oauth2/token`

10. <span data-ttu-id="ce355-219">Azure で作成し、`Intune Data Warehouse Client` という名前を付けたネイティブ アプリから **[クライアント ID]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce355-219">Add the **Client ID** from the native app that you created in Azure and named `Intune Data Warehouse Client`.</span></span> <span data-ttu-id="ce355-220">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ce355-220">It should look something like:</span></span>  

     `88C8527B-59CB-4679-A9C8-324941748BB4`

11. <span data-ttu-id="ce355-221">**[認証コード]** を選択し、アクセス トークンをローカルで要求します。</span><span class="sxs-lookup"><span data-stu-id="ce355-221">Select **Authorization Code**, and Request access token locally.</span></span>

12. <span data-ttu-id="ce355-222">**[Request Token]\(トークンの要求\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-222">Select **Request Token**.</span></span>

    ![トークンの情報](media\reports-postman_getnewtoken.png)

13. <span data-ttu-id="ce355-224">アクティブな AD 認証ページで資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-224">Type your credentials in the Active AD authorization page.</span></span> <span data-ttu-id="ce355-225">これで、Postman のトークン一覧に `Bearer` という名前のトークンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce355-225">The list of tokens in Postman now contains the token named `Bearer`.</span></span>
14. <span data-ttu-id="ce355-226">**[Use Token]\(トークンの使用\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-226">Select **Use Token**.</span></span> <span data-ttu-id="ce355-227">ヘッダーの一覧には、認証の新しいキー値と値 `Bearer <your-authorization-token>` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce355-227">The list of headers contains the new key value of Authorization and the value `Bearer <your-authorization-token>`.</span></span>

#### <a name="send-the-call-to-the-endpoint-using-postman"></a><span data-ttu-id="ce355-228">Postman を使用し、エンドポイントへの呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="ce355-228">Send the call to the endpoint using Postman</span></span>

1.  <span data-ttu-id="ce355-229">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-229">Select **Send**.</span></span>
2.  <span data-ttu-id="ce355-230">返されるデータは Postman の応答本文に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce355-230">The return data appears in the Postman response body.</span></span>

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a><span data-ttu-id="ce355-232">Intune データ ウェアハウスからデータを取得する REST クライアント (C#) を作成する</span><span class="sxs-lookup"><span data-stu-id="ce355-232">Create a REST client (C#) to get data from the Intune Data Warehouse</span></span>

<span data-ttu-id="ce355-233">次のサンプルには、単純な REST クライアントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce355-233">The following sample contains a simple REST client.</span></span> <span data-ttu-id="ce355-234">このコードでは、.Net ライブラリの **httpClient** クラスが使用されています。</span><span class="sxs-lookup"><span data-stu-id="ce355-234">The code uses the **httpClient** class from the .Net library.</span></span> <span data-ttu-id="ce355-235">クライアントが Azure AD の資格情報を得ると、GET REST 呼び出しを構築し、データ ウェアハウス API から日付エンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce355-235">Once the client gains credentials to Azure AD, the client constructs a GET REST call to retrieve the dates entity from the Data Warehouse API.</span></span>

> [!Note]  
> <span data-ttu-id="ce355-236">次のコード [サンプルは GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs) にあります。</span><span class="sxs-lookup"><span data-stu-id="ce355-236">You can access the following code [sample on GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs).</span></span> <span data-ttu-id="ce355-237">サンプルの最新の変更と更新については、GitHub リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce355-237">Refer to the GitHub repo for the latest changes and updates to the sample.</span></span>

1. <span data-ttu-id="ce355-238">**Microsoft Visual Studio** を起動します。</span><span class="sxs-lookup"><span data-stu-id="ce355-238">Open **Microsoft Visual Studio**.</span></span>
2. <span data-ttu-id="ce355-239">**[ファイル]** > **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-239">Choose **File** > **New Project**.</span></span> <span data-ttu-id="ce355-240">**[Visual C#]** を展開し、**[コンソール アプリ (.Net Framework)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-240">Expand **Visual C#**, and choose **Console App (.Net Framework)**.</span></span> 
3. <span data-ttu-id="ce355-241">プロジェクトに ` IntuneDataWarehouseSamples` という名前を付け、プロジェクトを保存する場所に進み、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-241">Name the project ` IntuneDataWarehouseSamples`, browse to where you would like to save the project, and then select **OK**.</span></span>
4. <span data-ttu-id="ce355-242">ソリューション エクスプローラーでソリューションの名前を右クリックし、**[ソリューションの NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-242">Right-click the name of the solution in the Solution Explorer, and then select **Manage NuGet Packages for Solution**.</span></span> <span data-ttu-id="ce355-243">**[参照]** を選択して、検索ボックスに「`Microsoft.IdentityModel.Clients.ActiveDirectory`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ce355-243">Select **Browse**, and then type `Microsoft.IdentityModel.Clients.ActiveDirectory` in the search box.</span></span>
5. <span data-ttu-id="ce355-244">パッケージを選択し、[Manage Packages for Your Solution]\(ソリューションのパッケージ管理\) で **IntuneDataWarehouseSamples** プロジェクトを選択して、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce355-244">Choose the package, select the **IntuneDataWarehouseSamples** project under Manage Packages for Your Solution, and then select **Install**.</span></span> 
6. <span data-ttu-id="ce355-245">**[同意する]** を選択し、NuGet パッケージ ライセンスに同意します。</span><span class="sxs-lookup"><span data-stu-id="ce355-245">Select **I Accept** to accept the NuGet package license.</span></span>
7. <span data-ttu-id="ce355-246">ソリューション エクスプローラーから `Program.cs` を開きます。</span><span class="sxs-lookup"><span data-stu-id="ce355-246">Open `Program.cs` from the Solution Explorer.</span></span>

    ![Visual Studio のプロジェクト](media\reports-get_rest_data_in.png)

8. <span data-ttu-id="ce355-248">Program.cs のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ce355-248">Replace the code in Program.cs with the following code:</span></span>  
   ```csharp
   namespace IntuneDataWarehouseSamples
   {
   using System;
   using System.Net.Http;
   using System.Net.Http.Headers;
   using Microsoft.IdentityModel.Clients.ActiveDirectory;

   class Program
   {
    static void Main(string[] args)
   {
   /**
   * TODO: Replace the below values with your own.
   * emailAddress - The email address of the user that you will authenticate as.
   *
   * password  - The password for the above email address.
   *    This is inline only for simplicity in this sample. We do not 
   *    recommend storing passwords in plaintext.
   *
   * applicationId - The application ID of the native app that was created in AAD.
   *
   * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
   *      the Azure portal.
   * 
   * collectionName - The name of the warehouse entity collection you would like to 
   *      access.
   */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
   resource: "https://api.manage.microsoft.com/",
   clientId: applicationId,
   userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
   }
   }
   ```

9. <span data-ttu-id="ce355-249">コード サンプルの `TODO` を更新します。</span><span class="sxs-lookup"><span data-stu-id="ce355-249">Update the `TODO`s in the code sample.</span></span>
10. <span data-ttu-id="ce355-250">**Ctrl + F5** を押し、デバッグ モードで Intune.DataWarehouseAPIClient クライアントをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="ce355-250">Press **Ctrl + F5** to build and execute the Intune.DataWarehouseAPIClient client in Debug mode.</span></span>

    ![JSON 形式で取得された日付エンティティ。](media\reports-get_rest_data_output.png)

11. <span data-ttu-id="ce355-252">コンソールの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce355-252">Review the console output.</span></span> <span data-ttu-id="ce355-253">出力には、JSON 形式のデータが含まれています。これは Intune テナントの **dates** エンティティから引き出されたものです。</span><span class="sxs-lookup"><span data-stu-id="ce355-253">The output contains data in a JSON format pulled from the **dates** entity in your Intune tenant.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce355-254">次の手順</span><span class="sxs-lookup"><span data-stu-id="ce355-254">Next steps</span></span>

<span data-ttu-id="ce355-255">認証、API URL 構造、OData エンドポイントの詳細は、「[Intune データ ウェアハウス API を使用する](reports-api-url.md)」にあります。</span><span class="sxs-lookup"><span data-stu-id="ce355-255">You can find details on authorization, the API URL structure, and OData endpoints in [Use the Intune Data Warehouse API](reports-api-url.md).</span></span> 

<span data-ttu-id="ce355-256">「Intune データ ウェアハウスのデータ モデル」にも、API に含まれるデータ エンティティがあります。</span><span class="sxs-lookup"><span data-stu-id="ce355-256">You can also refer to the Intune Data Warehouse Data Model to find the data entities contained in the API.</span></span> <span data-ttu-id="ce355-257">詳細については、「[Intune データ ウェアハウス API データ モデル](reports-ref-data-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce355-257">For more information, see [Intune Data Warehouse API Data Model](reports-ref-data-model.md)</span></span>