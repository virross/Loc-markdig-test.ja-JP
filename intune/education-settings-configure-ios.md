---
title: "iOS Classroom アプリの Intune 設定"
titlesuffix: Azure portal
description: "iOS デバイスの Classroom アプリの設定を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f31ad2226052b4a681bc79e366e7d1def01c3cc4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a><span data-ttu-id="b7e99-103">iOS Classroom アプリの Intune 設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b7e99-103">How to configure Intune settings for the iOS Classroom app</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a><span data-ttu-id="b7e99-104">概要</span><span class="sxs-lookup"><span data-stu-id="b7e99-104">Introduction</span></span>
<span data-ttu-id="b7e99-105">[Classroom](https://itunes.apple.com/app/id1085319084) は、教師が教室で学習を指導し、生徒のデバイスを操作するのを支援するアプリです。</span><span class="sxs-lookup"><span data-stu-id="b7e99-105">[Classroom](https://itunes.apple.com/app/id1085319084) is an app that helps teachers to guide learning, and control student devices in the classroom.</span></span> <span data-ttu-id="b7e99-106">たとえば、教師はこのアプリを利用して次のことができます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-106">For example, using the app, a teacher can:</span></span>

- <span data-ttu-id="b7e99-107">生徒のデバイスでアプリを起動する</span><span class="sxs-lookup"><span data-stu-id="b7e99-107">Open apps on student devices</span></span>
- <span data-ttu-id="b7e99-108">iPad 画面をロックし、ロックを解除する</span><span class="sxs-lookup"><span data-stu-id="b7e99-108">Lock, and unlock the iPad screen</span></span>
- <span data-ttu-id="b7e99-109">生徒の iPad の画面を表示する</span><span class="sxs-lookup"><span data-stu-id="b7e99-109">View the screen of a student iPad</span></span>
- <span data-ttu-id="b7e99-110">生徒の iPad を操作し、本の中のブックマークや章に移動する</span><span class="sxs-lookup"><span data-stu-id="b7e99-110">Navigate students iPads to a bookmark, or chapter in a book</span></span>
- <span data-ttu-id="b7e99-111">生徒の iPad を画面を Apple TV に映す</span><span class="sxs-lookup"><span data-stu-id="b7e99-111">Display the screen from a student iPad on an Apple TV</span></span>

<span data-ttu-id="b7e99-112">Intune iOS **Education** デバイス プロファイルとこのトピックの情報を利用し、Classroom アプリやそれを使用するデバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-112">Use the Intune iOS **Education** device profile, and the information in this topic to help you set up the Classroom app, and the devices on which you use it.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b7e99-113">開始する前に</span><span class="sxs-lookup"><span data-stu-id="b7e99-113">Before you start</span></span>

<span data-ttu-id="b7e99-114">以上の設定を構成する前に、次の事項について検討してください。</span><span class="sxs-lookup"><span data-stu-id="b7e99-114">Consider the following before you begin to configure these settings:</span></span>

- <span data-ttu-id="b7e99-115">教師と生徒の両方の iPad を Intune に登録する必要があります</span><span class="sxs-lookup"><span data-stu-id="b7e99-115">Both teachers and student iPads must be enrolled in Intune</span></span>
- <span data-ttu-id="b7e99-116">教師のデバイスに [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) アプリがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b7e99-116">Ensure that you have installed the [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) app on the teacher’s device.</span></span> <span data-ttu-id="b7e99-117">アプリは手動でインストールすることも、[Intune アプリ管理](app-management.md)を利用してインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-117">You can either install the app manually, or use [Intune app management](app-management.md).</span></span>
- <span data-ttu-id="b7e99-118">教師のデバイスと生徒のデバイスの間の接続を認証するために証明書を構成する必要があります (手順 2 参照)</span><span class="sxs-lookup"><span data-stu-id="b7e99-118">You must configure certificates to authenticate connections between teacher and student devices (see Step 2)</span></span>
- <span data-ttu-id="b7e99-119">教師と生徒の iPad を同じ Wi-Fi ネットワークに置き、Bluetooth を有効にする必要があります</span><span class="sxs-lookup"><span data-stu-id="b7e99-119">Teacher and student iPads must be on the same Wi-Fi network, and also have Bluetooth enabled</span></span>
- <span data-ttu-id="b7e99-120">iOS 9.3 以降が内蔵され、監視付きの iPad で Classroom アプリを実行します</span><span class="sxs-lookup"><span data-stu-id="b7e99-120">The Classroom app runs on supervised iPads running iOS 9.3 or later</span></span>
- <span data-ttu-id="b7e99-121">今回のリリースでは、Intune は 1:1 シナリオを管理できます。各生徒に専用の iPad が与えられます</span><span class="sxs-lookup"><span data-stu-id="b7e99-121">In this release, Intune supports managing a 1:1 scenario where each student has their own dedicated iPad</span></span>


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a><span data-ttu-id="b7e99-122">手順 1 - 学校のデータを Azure Active Directory にインポートする</span><span class="sxs-lookup"><span data-stu-id="b7e99-122">Step 1 - Import your school data into Azure Active Directory</span></span>

<span data-ttu-id="b7e99-123">Microsoft の School Data Sync (SDS) を利用し、既存の Student Information System (SIS) から Azure Active Directory (Azure AD) に学校の記録をインポートします。</span><span class="sxs-lookup"><span data-stu-id="b7e99-123">Use Microsoft's School Data Sync (SDS) to import school records from an existing Student Information System (SIS) to Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="b7e99-124">SDS は SIS の情報を同期し、それを Azure AD に保管します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-124">SDS synchronizes information from your SIS and stores it in Azure AD.</span></span> <span data-ttu-id="b7e99-125">Azure AD は、ユーザーやデバイスの整理に役立つ Microsoft の管理システムです。</span><span class="sxs-lookup"><span data-stu-id="b7e99-125">Azure AD is a Microsoft management system that helps you organize users and devices.</span></span> <span data-ttu-id="b7e99-126">その後、このデータを生徒やクラスの管理に利用できます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-126">You can then use this data to help you manage your students and classes.</span></span> <span data-ttu-id="b7e99-127">SDS の展開方法については[ここ](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7e99-127">[Learn more about how to deploy SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).</span></span>

### <a name="how-to-import-data-using-sds"></a><span data-ttu-id="b7e99-128">SDS を利用してデータをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="b7e99-128">How to import data using SDS</span></span>

<span data-ttu-id="b7e99-129">次のいずれかの方法で SDS に情報をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-129">You can import information into SDS by using one of the following methods:</span></span>

- <span data-ttu-id="b7e99-130">[CSV ファイル](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - コンマ区切り値 (.csv) ファイルを手動でエクスポートし、コンパイルします</span><span class="sxs-lookup"><span data-stu-id="b7e99-130">[CSV files](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - Manually export and compile comma-separated value (.csv) files</span></span>
- <span data-ttu-id="b7e99-131">[PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - Azure AD との同期を簡単にする SIS プロバイダー</span><span class="sxs-lookup"><span data-stu-id="b7e99-131">[PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - An SIS provider that simplifies syncing with Azure AD</span></span>
- <span data-ttu-id="b7e99-132">[Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - Azure AD と直接同期する ID 管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="b7e99-132">[Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - An identity management solution that syncs directly with Azure AD</span></span>
- <span data-ttu-id="b7e99-133">[OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - Azure AD と同期するためにエクスポートし、変換できる CSV 形式</span><span class="sxs-lookup"><span data-stu-id="b7e99-133">[OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - A CSV format that you can export and convert to sync with Azure AD</span></span>

### <a name="find-out-more"></a><span data-ttu-id="b7e99-134">詳細は以下のページをご覧ください</span><span class="sxs-lookup"><span data-stu-id="b7e99-134">Find out more</span></span>

- [<span data-ttu-id="b7e99-135">オンプレミスの学校データを Azure AD に同期する方法</span><span class="sxs-lookup"><span data-stu-id="b7e99-135">Find out more about the full experience of syncing on-premises school data to Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [<span data-ttu-id="b7e99-136">Microsoft School Data Sync の詳細</span><span class="sxs-lookup"><span data-stu-id="b7e99-136">Find out more about Microsoft School Data Sync</span></span>](https://sds.microsoft.com/)
- [<span data-ttu-id="b7e99-137">Azure Active Directory のライセンス詳細</span><span class="sxs-lookup"><span data-stu-id="b7e99-137">Find out more about licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a><span data-ttu-id="b7e99-138">手順 2 - Intune で iOS Education プロファイルを作成し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="b7e99-138">Step 2 - Create and assign an iOS Education profile in Intune</span></span>

### <a name="configure-general-settings"></a><span data-ttu-id="b7e99-139">全般的な設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-139">Configure general settings</span></span>

1. <span data-ttu-id="b7e99-140">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b7e99-140">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b7e99-141">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-141">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="b7e99-142">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-142">On the **Intune** blade, choose **Configure devices**.</span></span>
4.  <span data-ttu-id="b7e99-143">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-143">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5.  <span data-ttu-id="b7e99-144">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-144">On the profiles blade, choose **Create Profile**.</span></span>
6.  <span data-ttu-id="b7e99-145">**[プロファイルを作成します]** ブレードで、iOS Education プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-145">On the **Create Profile** blade, enter a **Name** and **Description** for the iOS education profile.</span></span>
7.  <span data-ttu-id="b7e99-146">**[プラットフォーム]** ドロップダウン リストで、**[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-146">From the **Platform** drop-down list, choose **iOS**.</span></span>
8.  <span data-ttu-id="b7e99-147">**[プロファイルの種類]** ドロップダウン リストで、**[教育]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-147">From the **Profile type** drop-down list, choose **Education**.</span></span>
9.  <span data-ttu-id="b7e99-148">**[設定]** > **[構成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-148">Choose **Settings** > **Configure**.</span></span>


<span data-ttu-id="b7e99-149">次に、教師の iPad と生徒の iPad の間の信頼関係を確立するための証明書が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b7e99-149">Next, you need certificates to establish a trust relationship between teacher and student iPads.</span></span> <span data-ttu-id="b7e99-150">証明書は、ユーザー名とパスワードを入力することなく、デバイス間の接続を速やかに認証するために利用されます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-150">Certificates are used to seamlessly and silently authenticate connections between devices without having to enter user names and passwords.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b7e99-151">教師の証明書と生徒の証明書は、異なる証明書機関 (CA) が発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e99-151">The teacher and student certificates you use must be issued by different certification authorities (CAs).</span></span> <span data-ttu-id="b7e99-152">既存の証明書インフラストラクチャに接続する下位 CA を新しく 2 つ作成する必要があります。1 つは教師用で、もう 1 つは生徒用です。</span><span class="sxs-lookup"><span data-stu-id="b7e99-152">You must create two new subordinate CAs connected to your existing certificate infrastructure; one for teachers, and one for students.</span></span>

<span data-ttu-id="b7e99-153">iOS 教育プロファイルは、PFX 証明書のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b7e99-153">iOS education profiles support only PFX certificates.</span></span> <span data-ttu-id="b7e99-154">SCEP 証明書はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-154">SCEP certificates are not supported.</span></span>

<span data-ttu-id="b7e99-155">作成する証明書は、ユーザー認証に加え、サーバー認証に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e99-155">Certificates you create must support server authentication in addition to user authentication.</span></span>

### <a name="configure-teacher-certificates"></a><span data-ttu-id="b7e99-156">教師の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-156">Configure teacher certificates</span></span>

<span data-ttu-id="b7e99-157">**[教育]** ブレードで **[教師の証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-157">On the **Education** blade, choose **Teacher certificates**.</span></span>

#### <a name="configure-teacher-root-certificate"></a><span data-ttu-id="b7e99-158">教師のルート証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-158">Configure teacher root certificate</span></span>

<span data-ttu-id="b7e99-159">**[教師のルート証明書]** で、閲覧ボタンを選択し、拡張子が .cer (DER または Base64 エンコード) または .P7B (完全なチェーンあり/なし) の教師のルート証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-159">Under **Teacher root certificate**, choose the browse button to select the teacher root certificate with the extension .cer (DER, or Base64 encoded), or .P7B (with or without full chain).</span></span>

#### <a name="configure-teacher-pkcs12-certificate"></a><span data-ttu-id="b7e99-160">教師の PKCS#12 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-160">Configure teacher PKCS#12 certificate</span></span>

<span data-ttu-id="b7e99-161">**[教師の PKCS #12 証明書]** で、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-161">Under **Teacher PKCS#12 certificate**, configure the following values:</span></span>

- <span data-ttu-id="b7e99-162">**サブジェクト名の形式** - Intune は証明書の共通名に自動的に接頭辞を追加します。教師の証明書の場合は **leader** で、生徒の証明書の場合は **member** です。</span><span class="sxs-lookup"><span data-stu-id="b7e99-162">**Subject name format** - Intune automatically prefixes the certificate common name with **leader**, for the teacher certificate, and **member**, for the student certificate.</span></span>
- <span data-ttu-id="b7e99-163">**証明機関**Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b7e99-163">**Certification authority** - An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="b7e99-164">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-164">A Standalone CA is not supported.</span></span> 
- <span data-ttu-id="b7e99-165">**証明機関名** - 証明機関の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-165">**Certification authority name** - Enter the name of your certification authority.</span></span>
- <span data-ttu-id="b7e99-166">**証明書テンプレート名** - 発行元 CA に追加されている証明書テンプレートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-166">**Certificate template name** - Enter the name of a certificate template that has been added to an issuing CA.</span></span> 
- <span data-ttu-id="b7e99-167">**[更新しきい値 (%)]** - 証明書の有効期間の残りがどの程度 (%) になったら、デバイスが更新を要求するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-167">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
- <span data-ttu-id="b7e99-168">**証明書の有効期間** - 証明書が失効するまでの残り時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-168">**Certificate validity period** - Specify the amount of remaining time before the certificate expires.</span></span>
<span data-ttu-id="b7e99-169">指定した証明書テンプレートの有効期限よりも小さい値を指定できますが、大きい値は指定できません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-169">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="b7e99-170">たとえば、証明書テンプレートで証明書の有効期限が 2 年になっている場合は、この値を 1 年することはできますが、5 年にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-170">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="b7e99-171">また、発行元の CA の証明書の残りの有効期限よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e99-171">The value must also be lower than the remaining validity period of the issuing CA certificate.</span></span>

<span data-ttu-id="b7e99-172">証明書の構成が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-172">When you have finished configuring certificates, choose **OK**.</span></span>

### <a name="configure-student-certificates"></a><span data-ttu-id="b7e99-173">生徒の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-173">Configure student certificates</span></span>

1.  <span data-ttu-id="b7e99-174">**[教育]** ブレードで **[学生の証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-174">On the **Education** blade, choose **Student certificates**.</span></span>
2.  <span data-ttu-id="b7e99-175">**[学生の証明書]** ブレードで、**[Student device certificates (学生デバイス証明書)]** の種類の一覧から **[1:1]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-175">On the **Student certificates** blade, from the **Student device certificates** type list, choose **1:1**.</span></span>

#### <a name="configure-student-root-certificate"></a><span data-ttu-id="b7e99-176">生徒のルート証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-176">Configure student root certificate</span></span>

<span data-ttu-id="b7e99-177">**[学生のルート証明書]** で、閲覧ボタンを選択し、拡張子が .cer (DER または Base64 エンコード) または .P7B (完全なチェーンあり/なし) の学生のルート証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-177">Under **Student root certificate**, choose the browse button to select the student root certificate with the extension .cer (DER, or Base64 encoded), or .P7B (with or without full chain).</span></span>

#### <a name="configure-student-pkcs12-certificate"></a><span data-ttu-id="b7e99-178">生徒の PKCS #12 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="b7e99-178">Configure student PKCS#12 certificate</span></span>

<span data-ttu-id="b7e99-179">**[学生の PKCS #12 証明書]** で、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-179">Under **Student PKCS#12 certificate**, configure the following values:</span></span>

- <span data-ttu-id="b7e99-180">**サブジェクト名の形式** - Intune は証明書の共通名に自動的に接頭辞を追加します。教師の証明書の場合は **leader** で、生徒の証明書の場合は **member** です。</span><span class="sxs-lookup"><span data-stu-id="b7e99-180">**Subject name format** - Intune automatically prefixes the certificate common name with **leader**, for the teacher certificate, and **member**, for the student certificate.</span></span>
- <span data-ttu-id="b7e99-181">**証明機関**Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b7e99-181">**Certification authority** - An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="b7e99-182">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-182">A Standalone CA is not supported.</span></span> 
- <span data-ttu-id="b7e99-183">**証明機関名** - 証明機関の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-183">**Certification authority name** - Enter the name of your certification authority.</span></span>
- <span data-ttu-id="b7e99-184">**証明書テンプレート名** - 発行元 CA に追加されている証明書テンプレートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-184">**Certificate template name** - Enter the name of a certificate template that has been added to an issuing CA.</span></span> 
- <span data-ttu-id="b7e99-185">**[更新しきい値 (%)]** - 証明書の有効期間の残りがどの程度 (%) になったら、デバイスが更新を要求するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-185">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
- <span data-ttu-id="b7e99-186">**証明書の有効期間** - 証明書が失効するまでの残り時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-186">**Certificate validity period** - Specify the amount of remaining time before the certificate expires.</span></span>
<span data-ttu-id="b7e99-187">指定した証明書テンプレートの有効期限よりも小さい値を指定できますが、大きい値は指定できません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-187">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="b7e99-188">たとえば、証明書テンプレートで証明書の有効期限が 2 年になっている場合は、この値を 1 年することはできますが、5 年にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7e99-188">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="b7e99-189">また、発行元の CA の証明書の残りの有効期限よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e99-189">The value must also be lower than the remaining validity period of the issuing CA certificate.</span></span>

<span data-ttu-id="b7e99-190">証明書の構成が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-190">When you are finished configuring certificates, choose **OK**.</span></span>

## <a name="finish-up"></a><span data-ttu-id="b7e99-191">完了</span><span class="sxs-lookup"><span data-stu-id="b7e99-191">Finish up</span></span>

1.  <span data-ttu-id="b7e99-192">**[教育]** ブレードで [OK] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-192">On the **Education** blade, choose OK.</span></span>
2.  <span data-ttu-id="b7e99-193">**[プロファイルの作成]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7e99-193">On the **Create Profile** blade, choose **Create**.</span></span>
    
<span data-ttu-id="b7e99-194">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-194">The profile is created and appears on the profiles list blade.</span></span>

<span data-ttu-id="b7e99-195">学校データと Azure AD を同期したときに作成された教室グループの生徒用デバイスにプロファイルを割り当てます (「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」参照)。</span><span class="sxs-lookup"><span data-stu-id="b7e99-195">Assign the profile to student devices in the classroom groups that were created when you synchronized your school data with Azure AD (see [How to assign device profiles](device-profile-assign.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7e99-196">次の手順</span><span class="sxs-lookup"><span data-stu-id="b7e99-196">Next steps</span></span>

<span data-ttu-id="b7e99-197">これで、教師が Classroom アプリを使用するとき、生徒のデバイスを完全に操作できます。</span><span class="sxs-lookup"><span data-stu-id="b7e99-197">Now, when a teacher uses the Classroom app, they will have full control over student devices.</span></span>

<span data-ttu-id="b7e99-198">Classroom アプリの詳細については、Apple Web サイトの [Classroom ヘルプ](https://help.apple.com/classroom/ipad/2.0/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7e99-198">For more information about the Classroom app, see [Classroom help](https://help.apple.com/classroom/ipad/2.0/), on the Apple web site.</span></span>

<span data-ttu-id="b7e99-199">受講者に対して共有 iPad デバイスを構成する場合は、[共有 iPad デバイスの Intune 教育設定の構成方法](education-settings-configure-ios-shared.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7e99-199">If you want to configure shared iPad devices for students, see [How to configure Intune education settings for shared iPad devices](education-settings-configure-ios-shared.md).</span></span>
