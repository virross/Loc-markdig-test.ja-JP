---
title: "Azure での Intune の機能の移動先"
titlesuffix: Azure portal
description: "Azure Portal で Intune の機能がどこにあるかを確認できます。"
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41b358f48412585ec40e369225b4263012bfd2f8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="where-did-my-intune-feature-go-in-azure"></a><span data-ttu-id="a9ffe-103">Azure での Intune の機能の移動先</span><span class="sxs-lookup"><span data-stu-id="a9ffe-103">Where did my Intune feature go in Azure?</span></span>
<span data-ttu-id="a9ffe-104">Intune から Azure Portal に移行する際に、いくつかのタスクがより論理的に整理されました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-104">We took the opportunity to organize some tasks more logically as we moved Intune into the Azure portal.</span></span> <span data-ttu-id="a9ffe-105">しかし、このような改善を行えば、新しい構成を学ばなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-105">But every improvement comes with the cost of learning the new organization.</span></span> <span data-ttu-id="a9ffe-106">このリファレンス ガイドは、従来のポータルを使用した Intune の知識があり、Intune で行われていた内容を Azure Portal ではどのように実行されるのかについて関心があるユーザーに向けて作成しました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-106">So, we created this reference guide for those of you who are thoroughly familiar with Intune in the classic portal and are wondering how to get something done in Intune in the Azure portal.</span></span> <span data-ttu-id="a9ffe-107">この記事でお探しの機能が記載されていない場合は、今後更新できるように記事の最後にコメントを残してください。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-107">If this article doesn’t cover a feature you’re trying to find, please leave a comment at the end of the article so we can update it.</span></span>
## <a name="quick-reference-guide"></a><span data-ttu-id="a9ffe-108">クイック リファレンス ガイド</span><span class="sxs-lookup"><span data-stu-id="a9ffe-108">Quick reference guide</span></span>
|<span data-ttu-id="a9ffe-109">機能</span><span class="sxs-lookup"><span data-stu-id="a9ffe-109">Feature</span></span> |<span data-ttu-id="a9ffe-110">従来のポータルでのパス</span><span class="sxs-lookup"><span data-stu-id="a9ffe-110">Path in classic portal</span></span>|<span data-ttu-id="a9ffe-111">Azure Portal の Intune でのパス</span><span class="sxs-lookup"><span data-stu-id="a9ffe-111">Path in Intune in the Azure portal</span></span>|
|------------|---------------|---------------|
|<span data-ttu-id="a9ffe-112">Device Enrollment Program (DEP) [iOS のみ]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-112">Device Enrollment Program (DEP) [iOS only]</span></span>|<span data-ttu-id="a9ffe-113">[管理] > [モバイル デバイス管理] > [iOS] > [Device Enrollment Program]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-113">Admin > Mobile Device Management > iOS > Device Enrollment Program</span></span>|<span data-ttu-id="a9ffe-114">[[デバイスの登録] > [Apple の登録] > [Enrollment Program トークン]](#where-did-apple-dep-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-114">[Device enrollment > Apple Enrollment > Enrollment Program Token](#where-did-apple-dep-go)</span></span> |
|<span data-ttu-id="a9ffe-115">Device Enrollment Program (DEP) [iOS のみ]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-115">Device Enrollment Program (DEP) [iOS only]</span></span>| <span data-ttu-id="a9ffe-116">[管理] > [モバイル デバイス管理] > [iOS および Mac OS X] > [Device Enrollment Program]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-116">Admin > Mobile Device Management > iOS and Mac OS X > Device Enrollment Program</span></span> |<span data-ttu-id="a9ffe-117">[[デバイスの登録] > [Apple の登録] > [Enrollment Program Serial Numbers]\(Enrollment Program シリアル番号\)](#where-did-apple-dep-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-117">[Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers](#where-did-apple-dep-go)</span></span> |
|<span data-ttu-id="a9ffe-118">登録ルール</span><span class="sxs-lookup"><span data-stu-id="a9ffe-118">Enrollment Rules</span></span> |<span data-ttu-id="a9ffe-119">[管理] > [モバイル デバイス管理] > [登録ルール]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-119">Admin > Mobile Device Management > Enrollment Rules</span></span>|<span data-ttu-id="a9ffe-120">[[デバイスの登録] > [登録制限]](#where-did-enrollment-rules-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-120">[Device enrollment > Enrollment Restrictions](#where-did-enrollment-rules-go)</span></span> |
|<span data-ttu-id="a9ffe-121">iOS シリアル番号別のグループ</span><span class="sxs-lookup"><span data-stu-id="a9ffe-121">Groups by iOS Serial Number</span></span> |<span data-ttu-id="a9ffe-122">[グループ] > [すべてのデバイス] > [会社の事前登録済みデバイス] > [iOS シリアル番号を使用]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-122">Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number</span></span>|<span data-ttu-id="a9ffe-123">[[デバイスの登録] > [Apple の登録] > [Enrollment Program Serial Numbers]\(Enrollment Program シリアル番号\)](#where-did-corporate-pre-enrolled-devices-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-123">[Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers](#where-did-corporate-pre-enrolled-devices-go)</span></span> |
|<span data-ttu-id="a9ffe-124">iOS シリアル番号別のグループ</span><span class="sxs-lookup"><span data-stu-id="a9ffe-124">Groups by iOS Serial Number</span></span> |<span data-ttu-id="a9ffe-125">[グループ] > [すべてのデバイス] > [会社の事前登録済みデバイス] > [iOS シリアル番号を使用]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-125">Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number</span></span>| <span data-ttu-id="a9ffe-126">[[デバイスの登録] > [Apple の登録] > [AC Serial numbers]\(AC シリアル番号\)](#where-did-corporate-pre-enrolled-devices-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-126">[Device enrollment > Apple Enrollment > AC Serial numbers](#where-did-corporate-pre-enrolled-devices-go)</span></span>|
|<span data-ttu-id="a9ffe-127">IMEI 別のグループ (すべてのプラットフォーム)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-127">Groups by IMEI (all platforms)</span></span>| <span data-ttu-id="a9ffe-128">[グループ] > [すべてのデバイス] > [会社の事前登録済みデバイス] > [By IMEI]\(IMEI を使用\) (すべてのプラットフォーム)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-128">Groups > All Devices > Corporate Pre-enrolled devices > By IMEI (All platforms)</span></span> | <span data-ttu-id="a9ffe-129">[[デバイスの登録] > [業務用デバイスの ID]](#by-imei-all-platforms)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-129">[Device enrollment > Corporate Device Identifiers](#by-imei-all-platforms)</span></span>|
| <span data-ttu-id="a9ffe-130">業務用デバイスの登録プロファイル</span><span class="sxs-lookup"><span data-stu-id="a9ffe-130">Corporate Device Enrollment profile</span></span>| <span data-ttu-id="a9ffe-131">[ポリシー] > [業務用デバイスの登録]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-131">Policy > Corporate Device Enrollment</span></span> | <span data-ttu-id="a9ffe-132">[[デバイスの登録] > [Apple の登録] > [Enrollment Program プロファイル]](#where-did-corporate-pre-enrolled-devices-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-132">[Device enrollment > Apple Enrollment > Enrollment Program Profiles](#where-did-corporate-pre-enrolled-devices-go)</span></span> |
| <span data-ttu-id="a9ffe-133">業務用デバイスの登録プロファイル</span><span class="sxs-lookup"><span data-stu-id="a9ffe-133">Corporate Device Enrollment profile</span></span> | <span data-ttu-id="a9ffe-134">[ポリシー] > [業務用デバイスの登録]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-134">Policy > Corporate Device Enrollment</span></span> | <span data-ttu-id="a9ffe-135">[[デバイスの登録] > [Apple の登録] > [AC プロファイル]](#where-did-corporate-pre-enrolled-devices-go)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-135">[Device enrollment > Apple Enrollment > AC Profiles](#where-did-corporate-pre-enrolled-devices-go)</span></span> |
| <span data-ttu-id="a9ffe-136">Android for Work</span><span class="sxs-lookup"><span data-stu-id="a9ffe-136">Android for Work</span></span> | <span data-ttu-id="a9ffe-137">[管理] > [モバイル デバイス管理] > [Android for Work]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-137">Admin > Mobile Device Management > Android for Work</span></span> | <span data-ttu-id="a9ffe-138">[デバイスの登録] > [Android for Work への登録]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-138">Device enrollment > Android for Work Enrollment</span></span> |
| <span data-ttu-id="a9ffe-139">使用条件</span><span class="sxs-lookup"><span data-stu-id="a9ffe-139">Terms and Conditions</span></span> | <span data-ttu-id="a9ffe-140">[ポリシー] > [使用条件]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-140">Policy > Terms and Conditions</span></span> | <span data-ttu-id="a9ffe-141">[デバイスの登録] > [使用条件]</span><span class="sxs-lookup"><span data-stu-id="a9ffe-141">Device enrollment > Terms and Conditions</span></span> |


## <a name="where-do-i-manage-groups"></a><span data-ttu-id="a9ffe-142">グループを管理する場所</span><span class="sxs-lookup"><span data-stu-id="a9ffe-142">Where do I manage groups?</span></span>
<span data-ttu-id="a9ffe-143">Azure Portal の Intune では、[Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) を使用してグループを管理します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-143">Intune in the Azure portal uses [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) to manage groups.</span></span>

## <a name="where-did-enrollment-rules-go"></a><span data-ttu-id="a9ffe-144">登録ルールの移動先</span><span class="sxs-lookup"><span data-stu-id="a9ffe-144">Where did enrollment rules go?</span></span>
<span data-ttu-id="a9ffe-145">従来のポータルでは、モバイルおよび最新の Windows/macOS デバイスの MDM の登録に適用されるルールを次のようにして設定できました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-145">In the classic portal, you could set rules governing the MDM enrollment of mobile and modern Windows and macOS devices:</span></span>

![従来のモバイル デバイスの登録ルールの画像](./media/01-classic-rules.png)

<span data-ttu-id="a9ffe-147">これらのルールは例外なくすべてのユーザーの Intune アカウントに適用されました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-147">These rules applied to all users in your Intune account without exception.</span></span> <span data-ttu-id="a9ffe-148">Azure Portal では、これらのルールは [デバイスの種類の制限] と [デバイス数の制限] という 2 つのポリシーの種類に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-148">In the Azure portal these rules now appear in two distinct polices types: Device Type Restrictions and Device Limit Restrictions:</span></span>

![Azure のモバイル デバイス登録制限の画像](./media/02-azure-enroll-restrictions.png)

<span data-ttu-id="a9ffe-150">既定の [デバイスの上限数の制限] は、従来のポータルの [デバイス登録制限] に対応します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-150">The default Device Limit Restriction corresponds to the Device Enrollment Limit in the classic portal:</span></span>

![Azure のデバイス数の制限の画像](./media/03-azure-device-limit.png)

<span data-ttu-id="a9ffe-152">既定の [デバイスの種類の制限] は、従来のポータルの [プラットフォームの制限] に対応します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-152">The default Device Type Restriction corresponds to the Platform Restrictions in the classic portal:</span></span>

![Azure のデバイスの種類の制限の画像](./media/04-azure-platform-restrictions.png)

<span data-ttu-id="a9ffe-154">個人所有のデバイスを許可またはブロックする機能を、[デバイスの種類の制限] の [プラットフォーム構成] で管理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-154">The ability to allow or block personally owned devices is now managed under the Device Type Restriction’s Platform Configurations:</span></span>

![Azure の個人用デバイスのブロック設定の画像](./media/05-azure-personal-block.png)

<span data-ttu-id="a9ffe-156">新しい制限の機能は、Azure Portal のみに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-156">New restriction capabilities will be added to the Azure Portal only.</span></span>

## <a name="where-did-apple-dep-go"></a><span data-ttu-id="a9ffe-157">Apple DEP の移動先</span><span class="sxs-lookup"><span data-stu-id="a9ffe-157">Where did Apple DEP go?</span></span>
<span data-ttu-id="a9ffe-158">従来のポータルでは、Intune が Apple のデバイス登録プログラムと統合されるように設定し、Apple サービスとの同期を手動で要求できました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-158">In the classic portal, you could set up Intune to integrate with Apple’s Device Enrollment Program and manually request synchronization with Apple’s service:</span></span>

![従来の DEP トークンの画像](./media/06-classic-dep-token.png)

<span data-ttu-id="a9ffe-160">Azure Portal でも、Intune クラシックと同じ手順で Apple のデバイス登録プログラムを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-160">In the Azure portal, you set up Apple Device Enrollment Program with the same steps as in Intune classic:</span></span>

![Azure の DEP トークンの画像](./media/07-azure-dep-token.png)

<span data-ttu-id="a9ffe-162">ただし、従来のポータルの **[同期]** オプションが、シリアル番号管理のワークフローに移動しています。手動による同期の結果がここに表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-162">However the **Sync** option in the classic portal has been moved to the serial number management workflow since the results of a manual sync will appear there:</span></span>

![Azure の DEP 同期の画像](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a><span data-ttu-id="a9ffe-164">会社の事前登録済みデバイスの移動先</span><span class="sxs-lookup"><span data-stu-id="a9ffe-164">Where did corporate pre-enrolled devices go?</span></span>
### <a name="by-ios-serial-number"></a><span data-ttu-id="a9ffe-165">iOS シリアル番号を使用</span><span class="sxs-lookup"><span data-stu-id="a9ffe-165">By iOS serial number</span></span>
<span data-ttu-id="a9ffe-166">従来のポータルでは、Apple デバイス登録プログラム (DEP) と Apple Configurator ツールを使用して iOS デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-166">In the classic portal, you can enroll iOS devices through the Apple Device Enrollment Program (DEP) and the Apple Configurator tool.</span></span> <span data-ttu-id="a9ffe-167">どちらの方法でも、シリアル番号を使用したデバイスの事前登録が可能で、この登録によって特別な業務用デバイスの登録プロファイルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-167">Both methods offer device pre-enrollment by serial number and involve the assignment of special Corporate Device Enrollment profiles.</span></span> <span data-ttu-id="a9ffe-168">登録の前に、**[会社の事前登録済みデバイス] の [iOS シリアル番号を使用]** のデバイス グループから登録プロファイルの割り当てを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-168">Prior to enrollment, the enrollment profile assignment can be managed through the **Corporate Pre-enrolled Device by iOS Serial Number** device group:</span></span>

![従来の Apple シリアル番号の画像](./media/09-classic-apple-serials.png)

<span data-ttu-id="a9ffe-170">これには、Apple DEP と Configurator で登録されたシリアル番号が 1 つの一覧に表示されています。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-170">This lists serial numbers for both Apple DEP and Configurator enrollment in a single list.</span></span> <span data-ttu-id="a9ffe-171">プロファイルの割り当て (DEP プロファイルから AC シリアル番号、およびその逆) の不一致を減らすため、Azure Portal ではシリアル番号を 2 つの一覧に分割しました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-171">To reduce profile assignment mis-match (DEP profile to AC serial number and vice-versa), we have separated the serial numbers into two lists in the Azure portal:</span></span>

<span data-ttu-id="a9ffe-172">**DEP のシリアル番号**
![Azure DEP のシリアル番号の画像](./media/10-azure-dep-serials.png)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-172">**DEP serial numbers**
![Image of Azure DEP serial numbers](./media/10-azure-dep-serials.png)</span></span>

<span data-ttu-id="a9ffe-173">**Apple Configurator のシリアル番号**
![Azure Apple Configurator のシリアル番号の画像](./media/11-azure-ac-serials.png)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-173">**Apple Configurator serial numbers**
![Image of Azure Apple Configurator serial numbers](./media/11-azure-ac-serials.png)</span></span>

### <a name="by-imei-all-platforms"></a><span data-ttu-id="a9ffe-174">IMEI (すべてのプラットフォーム) を使用</span><span class="sxs-lookup"><span data-stu-id="a9ffe-174">By IMEI (all platforms)</span></span>

<span data-ttu-id="a9ffe-175">従来のポータルでは、デバイスの IMEI 番号を事前に一覧表示することで、デバイスを Intune に登録する際に業務用としてマークすることができました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-175">In the classic portal, you can pre-list the IMEI numbers of devices to mark them as corporate when they enrolled to Intune:</span></span>

![IMEI 番号の従来の一覧の画像](./media/12-classic-corp-imei.png)

<span data-ttu-id="a9ffe-177">Azure Portal では、コンマ区切り値 (CSV) ファイルを使用して同じ IMEI を [業務用デバイスの ID] 一覧にアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-177">In the Azure portal, you must upload the same IMEI to the Corporate Device Identifiers list with a comma-separated-values (CSV) file.</span></span> <span data-ttu-id="a9ffe-178">新しいポータルでは、IMEI 番号の手動での入力はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-178">The new portal will not support manual entry of IMEI numbers:</span></span>

![IMEI 番号の Azure の一覧の画像](./media/13-azure-corp-imei.png)

<span data-ttu-id="a9ffe-180">Azure Portal の Intune では IMEI 以外の種類の ID も今後サポートされることになっていますが、現在は事前表示用の IMEI 番号のみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-180">Intune in the Azure portal is future-proofed to support other types of identifiers beside IMEI, but currently only allows IMEI numbers for pre-listing.</span></span>

## <a name="where-did-corporate-device-enrollment-profiles-go"></a><span data-ttu-id="a9ffe-181">業務用デバイスの登録プロファイルの移動先</span><span class="sxs-lookup"><span data-stu-id="a9ffe-181">Where did Corporate Device Enrollment profiles go?</span></span>
<span data-ttu-id="a9ffe-182">Apple のデバイス登録プログラムまたは Apple Configurator ツールを使用して iOS デバイスを登録するには、デバイスに割り当てられる業務用デバイスの登録プロファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-182">To enroll iOS devices through the Apple Device Enrollment Program or with the Apple Configurator tool, you must supply a Corporate Device Enrollment profile to be assigned the device.</span></span> <span data-ttu-id="a9ffe-183">従来のポータルでは、これらのプロファイルの作成と管理は同じ一覧にありました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-183">In the classic portal, the creation and management of these profiles was located in a single list:</span></span>

![従来のデバイスの登録プロファイルの画像](./media/14-classic-corp-profiles.png)

<span data-ttu-id="a9ffe-185">この一覧には Apple のデバイス登録プログラムでの使用が有効なプロファイル (**DEP が [On (オン)]**) と、Apple Configurator ツールでの使用のみが有効なプロファイル (**DEP が [Off (オフ)]**) が表示されています。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-185">This list shows profiles enabled for use with the Apple Device Enrollment Program (**DEP On**) and profile only enabled for use with the Apple Configurator tool (**DEP Off**).</span></span>

<span data-ttu-id="a9ffe-186">2 つのプロファイルを混同し、割り当て (DEP プロファイルから Configurator デバイス、およびその逆) が一致しない可能性を少なくするため、(Apple のデバイス登録プログラムと Apple スクール マネージャーの両方をサポートする) 登録プログラムのプロファイルと、Apple Configurator プロファイルの作成と管理を分けました。</span><span class="sxs-lookup"><span data-stu-id="a9ffe-186">To reduce confusion between the two profile types and potential mis-matched assignments (DEP profile to Configurator devices and vice-versa), we have separated creation and management of Enrollment Program profiles (support both Apples Device Enrollment Program and Apple School Manager) and Apple Configurator profiles:</span></span>

<span data-ttu-id="a9ffe-187">**DEP プロファイル**
![Azure の DEP プロファイルの画像](./media/15-azure-dep-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-187">**DEP profiles**
![Image of Azure DEP profiles](./media/15-azure-dep-profiles.png)</span></span>

<span data-ttu-id="a9ffe-188">**Apple Configurator のプロファイル**
![Azure の Apple Configurator プロファイルの画像](./media/16-azure-ac-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="a9ffe-188">**Apple Configurator profiles**
![Image of Azure Apple Configurator profiles](./media/16-azure-ac-profiles.png)</span></span>
