---
title: "Azure Portal での Microsoft Intune の既知の問題"
titlesuffix: Azure portal
description: "Intune の既知の問題についての説明"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9ad436878bcc6ed3d9e6fc4c6e7bd92ae4bf336a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="known-issues-in-microsoft-intune"></a><span data-ttu-id="c56a2-103">Microsoft Intune の既知の問題</span><span class="sxs-lookup"><span data-stu-id="c56a2-103">Known issues in Microsoft Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c56a2-104">このトピックでは、Microsoft Intune の既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-104">Use this topic to learn about any known issues in Microsoft Intune.</span></span>

<span data-ttu-id="c56a2-105">ここに記載されていないバグを報告する場合は、[サポートを依頼](get-support.md)してください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-105">If you want to report a bug that is not listed here, [open a support request](get-support.md).</span></span>

<span data-ttu-id="c56a2-106">Intune への新機能の追加を依頼する場合は、[Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) サイトでレポートを提出することをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-106">If you want to request a new feature for Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.</span></span>

## <a name="migration"></a><span data-ttu-id="c56a2-107">移行</span><span class="sxs-lookup"><span data-stu-id="c56a2-107">Migration</span></span>

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a><span data-ttu-id="c56a2-108">Intune の従来の PC クライアント機能が使用できるのは Silverlight コンソールのみです。</span><span class="sxs-lookup"><span data-stu-id="c56a2-108">Intune legacy PC client features are only available in the Silverlight console</span></span>

<span data-ttu-id="c56a2-109">Azure Portal 上の Intune で Windows 10 を管理する機能は、Windows MDM を通して提供されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-109">The ability to manage Windows 10 in the Intune on Azure portal is available via Windows MDM enrollment.</span></span> <span data-ttu-id="c56a2-110">詳細については、「[Azure コンソールと従来の Intune PC クライアントでの Intune](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-110">For more information, see [Intune on Azure console and legacy Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).</span></span>

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a><span data-ttu-id="c56a2-111">移行中に Intune で作成されるグループは、他の Microsoft 製品の機能に影響する可能性がある</span><span class="sxs-lookup"><span data-stu-id="c56a2-111">Groups created by Intune during migration might affect functionality of other Microsoft products</span></span>

<span data-ttu-id="c56a2-112">Intune から Azure Portal に移行すると、**All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** という新しいグループが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-112">When you migrate from Intune to the Azure portal, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**.</span></span> <span data-ttu-id="c56a2-113">このグループには、Intune のライセンスを持つユーザーだけでなく、ご利用の Azure Active Directory のすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-113">This group contains all users in your Azure Active Directory, not only Intune licensed users.</span></span> <span data-ttu-id="c56a2-114">このグループを使用すると、一部の既存のユーザーまたは新規ユーザーがどのグループにも属さない場合に、他の Microsoft 製品に関する問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-114">This usage can cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.</span></span>

### <a name="secondary-migration-required-for-select-capabilities"></a><span data-ttu-id="c56a2-115">特定の機能に必要な二次移行</span><span class="sxs-lookup"><span data-stu-id="c56a2-115">Secondary migration required for select capabilities</span></span>

<span data-ttu-id="c56a2-116">2017 年 1 月よりも前に作成された Intune アカウントでは、Azure Portal で次の機能を使用する前に、移行が必要です。</span><span class="sxs-lookup"><span data-stu-id="c56a2-116">Intune accounts created before January 2017 must be migrated before the following capabilities can be used in the Azure portal:</span></span>

- <span data-ttu-id="c56a2-117">業務用デバイスの登録プロファイル</span><span class="sxs-lookup"><span data-stu-id="c56a2-117">Corporate Device Enrollment profiles</span></span>
- <span data-ttu-id="c56a2-118">Apple Device Enrollment Program</span><span class="sxs-lookup"><span data-stu-id="c56a2-118">Apple Device Enrollment Program</span></span>
- <span data-ttu-id="c56a2-119">iOS シリアル番号で企業デバイスを事前宣言する</span><span class="sxs-lookup"><span data-stu-id="c56a2-119">Predeclare corporate devices by iOS serial number</span></span>
- <span data-ttu-id="c56a2-120">デバイス登録マネージャー アカウント</span><span class="sxs-lookup"><span data-stu-id="c56a2-120">Device Enrollment Manager accounts</span></span>
- <span data-ttu-id="c56a2-121">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="c56a2-121">Apple Volume Purchase Program</span></span>

<span data-ttu-id="c56a2-122">これらの機能は、Intune (Silverlight) コンソールや Azure Portal では管理できないため、移行すると以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-122">Because these capabilities cannot be managed from both the Intune (Silverlight) console and Azure portal, the migration:</span></span>
- <span data-ttu-id="c56a2-123">従来のポータルでは無効になります</span><span class="sxs-lookup"><span data-stu-id="c56a2-123">Disables them in the classic portal</span></span>
- <span data-ttu-id="c56a2-124">Azure Portal では有効になります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-124">Enables them in the Azure portal</span></span>  

<span data-ttu-id="c56a2-125">2017 年 9 月 22 日後、これらの機能の移行は、Azure へのプライマリ移行に結合されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-125">After September 22, 2017, the migration of these features will be merged into the primary migration to Azure.</span></span> <span data-ttu-id="c56a2-126">自分のアカウントが Azure Portal を使用するために既に移行されている場合、このセカンダリ移行は現在までに完了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-126">If your account was already migrated to use the Azure portal, this secondary migration may have been completed by now.</span></span> <span data-ttu-id="c56a2-127">完了していない場合、これらの機能は 11 月までに移行されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-127">If not, these capabilities will be migrated to Azure by November.</span></span> <span data-ttu-id="c56a2-128">アカウントの移行が開始すると、同じ日に完了します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-128">Once your account’s migration begins, it will complete the same day.</span></span> <span data-ttu-id="c56a2-129">移行には、Intune クラシック ポータルでこれらの機能が無効になった時刻から最大 6 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-129">Migration can take up to 6 hours from the time these features are disabled in the Intune classic portal.</span></span>

<span data-ttu-id="c56a2-130">現在 Azure Portal でこれらの Intune 機能を管理している場合は、以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-130">If you now manage these Intune capabilities in the Azure portal, be aware of the following points:</span></span>

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a><span data-ttu-id="c56a2-131">Apple DEP における、既定の業務用デバイスの登録プロファイルの削除</span><span class="sxs-lookup"><span data-stu-id="c56a2-131">Removes default Corporate Device Enrollment profiles in Apple DEP</span></span>
<span data-ttu-id="c56a2-132">Azure Portal では、Apple Device Enrollment Program (DEP) デバイスについての、既定の業務用デバイスの登録プロファイルがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-132">The Azure portal does not support a default Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) devices.</span></span> <span data-ttu-id="c56a2-133">この機能は、Intune (Silverlight) コンソールで使うことはできますが、プロファイルが意図せずに割り当てられることを防ぐため、廃止されています。</span><span class="sxs-lookup"><span data-stu-id="c56a2-133">This functionality, available in the Intune (Silverlight) console, is discontinued to prevent unintentional profile assignment.</span></span> <span data-ttu-id="c56a2-134">DEP シリアル番号が Azure Portal で同期されている場合、業務用デバイスの登録プロファイルは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-134">When DEP serial numbers sync in the Azure portal, no Corporate Device Enrollment profile is assigned.</span></span> <span data-ttu-id="c56a2-135">登録プロファイルは、デバイスを使用する前に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-135">An enrollment profile must be assigned before using the device.</span></span>

#### <a name="apple-dep-token-restored-with-migration"></a><span data-ttu-id="c56a2-136">移行により復元された Apple DEP トークン</span><span class="sxs-lookup"><span data-stu-id="c56a2-136">Apple DEP token restored with migration</span></span>

<span data-ttu-id="c56a2-137">Intune (Silverlight) ポータルで Apple Device Enrollment Program トークンを削除し、新しいトークンを Azure Portal にアップロードしない場合、移行すると元のトークンが Azure Portal 上に復元されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-137">If you deleted an Apple Device Enrollment Program token in the Intune (Silverlight) portal and do not upload a new token to the Azure portal, the original token is restored in the Azure portal when you migrate.</span></span> <span data-ttu-id="c56a2-138">このトークンを削除して DEP 登録をブロックするには、Azure Portal からトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-138">To remove this token and prevent DEP enrollment, delete the token from the Azure portal.</span></span>

### <a name="status-blades-for-migrated-policies-do-not-work"></a><span data-ttu-id="c56a2-139">移行したポリシーの状態を示すブレードが機能しない</span><span class="sxs-lookup"><span data-stu-id="c56a2-139">Status blades for migrated policies do not work</span></span>

<span data-ttu-id="c56a2-140">クラシック ポータルから移行したポリシーの状態に関する情報は、Azure Portal では表示できません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-140">You cannot view status information for policies that were migrated from the classic portal in the Azure portal.</span></span> <span data-ttu-id="c56a2-141">ただし、クラシック ポータルではこれらのポリシーに関するレポートを引き続き表示できます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-141">However, you can continue to view reports for these policies in the classic portal.</span></span> <span data-ttu-id="c56a2-142">移行した構成ポリシーの状態に関する情報を表示するには、Azure Portal でポリシーを再作成します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-142">To view status information for migrated configuration policies, recreate them in the Azure portal.</span></span>

## <a name="apps"></a><span data-ttu-id="c56a2-143">アプリ</span><span class="sxs-lookup"><span data-stu-id="c56a2-143">Apps</span></span>

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a><span data-ttu-id="c56a2-144">iOS ボリューム購入アプリが Intune テナントの既定の言語でしか利用できない</span><span class="sxs-lookup"><span data-stu-id="c56a2-144">iOS volume-purchased apps only available in default Intune tenant language</span></span>
<span data-ttu-id="c56a2-145">iOS ボリューム購入アプリが表示されても、Intune アカウントと同じ国コードに対してしか割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-145">iOS volume-purchased apps are displayed, and can be assigned only for the same country code as your Intune account.</span></span> <span data-ttu-id="c56a2-146">Intune は、Intune テナント アカウントの国コードと同じ iTunes ロケールのアプリのみを同期します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-146">Intune only sync apps from the same iTunes locale as the Intune tenant account country code.</span></span> <span data-ttu-id="c56a2-147">たとえば、米国のストアでのみ利用可能なアプリを購入したが、自分の Intune アカウントがドイツ語である場合、Intune ではそのアプリが表示されません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-147">For example, if you purchase an app which is only available in the U.S. store, but your Intune account is German, Intune will not show that app.</span></span>

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a><span data-ttu-id="c56a2-148">同じ iOS ボリューム購入プログラムの複数のコピーがアップロードされる</span><span class="sxs-lookup"><span data-stu-id="c56a2-148">Multiple copies of the same iOS volume-purchase program are uploaded</span></span>
<span data-ttu-id="c56a2-149">同じ VPP トークンで **[アップロード]** ボタンを複数回クリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-149">Do not click the **Upload** button multiple times for the same VPP token.</span></span> <span data-ttu-id="c56a2-150">これにより、重複した VPP トークンがアップロードされ、同じ VPP トークンに対してアプリが複数回同期されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-150">This will result in duplicate VPP tokens being uploaded, and apps syncing multiple times for the same VPP token.</span></span>

<!-- ## Groups -->

## <a name="device-configuration"></a><span data-ttu-id="c56a2-151">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="c56a2-151">Device configuration</span></span>

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a><span data-ttu-id="c56a2-152">一部のデバイスで Windows 情報保護ポリシーを保存できない</span><span class="sxs-lookup"><span data-stu-id="c56a2-152">You cannot save a Windows Information Protection policy for some devices</span></span>

<span data-ttu-id="c56a2-153">Intune に登録されていないデバイスでは、Windows 情報保護ポリシー設定の **[Corporate Identify]\(業務用の特定\)** フィールドにプライマリ ドメインのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-153">For devices not enrolled with Intune, you can only specify a primary domain in the **Corporate Identify** field in the settings for a Windows Information Protection policy.</span></span>
<span data-ttu-id="c56a2-154">(**[詳細設定]** > **[ネットワーク境界]** > **[Add a protected domain]\(保護されているドメインの追加\)** で追加ドメインを追加する場合に、ポリシーを保存できません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-154">If you add additional domains (using **Advanced settings** > **Network perimeter** > **Add a protected domain**), you cannot save the policy.</span></span> <span data-ttu-id="c56a2-155">表示されるエラー メッセージは間もなく変更され、より正確な内容となる予定です。</span><span class="sxs-lookup"><span data-stu-id="c56a2-155">The error message you see will soon be changed to be more accurate.</span></span>

### <a name="cisco-anyconnect-vpn-client-support"></a><span data-ttu-id="c56a2-156">Cisco AnyConnect VPN クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="c56a2-156">Cisco AnyConnect VPN client support</span></span>

<span data-ttu-id="c56a2-157">Cisco AnyConnect VPN クライアント (4.0.07072) の最新のリリースは、現在 Intune との互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-157">The latest release of the Cisco AnyConnect VPN client (4.0.07072) is not currently compatible with Intune.</span></span>
<span data-ttu-id="c56a2-158">Intune の今後の更新には、この VPN クライアントのバージョンとの互換性が含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="c56a2-158">A future Intune update will include compatibility with this VPN client version.</span></span> <span data-ttu-id="c56a2-159">それまでは、Cisco AnyConnect VPN クライアントを更新せず、既存のバージョンを使い続けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c56a2-159">Until then, we recommend that you do not update your Cisco AnyConnect VPN client, and continue to use the existing version.</span></span>

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a><span data-ttu-id="c56a2-160">macOS Sierra デバイスで数字のパスワードを使用する</span><span class="sxs-lookup"><span data-stu-id="c56a2-160">Using the numeric password type with macOS Sierra devices</span></span>

<span data-ttu-id="c56a2-161">現在、macOS Sierra デバイスのデバイス制限プロファイルで **[必要なパスワードの種類]** に **[数字]** を選択すると、**[英数字]** が強制的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-161">Currently, if you select the **Numeric** **Required password type** in a device restriction profile for macOS Sierra devices, it is enforced as **Alphanumeric**.</span></span> <span data-ttu-id="c56a2-162">これらのデバイスで数字のパスワードを使用する場合は、この設定を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-162">If you want to use a numeric password with these devices, do not configure this setting.</span></span>
<span data-ttu-id="c56a2-163">この問題は、macOS の今後のバージョンで修正される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-163">This issue might be corrected in a future version of macOS.</span></span>

<span data-ttu-id="c56a2-164">これらの設定の詳細については、「[Microsoft Intune での macOS デバイスの制限設定](device-restrictions-macos.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-164">For more information about these settings, see [macOS device restriction settings in Microsoft Intune](device-restrictions-macos.md).</span></span>

## <a name="compliance"></a><span data-ttu-id="c56a2-165">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c56a2-165">Compliance</span></span>

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a><span data-ttu-id="c56a2-166">Intune のコンプライアンス ポリシーが新しいコンソールに表示されない</span><span class="sxs-lookup"><span data-stu-id="c56a2-166">Compliance policies from Intune do not show up in new console</span></span>

<span data-ttu-id="c56a2-167">クラシック Intune ポータルで作成したコンプライアンス ポリシーは移行できますが、Azure Portal では設計が変更されているため、Azure Portal には表示されません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-167">Compliance policies you created in the classic portal are migrated, but are not displayed in the Azure portal because of design changes in the Azure portal.</span></span> <span data-ttu-id="c56a2-168">Intune クラシック ポータルで作成したコンプライアンス ポリシーは依然として有効ですが、ポリシーの表示や編集はクラシック ポータル上で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-168">Compliance policies you created in the Intune classic portal are still enforced, but you must view and edit them in the classic portal.</span></span>

<span data-ttu-id="c56a2-169">また、Azure Portal で作成した新しいコンプライアンス ポリシーは、クラシック ポータル上には表示されません。</span><span class="sxs-lookup"><span data-stu-id="c56a2-169">Additionally, new compliance policies you create in the Azure portal are not visible in the classic portal.</span></span>

<span data-ttu-id="c56a2-170">詳細については、「[Intune Azure プレビューでのデバイス コンプライアンスとは](device-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c56a2-170">For more information, see [What is device compliance](device-compliance.md).</span></span>

<!-- ## Enrollment -->


## <a name="data-protection"></a><span data-ttu-id="c56a2-171">データの保護</span><span class="sxs-lookup"><span data-stu-id="c56a2-171">Data protection</span></span>

### <a name="ios-app-protection-policies"></a><span data-ttu-id="c56a2-172">iOS アプリの保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="c56a2-172">iOS app protection policies</span></span>

<span data-ttu-id="c56a2-173">登録しなくてもモバイル アプリ管理 (MAM) によって管理されているデバイス上で、ユーザーが利用できる [iOS 用のアプリ保護ポリシー](app-protection-policy-settings-ios.md)を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-173">You can define [app protection policies for iOS](app-protection-policy-settings-ios.md) that are available for users on devices managed through mobile app management (MAM) without enrollment.</span></span> <span data-ttu-id="c56a2-174">一時的なエラーのため、これらのポリシーは、複数の小数点ではなく、1 つの小数点のバージョンでの iOS バージョンに対してのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-174">Due to a temporary error, you can only define these policies for iOS versions with a single decimal point version rather than multiple decimal points.</span></span> <span data-ttu-id="c56a2-175">最小バージョンの iOS 10.3.1 を設定するのではなく、iOS 10.3 に対して設定します。</span><span class="sxs-lookup"><span data-stu-id="c56a2-175">Instead of setting a minimum version of iOS 10.3.1, you set it for iOS 10.3.</span></span> <span data-ttu-id="c56a2-176">これは、iOS SDK への近日公開予定の更新プログラミングによって解決されます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-176">This will be resolved with a forthcoming update to the iOS SDK.</span></span>


## <a name="administration-and-accounts"></a><span data-ttu-id="c56a2-177">管理とアカウント</span><span class="sxs-lookup"><span data-stu-id="c56a2-177">Administration and accounts</span></span>

<span data-ttu-id="c56a2-178">グローバル管理者 (テナント管理者とも呼ばれる) は別個の Intune または Enterprise Mobility Suite (EMS) のライセンスがなくても日常的な管理タスクを引き続き行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c56a2-178">Global Admins (also referred to as Tenant Admins) can continue day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license.</span></span> <span data-ttu-id="c56a2-179">ただし、自分自身のデバイスの登録、業務用デバイスの登録、Intune ポータル サイトの使用などのサービスを使用するためには、Intune または EMS のライセンスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c56a2-179">However, to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they need an Intune or EMS license.</span></span>

<!-- ## Additional items -->
