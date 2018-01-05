---
title: "Android でユーザーに表示される可能性のあるポータル サイト メッセージ"
description: "Intune エンド ユーザーに表示される可能性のあるポータル サイト アプリのメッセージについて説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.openlocfilehash: f1a5c8a15007a38942fe543e6c1062bf957a481c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="help-end-users-understand-company-portal-app-messages"></a><span data-ttu-id="c2971-103">ポータル サイト アプリで表示されるメッセージに関してエンド ユーザーをサポートする</span><span class="sxs-lookup"><span data-stu-id="c2971-103">Help end users understand Company Portal app messages</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> <span data-ttu-id="c2971-104">次の情報は、Android 6.0 以上のデバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-104">The following information applies only on devices with Android 6.0+.</span></span>

<span data-ttu-id="c2971-105">登録プロセスで表示される 2 つのメッセージが、エンド ユーザーにとって混乱の原因となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2971-105">At different points in the enrollment process, end users will see two different messages that could be cause for concern.</span></span>

- <span data-ttu-id="c2971-106">__電話での通話とその管理をポータル サイトに許可しますか?__</span><span class="sxs-lookup"><span data-stu-id="c2971-106">__Allow Company Portal to make and manage phone calls?__</span></span>
- <span data-ttu-id="c2971-107">__デバイス上の写真、メディア、およびファイルへのアクセスをポータル サイトに許可しますか?__</span><span class="sxs-lookup"><span data-stu-id="c2971-107">__Allow Company Portal to access photos, media, and files on your device?__</span></span>

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a><span data-ttu-id="c2971-108">電話での通話とその管理をポータル サイトに許可しますか?</span><span class="sxs-lookup"><span data-stu-id="c2971-108">Allow Company Portal to make and manage phone calls?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="c2971-109">表示内容</span><span class="sxs-lookup"><span data-stu-id="c2971-109">Where it appears</span></span>
<span data-ttu-id="c2971-110">ユーザーがデバイスを登録するときにポータル サイト アプリで **[登録]** をタップすると、**[電話での通話とその管理をポータル サイトに許可しますか?]** のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-110">The message **Allow Company Portal to make and manage phone calls?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="c2971-111">意味</span><span class="sxs-lookup"><span data-stu-id="c2971-111">What it means</span></span>
<span data-ttu-id="c2971-112">ユーザーがこの同意すると、デバイスの電話番号と IMEI 番号が Intune サービスに送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c2971-112">By accepting this prompt, users allow their device's phone and IMEI numbers to be sent to the Intune service.</span></span> <span data-ttu-id="c2971-113">これらは管理コンソールの __[ハードウェア]__ ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-113">These will appear on the admin console on the __Hardware__ page.</span></span>

> [!NOTE]
> <span data-ttu-id="c2971-114">**ポータル サイト アプリは電話での通話やその管理を行いません。**</span><span class="sxs-lookup"><span data-stu-id="c2971-114">**The Company Portal app never makes or manages phone calls!**</span></span> <span data-ttu-id="c2971-115">このメッセージ テキストは Google によって制御されているので、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2971-115">The message text is controlled by Google and cannot be changed.</span></span>

<span data-ttu-id="c2971-116">**[ハードウェア]** ページを参照するには、**[グループ]** > **[すべてのモバイル デバイス]** > **[デバイス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2971-116">To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Devices**.</span></span> <span data-ttu-id="c2971-117">ユーザーのデバイスを選択し、**[プロパティの表示]** > **[ハードウェア]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c2971-117">Select the user's device, and go to **View Properties** > **Hardware**.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="c2971-118">ユーザーがアクセスを拒否した場合の動作</span><span class="sxs-lookup"><span data-stu-id="c2971-118">What happens if users deny access</span></span>
<span data-ttu-id="c2971-119">ユーザーはアクセスを拒否した場合でも、引き続きポータル サイト アプリを使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="c2971-119">If users deny access, they can continue to use the Company Portal app and enroll their device.</span></span> <span data-ttu-id="c2971-120">ただし、管理コンソールの __[ハードウェア]__ ページでデバイスの電話番号と IMEI 番号が空白になります。</span><span class="sxs-lookup"><span data-stu-id="c2971-120">However, the device phone number and IMEI number will be blank on the __Hardware__ page in the admin console.</span></span> <span data-ttu-id="c2971-121">アクセスを拒否したあとで、ユーザーがポータル サイト アプリに 2 回目にサインインしたときに、メッセージに **[今後このメッセージを表示しない]** チェック ボックスが表示されます。これを選択すると、プロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c2971-121">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="c2971-122">ユーザーがアクセスを許可し、その後アクセスを拒否した場合は、登録後、次回ユーザーがポータル サイト アプリにサインインしたときに、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-122">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="c2971-123">後でアクセスを許可する場合は、**[設定]** > **[アプリ]** > **[ポータル サイト]** > **[アクセス許可]** > **[電話]** の順に移動して、アクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c2971-123">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="c2971-124">ユーザーへの説明方法</span><span class="sxs-lookup"><span data-stu-id="c2971-124">How to explain this to your users</span></span>
<span data-ttu-id="c2971-125">ユーザーは、「[Intune に Android デバイスを登録する](/intune-user-help/enroll-your-device-in-intune-android)」で詳細を参照できます。</span><span class="sxs-lookup"><span data-stu-id="c2971-125">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <a name="allow-company-portal-to-access-your-contacts"></a><span data-ttu-id="c2971-126">ポータル サイトに連絡先へのアクセスを許可しますか?</span><span class="sxs-lookup"><span data-stu-id="c2971-126">Allow Company Portal to access your contacts?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="c2971-127">表示内容</span><span class="sxs-lookup"><span data-stu-id="c2971-127">Where it appears</span></span>
<span data-ttu-id="c2971-128">ユーザーがデバイスを登録するときに、ポータル サイト アプリで **[登録]** をタップすると、**[連絡先へのアクセスをポータル サイトに許可しますか?]** のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-128">The message **Allow Company Portal to access your contacts?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="c2971-129">意味</span><span class="sxs-lookup"><span data-stu-id="c2971-129">What it means</span></span>
<span data-ttu-id="c2971-130">ユーザーが同意すると、Intune が職場アカウントを作成し、そのデバイスでユーザーに登録されている Azure Active Directory ID を管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c2971-130">By accepting this prompt, users allow Intune to create their work account and manage the Azure Active Directory identity that is registered for the user on that device.</span></span>

> [!NOTE]
> <span data-ttu-id="c2971-131">**Microsoft が連絡先にアクセスすることはありません。**</span><span class="sxs-lookup"><span data-stu-id="c2971-131">**Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="c2971-132">このメッセージ テキストは Google によって制御されているので、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2971-132">The message text is controlled by Google and cannot be changed.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="c2971-133">ユーザーがアクセスを拒否した場合の動作</span><span class="sxs-lookup"><span data-stu-id="c2971-133">What happens if users deny access</span></span>
<span data-ttu-id="c2971-134">ユーザーがアクセスを拒否すると、デバイスは Intune に登録されず、管理できません。</span><span class="sxs-lookup"><span data-stu-id="c2971-134">If users deny access, their device will not be enrolled in Intune and cannot be managed.</span></span> <span data-ttu-id="c2971-135">アクセスを拒否したあとで、ユーザーがポータル サイト アプリに 2 回目にサインインしたときに、メッセージに **[今後このメッセージを表示しない]** チェック ボックスが表示されます。これを選択すると、プロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c2971-135">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="c2971-136">ユーザーがアクセスを許可し、その後アクセスを拒否した場合は、登録後、次回ユーザーがポータル サイト アプリにサインインしたときに、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-136">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="c2971-137">後でアクセスを許可する場合は、**[設定]** > **[アプリ]** > **[ポータル サイト]** > **[アクセス許可]** > **[電話]** の順に移動して、アクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c2971-137">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="c2971-138">ユーザーへの説明方法</span><span class="sxs-lookup"><span data-stu-id="c2971-138">How to explain this to your users</span></span>
<span data-ttu-id="c2971-139">ユーザーは、「[Intune に Android デバイスを登録する](/intune-user-help/enroll-your-device-in-intune-android)」で詳細を参照できます。</span><span class="sxs-lookup"><span data-stu-id="c2971-139">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a><span data-ttu-id="c2971-140">デバイス上の写真、メディア、およびファイルへのアクセスをポータル サイトに許可しますか?</span><span class="sxs-lookup"><span data-stu-id="c2971-140">Allow Company Portal to access photos, media, and files on your device?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="c2971-141">表示内容</span><span class="sxs-lookup"><span data-stu-id="c2971-141">Where it appears</span></span>
<span data-ttu-id="c2971-142">ユーザーがログを IT 管理者に送信するときに、**[データを送信]** をタップすると、**[デバイス上の写真、メディア、およびファイルへのアクセスをポータル サイトに許可しますか?]** のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-142">The message **Allow Company Portal to access photos, media, and files on your device?** appears when users tap **Send Data** to send logs to their IT admin.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="c2971-143">意味</span><span class="sxs-lookup"><span data-stu-id="c2971-143">What it means</span></span>
<span data-ttu-id="c2971-144">これに同意すると、ユーザーのデバイスでデータ ログがデバイスの SD カードに書き込まれ、それらのログを USB ケーブルを使用して移動することが許可されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-144">By accepting this prompt, users allow their device to write data logs to the device's SD card and enable those logs to be moved using a USB cable.</span></span>   

> [!NOTE]
> <span data-ttu-id="c2971-145">**ポータル サイト アプリはユーザーの写真、メディア、およびファイルにアクセスしません。**</span><span class="sxs-lookup"><span data-stu-id="c2971-145">**The Company Portal app never accesses users' photos, media, and files!**</span></span> <span data-ttu-id="c2971-146">このメッセージ テキストは Google によって制御されているので、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2971-146">The message text is controlled by Google and cannot be changed.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="c2971-147">ユーザーがアクセスを拒否した場合の動作</span><span class="sxs-lookup"><span data-stu-id="c2971-147">What happens if users deny access</span></span>
<span data-ttu-id="c2971-148">ユーザーがアクセスを拒否した場合、ユーザーは引き続きデータ ログを電子メールで送信できますが、ログはデバイスの SD カードにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="c2971-148">If users deny access, they can still send data logs via email, but the logs won't be copied to the device's SD card.</span></span>

<span data-ttu-id="c2971-149">アクセスを拒否すると、ユーザーがポータル サイト アプリに 2 回目にサインインしたときに、メッセージに **[今後このメッセージを表示しない]** チェック ボックスが表示されます。ユーザーはこれを選ぶことによって、メッセージが再び表示されないようにできます。</span><span class="sxs-lookup"><span data-stu-id="c2971-149">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</span></span> <span data-ttu-id="c2971-150">ユーザーがアクセスを許可し、その後アクセスを拒否した場合は、次回ユーザーがログを送信しようとすると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2971-150">If users allow, but then later deny access, the message appears the next time users try to send logs.</span></span> <span data-ttu-id="c2971-151">後でアクセスを許可する場合は、**[設定]**  >  **[アプリ]**  >  **[ポータル サイト]**  >  **[アクセス許可]**  >  **[ストレージ]** に移動して、アクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c2971-151">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.</span></span>


### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="c2971-152">ユーザーへの説明方法</span><span class="sxs-lookup"><span data-stu-id="c2971-152">How to explain this to your users</span></span>
<span data-ttu-id="c2971-153">ユーザーは、[IT 管理者への電子メールによるログの送信](/intune-user-help/send-logs-to-your-it-admin-by-email-android)に関する記事を参照できます。</span><span class="sxs-lookup"><span data-stu-id="c2971-153">Send your users to [Send logs to your IT admin by email](/intune-user-help/send-logs-to-your-it-admin-by-email-android).</span></span> <span data-ttu-id="c2971-154">また、[IT 管理者へのケーブルを使用したログの送信](/intune-user-help/send-logs-to-your-it-admin-by-cable-android)に関する記事を参照すると、2 つの方法を比較できます。</span><span class="sxs-lookup"><span data-stu-id="c2971-154">You can also send them to [Send logs to your IT admin by cable](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) if you want to let them compare the two methods.</span></span>

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a><span data-ttu-id="c2971-155">会社のサポートが会社のリソースへのアクセス権を与える必要がある</span><span class="sxs-lookup"><span data-stu-id="c2971-155">Your company support needs to give you access to company resources</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="c2971-156">表示内容</span><span class="sxs-lookup"><span data-stu-id="c2971-156">Where it appears</span></span>
<span data-ttu-id="c2971-157">ポータル サイト アプリを **[許可されたアプリ]** または **[適用から除外されるアプリ]** の一覧に追加していない場合にユーザーがサインインしようとすると、サインインが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c2971-157">If you have not added the Company Portal app to the **Allowed apps** or **Exempt apps** list, and a user attempts to sign in, the sign in will fail.</span></span> <span data-ttu-id="c2971-158">次のメッセージが表示されます:</span><span class="sxs-lookup"><span data-stu-id="c2971-158">The following message displays:</span></span>

> <span data-ttu-id="c2971-159">**Your company support needs to give you access to company resources\(会社のサポートから会社のリソースへのアクセス権を付与してもらう必要があります\)**</span><span class="sxs-lookup"><span data-stu-id="c2971-159">**Your company support needs to give you access to company resources**</span></span>  
> <span data-ttu-id="c2971-160">あなたの会社は Windows 情報保護ポリシーを使用してデバイスを保護しています。</span><span class="sxs-lookup"><span data-stu-id="c2971-160">Your company is using Windows Information Protection policies to protect your device.</span></span> <span data-ttu-id="c2971-161">ポータル サイトからこのポリシーにアクセスできることを、会社のサポートが確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2971-161">Your company support will need to make sure they allow the Company Portal to access those.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="c2971-162">意味</span><span class="sxs-lookup"><span data-stu-id="c2971-162">What it means</span></span>

<span data-ttu-id="c2971-163">ポータル サイトを Windows 情報保護 (WIP) のアプリ保護ポリシーの **[許可されたアプリ]** または**[適用から除外されるアプリ]** 一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="c2971-163">Add the Company Portal the **Allowed apps** or **Exempt apps** list in the Windows Information Protection (WIP) app protection policy.</span></span> <span data-ttu-id="c2971-164">詳細については、「[Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成して展開する](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2971-164">For more information, see [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).</span></span>

### <a name="see-also"></a><span data-ttu-id="c2971-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2971-165">See also</span></span>
[<span data-ttu-id="c2971-166">Intune の使用に関するエンドユーザーへの通知内容</span><span class="sxs-lookup"><span data-stu-id="c2971-166">What to tell your end users about using Intune</span></span>](end-user-educate.md)
