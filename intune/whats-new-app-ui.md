---
title: "Intune とエンド ユーザー アプリの UI の更新"
description: "Intune を使用したエンド ユーザー デバイスで動作するアプリの UI の変更点について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 49773483ab8610ee8b348c10aa25bbd6d81151d9
ms.sourcegitcommit: 6a9b80772abe6f6b06f1523461cdb5aea949fc02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="ui-updates-for-intune-end-user-apps"></a><span data-ttu-id="c87d5-103">Intune とエンド ユーザー アプリの UI の更新</span><span class="sxs-lookup"><span data-stu-id="c87d5-103">UI updates for Intune end user apps</span></span>
<span data-ttu-id="c87d5-104">このリリースの Microsoft Intune でエンド ユーザーに表示されるアプリの UI に加えられた変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-104">Learn what updates we've made to the UI for apps that your end users will see in this release of Microsoft Intune.</span></span> <span data-ttu-id="c87d5-105">これは、ユーザーとの通信や、展開のサポートのために作成したカスタム ドキュメントの更新に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-105">This can help you with user communications and any updating custom documentation that you've created to support your deployment.</span></span> <span data-ttu-id="c87d5-106">会社のポータルを使用してヘルプデスクにサポートを求める場合に、直面している問題のトラブルシューティングをより適切に行う方法を理解するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-106">It can also help you understand how to better troubleshoot any issues they're facing should they call helpdesk for support using the Company Portal.</span></span>

## <a name="week-of-december-11-2017"></a><span data-ttu-id="c87d5-107">2017 年 12 月 11 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-107">Week of December 11, 2017</span></span>

### <a name="end-user-messaging-for-accounts---1573558-1712-changes-to-be-made-for-other-platforms-for-1801--"></a><span data-ttu-id="c87d5-108">アカウントに関するエンド ユーザーへのメッセージング<!--1573558, 1712; changes to be made for other platforms for 1801--></span><span class="sxs-lookup"><span data-stu-id="c87d5-108">End user messaging for accounts <!--1573558, 1712; changes to be made for other platforms for 1801--></span></span>

<span data-ttu-id="c87d5-109">ポータル サイトの Web サイト ユーザーによる、テナントへの書き込みアクセスを必要とする操作はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-109">Users of the Company Portal website, will be blocked from taking actions that require write access to your tenant.</span></span> <span data-ttu-id="c87d5-110">対象ユーザーには、使用アカウントがメンテナンス中であることを示すエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-110">They will see appropriate error messaging explaining that their account is under maintenance.</span></span> <span data-ttu-id="c87d5-111">Android、iOS、macOS、Windows 向けのポータル サイト アプリにも、同様の変更がまもなく適用されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-111">Similar changes are coming to the Company Portal apps for Android, iOS, macOS, and Windows soon.</span></span>

![アカウントの移動時に発生するエラー メッセージ](./media/account-move-rom-iwp-user-1712.png)

## <a name="week-of-november-27-2017"></a><span data-ttu-id="c87d5-113">2017 年 11 月 27 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-113">Week of November 27, 2017</span></span>

### <a name="new-device-categories-step-in-guided-setup-for-the-company-portal-app-for-windows-10----1335292---"></a><span data-ttu-id="c87d5-114">Windows 10 用ポータル サイト アプリのガイド付きセットアップでの新しい [デバイス カテゴリ] ステップ <!---1335292---></span><span class="sxs-lookup"><span data-stu-id="c87d5-114">New "Device Categories" step in guided setup for the Company Portal app for Windows 10 <!---1335292---></span></span>

<span data-ttu-id="c87d5-115">[デバイス グループ マッピング](device-group-mapping.md)が有効になっている場合、Windows 10 用ポータル サイト アプリのセットアップで、ユーザーはデバイスを登録した後にデバイスのカテゴリを選ぶようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-115">If you've enabled [device group mapping](device-group-mapping.md), the Company Portal app for Windows 10 now walks your users through selecting a device category after enrolling their device.</span></span>

![デバイス グループ マッピングのカテゴリ](./media/w10_cp_category_device_setup_after_1711.png)

## <a name="week-of-november-13-2017"></a><span data-ttu-id="c87d5-117">2017 年 11 月 13 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-117">Week of November 13, 2017</span></span>

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a><span data-ttu-id="c87d5-118">iOS 用ポータル サイト バージョン 2.9.0 でのデバイスのセットアップ ワークフローの機能強化<!---1417174---></span><span class="sxs-lookup"><span data-stu-id="c87d5-118">Improvements to device setup workflow in the Company Portal for iOS in version 2.9.0 <!---1417174---></span></span>

<span data-ttu-id="c87d5-119">iOS 用ポータル サイト アプリでのデバイス セットアップ ワークフローを改善しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-119">We've improved the device setup workflow in the Company Portal app for iOS.</span></span> <span data-ttu-id="c87d5-120">言葉がよりわかりやすくなり、可能な範囲で画面をまとめました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-120">The language is more user-friendly and we've combined screens where possible.</span></span> <span data-ttu-id="c87d5-121">また、セットアップのテキスト全体でお客様の会社名を使用することで、表現がより会社に合ったものになっています。</span><span class="sxs-lookup"><span data-stu-id="c87d5-121">We have also made the language more specific to your company by using your company name throughout the setup text.</span></span>

> [!NOTE]
> <span data-ttu-id="c87d5-122">**[Microsoft Intune]** > **[モバイル アプリ]** > **[ポータル サイトのブランド化]** > **[会社名]** の Azure Portal で設定した会社名が使用されています。</span><span class="sxs-lookup"><span data-stu-id="c87d5-122">We use the company name you have set in the Azure Portal in **Microsoft Intune** > **Mobile Apps** > **Company Portal branding** > **Company name**.</span></span> <span data-ttu-id="c87d5-123">この値を設定していない場合、**[Azure Active Directory]** > **[プロパティ]** > **[名前]** で設定したテナント名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-123">If you have not set this value, we will use the tenant name set in **Azure Active Directory** > **Properties** > **Name**.</span></span> <span data-ttu-id="c87d5-124">[ポータル サイトのブランド化] で会社名を設定しておらず、テナント名を表示させたくない場合は、[ポータル サイトのブランド化] タブで会社名を設定することをお勧めします。この文字列をポータル サイトのヘッダーに表示させたくない場合は、[Show company name next to logo]\(ロゴの横に会社名を表示する\) チェックボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-124">If you have not set a company name in Company Portal branding and don’t want your tenant name to be displayed, we recommend that you set the company name in the Company Portal branding tab. If you don’t want this string to show in the header in Company Portal, you can deselect the checkbox to “Show company name next to logo.”</span></span>

|<span data-ttu-id="c87d5-125">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-125">Before</span></span>|<span data-ttu-id="c87d5-126">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-126">After</span></span>|
|---|---|
|![01](./media/ios_cp_enroll_01_before_1711.png)|![01](./media/ios_cp_enroll_01_after_1711.png)|
|![02](./media/ios_cp_enroll_02_before_1711.png)|<span data-ttu-id="c87d5-130">*前のステップと結合*</span><span class="sxs-lookup"><span data-stu-id="c87d5-130">*Combined with previous step*</span></span>|
|![03](./media/ios_cp_enroll_03_before_1711.png)|![03](./media/ios_cp_enroll_03_after_1711.png)|
|![04](./media/ios_cp_enroll_04_before_1711.png)|![04](./media/ios_cp_enroll_04_after_1711.png)|
|![05](./media/ios_cp_enroll_05_before_1711.png)|![05](./media/ios_cp_enroll_05_after_1711.png)|
|![06](./media/ios_cp_enroll_06_before_1711.png)|![06](./media/ios_cp_enroll_06_after_1711.png)|
|![07](./media/ios_cp_enroll_07_before_1711.png)|![07](./media/ios_cp_enroll_07_after_1711.png)|


## <a name="week-of-november-6-2017"></a><span data-ttu-id="c87d5-141">2017 年 11 月 6 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-141">Week of November 6, 2017</span></span>

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a><span data-ttu-id="c87d5-142">Windows 10 用ポータル サイト アプリの更新内容 <!--1299474--></span><span class="sxs-lookup"><span data-stu-id="c87d5-142">Updates to the Company Portal app for Windows 10 <!--1299474--></span></span>
<span data-ttu-id="c87d5-143">Windows 10 用ポータル サイト アプリの [設定] ページが更新され、すべての設定で、設定と目的のユーザー アクションの一貫性が高まっています。</span><span class="sxs-lookup"><span data-stu-id="c87d5-143">The Settings page in the Company Portal app for Windows 10 has been updated to make the settings and intended user actions to be more consistent across all settings.</span></span> <span data-ttu-id="c87d5-144">また、その他の Windows アプリのレイアウトと一致させる更新も行われています。</span><span class="sxs-lookup"><span data-stu-id="c87d5-144">It has also been updated to match the layout of other Windows apps.</span></span>

|<span data-ttu-id="c87d5-145">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-145">Before</span></span>|<span data-ttu-id="c87d5-146">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-146">After</span></span>|
|---|---|
|![01](./media/w10-share-logs.png)|![02](./media/w10-share-logs-after-1711.png)|


### <a name="search-improvements-to-the-company-portal-apps-and-website---1418189--"></a><span data-ttu-id="c87d5-149">ポータル サイト アプリおよび Web サイトの検索機能強化 <!--1418189--></span><span class="sxs-lookup"><span data-stu-id="c87d5-149">Search improvements to the Company Portal apps and website <!--1418189--></span></span>
<span data-ttu-id="c87d5-150">ポータル サイト アプリでは、アプリのカテゴリ、名前、説明で検索できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-150">The Company Portal apps now use searches across app categories, names, and descriptions.</span></span> <span data-ttu-id="c87d5-151">結果は関連性の高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-151">The results are sorted in decreasing order of relevance.</span></span> <span data-ttu-id="c87d5-152">これらの更新は、[ポータル Web サイト](https://portal.manage.microsoft.com)でも利用可能です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-152">These updates are also available on the [Company Portal website](https://portal.manage.microsoft.com).</span></span>

<span data-ttu-id="c87d5-153">マイクロソフトは関連性の追跡方法を微調整しています。ポータル Web サイトの一番下にある "フィードバック" リンクから調整具合をお知らせください。</span><span class="sxs-lookup"><span data-stu-id="c87d5-153">We're still fine-tuning the way relevance is tracked, so please let us know how it's working using the "Feedback" link at the bottom of the Company Portal website.</span></span>

## <a name="week-of-october-16-2017"></a><span data-ttu-id="c87d5-154">2017 年 10 月 16 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-154">Week of October 16, 2017</span></span>

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a><span data-ttu-id="c87d5-155">ポータル Web サイトの検索機能強化 <!--1331697--></span><span class="sxs-lookup"><span data-stu-id="c87d5-155">Search improvements to the Company Portal website <!--1331697--></span></span>
<span data-ttu-id="c87d5-156">マイクロソフトはアプリの検索機能を強化しています。その最初が[ポータル Web サイト](https://portal.manage.microsoft.com)です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-156">We're improving our app search capabilities, starting with the [Company Portal website](https://portal.manage.microsoft.com).</span></span> <span data-ttu-id="c87d5-157">名前フィールドや説明フィールドだけでなく、アプリ カテゴリでも検索できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-157">Searches will now be performed on app categories in addition to the Name and Description fields.</span></span> <span data-ttu-id="c87d5-158">結果は既定で、関連性の降順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-158">The results will be sorted, by default, in decreasing order of relevance.</span></span> 

<span data-ttu-id="c87d5-159">iOS ユーザーもこの変更の影響を受けます。ポータル Web サイトは、iOS のポータル サイト アプリの一部としても利用されるためです。</span><span class="sxs-lookup"><span data-stu-id="c87d5-159">iOS users will also receive this change, as the Company Portal website is also used as part of the Company Portal app for iOS.</span></span> <span data-ttu-id="c87d5-160">Android と Windows のポータル サイト アプリも数か月後に同じように更新されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-160">The Company Portal apps for Android and Windows will receive similar updates in the coming months.</span></span>

<span data-ttu-id="c87d5-161">マイクロソフトは関連性の追跡方法を微調整しています。ポータル Web サイトの一番下にある "フィードバック" リンクから調整具合をお知らせください。</span><span class="sxs-lookup"><span data-stu-id="c87d5-161">We're still fine-tuning the way relevance is tracked, so please let us know how it's working using the "Feedback" link at the bottom of the Company Portal website.</span></span>


### <a name="ios-company-portal-displays-large-icons----1454593---"></a><span data-ttu-id="c87d5-162">iOS ポータル サイトでの大きいアイコンの表示 <!-- 1454593 --></span><span class="sxs-lookup"><span data-stu-id="c87d5-162">iOS Company Portal displays large icons <!-- 1454593 --></span></span>
<span data-ttu-id="c87d5-163">このリリースでは、iOS ポータル サイトのアプリ タイルでのアイコンの表示方法に関する既知の問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-163">This release fixes a known issue with how the iOS Company Portal displays icons in the app tile.</span></span> <span data-ttu-id="c87d5-164">現在は、120 x 120 ピクセル以上のアプリ アイコンをアップロードすると、[ポータル Web サイト](https://portal.manage.microsoft.com)内と iOS ポータル サイトのアプリ ページ内で、アプリ タイルのフル サイズで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-164">If you upload app icons of 120x120 pixels or larger, they now display in the [Company Portal website](https://portal.manage.microsoft.com) and the iOS Company Portal's apps pages at the full size of the app tile.</span></span>


## <a name="week-of-october-2-2017"></a><span data-ttu-id="c87d5-165">2017 年 10 月 2 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-165">Week of October 2, 2017</span></span>

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a><span data-ttu-id="c87d5-166">ポータル サイトでのデバイスのセットアップ ワークフローの機能強化<!--1490692--></span><span class="sxs-lookup"><span data-stu-id="c87d5-166">Improvements to device setup workflow in Company Portal <!--1490692--></span></span>
<span data-ttu-id="c87d5-167">Android 用のポータル サイト アプリでデバイスのセットアップ ワークフローを改良しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-167">We've improved the device setup workflow in the Company Portal app for Android.</span></span> <span data-ttu-id="c87d5-168">言語がよりわかりやすく、会社固有のものとなり、可能な範囲で画面をまとめるようにしました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-168">The language is more user-friendly and specific to your company, and we've combined screens where possible.</span></span> 

|<span data-ttu-id="c87d5-169">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-169">Before</span></span>|<span data-ttu-id="c87d5-170">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-170">After</span></span>|
|---|---|
|![01](./media/android_cp_enroll_01_post_1709.png)|![01](./media/android_cp_enroll_01_1709_new.png)|
|![01a](./media/android_cp_enroll_01_before_1710.png)| <span data-ttu-id="c87d5-174">*前のステップと結合*</span><span class="sxs-lookup"><span data-stu-id="c87d5-174">*Combined with previous step*</span></span> |
|![02](./media/android_cp_enroll_02_before_1710.png)|![02](./media/android_cp_enroll_02_after_1710.png)|
|![03](./media/android_cp_enroll_03_before_1710.png)|![03](./media/android_cp_enroll_03_after_1710.png)|

<span data-ttu-id="c87d5-179">Android for Work デバイスに対して追加のステップが強化されました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-179">Additional steps have been improved on Android for Work devices.</span></span>

|<span data-ttu-id="c87d5-180">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-180">Before</span></span>|<span data-ttu-id="c87d5-181">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-181">After</span></span>|
|---|---|
|![04](./media/android_work_cp_enroll_01_before_1710.png)|![04](./media/android_work_cp_enroll_01_after_1710.png)|
|![05](./media/android_work_cp_enroll_02_before_1710.png)| <span data-ttu-id="c87d5-185">*前のステップと結合*</span><span class="sxs-lookup"><span data-stu-id="c87d5-185">*Combined with previous step*</span></span> |
|![06](./media/android_work_cp_enroll_03_before_1710.png)|![06](./media/android_work_cp_enroll_03_after_1710.png)|
|![07](./media/android_work_cp_enroll_04_before_1710.png)|![07](./media/android_work_cp_enroll_04_after_1710.png)|
|![08](./media/android_work_cp_enroll_05_before_1710.png)| <span data-ttu-id="c87d5-191">*前のステップと結合*</span><span class="sxs-lookup"><span data-stu-id="c87d5-191">*Combined with previous step*</span></span> |


<span data-ttu-id="c87d5-192">電子メールへの条件付きアクセスのアクティブ化画面も更新しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-192">We've also updated the conditional access email activation screen.</span></span>

|<span data-ttu-id="c87d5-193">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-193">Before</span></span>|<span data-ttu-id="c87d5-194">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-194">After</span></span>|
|---|---|
|![06](./media/android_conditional_access_email_before_1710.png)|![06](./media/android_conditional_access_email_after_1710.png)

## <a name="week-of-september-11-2017"></a><span data-ttu-id="c87d5-197">2017 年 9 月 11 日の週</span><span class="sxs-lookup"><span data-stu-id="c87d5-197">Week of September 11, 2017</span></span>

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a><span data-ttu-id="c87d5-198">Android 用ポータル サイト アプリの文言をわかりやすいように変更 <!---1396349---></span><span class="sxs-lookup"><span data-stu-id="c87d5-198">Easier-to-understand phrasing for the Company Portal app for Android <!---1396349---></span></span>  

<span data-ttu-id="c87d5-199">Android 用ポータル サイト アプリについて、エンドユーザーが登録しやすくなるよう、テキストを変更して登録プロセスを簡易化しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-199">The enrollment process for the Company Portal app for Android has been simplified with new text to make it easier for end users to enroll.</span></span> <span data-ttu-id="c87d5-200">カスタム登録ドキュメントがある場合は、新しい画面が反映されるように更新できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-200">If you have custom enrollment documentation, you will want to update it to reflect the new screens.</span></span> <span data-ttu-id="c87d5-201">以下でサンプル画像を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-201">You can find sample images below:</span></span>

|<span data-ttu-id="c87d5-202">以前</span><span class="sxs-lookup"><span data-stu-id="c87d5-202">Before</span></span>|<span data-ttu-id="c87d5-203">これらの手順の完了後、</span><span class="sxs-lookup"><span data-stu-id="c87d5-203">After</span></span>|
|---|---|
|![01](./media/android_cp_enroll_01_before_1709.png)|![01](./media/android_cp_enroll_01_post_1709.png)|
|![02](./media/android_cp_enroll_02_before_1709.png)|![02](./media/android_cp_enroll_02_post_1709.png)|
|![03](./media/android_cp_enroll_03_before_1709.png)|![03](./media/android_cp_enroll_03_post_1709.png)|
|![04](./media/android_cp_enroll_04_before_1709.png)|![04](./media/android_cp_enroll_04_post_1709.png)|
|![05](./media/android_cp_enroll_05_before_1709.png)|![05](./media/android_cp_enroll_05_post_1709.png)|


## <a name="august-2017"></a><span data-ttu-id="c87d5-214">2017 年 8 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-214">August 2017</span></span>

### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a><span data-ttu-id="c87d5-215">iOS 11 のメール アプリが OAuth をサポート <!---1196951---></span><span class="sxs-lookup"><span data-stu-id="c87d5-215">iOS 11 Mail app will support OAuth <!---1196951---></span></span>

<span data-ttu-id="c87d5-216">Intune での条件付きアクセスで、OAuth を使用した iOS デバイスのより安全な認証がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-216">Conditional access with Intune supports more secure authentication on iOS devices with OAuth.</span></span> <span data-ttu-id="c87d5-217">これをサポートし、より安全な認証を可能にするため、iOS のポータル サイト アプリに異なるフローが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-217">To support this, there will now be a different flow on the Company Portal app for iOS to allow for more secure authentication.</span></span> <span data-ttu-id="c87d5-218">エンドユーザーがメール アプリで新しい Exchange アカウントにサインインしようとすると、Web ビューのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-218">When end users try to sign in to a new Exchange account in the Mail app, they will see a web view prompt.</span></span> <span data-ttu-id="c87d5-219">Intune に登録すると、ネイティブのメール アプリによる証明書へのアクセスを許可するプロンプトがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-219">Upon enrollment in Intune, users will see a prompt to allow the native Mail app to access a certificate.</span></span> <span data-ttu-id="c87d5-220">ほとんどのエンドユーザーにはそれ以上の検疫済みメールは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c87d5-220">Most end users will not see any more quarantined emails.</span></span> <span data-ttu-id="c87d5-221">既存のメール アカウントは引き続き基本認証プロトコルを使用するため、これに該当するユーザーには検疫済みメールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-221">Existing mail accounts will continue to use basic authentication protocol, so these users will still have quarantine emails delivered to them.</span></span> <span data-ttu-id="c87d5-222">このエンド ユーザー向けサインイン エクスペリエンスは Office モバイル アプリの場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="c87d5-222">This sign in experience for end users is similar to the one on Office mobile apps.</span></span>

![ネイティブ メール アプリでアカウントの種類を選択します。](./media/ios-11-ca-email-after-1708-01.png)

![Exchange を選択すると、iOS デバイスのプロンプトで電子メール アドレスとアカウント名が求められます。](./media/ios-11-ca-email-after-1708-02.png)

![電子メール アドレスとアカウント名を入力します。](./media/ios-11-ca-email-after-1708-03.png)

![Microsoft の外部ログイン ページに移動します。](./media/ios-11-ca-email-after-1708-04.png)

![Microsoft のページでパスワードを入力します。](./media/ios-11-ca-email-after-1708-05.png)

![Microsoft からユーザーに管理するデバイスを登録するように求められます。](./media/ios-11-ca-email-after-1708-06.png)

![ユーザーはポータル Web サイトから登録するように求められます。](./media/ios-11-ca-email-after-1708-07.png)



### <a name="intune-mobile-application-management-mam-dialog-boxes-will-have-a-modern-interface----1199015---"></a><span data-ttu-id="c87d5-230">Intune モバイル アプリケーション管理 (MAM) ダイアログ ボックスの現代的インターフェイス <!-- 1199015 --></span><span class="sxs-lookup"><span data-stu-id="c87d5-230">Intune Mobile Application Management (MAM) dialog boxes will have a modern interface <!-- 1199015 --></span></span>

<span data-ttu-id="c87d5-231">Intune モバイル アプリケーション管理 (MAM) ダイアログ ボックスが現代的な外観に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-231">Intune Mobile Application Management (MAM) dialog boxes will be updated to a modern look and feel.</span></span> <span data-ttu-id="c87d5-232">このダイアログ ボックスは、以前と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-232">The dialog boxes will function in the same way as the previous style.</span></span>

<span data-ttu-id="c87d5-233">**以前の操作性**</span><span class="sxs-lookup"><span data-stu-id="c87d5-233">**Previous experience**</span></span>

![以前のインターフェイス](./media/NewUI_Old_AttachFileHandler.jpg)

<span data-ttu-id="c87d5-235">**現代的な操作性**</span><span class="sxs-lookup"><span data-stu-id="c87d5-235">**Modern experience**</span></span>

![現代的なインターフェイス](./media/NewUI_Modern_AttachFileHandler.jpg)


### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10----1287448---"></a><span data-ttu-id="c87d5-237">Windows 10 のポータル サイト アプリの "デバイスの詳細" ページの更新 <!---1287448---></span><span class="sxs-lookup"><span data-stu-id="c87d5-237">Updates to the "Device Details" page on the Company Portal app for Windows 10 <!---1287448---></span></span>

<span data-ttu-id="c87d5-238">Windows 10 のポータル サイト アプリで、__[デバイスの詳細]__ ページで __[カテゴリ]__ タグがタイトルの下からプロパティに移動しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-238">The Company Portal app for Windows 10 is moving the __Category__ tag from below the title to a property on the __Device Details__ page.</span></span>

![Windows ポータル サイト アプリの "デバイスの詳細" 画面。"カテゴリ" フィールドが画面のタイトルのすぐ下ではなく、プロパティとして表示されています。](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="july-2017"></a><span data-ttu-id="c87d5-240">2017 年 7 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-240">July 2017</span></span>

### <a name="apps-details-pages-will-display-new-information-for-android-devices---1287476--"></a><span data-ttu-id="c87d5-241">[アプリの詳細] ページでの Android デバイスの新しい情報の表示 <!--1287476--></span><span class="sxs-lookup"><span data-stu-id="c87d5-241">Apps details pages will display new information for Android devices <!--1287476--></span></span>

<span data-ttu-id="c87d5-242">Android 用のポータル サイト アプリのアプリの詳細ページに、IT 管理者がそのアプリに対して定義したアプリのカテゴリが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-242">The apps details page of the Company Portal app for Android will now display the app categories that the IT admin has defined for that app.</span></span>

![新しいアプリの詳細ポリシー](./media/cp_android_appdetails_after_1708.png)

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a><span data-ttu-id="c87d5-244">すべてのプラットフォームでのポータル サイト アプリのサインイン操作の改善<!--User Story 1132123--></span><span class="sxs-lookup"><span data-stu-id="c87d5-244">Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123--></span></span>

<span data-ttu-id="c87d5-245">Android、iOS、Windows での Intune ポータル サイト アプリのサインイン エクスペリエンス向上のために、今後数か月間に予定されている変更についてお知らせします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-245">We are announcing a change that is coming in the next few months that will improve the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows.</span></span> <span data-ttu-id="c87d5-246">Azure AD でこの変更が行われ次第、自動的にすべてのプラットフォームでポータル サイト アプリのユーザー エクスペリエンスが一新される予定です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-246">The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change.</span></span> <span data-ttu-id="c87d5-247">また、自動生成される一時使用コードを使用して、別のデバイスからポータル サイトにサインインできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-247">In addition, users can now sign in to the Company Portal from another device with a generated, single-use code.</span></span> <span data-ttu-id="c87d5-248">この機能は、資格情報を使用せずにサインインする必要がある場合には特に便利です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-248">This is especially useful in cases when users need to sign in without credentials.</span></span>  

<span data-ttu-id="c87d5-249">以下に、従来のサインイン、資格情報を使用した新たなサインイン、別のデバイスからのサインインをそれぞれ以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-249">Below you can see the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device.</span></span>

<span data-ttu-id="c87d5-250">__従来のサインイン エクスペリエンス__</span><span class="sxs-lookup"><span data-stu-id="c87d5-250">__Previous sign in experience__</span></span>

![Web サイトのイメージ図の前にユーザーのアイコンが表示されたポータル サイトのサインイン ページ。](./media/cp_ios_aad_signin_before_1704_001.png)

![[サインイン] をタップした後に、このページで資格情報を入力します。電子メールとパスワードが要求され、パスワードのエラーを解決する方法も提供されます。](./media/cp_ios_aad_signin_before_1704_002.png)

![パスワードを入力すると、ポータル サイト アプリはサインインを行い、読み込みバーが表示されます。](./media/cp_ios_aad_signin_before_1704_003.png)

<span data-ttu-id="c87d5-256">__新たなサインイン エクスペリエンス__</span><span class="sxs-lookup"><span data-stu-id="c87d5-256">__New sign in experience__</span></span>

![Web サイトのイメージ図の前にユーザーのアイコンが表示されたポータル サイトのサインイン ページ。](./media/cp_ios_aad_signin_after_1704_001.png)

![画面は同じですが電子メールとパスワードではなく、電子メールのみを入力するように要求されます。](./media/cp_ios_aad_signin_after_1704_002.png)

![電子メールが承認されると、パスワードの入力が要求されます。](./media/cp_ios_aad_signin_after_1704_003.png)

![認証プロセスが終了すると、ポータル サイト アプリはサインインを行い、読み込みバーが表示されます。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

<span data-ttu-id="c87d5-263">__別のデバイスからサインインする際の新たなサインイン エクスペリエンス__</span><span class="sxs-lookup"><span data-stu-id="c87d5-263">__New sign in experience when signing in from another device__</span></span>

![Web サイトのイメージ図の前にユーザーのアイコンが表示されたポータル サイトのサインイン ページ。](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

<span data-ttu-id="c87d5-267">__[別のデバイスからサインインする]__ リンクをタップします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-267">Tap the __Sign in from another device__ link.</span></span>

![会社のコンピューターから固有のパスワードで aka.ms/devicelogin ページにアクセスし、コードを使用してサインインするように指示されます。](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

<span data-ttu-id="c87d5-269">ブラウザーを起動して、[https://aka.ms/devicelogin](https://aka.ms/devicelogin) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-269">Launch a browser and go to [https://aka.ms/devicelogin](https://aka.ms/devicelogin).</span></span>

![ポータル サイト アプリの画像ではなく会社のコンピューターのブラウザーの画像です。](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

<span data-ttu-id="c87d5-272">ポータル サイト アプリで表示されたコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-272">Enter the code you saw in the Company Portal app.</span></span> <span data-ttu-id="c87d5-273">__[続行]__ を選択すると、スマートカードなど、お客様の会社でサポートされている任意の方法を使用して認証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-273">When you select __Continue__, you will be able to authenticate in the using any method that is supported by your company, such as a smartcard.</span></span>

![固有のコードをフィールドに入力すると、[デバイス ログイン] サイトから、Intune ポータル サイトがサインインを許可してよい適切なアプリであることを確認されます。](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![デバイスでポータル サイト アプリへのログインが完了したことと、このページを閉じることができることを示す確認ページ。](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

<span data-ttu-id="c87d5-276">ポータル サイト アプリがサインインを開始します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-276">The Company Portal app will begin signing in.</span></span>

![認証プロセスが終了すると、ポータル サイト アプリはサインインを行い、読み込みバーが表示されます。](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="june-2017"></a><span data-ttu-id="c87d5-278">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-278">June 2017</span></span>

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a><span data-ttu-id="c87d5-279">Android 用ポータル サイト アプリのアプリ保護ポリシーの新しいエンド ユーザー エクスペリエンス <!--1305217--></span><span class="sxs-lookup"><span data-stu-id="c87d5-279">Company Portal app for Android now has a new end user experience for App Protection Policies <!--1305217--></span></span>
<span data-ttu-id="c87d5-280">ユーザーのフィードバックに基づいて、Android 用ポータル サイト アプリに **[会社のコンテンツにアクセスする]** ボタンが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-280">Based on customer feedback, we've modified the Company Portal app for Android to show an **Access Company Content** button.</span></span> <span data-ttu-id="c87d5-281">このボタンの目的は、Intune モバイル アプリケーション管理の機能であるアプリ保護ポリシーをサポートするアプリにアクセスすることだけが必要なユーザーが、不要な登録プロセスを経なくて済むようにすることです。</span><span class="sxs-lookup"><span data-stu-id="c87d5-281">The intent is to prevent end users from unnecessarily going through the enrollment process when they only need to access apps that support App Protection Policies, a feature of Intune mobile application management.</span></span>

<span data-ttu-id="c87d5-282">ユーザーはデバイスの登録を始める代わりに **[会社のコンテンツにアクセスする]** ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-282">The user will tap on the **Access Company Content** button instead of beginning to enroll the device.</span></span>

![Android ポータル サイト アプリの画像。標準では登録オプションがすぐに表示されますが、ここでは中央に "会社のコンテンツにアクセスする" という大きなテキストを確認できます。](./media/and_access_company_content_after_1706.png)

<span data-ttu-id="c87d5-284">ポータル Web サイトが表示されるので、デバイスで使用するアプリを承認します。ポータル Web サイトで資格情報が確認されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-284">The user then is taken to the Company Portal website to authorize the app for use on their device, where the Company Portal website verifies their credentials.</span></span>

![ポータル Web サイトのサインイン確定画像。](./media/and_iwp_sign_in_auth_page_after_1706.png)

<span data-ttu-id="c87d5-286">**[アクション]** メニューをタップすれば、引き続き完全管理にデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-286">The device can still be enrolled into full management by tapping on the **action** menu.</span></span>

![Android 向けポータル サイト アプリの画像。画面の右上隅にメニューが表示されています。デバイスを登録するためのオプションがあります。](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a><span data-ttu-id="c87d5-288">Windows 10 Creators Update とアプリを同期する機能の強化 <!--676505--></span><span class="sxs-lookup"><span data-stu-id="c87d5-288">Improvements to app syncing with Windows 10 Creators Update <!--676505--></span></span>

<span data-ttu-id="c87d5-289">Windows 10 用ポータル サイト アプリでは、Windows 10 Creators Update (バージョン 1703) がインストールされているデバイスのアプリ インストール要求の同期が自動的に開始されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-289">The Company Portal app for Windows 10 will now automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (version 1703).</span></span> <span data-ttu-id="c87d5-290">"同期保留中" 状態中、アプリ インストールが止まる問題を減らします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-290">This will reduce the issue of app installs stalling during the "Pending Sync" state.</span></span> <span data-ttu-id="c87d5-291">また、ユーザーはアプリ内から同期を手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-291">In addition, users will be able to manually initiate a sync from within the app.</span></span>

![Windows 10 ポータル サイト アプリの画像。ポータル サイト アプリ ストアからの Microsoft Word のダウンロードが保留になっています。](./media/w10_download_pending_after_1706.png)

![Windows 10 ポータル サイト アプリの画像。自動同期が新たに行われている状態を確認できます。デバイスが同期中であり、アプリのダウンロードを試行している旨の状態メッセージが表示されています。](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a><span data-ttu-id="c87d5-294">Windows 10 ポータル サイトの新しいガイド機能 <!---1058938---></span><span class="sxs-lookup"><span data-stu-id="c87d5-294">New guided experience for Windows 10 Company Portal <!---1058938---></span></span>
<span data-ttu-id="c87d5-295">Windows 10 用のポータル サイト アプリで、特定または登録されていないデバイス向けのガイド付き Intune チュートリアルを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-295">The Company Portal app for Windows 10 will include a guided Intune walkthrough experience for devices that have not been identified or enrolled.</span></span> <span data-ttu-id="c87d5-296">ユーザーは新たな段階的手順に従って、Azure Active Directory (条件付きアクセス機能のために必要) と MDM (デバイス管理機能のために必要) に登録できます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-296">The new experience provides step-by-step instructions that guide the user through registering into Azure Active Directory (required for Conditional Access features) and MDM enrollment (required for device management features).</span></span> <span data-ttu-id="c87d5-297">このガイドには、ポータル サイトのホーム ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-297">The guided experience will be accessible from the Company Portal home page.</span></span> <span data-ttu-id="c87d5-298">ユーザーは、これらの登録を完了していない場合でも引き続きアプリを使用できますが、機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-298">Users can continue to use the app if they do not complete registration and enrollment, but will experience limited functionality.</span></span>

<span data-ttu-id="c87d5-299">この更新は、Windows 10 Anniversary Update (ビルド 1607) 以降を実行しているデバイスのみで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-299">This update is only visible on devices running Windows 10 Anniversary Update (build 1607) or higher.</span></span>

![Windows 10 ポータル サイト アプリのランディング ページの画像。"デバイス" リストの中央に状態メッセージが表示されており、会社の使用がまだ設定されておらず、ユーザーはメッセージを選択し、設定を開始してくださいとユーザーに伝えています。](./media/win10_guided_enroll_select_setup_after_1706.png)

![Windows 10 ポータル サイト アプリの設定ページの画像。管理に登録するには、このデバイスに会社のアカウントを追加する必要があるとユーザーに警告しています。](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Windows 10 ポータル サイト アプリの "このデバイスに会社のアカウントを追加する" ページの画像。設定アプリに進み、"接続" を選択して登録を完了する必要があると伝えています。](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Windows 10 ポータル サイト アプリの "管理に登録する" 画面の画像。完了状態メッセージを確認できます。ユーザーのデバイスが登録されており、 '次へ' ボタンをタップして続行するように伝えています。](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Windows 10 ポータル サイト アプリの完了画面の画像。すべて設定済みであり、デバイスに適切に追加された会社のアカウントでデバイスが登録されたことをユーザーに知らせています。](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a><span data-ttu-id="c87d5-306">ポータル サイトを簡単に削除できるアクション メニューの追加<!--1164569--></span><span class="sxs-lookup"><span data-stu-id="c87d5-306">New menu action to easily remove Company Portal <!--1164569--></span></span>
<span data-ttu-id="c87d5-307">Android 用ポータル サイト アプリでは、ユーザーからのフィードバックに基づき、デバイスからポータル サイトの削除を開始できる新しいアクション メニューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-307">Based on user feedback, the Company Portal app for Android has added a new menu action to initiate the removal of Company Portal from your device.</span></span> <span data-ttu-id="c87d5-308">この操作では Intune の管理対象からデバイスが削除されるため、ユーザーはデバイスからアプリを削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-308">This action removes the device from Intune management so that the app can be removed from the device by the user.</span></span>

![右上隅にアクション メニューが開いた Android 用ポータル サイト アプリの画像です。](./media/android_remove_cp_menu_action_after_1705.png)

![アクション メニューから新しい [ポータル サイトの削除] オプションを選択した後に表示される確認ダイアログの画像です。](./media/android_remove_cp_menu_confirmation_after_1705.png)

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios---1230777--"></a><span data-ttu-id="c87d5-314">iOS 用ポータル サイト アプリのアプリ タイルを改善 <!--1230777--></span><span class="sxs-lookup"><span data-stu-id="c87d5-314">Improvements to the app tiles in the Company Portal app for iOS <!--1230777--></span></span>
<span data-ttu-id="c87d5-315">ポータル サイトに設定したブランド カラーが反映されるよう、ホーム ページのアプリ タイルのデザインを一新しました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-315">We updated the design of the app tiles on the homepage to reflect the branding color you set for the Company Portal.</span></span>

<span data-ttu-id="c87d5-316">**更新前**</span><span class="sxs-lookup"><span data-stu-id="c87d5-316">**Before**</span></span>

!["すべてのアプリ"、"おすすめアプリ"、"カテゴリ" の事前設定の画像が表示された更新前の iOS 用ポータル サイト アプリの画像。](./media/cp_ios_homepage_before_1705.png)

<span data-ttu-id="c87d5-318">**更新後**</span><span class="sxs-lookup"><span data-stu-id="c87d5-318">**After**</span></span>

![組織に関連するカラーを選択できる機能が反映された、更新後の iOS 用ポータル サイト アプリの画像。](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a><span data-ttu-id="c87d5-320">iOS 用ポータル サイト アプリでアカウント選択の提供を開始</span><span class="sxs-lookup"><span data-stu-id="c87d5-320">Account picker now available for the Company Portal app for iOS</span></span>
<span data-ttu-id="c87d5-321">iOS デバイスで、職場または学校アカウントを使用して別の Microsoft アプリにサインインしたことのあるユーザーが、ポータル サイトに初めてサインインしようとすると、新しいアカウントの選択が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-321">If users have used their work or school account to sign in to other Microsoft apps on their iOS device, then they may see our new account picker when signing into the Company Portal for the first time.</span></span>

![テスト ユーザー "Robin Swanson" が 2 つのメール アドレスのうち 1 つを選択していることを示す、アカウント選択の画像。](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a><span data-ttu-id="c87d5-324">2017 年 4 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-324">April 2017</span></span>

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a><span data-ttu-id="c87d5-325">Managed Browser とポータル サイトの新しいアイコン <!--918433, 918431--></span><span class="sxs-lookup"><span data-stu-id="c87d5-325">New icons for the Managed Browser and the Company Portal <!--918433, 918431--></span></span>

<span data-ttu-id="c87d5-326">Managed Browser の Android バージョンと iOS バージョンのアイコンが更新されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-326">The Managed Browser is receiving updated icons for both the Android and iOS versions of the app.</span></span> <span data-ttu-id="c87d5-327">新しいアイコンには、Enterprise Mobility + Security (EM+S) での他のアプリとの一貫性が向上した新しい Intune バッジが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-327">The new icon will contain the updated Intune badge to make it more consistent with other apps in Enterprise Mobility + Security (EM+S).</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width="200" height="366" align="center">
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width="200" height="366" align="center">
           </td>
      </tr>
   </table>
</body>
</html>

<span data-ttu-id="c87d5-328">Android、iOS、Windows でのポータル サイト アプリのアイコンも更新されて、EM+S での他のアプリとの一貫性が向上します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-328">The Company Portal is also receiving updated icons for the Android, iOS, and Windows versions of the app to improve consistency with other apps in EM+S.</span></span> <span data-ttu-id="c87d5-329">これらのアイコンは、4 月から 5 月末にかけて段階的にプラットフォーム全体にリリースされます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-329">These icons will be gradually released across platforms from April to late May.</span></span>

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a><span data-ttu-id="c87d5-330">Android 用ポータル サイトでのサインイン進行状況インジケーター<!--953374--></span><span class="sxs-lookup"><span data-stu-id="c87d5-330">Sign-in progress indicator in Android Company Portal <!--953374--></span></span>

<span data-ttu-id="c87d5-331">Android 用ポータル サイト アプリが更新されて、起動または再開時にサインイン進行状況インジケーターが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-331">An update to the Android Company Portal app shows a sign-in progress indicator when the user launches or resumes the app.</span></span> <span data-ttu-id="c87d5-332">ユーザーがアプリへのアクセスを許可されるまでにインジケーターに順番に表示される新しいステータスは、[接続中...]、[サインイン中...]、[Checking for security requirements... (セキュリティ要件確認中...)] です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-332">The indicator progresses through new statuses, beginning with "Connecting...", then "Signing in...", then "Checking for security requirements..." before allowing the user to access the app.</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width="200" height="366" align="center">
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width="200" height="366" align="center">
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width="200" height="366" align="center">
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a><span data-ttu-id="c87d5-333">Windows 10 ポータル サイト アプリのアプリ インストール状態の向上<!--676495--></span><span class="sxs-lookup"><span data-stu-id="c87d5-333">Improved app install status for the Windows 10 Company Portal app <!--676495--></span></span>
<span data-ttu-id="c87d5-334">現在の Windows 10 ポータル サイト アプリでは、アプリ詳細ページにインストール進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-334">The Windows 10 Company Portal app now provides an install progress bar on the app details page.</span></span> <span data-ttu-id="c87d5-335">これは、Windows 10 Anniversary Update 以降を実行するデバイスの最新アプリについてサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-335">This is supported for modern apps on devices running the Windows 10 Anniversary Update and up..</span></span>

<span data-ttu-id="c87d5-336">__変更前__ ![変更前のバージョンの読み込み画面の画像。状態は単に 'インストール中' と表示されていました。](./media/cp_win10_install_status_before_1704.png)</span><span class="sxs-lookup"><span data-stu-id="c87d5-336">__Before__ ![An image of the previous version of the loading screen, where the status simply said 'installing.'](./media/cp_win10_install_status_before_1704.png)</span></span>

<span data-ttu-id="c87d5-337">__変更後__ ![変更後のバージョンの読み込み画面の画像。インストール進行状況バーが表示されるようになりました。](./media/cp_win10_install_status_after_1704.png)</span><span class="sxs-lookup"><span data-stu-id="c87d5-337">__After__ ![An image of the updated version of the loading screen, which now shows an install progress bar.](./media/cp_win10_install_status_after_1704.png)</span></span>

## <a name="february-2017"></a><span data-ttu-id="c87d5-338">2017 年 2 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-338">February 2017</span></span>

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a><span data-ttu-id="c87d5-339">Android 用ポータル サイト アプリに関する新しいユーザー エクスペリエンス <!--621622, announced 1702--></span><span class="sxs-lookup"><span data-stu-id="c87d5-339">New user experience for the Company Portal app for Android <!--621622, announced 1702--></span></span>
<span data-ttu-id="c87d5-340">3 月以降、Android 用ポータル サイト アプリでは[材料設計ガイドライン](https://material.io/guidelines/material-design/introduction.html)に従って、最新の外観が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-340">Beginning in March, the Company Portal app for Android will follow [material design guidelines](https://material.io/guidelines/material-design/introduction.html) to create a more modern look and feel.</span></span> <span data-ttu-id="c87d5-341">この改善されたユーザー エクスペリエンスには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-341">This improved user experience includes:</span></span>

* <span data-ttu-id="c87d5-342">__色__: タブ ヘッダーを、カスタムの色パレットに従って色付けすることができます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-342">__Colors__: tab headers can be colored according to your custom color palette.</span></span>

![左側は、更新前の Android 用ポータル サイト アプリのイメージです。](./media/CP_Android_DevicesTab_BeforeAfter.png)

* <span data-ttu-id="c87d5-346">__インターフェイス__: __[アプリ]__ タブの __[おすすめアプリ]__ ボタンと __[すべてのアプリ]__ ボタンが更新されました。__[検索]__ ボタンは浮動アクション ボタンになりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-346">__Interface__: __Featured Apps__ and __All Apps__ buttons have been updated in the __Apps__ tab. The __Search__ button is now a floating action button.</span></span>

![左側は、更新前の Android 用ポータル サイト アプリのイメージです。](./media/CP_Android_AppsTab_BeforeAfter.png)

* <span data-ttu-id="c87d5-350">__ナビゲーション__: [すべてのアプリ] で __[おすすめ]__、__[すべて]__ および __[カテゴリ]__ のタブ付きビューが表示され、移動がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c87d5-350">__Navigation__: All Apps shows a tabbed view of __Featured__, __All__ and __Categories__ for easier navigation.</span></span> <span data-ttu-id="c87d5-351">__[IT に連絡]__ が簡素化され、読みやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-351">__Contact IT__ has been streamlined for improved readability.</span></span>

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width="200" height="366" align="center">
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a><span data-ttu-id="c87d5-352">2017 年 1 月</span><span class="sxs-lookup"><span data-stu-id="c87d5-352">January 2017</span></span>

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a><span data-ttu-id="c87d5-353">ポータル Web サイトの進化 <!--753980, announced 1701--></span><span class="sxs-lookup"><span data-stu-id="c87d5-353">Modernizing the Company Portal website <!--753980, announced 1701--></span></span>
<span data-ttu-id="c87d5-354">2 月から、ポータル Web サイトで管理対象のデバイスを持っていないユーザーを対象とするアプリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c87d5-354">Beginning in February, the Company Portal website will support apps that are targeted to users who do not have managed devices.</span></span> <span data-ttu-id="c87d5-355">この Web サイトは、新しいコントラストの配色パターン、動的な図、および "ハンバーガー メニュー" </span><span class="sxs-lookup"><span data-stu-id="c87d5-355">The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu,"</span></span> ![(ヘルプデスクの連絡先詳細や既存の管理対象デバイスに関する情報を含む、](./media/CP_hamburger_menu.png) <span data-ttu-id="c87d5-357">ポータル Web サイトの左上隅に新たに追加されたハンバーガー メニューの小さなイメージ) を使用することで、Microsoft の他の製品やサービスと連携します。</span><span class="sxs-lookup"><span data-stu-id="c87d5-357">which will contain helpdesk contact details and information on existing managed devices.</span></span> <span data-ttu-id="c87d5-358">ランディング ページはユーザーが利用できるアプリをわかりやすくするために再配置され、おすすめのアプリや最近更新されたアプリはカルーセル ビューで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87d5-358">The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps.</span></span>

![左側は、以前のバージョンの [アプリ]、[デバイス]、[おすすめ] ビュー、[カテゴリ] ビューが表示された、会社のポータル Web サイトの現在のバージョンのイメージです。](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a><span data-ttu-id="c87d5-361">UI で近日公開予定</span><span class="sxs-lookup"><span data-stu-id="c87d5-361">Coming soon in the UI</span></span>
<span data-ttu-id="c87d5-362">これらは、ユーザー インターフェイスを更新することによってユーザー エクスペリエンスを向上させるために計画されている方法です。</span><span class="sxs-lookup"><span data-stu-id="c87d5-362">These are the plans for ways we will be improving the user experience by updating our user interface.</span></span>

> [!Note]
> <span data-ttu-id="c87d5-363">次のイメージはプレビューであり、発表される製品は示されているバージョンとは異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c87d5-363">Please note that the images below may be previews, and the announced product may differ from the presented versions.</span></span>

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a><span data-ttu-id="c87d5-364">ポータル Web サイトの UI の更新 <!--1313244 part 2--></span><span class="sxs-lookup"><span data-stu-id="c87d5-364">UI updates to the Company Portal website <!--1313244 part 2--></span></span>

<span data-ttu-id="c87d5-365">__おすすめアプリの更新__ サイトにおすすめとして選択したアプリを参照できる専用ページを追加し、ホームページのおすすめセクションでいくつかの UI の修正を行いました。</span><span class="sxs-lookup"><span data-stu-id="c87d5-365">__Updates to Featured Apps__ We've added a dedicated page to the site where users can browse apps that you've chosen to feature, and made some UI tweaks to the Featured section on the homepage.</span></span>

![アプリが表示されたカラフルなタイル。](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a><span data-ttu-id="c87d5-369">関連項目</span><span class="sxs-lookup"><span data-stu-id="c87d5-369">See also</span></span>
* [<span data-ttu-id="c87d5-370">Microsoft Intune のブログ</span><span class="sxs-lookup"><span data-stu-id="c87d5-370">Microsoft Intune Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=273882)
* [<span data-ttu-id="c87d5-371">クラウド プラットフォームのロードマップ</span><span class="sxs-lookup"><span data-stu-id="c87d5-371">Cloud Platform roadmap</span></span>](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [<span data-ttu-id="c87d5-372">Intune の新機能</span><span class="sxs-lookup"><span data-stu-id="c87d5-372">What's new in Intune</span></span>](https://docs.microsoft.com/intune/whats-new)
