---
title: "Intune に Android デバイスを登録する | Microsoft Docs"
description: "Intune に Android デバイスを登録する方法について説明します"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7a90ae7db1141b40934648c951276e3f4d43bc05
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-android-device-in-intune"></a><span data-ttu-id="922c9-103">Intune に Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="922c9-103">Enroll your Android device in Intune</span></span>

<span data-ttu-id="922c9-104">職場または学校が Microsoft Intune を使用している場合は、お使いの Android デバイスを登録して、会社の電子メール、ファイル、またその他のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="922c9-104">If your company or school uses Microsoft Intune, you can enroll your Android device to get access to company email, files, and other resources.</span></span> <span data-ttu-id="922c9-105">デバイスを登録すると、IT 部門が職場や学校のリソースを管理してそれらの安全性を保持する一方で、ユーザーは好みのデバイスを使用して作業を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="922c9-105">When you enroll your devices, your IT department can manage those work or school resources, keep them secure, and give you the freedom to use your preferred device to get your work done.</span></span> <span data-ttu-id="922c9-106">登録の詳細については、「[ポータル サイト アプリをインストールし、Intune にデバイスを登録するとどうなるか](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="922c9-106">To learn more about enrollment, see [What happens when I install and Company Portal app and enroll my device?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

<span data-ttu-id="922c9-107">これらの登録手順は、ネイティブ Android デバイスおよび Samsung KNOX Android デバイス用の手順です。</span><span class="sxs-lookup"><span data-stu-id="922c9-107">These enrollment instructions are for native and Samsung KNOX Android devices.</span></span> <span data-ttu-id="922c9-108">Samsung KNOX は、ネイティブ Android に用意されている以外の追加保護を提供するために特定の Samsung 製のデバイスで使用されるセキュリティの一種です。</span><span class="sxs-lookup"><span data-stu-id="922c9-108">Samsung KNOX is a type of security that certain Samsung devices use to provide additional protection outside of what native Android provides.</span></span> <span data-ttu-id="922c9-109">Samsung KNOX デバイスかどうかを確認するには、**[Settings]** > **[About device]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="922c9-109">To check if you have a Samsung KNOX device, go to **Settings** > **About device**.</span></span> <span data-ttu-id="922c9-110">"KNOX version" という文字がない場合、デバイスはネイティブ Android デバイスです。</span><span class="sxs-lookup"><span data-stu-id="922c9-110">If you don't see "KNOX version" listed there, you have a native Android device.</span></span>

<span data-ttu-id="922c9-111">登録の前後に、デバイスの使用方法に適したカテゴリを選ぶように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="922c9-111">Before or after enrolling, you may be asked to choose a category that best describes how you use your device.</span></span> <span data-ttu-id="922c9-112">会社のサポートは、このカテゴリを使用して、ユーザーがアクセスできるアプリの確認に役立てています。</span><span class="sxs-lookup"><span data-stu-id="922c9-112">Your company support uses this category to help check the apps that you have access to.</span></span>

<span data-ttu-id="922c9-113">**Android デバイスを登録するには:**</span><span class="sxs-lookup"><span data-stu-id="922c9-113">**To enroll your Android device:**</span></span>

1.  <span data-ttu-id="922c9-114">無料の Intune ポータル サイト アプリを [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) からインストールします。</span><span class="sxs-lookup"><span data-stu-id="922c9-114">Install the free Intune Company Portal app from [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span></span>

2.  <span data-ttu-id="922c9-115">ポータル サイト アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="922c9-115">Open the Company Portal app.</span></span>

3.  <span data-ttu-id="922c9-116">ポータル サイトの **[ようこそ]** 画面で、**[サインイン]** をタップし、職場または学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="922c9-116">On the Company Portal **Welcome** screen, tap **Sign in**, and then sign in with your work or school account.</span></span>

    ![必要な職場または学校アカウントでサインインするようにユーザーに求める Android のようこそ画面のポータル サイト アプリ。](./media/and-enroll-0-welcome-screen.png)   

4.  <span data-ttu-id="922c9-119">会社のサポートによって会社の使用条件が設定されている場合は、**[同意する]** をタップして該当する条項に同意します。</span><span class="sxs-lookup"><span data-stu-id="922c9-119">If your company support set up company terms and conditions, tap **ACCEPT** to accept the terms.</span></span> <span data-ttu-id="922c9-120">現在使用する Android のバージョンによっては、画面が下の図と少し異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="922c9-120">This screen may differ slightly from the image below based on the version of Android you're currently using.</span></span>

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  <span data-ttu-id="922c9-122">職場または学校の電子メール アドレスとパスワードを使用してポータル サイト アプリにサインインし、**[サインイン]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-122">Sign in to the Company Portal app using your work or school account and password, and then tap **Sign in**.</span></span>

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  <span data-ttu-id="922c9-124">**[会社アクセスのセットアップ]** 画面で、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-124">On the **Company Access Setup** screen, tap **CONTINUE**.</span></span>

    ![[会社アクセスのセットアップ] 画面](/intune/media/android_cp_enroll_01_1709_new.png)

    > [!NOTE]
    > <span data-ttu-id="922c9-126">黄色い三角形は、エラーが既に発生していることを意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="922c9-126">The yellow triangles don't mean you've already got an error.</span></span> <span data-ttu-id="922c9-127">これらのアイコンは、登録プロセスに完了する必要のある手順があることを示します。</span><span class="sxs-lookup"><span data-stu-id="922c9-127">Those icons indicate that there are still steps to be completed in the enrollment process.</span></span>

7.  <span data-ttu-id="922c9-128">会社のサポートがユーザーのデバイスに関して確認できる情報と確認できない情報について確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-128">Review a list of what your company support can and can't see on your device, and then tap **CONTINUE**.</span></span>

    ![プライバシーの設定](/intune/media/android_cp_enroll_02_after_1710.png)

9.  <span data-ttu-id="922c9-130">**[What's next?]\(次のステップ\)** 画面で、登録中に行う内容を確認し、**[登録]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-130">On the **What's next?** screen, read about what happens during enrollment, and then tap **ENROLL**.</span></span>

    ![[次に行うこと] 画面](/intune/media/android_cp_enroll_03_after_1710.png)

10.  <span data-ttu-id="922c9-132">Android 6.0 以降を使用している場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="922c9-132">If you're using Android 6.0 or later, do this step.</span></span> <span data-ttu-id="922c9-133">使用できない場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="922c9-133">Otherwise, go to the next step.</span></span>

    <span data-ttu-id="922c9-134">会社のサポートが特定のポリシーを設定している場合は、次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="922c9-134">If your company support has set up certain policies, you may see the following messages:</span></span>
    -   <span data-ttu-id="922c9-135">**電話での通話とその管理をポータル サイトに許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="922c9-135">**Allow Company Portal to make and manage phone calls?**</span></span>

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    <span data-ttu-id="922c9-137">このメッセージが表示された場合は、**[許可]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-137">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="922c9-138">**Microsoft が通話や電話の管理を行うことはない**ため、[許可] をタップしても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="922c9-138">It is safe to tap ALLOW because **Microsoft never makes or manages your phone calls**!</span></span> <span data-ttu-id="922c9-139">このメッセージ テキストは Google が制御しているため、Microsoft ではそれを変更することができません。</span><span class="sxs-lookup"><span data-stu-id="922c9-139">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="922c9-140">アクセスを許可すると、デバイスからデバイスの国際移動体加入者識別番号 (IMEI) が Intune に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="922c9-140">When you allow access, all you're doing is letting your device send your device's international mobile station equipment identity (IMEI) number to Intune.</span></span> <span data-ttu-id="922c9-141">IMEI は、モバイル デバイスを一意に識別するシリアル番号のような番号です。</span><span class="sxs-lookup"><span data-stu-id="922c9-141">The IMEI number is like a serial number that uniquely identifies a mobile device.</span></span>

    <span data-ttu-id="922c9-142">アクセスを拒否すると、次に会社のポータルにサインインしたときにもう一度メッセージが表示されますが、**[今後このメッセージを表示しない]** ボックスをタップすると、メッセージ表示をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="922c9-142">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="922c9-143">後でアクセスを許可する場合、**[設定]** &gt; **[アプリ]** &gt; **[ポータル サイト]** &gt; **[アクセス許可]** &gt; **[電話]** に移動して、アクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="922c9-143">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

    -   <span data-ttu-id="922c9-144">**ポータル サイトに連絡先へのアクセスを許可しますか?**</span><span class="sxs-lookup"><span data-stu-id="922c9-144">**Allow Company Portal to access your contacts?**</span></span>

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

        <span data-ttu-id="922c9-146">このメッセージが表示された場合は、**[許可]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-146">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="922c9-147">**Microsoft が連絡先にアクセスすることはない**ため、[許可] をタップしても問題はありません。</span><span class="sxs-lookup"><span data-stu-id="922c9-147">It is safe to tap ALLOW because **Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="922c9-148">このメッセージ テキストは Google が制御しているため、Microsoft ではそれを変更することができません。</span><span class="sxs-lookup"><span data-stu-id="922c9-148">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="922c9-149">アクセスを許可すると、ポータル サイト アプリに仕事用アカウントの作成、使用、管理のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="922c9-149">When you allow access, it only lets the Company Portal app create, use, and manage your work account.</span></span>

        <span data-ttu-id="922c9-150">アクセスを拒否すると、次に会社のポータルにサインインしたときにもう一度メッセージが表示されますが、**[今後このメッセージを表示しない]** ボックスをタップすると、メッセージ表示をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="922c9-150">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="922c9-151">後でアクセスを許可する場合、**[設定]** &gt; **[アプリ]** &gt; **[ポータル サイト]** &gt; **[アクセス許可]** &gt; **[電話]** に移動して、アクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="922c9-151">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

11.  <span data-ttu-id="922c9-152">**[デバイス管理者のアクティブ化]** 画面で、**[アクティブ化]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-152">On the **Activate device administrator** screen, tap **Activate**.</span></span>

    ![[デバイス管理者のアクティブ化] 画面](./media/and-enroll-5-activate.png)

    <span data-ttu-id="922c9-154">デバイス管理者の役割は、ポータル サイトでデバイスを管理するために必要な役割です。</span><span class="sxs-lookup"><span data-stu-id="922c9-154">The device administrator role is one that the Company Portal needs to manage your device.</span></span> <span data-ttu-id="922c9-155">この役割を用意すると、管理者は特定の項目、たとえば、画面のロック解除が何回試行されたかなどを表示し、措置を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="922c9-155">It allows your admin to see certain things - like how many times you've attempted to unlock your screen - and to take some actions.</span></span>

    <span data-ttu-id="922c9-156">重要なことは、これらのアクションがセキュリティの名の下に行われるということです。</span><span class="sxs-lookup"><span data-stu-id="922c9-156">The key to remember is that these are actions that are taken in the name of security.</span></span> <span data-ttu-id="922c9-157">会社のサポートは理由なくプライバシーを侵害したり、情報を削除したりしません。企業のデータが守られていることを確認しようとしているだけです。</span><span class="sxs-lookup"><span data-stu-id="922c9-157">Your company support isn't trying to violate your privacy or erase your information for no reason, but wants to make sure that corporate data is kept safe.</span></span>

    <span data-ttu-id="922c9-158">Microsoft はこのメッセージは制御しません。その言葉遣いが少々極端であることは理解しています。</span><span class="sxs-lookup"><span data-stu-id="922c9-158">Microsoft does not control this message, and we understand that its phrasing can seem somewhat drastic.</span></span> <span data-ttu-id="922c9-159">特定の組織に関連する制約やアクセスのみをポータル サイトで表示する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="922c9-159">There's not a way for the Company Portal to display just the restrictions and access that are relevant to your organization.</span></span> <span data-ttu-id="922c9-160">すべて一度にこの画面で与えられます。</span><span class="sxs-lookup"><span data-stu-id="922c9-160">All of them are granted at once on this screen.</span></span> <span data-ttu-id="922c9-161">個別の組織の利用に関して質問があれば、[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)の連絡先情報を利用し、会社のサポートに詳細を問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="922c9-161">Contact your company support for more information using the contact information in the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) if you have questions specific to your individual organization's use.</span></span>

12.  <span data-ttu-id="922c9-162">画面の指示に従って、PIN またはパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="922c9-162">Follow the prompts to enter a PIN or password.</span></span> <span data-ttu-id="922c9-163">このデバイス上で PIN またはパスワードを既に設定している場合は、この画面は表示されず、新しい PIN またはパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="922c9-163">If you already set up a PIN or password on this device, you won't see this screen or be required to enter a new PIN or password.</span></span>

    ![PIN またはパスワードを入力する](./media/and-enroll-6-PIN-native.png)

13.  <span data-ttu-id="922c9-165">Samsung KNOX デバイスを使用している場合は、**[Confirm]** をタップすると、デバイスが登録中であることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="922c9-165">If you are using a Samsung KNOX device, tap **Confirm**, and you’ll see a message that your device is being enrolled.</span></span> <span data-ttu-id="922c9-166">ネイティブ Android デバイスを使用している場合は、デバイスが登録されていることを示す次の画面にだけ注意してください。</span><span class="sxs-lookup"><span data-stu-id="922c9-166">If you are using a native Android device, just notice the following screen that shows that your device is being enrolled.</span></span>

    ![Samsung KNOX プライバシー ポリシー](./media/and-enroll-7-knox-privacy-policy.png)

    <span data-ttu-id="922c9-168">この画面は、デバイスが登録されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="922c9-168">This screen shows that your device is being enrolled.</span></span>

    ![デバイス登録中画面](./media/and-enroll-8-device-enrolling.png)

14. <span data-ttu-id="922c9-170">**[会社アクセスのセットアップ]** 画面が表示されたら、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-170">When the **Company Access Setup** screen appears, tap **CONTINUE**.</span></span> <span data-ttu-id="922c9-171">デバイスが対応していないことを示すメッセージが表示された場合は、問題を解決するための指示に従い、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-171">If a message indicates that your device is out of compliance, follow the instructions to fix the issue, and then tap **CONTINUE**.</span></span>

    ![デバイスはポリシー準拠していないが、登録されている](/intune/media/android_cp_enroll_05_post_1709.png)

    ![解決が必要なデバイスのポリシー準拠の問題が発生している](/intune/media/android_cp_enroll_03_post_1709.png)

    <span data-ttu-id="922c9-174">問題の詳細を表示するには、これらをタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-174">You can find out more about the issues by tapping on them.</span></span>

    ![展開されたデバイスのポリシー準拠の問題](/intune/media/android_cp_enroll_04_post_1709.png)

    ![[会社アクセスのセットアップ] 画面](./media/and-enroll-9d-comp-access-setup.png)  

15. <span data-ttu-id="922c9-177">**[会社アクセスのセットアップが完了しました]** の画面で、**[完了]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="922c9-177">On the **Company Access Setup complete** screen, tap **DONE**.</span></span> <span data-ttu-id="922c9-178">これでデバイスが登録されました。</span><span class="sxs-lookup"><span data-stu-id="922c9-178">Your device is now enrolled.</span></span>

    ![[会社アクセスのセットアップが完了しました] 画面](./media/and-enroll-10-comp-access-setup-complete.png)

<span data-ttu-id="922c9-180">会社のアプリをインストールするには、最初に **[設定]** &gt; **[セキュリティ]** の順に選択し、**[不明なソース]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="922c9-180">Before you try to install company apps, go to **Settings** &gt; **Security**, and turn on **Unknown sources**.</span></span> <span data-ttu-id="922c9-181">アプリをインストールする前に、このオプションをオンにしない場合、次のメッセージが表示されます。インストールがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="922c9-181">If you don't turn on this option before you try to install apps, you'll see the following message: "Install blocked.</span></span> <span data-ttu-id="922c9-182">セキュリティ上の理由から、デバイスは不明のソースから取得したアプリのインストールをブロックするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="922c9-182">For security reasons, your device is set to block installations of apps obtained from unknown sources."</span></span> <span data-ttu-id="922c9-183">エラー ダイアログ ボックスの **[設定]** をタップすると、**[不明なソース]** オプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="922c9-183">You can tap **Settings** on the error dialog box to go to the **Unknown sources** option.</span></span>

> [!Note]
> <span data-ttu-id="922c9-184">組織で通信費管理ソフトウェアを使用している場合は、デバイスの登録を完了する前にいくつかの追加手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="922c9-184">If your organization is using telecom expense management software, you will have an additional few steps to complete before your device is fully enrolled.</span></span> <span data-ttu-id="922c9-185">詳細については、[こちら](enroll-your-device-with-telecom-expense-management-android.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="922c9-185">Find out more [here](enroll-your-device-with-telecom-expense-management-android.md).</span></span>

<span data-ttu-id="922c9-186">Intune にデバイスを登録している最中にエラーが表示された場合は、[会社のサポートに登録に関するエラーを送信](send-enrollment-errors-to-your-it-admin-android.md)できます。</span><span class="sxs-lookup"><span data-stu-id="922c9-186">If you get an error while you try to enroll your device in Intune, you can [send enrollment errors to your company support](send-enrollment-errors-to-your-it-admin-android.md).</span></span>

<span data-ttu-id="922c9-187">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="922c9-187">Still need help?</span></span> <span data-ttu-id="922c9-188">会社のサポートに問い合わせるか (連絡先情報については[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください)、または <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android チーム</a>にご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="922c9-188">Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
