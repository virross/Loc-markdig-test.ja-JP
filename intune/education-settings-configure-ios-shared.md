---
title: "iOS Classroom アプリの Intune 共有デバイス設定"
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
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b24ee84d339b728addd753cb309b4d8572e5582
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a><span data-ttu-id="a8956-103">共有 iPad デバイスの Intune 教育設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a8956-103">How to configure Intune education settings for shared iPad devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a8956-104">Intune は iOS Classroom をサポートしています。このアプリは、教師が教室で学習を指導し、生徒のデバイスを操作するのを支援するアプリです。</span><span class="sxs-lookup"><span data-stu-id="a8956-104">Intune supports the iOS Classroom app that helps teachers to guide learning, and control student devices in the classroom.</span></span> <span data-ttu-id="a8956-105">Classroom アプリに加え、Apple では、複数の生徒が 1 台のデバイスを共有できるように、生徒の iPad デバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a8956-105">In addition, to the Classroom app, Apple supports the ability for student iPad devices to be configured such that multiple students can share a single device.</span></span> <span data-ttu-id="a8956-106">本書では、Intune でこの目標を達成する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="a8956-106">This document guides you to achieve this goal with Intune.</span></span>

<span data-ttu-id="a8956-107">専用 (1:1) iPad デバイスを構成し、Classroom アプリを使用する方法については、「[iOS Classroom アプリの Intune 設定を構成する方法](education-settings-configure-ios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8956-107">For information about configuring dedicated (1:1) iPad devices to use the Classroom app, see [How to configure Intune settings for the iOS Classroom app](education-settings-configure-ios.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a8956-108">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="a8956-108">Before you start</span></span>

<span data-ttu-id="a8956-109">共有 iPad 機能を使用するための前提条件:</span><span class="sxs-lookup"><span data-stu-id="a8956-109">The prerequisites to use the shared iPad capabilities are:</span></span>

- <span data-ttu-id="a8956-110">[Apple School Manager](apple-school-manager-set-up-ios.md) と [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617) の設定。</span><span class="sxs-lookup"><span data-stu-id="a8956-110">Setup [Apple School Manager](apple-school-manager-set-up-ios.md) and [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617).</span></span>
- <span data-ttu-id="a8956-111">Apple School Manager 設定の一環として、生徒の[管理対象 Apple ID](http://help.apple.com/schoolmanager/#/tes78b477c81) を設定します。</span><span class="sxs-lookup"><span data-stu-id="a8956-111">As part of Apple School Manager setup, configure [Managed Apple IDs](http://help.apple.com/schoolmanager/#/tes78b477c81) for students.</span></span> <span data-ttu-id="a8956-112">管理対象 Apple ID の詳細については、[こちら](https://support.apple.com/en-us/HT205918)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8956-112">[Learn more about Managed Apple IDs](https://support.apple.com/en-us/HT205918).</span></span>
- <span data-ttu-id="a8956-113">Apple School Manager から同期されたデバイス シリアル番号の登録プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8956-113">Create an enrollment profile for the device serial numbers synced from Apple School Manager.</span></span>

## <a name="step-1---import-your-school-data-into-azure-active-directory"></a><span data-ttu-id="a8956-114">手順 1 - 学校のデータを Azure Active Directory にインポートする</span><span class="sxs-lookup"><span data-stu-id="a8956-114">Step 1 - Import your school data into Azure Active Directory</span></span>

<span data-ttu-id="a8956-115">Microsoft の School Data Sync (SDS) を利用し、既存の Student Information System (SIS) から Azure Active Directory (Azure AD) に学校の記録をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a8956-115">Use Microsoft's School Data Sync (SDS) to import school records from an existing Student Information System (SIS) to Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="a8956-116">SDS は SIS の情報を同期し、それを Azure AD に保管します。</span><span class="sxs-lookup"><span data-stu-id="a8956-116">SDS synchronizes information from your SIS and stores it in Azure AD.</span></span> <span data-ttu-id="a8956-117">Azure AD は、ユーザーやデバイスの整理に役立つ Microsoft の管理システムです。</span><span class="sxs-lookup"><span data-stu-id="a8956-117">Azure AD is a Microsoft management system that helps you organize users and devices.</span></span> <span data-ttu-id="a8956-118">その後、このデータを生徒やクラスの管理に利用できます。</span><span class="sxs-lookup"><span data-stu-id="a8956-118">You can then use this data to help you manage your students and classes.</span></span> <span data-ttu-id="a8956-119">SDS の展開方法については[ここ](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8956-119">[Learn more about how to deploy SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).</span></span>

### <a name="how-to-import-data-using-sds"></a><span data-ttu-id="a8956-120">SDS を利用してデータをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="a8956-120">How to import data using SDS</span></span>

<span data-ttu-id="a8956-121">次のいずれかの方法で SDS に情報をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="a8956-121">You can import information into SDS by using one of the following methods:</span></span>

- <span data-ttu-id="a8956-122">[CSV ファイル](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - コンマ区切り値 (.csv) ファイルを手動でエクスポートし、コンパイルします</span><span class="sxs-lookup"><span data-stu-id="a8956-122">[CSV files](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - Manually export and compile comma-separated value (.csv) files</span></span>
- <span data-ttu-id="a8956-123">[PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - Azure AD との同期を簡単にする SIS プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a8956-123">[PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - An SIS provider that simplifies syncing with Azure AD</span></span>
- <span data-ttu-id="a8956-124">[Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - Azure AD と直接同期する ID 管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="a8956-124">[Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - An identity management solution that syncs directly with Azure AD</span></span>
- <span data-ttu-id="a8956-125">[OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - Azure AD と同期するためにエクスポートし、変換できる CSV 形式</span><span class="sxs-lookup"><span data-stu-id="a8956-125">[OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - A CSV format that you can export and convert to sync with Azure AD</span></span>

### <a name="find-out-more"></a><span data-ttu-id="a8956-126">詳細は以下のページをご覧ください</span><span class="sxs-lookup"><span data-stu-id="a8956-126">Find out more</span></span>

- [<span data-ttu-id="a8956-127">オンプレミスの学校データを Azure AD に同期する方法</span><span class="sxs-lookup"><span data-stu-id="a8956-127">Find out more about the full experience of syncing on-premises school data to Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [<span data-ttu-id="a8956-128">Microsoft School Data Sync の詳細</span><span class="sxs-lookup"><span data-stu-id="a8956-128">Find out more about Microsoft School Data Sync</span></span>](https://sds.microsoft.com/)
- [<span data-ttu-id="a8956-129">Azure Active Directory のライセンス詳細</span><span class="sxs-lookup"><span data-stu-id="a8956-129">Find out more about licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)


## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a><span data-ttu-id="a8956-130">手順 2 - Intune で iOS Education プロファイルを作成し、割り当てる</span><span class="sxs-lookup"><span data-stu-id="a8956-130">Step 2 - Create and assign an iOS Education profile in Intune</span></span>

### <a name="configure-general-settings"></a><span data-ttu-id="a8956-131">全般的な設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-131">Configure general settings</span></span>

1. <span data-ttu-id="a8956-132">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-132">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-133">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-133">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-134">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-134">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="a8956-135">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-135">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5. <span data-ttu-id="a8956-136">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-136">On the profiles blade, choose **Create Profile**.</span></span>
6. <span data-ttu-id="a8956-137">**[プロファイルを作成します]** ブレードで、iOS Education プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-137">On the **Create Profile** blade, enter a **Name** and **Description** for the iOS education profile.</span></span>
7. <span data-ttu-id="a8956-138">**[プラットフォーム]** ドロップダウン リストで、**[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-138">From the **Platform** drop-down list, choose **iOS**.</span></span>
8. <span data-ttu-id="a8956-139">**[プロファイルの種類]** ドロップダウン リストで、**[教育]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-139">From the **Profile type** drop-down list, choose **Education**.</span></span>
9. <span data-ttu-id="a8956-140">**[設定]** > **[構成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-140">Choose **Settings** > **Configure**.</span></span>

<span data-ttu-id="a8956-141">次に、教師の iPad と生徒の iPad の間の信頼関係を確立するための証明書が必要になります。</span><span class="sxs-lookup"><span data-stu-id="a8956-141">Next, you need certificates to establish a trust relationship between teacher and student iPads.</span></span> <span data-ttu-id="a8956-142">証明書は、ユーザー名とパスワードを入力することなく、デバイス間の接続を速やかに認証するために利用されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-142">Certificates are used to seamlessly and silently authenticate connections between devices without having to enter user names and passwords.</span></span>

>[!Important]
><span data-ttu-id="a8956-143">教師の証明書と生徒の証明書は、異なる証明書機関 (CA) が発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8956-143">The teacher and student certificates you use must be issued by different certificate authorities (CAs).</span></span> <span data-ttu-id="a8956-144">既存の証明書インフラストラクチャに接続する下位 CA を新しく 2 つ作成する必要があります。1 つは教師用で、もう 1 つは生徒用です。</span><span class="sxs-lookup"><span data-stu-id="a8956-144">You must create two new subordinate CAs connected to your existing certificate infrastructure; one for teachers, and one for students.</span></span>

<span data-ttu-id="a8956-145">iOS 教育プロファイルは、PFX 証明書のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a8956-145">iOS education profiles support only PFX certificates.</span></span> <span data-ttu-id="a8956-146">SCEP 証明書はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a8956-146">SCEP certificates are not supported.</span></span>

<span data-ttu-id="a8956-147">作成する証明書は、ユーザー認証に加え、サーバー認証に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8956-147">Certificates you create must support server authentication in addition to user authentication.</span></span>

### <a name="configure-teacher-certificates"></a><span data-ttu-id="a8956-148">教師の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-148">Configure teacher certificates</span></span>

<span data-ttu-id="a8956-149">**[教育]** ブレードで **[教師の証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-149">On the **Education** blade, choose **Teacher certificates**.</span></span>

#### <a name="configure-teacher-root-certificate"></a><span data-ttu-id="a8956-150">教師のルート証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-150">Configure teacher root certificate</span></span>

<span data-ttu-id="a8956-151">**[教師のルート証明書]** で、閲覧ボタンを選択し、拡張子が .cer (DER または Base64 エンコード) または .P7B (完全なチェーンあり/なし) の教師のルート証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-151">Under **Teacher root certificate**, choose the browse button to select the teacher root certificate with the extension .cer (DER, or Base64 encoded), or .P7B (with or without full chain).</span></span>

#### <a name="configure-teacher-pkcs12-certificate"></a><span data-ttu-id="a8956-152">教師の PKCS#12 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-152">Configure teacher PKCS#12 certificate</span></span>

<span data-ttu-id="a8956-153">**[教師の PKCS #12 証明書]** で、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="a8956-153">Under **Teacher PKCS#12 certificate**, configure the following values:</span></span>

- <span data-ttu-id="a8956-154">**サブジェクト名の形式** - Intune は証明書の共通名に自動的に接頭辞を追加します。教師の証明書の場合は **leader** で、生徒の証明書の場合は **member** です。</span><span class="sxs-lookup"><span data-stu-id="a8956-154">**Subject name format** - Intune automatically prefixes the certificate common name with **leader**, for the teacher certificate, and **member**, for the student certificate.</span></span>
- <span data-ttu-id="a8956-155">**証明機関**Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8956-155">**Certification authority** - An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="a8956-156">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a8956-156">A Standalone CA is not supported.</span></span>
- <span data-ttu-id="a8956-157">**証明機関名** - 証明機関の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-157">**Certification authority name** - Enter the name of your certification authority.</span></span>
- <span data-ttu-id="a8956-158">**証明書テンプレート名** - 発行元 CA に追加されている証明書テンプレートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-158">**Certificate template name **- Enter the name of a certificate template that has been added to an issuing CA.</span></span>
- <span data-ttu-id="a8956-159">**[更新しきい値 (%)]** - 証明書の有効期間の残りがどの程度 (%) になったら、デバイスが更新を要求するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8956-159">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
- <span data-ttu-id="a8956-160">**証明書の有効期間** - 証明書が失効するまでの残り時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8956-160">**Certificate validity period** - Specify the amount of remaining time before the certificate expires.</span></span> <span data-ttu-id="a8956-161">指定した証明書テンプレートの有効期限よりも小さい値を指定できますが、大きい値は指定できません。</span><span class="sxs-lookup"><span data-stu-id="a8956-161">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="a8956-162">たとえば、証明書テンプレートで証明書の有効期限が 2 年になっている場合は、この値を 1 年することはできますが、5 年にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8956-162">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="a8956-163">また、発行元の CA の証明書の残りの有効期限よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8956-163">The value must also be lower than the remaining validity period of the issuing CA certificate.</span></span>

<span data-ttu-id="a8956-164">教師の証明書の構成が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-164">When you have finished configuring teacher certificates, choose **OK**.</span></span>

### <a name="configure-student-certificates"></a><span data-ttu-id="a8956-165">生徒の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-165">Configure student certificates</span></span>

1. <span data-ttu-id="a8956-166">**[教育]** ブレードで **[学生の証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-166">On the **Education blade**, choose **Student certificates**.</span></span>
2. <span data-ttu-id="a8956-167">**[学生の証明書]** ブレードで、**[学生用デバイス証明書]** の種類の一覧から **[共有 iPad]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-167">On the **Student certificates** blade, from the **Student device certificates type** list, choose **Shared iPad**.</span></span>

#### <a name="configure-student-root-certificate"></a><span data-ttu-id="a8956-168">生徒のルート証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-168">Configure student root certificate</span></span>

<span data-ttu-id="a8956-169">**[デバイスのルート証明書]** で、閲覧ボタンを選択し、拡張子が .cer (DER または Base64 エンコード) または .P7B (完全なチェーンあり/なし) の学生のルート証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-169">Under **Device root certificate**, choose the browse button to select the student root certificate with the extension .cer (DER, or Base64 encoded), or .P7B (with or without full chain).</span></span>

#### <a name="configure-device-pkcs12-certificate"></a><span data-ttu-id="a8956-170">デバイスの PKCS #12 証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a8956-170">Configure device PKCS#12 certificate</span></span>

<span data-ttu-id="a8956-171">**[学生の PKCS #12 証明書]** で、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="a8956-171">Under **Student PKCS#12 certificate**, configure the following values:</span></span>

- <span data-ttu-id="a8956-172">**サブジェクト名の形式** - Intune は証明書の共通名に自動的に接頭辞を追加します。教師の証明書の場合は leader で、デバイスの証明書の場合は member です。</span><span class="sxs-lookup"><span data-stu-id="a8956-172">**Subject name format** - Intune automatically prefixes the certificate common name with leader, for the teacher certificate, and member, for the device certificate.</span></span>
- <span data-ttu-id="a8956-173">**証明機関**Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8956-173">**Certification authority** - An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="a8956-174">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a8956-174">A Standalone CA is not supported.</span></span>
- <span data-ttu-id="a8956-175">**証明機関名** - 証明機関の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-175">**Certification authority name** - Enter the name of your certification authority.</span></span>
- <span data-ttu-id="a8956-176">**証明書テンプレート名** - 発行元 CA に追加されている証明書テンプレートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-176">**Certificate template name** - Enter the name of a certificate template that has been added to an issuing CA.</span></span>
- <span data-ttu-id="a8956-177">**[更新しきい値 (%)]** - 証明書の有効期間の残りがどの程度 (%) になったら、デバイスが更新を要求するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8956-177">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
- <span data-ttu-id="a8956-178">**証明書の有効期間** - 証明書が失効するまでの残り時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8956-178">**Certificate validity period** - Specify the amount of remaining time before the certificate expires.</span></span> <span data-ttu-id="a8956-179">指定した証明書テンプレートの有効期限よりも小さい値を指定できますが、大きい値は指定できません。</span><span class="sxs-lookup"><span data-stu-id="a8956-179">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="a8956-180">たとえば、証明書テンプレートで証明書の有効期限が 2 年になっている場合は、この値を 1 年することはできますが、5 年にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8956-180">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="a8956-181">また、発行元の CA の証明書の残りの有効期限よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8956-181">The value must also be lower than the remaining validity period of the issuing CA certificate.</span></span>

<span data-ttu-id="a8956-182">証明書の構成が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-182">When you are finished configuring certificates, choose **OK**.</span></span>

### <a name="complete-certificate-setup"></a><span data-ttu-id="a8956-183">証明書の設定を完了する</span><span class="sxs-lookup"><span data-stu-id="a8956-183">Complete Certificate Setup</span></span>

1. <span data-ttu-id="a8956-184">**[教育]** ブレードで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-184">On the **Education** blade, choose **OK**.</span></span>
2. <span data-ttu-id="a8956-185">**[プロファイルの作成]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-185">On the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="a8956-186">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-186">The profile is created and appears on the profiles list blade.</span></span>

## <a name="step-3---create-a-device-category"></a><span data-ttu-id="a8956-187">手順 3 - デバイス カテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="a8956-187">Step 3 - Create a device category</span></span>

1. <span data-ttu-id="a8956-188">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-188">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-189">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-189">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-190">**[Intune]** ブレードで、**[デバイスの登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-190">On the **Intune** blade, choose **Device enrollment**.</span></span>
4. <span data-ttu-id="a8956-191">**[登録 - 概要]** ブレードで、**[デバイス カテゴリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-191">On the **Enrollment - Overview** blade, choose **Device Categories**.</span></span>
5. <span data-ttu-id="a8956-192">**[登録 - デバイス カテゴリ]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-192">On the **Enrollment - Device Categories** blade, choose **Create**.</span></span>
6. <span data-ttu-id="a8956-193">**[デバイス カテゴリの作成]** ブレードで、カスタム プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-193">On the **Create device category** blade, enter a **Name** and **Description** for the category.</span></span>
7. <span data-ttu-id="a8956-194">**[デバイス カテゴリの作成]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-194">On the **Create device category** blade, choose **Create**.</span></span>

<span data-ttu-id="a8956-195">**[登録 - デバイス カテゴリ]** ブレードにデバイス カテゴリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-195">The device category is created in the **Enrollment – Device Categories** blade.</span></span>

## <a name="step-4--create-a-dynamic-group"></a><span data-ttu-id="a8956-196">手順 4 – 動的グループを作成する</span><span class="sxs-lookup"><span data-stu-id="a8956-196">Step 4 – Create a dynamic group</span></span>

1. <span data-ttu-id="a8956-197">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-197">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-198">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-198">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-199">**[Intune]** ブレードで、**[グループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-199">On the **Intune** blade, choose **Groups**.</span></span>
4. <span data-ttu-id="a8956-200">**[ユーザーとグループ - すべてのグループ]** ブレードで、**[新しいグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-200">On the **Users and Groups – All Groups** blade, choose **New Group**.</span></span>
5. <span data-ttu-id="a8956-201">**[グループ]** ブレードで、グループの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-201">On the **Group** blade, enter a **Name** and **Description** for the group.</span></span>
6. <span data-ttu-id="a8956-202">**[メンバーシップの種類]** ドロップダウン リストから、**[動的デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-202">From the **Membership Type** drop-down list, choose **Dynamic Device**.</span></span>
7. <span data-ttu-id="a8956-203">**[動的デバイス メンバー]** を選択し、メンバーシップ ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8956-203">Choose **Dynamic device members** to create membership rules.</span></span>
8. <span data-ttu-id="a8956-204">**[動的メンバーシップ ルール]** ブレードで:</span><span class="sxs-lookup"><span data-stu-id="a8956-204">On the **Dynamic membership rules** blade:</span></span>
1. <span data-ttu-id="a8956-205">**[追加するデバイスの場所]** ドロップダウン リストから **[デバイス カテゴリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-205">Select **deviceCategory** from the **Add devices where** drop-down list.</span></span>
2. <span data-ttu-id="a8956-206">**[等しい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-206">Choose **Equals**</span></span>
3. <span data-ttu-id="a8956-207">作成したデバイス カテゴリを空のテキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-207">Enter the device category you created in the blank text box</span></span>
9. <span data-ttu-id="a8956-208">**[動的メンバーシップ ルール]** ブレードで、**[クエリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-208">On the **Dynamic membership rules** blade, choose **Add query**.</span></span>
10. <span data-ttu-id="a8956-209">**[グループ]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-209">On the **Group** blade, choose **Create**.</span></span>

<span data-ttu-id="a8956-210">**[ユーザーとグループ - すべてのグループ]** ブレードで動的グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-210">The dynamic group is created in the **Users and Groups – All Groups** blade.</span></span>

## <a name="step-5--assign-a-device-to-a-category-carts"></a><span data-ttu-id="a8956-211">手順 5 – デバイスをカテゴリに割り当てる (カート)</span><span class="sxs-lookup"><span data-stu-id="a8956-211">Step 5 – Assign a device to a category (Carts)</span></span>

1. <span data-ttu-id="a8956-212">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-212">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-213">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-213">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-214">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-214">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="a8956-215">**[デバイス]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-215">On the **Devices** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="a8956-216">**[デバイス - すべてのデバイス]** ブレードで、デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-216">On the **Devices – All devices** blade, choose a device.</span></span>
6. <span data-ttu-id="a8956-217">[デバイス] ブレードで、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-217">On the device blade, choose **Properties**.</span></span>
7. <span data-ttu-id="a8956-218">デバイスのプロパティ ブレードで、**[デバイス カテゴリ]** テキスト ボックスにデバイス カテゴリを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-218">On the device’s properties blade, enter the device category in the **Device category** text box.</span></span>
8. <span data-ttu-id="a8956-219">[デバイス] ブレードで、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-219">On the device blade, choose **Save**.</span></span>

<span data-ttu-id="a8956-220">これでデバイスがデバイス カテゴリに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a8956-220">The device is now associated to the device category.</span></span> <span data-ttu-id="a8956-221">作成したデバイス カテゴリに関連付けるすべてのデバイスにこの過程を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8956-221">Repeat this process for all the devices you want to associate to the device category you created.</span></span>

## <a name="step-6--create-classroom-profiles"></a><span data-ttu-id="a8956-222">手順 6 – 教室プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="a8956-222">Step 6 – Create classroom profiles</span></span>

1. <span data-ttu-id="a8956-223">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-223">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-224">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-224">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-225">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-225">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="a8956-226">**[デバイス構成]** ブレードで、**[管理]** > **[カート プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-226">On the **Device Configuration** blade, choose **Manage** > **Cart Profiles**.</span></span>
5. <span data-ttu-id="a8956-227">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-227">On the profiles blade, choose **Create Profile**.</span></span>
6. <span data-ttu-id="a8956-228">**[関連付けの作成]** ブレードで、**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8956-228">On the **Create Association** blade, enter a **Name** and **Description**.</span></span>
7. <span data-ttu-id="a8956-229">**[クラスの選択]** > **[構成]** の順に選択し、カート プロファイルにグループを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a8956-229">Choose **Select Classes** > **Configure** to associate groups to the Cart Profile.</span></span>
8. <span data-ttu-id="a8956-230">カート プロファイルに追加するクラスを選択し、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-230">Choose the classes to include to the Cart Profile then choose **Select**.</span></span> 
9. <span data-ttu-id="a8956-231">**[クラスの選択]** > **[構成]** の順に選択し、カート プロファイルにグループを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a8956-231">Choose **Select Carts** > **Configure** to associate groups to the Cart Profile.</span></span>
10. <span data-ttu-id="a8956-232">カート プロファイルに追加するグループを選択し、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-232">Choose the groups to include to the Cart Profile then choose **Select**.</span></span>
11. <span data-ttu-id="a8956-233">**[関連付けの作成]** ブレードで、**[保存]** を選択してカート プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a8956-233">On the **Create Association** blade, choose **Save** to save the Cart Profile.</span></span>

<span data-ttu-id="a8956-234">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-234">The profile is created and appears on the profiles list blade.</span></span>

## <a name="step-7---assign-the-cart-profile-to-classes"></a><span data-ttu-id="a8956-235">手順 7 - カート プロファイルをクラスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a8956-235">Step 7 - Assign the Cart Profile to Classes</span></span>

1. <span data-ttu-id="a8956-236">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8956-236">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8956-237">**[その他のサービス]** > **[その他]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-237">Choose **More Services** > **Other** > **Intune**.</span></span>
3. <span data-ttu-id="a8956-238">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-238">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="a8956-239">**[デバイス構成]** ブレードで、**[モニター]** > **[割り当ての状態]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-239">On the **Device Configuration** blade, choose **Monitor** > **Assignment status**.</span></span>
5. <span data-ttu-id="a8956-240">**[割り当ての状態]** ブレードで、作成した **[カート プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-240">On the **Assignment status** blade, select the **Cart Profile** you created.</span></span>
6. <span data-ttu-id="a8956-241">**[カート プロファイル]** ブレードで **[割り当て]** を選択し、**[含める]** で **[含めるグループを選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-241">On the **Cart Profile** blade choose **Assignments** and then, under **Include** choose **Select groups to include**.</span></span>
7. <span data-ttu-id="a8956-242">カート プロファイルのターゲットにするクラスを選択し (グループを選択しないでください)、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-242">Select the classes you want the cart profile to target (do not select a group), then choose **Select**.</span></span> 
8. <span data-ttu-id="a8956-243">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8956-243">When you are finished, choose **Save**.</span></span>

<span data-ttu-id="a8956-244">割り当てが完了します。教室の割り当てに基づき、教室プロファイルがターゲットのデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="a8956-244">The assignment completes, and Intune deploys the Classroom profile to the targeted devices based on the classroom assignment.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8956-245">次の手順</span><span class="sxs-lookup"><span data-stu-id="a8956-245">Next Steps</span></span>

<span data-ttu-id="a8956-246">これで生徒は生徒間でデバイスを共有できます。また、教室にある iPad を選択し、PIN でログインし、自分のコンテンツでパーソナル化できます。</span><span class="sxs-lookup"><span data-stu-id="a8956-246">Now students can share devices between students, and students can pick up any iPad in a classroom, log in with a PIN and have it personalized with their content.</span></span> <span data-ttu-id="a8956-247">共有 iPad に関する情報については、[Apple の Web サイト](https://www.apple.com/education/it/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8956-247">For more information about Shared iPads, see the [Apple website](https://www.apple.com/education/it/).</span></span>
