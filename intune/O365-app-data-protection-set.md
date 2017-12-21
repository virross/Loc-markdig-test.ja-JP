---
title: "Intune で Office 365 アプリの基本的なデータ管理を設定する"
titlesuffix: Azure portal
description: "Office 365 アプリの管理ウィザードのサポート ドキュメント。\""
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6aa850a61ab578d7dfebe2c76531ab9271e501cd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps"></a><span data-ttu-id="ca685-103">管理対象の Office 365 アプリの基本的な保護に関するユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ca685-103">How your users will experience basic protection on managed Office 365 apps</span></span>

<span data-ttu-id="ca685-104">**Manage Office 365 apps (Office 365 アプリの管理)** ウィザードでは、各デバイス プラットフォームのアプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca685-104">The **Manage Office 365 apps** wizard creates an app protection policy for each device platform.</span></span>

<span data-ttu-id="ca685-105">このウィザードでは、次のポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ca685-105">The wizard turns on the following policies:</span></span>

<span data-ttu-id="ca685-106">**iOS**</span><span class="sxs-lookup"><span data-stu-id="ca685-106">**iOS**</span></span>
* <span data-ttu-id="ca685-107">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="ca685-107">Encrypt app data</span></span>

<span data-ttu-id="ca685-108">**Android**</span><span class="sxs-lookup"><span data-stu-id="ca685-108">**Android**</span></span>
* <span data-ttu-id="ca685-109">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="ca685-109">Encrypt app data</span></span>
* <span data-ttu-id="ca685-110">[アクセスには簡易暗証番号が必要]</span><span class="sxs-lookup"><span data-stu-id="ca685-110">Require simple PIN for access</span></span>

<span data-ttu-id="ca685-111">これらのポリシーにより、Office 365 アプリを管理し、必要に応じて Office アプリからの仕事のデータをワイプできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ca685-111">These policies ensure that you can manage the Office 365 apps, giving you the ability to wipe work data from the Office apps when you need to.</span></span> <span data-ttu-id="ca685-112">また、仕事のデータを暗号化し、PIN を入力しないと Office 365 アプリでデータを表示できないようにすることで、デバイスを紛失したり盗まれたりした場合の基本的な保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-112">They also ensure basic protection in case a device gets lost or stolen by ensuring that your work data is encrypted and that a PIN must be entered to view the data in the Office 365 apps.</span></span>


<span data-ttu-id="ca685-113">この記事では、例として OneDrive for Business を使用して、Intune で管理されているアプリケーションでのユーザー エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ca685-113">This article uses OneDrive for Business as the example to demonstrate the user’s experience on an application managed by Intune.</span></span>


>[!NOTE]
><span data-ttu-id="ca685-114">個人用デバイスの場合は、通常、エンドユーザーがアプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ca685-114">On a personal device, typically the end user would download the app.</span></span> <span data-ttu-id="ca685-115">デバイスがモバイル デバイス管理 (MDM) ソリューションで管理されている場合は、管理者がアプリをデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="ca685-115">If the device is managed by a mobile device management (MDM) solution, you can deploy the app to the device.</span></span>

## <a name="user-experience-on-an-ios-device"></a><span data-ttu-id="ca685-116">iOS デバイスでのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ca685-116">User experience on an iOS device</span></span>

1. <span data-ttu-id="ca685-117">OneDrive for Business アプリを起動し、サインイン ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca685-117">Start the OneDrive for Business app to open the sign-in page.</span></span>  <br/> ![iOS の OneDrive サインイン画面の画像](./media/onedrive-ios-sign-in.png)
2. <span data-ttu-id="ca685-119">自分の作業アカウントのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca685-119">Type your work account user name.</span></span> <span data-ttu-id="ca685-120">Office 365 認証ページにリダイレクトされたら、作業用の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca685-120">You are redirected to the Office 365 authentication page to enter your work credentials.</span></span> <br/> ![Office 365 サインイン ページの画像](./media/o365-sign-in-ios.png)
3. <span data-ttu-id="ca685-122">Azure Active Directory によって資格情報が正常に認証されると、アプリ保護ポリシーが適用され、OneDrive for Business アプリを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ca685-122">After your credentials are successfully authenticated by Azure Active Directory, the app protection polices are applied, and you will be asked to restart the OneDrive for Business app.</span></span>  <br/>![iOS の再起動を求めるメッセージの画像](./media/ios-restart-prompt.png)    
  > [!NOTE]
  > <span data-ttu-id="ca685-124">再起動を求めるメッセージは、Intune に登録されていないデバイスにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-124">The restart required message is displayed only on devices that are not enrolled in Intune.</span></span>


4. <span data-ttu-id="ca685-125">OneDrive for Business アプリを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ca685-125">Re-start the OneDrive for Business app.</span></span> <span data-ttu-id="ca685-126">アプリ保護ポリシーが有効になっている状態でアプリが起動すると、デバイスの PIN を設定するように求められます (デバイスで PIN をまだ構成していない場合)。</span><span class="sxs-lookup"><span data-stu-id="ca685-126">The app starts with the app protection policies turned on and you are prompted to set a PIN for the device (if you do not have a PIN configured for the device yet).</span></span> <br/> ![PIN を作成するように求めるメッセージの画像](./media/pin-prompt-ios.png)    
  > [!NOTE]
  > <span data-ttu-id="ca685-128">ほとんどのユーザーには、このメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca685-128">Most of your users won't see this prompt.</span></span> <span data-ttu-id="ca685-129">iOS デバイスで PIN を有効にしていないユーザーにのみこのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-129">Only users who haven't enabled a PIN on their iOS device will see this prompt.</span></span>


5. <span data-ttu-id="ca685-130">PIN を設定して確認すると、OneDrive for Business アプリに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ca685-130">Once you set the PIN and confirm it, return to the OneDrive for Business app.</span></span> <span data-ttu-id="ca685-131">IT 管理者が OneDrive の仕事のデータを保護していることを伝える 1 回限りの通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-131">You will see a one-time notice that your IT administrator is now protecting work data in OneDrive.</span></span> <br/> ![IT 管理者からの 1 回限りの通知の画像](./media/one-time-notice.png)
6. <span data-ttu-id="ca685-133">この通知をクリックして、OneDrive for Business のファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca685-133">Click past this notice to access the files on your OneDrive for Business.</span></span> <br/> ![iOS デバイスでの OneDrive ファイルの画像](./media/onedrive-files-ios.png) <br/>

>[!NOTE]
><span data-ttu-id="ca685-135">展開済みのポリシーを変更すると、次回アプリを開いたときにその変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-135">When you change a deployed policy, the changes will be applied next time you open the app.</span></span>


## <a name="user-experience-on-an-android-device"></a><span data-ttu-id="ca685-136">Android デバイスでのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ca685-136">User experience on an Android device</span></span>

1. <span data-ttu-id="ca685-137">OneDrive for Business アプリを起動し、サインイン ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca685-137">Start the OneDrive for Business app to open the sign-in page.</span></span>  <br/> ![OneDrive アプリのようこそ画面の画像](./media/onedrive-android-welcome.png)
2. <span data-ttu-id="ca685-139">自分の作業アカウントのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca685-139">Type your work account user name.</span></span> <span data-ttu-id="ca685-140">Office 365 認証ページにリダイレクトされたら、作業用の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca685-140">You are redirected to the Office 365 authentication page to enter your work credentials.</span></span> <br/> ![Android での O365 サインインの画像](./media/o365-sign-in-android.png)
3. <span data-ttu-id="ca685-142">Azure Active Directory によって資格情報が正常に認証されると、まだポータル サイト アプリがデバイスにインストールされていない場合はインストールするよう指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-142">After your credentials are successfully authenticated by Azure Active Directory, you will see a message instructing you to install the Company Portal app, if it is not already installed on the device.</span></span> <span data-ttu-id="ca685-143">**[ストアにアクセス]** をタップして、続行します。</span><span class="sxs-lookup"><span data-stu-id="ca685-143">Tap on **Go to store** to proceed.</span></span> <br/> <span data-ttu-id="ca685-144">![ポータル サイト アプリを入手する際のメッセージの画像](./media/get-company-portal-android.png)</span><span class="sxs-lookup"><span data-stu-id="ca685-144">![Image of message to get the Company Portal app](./media/get-company-portal-android.png)</span></span> <br/><span data-ttu-id="ca685-145">ポータル サイト アプリが電話に既にインストールされている場合は、OneDrive for Business アプリが自動的に起動し、文末脚注にスキップできます。</span><span class="sxs-lookup"><span data-stu-id="ca685-145">If you already have the Company Portal app installed on your phone, the OneDrive for Business app will automatically start and you can skip to the end note.</span></span>    
  > [!IMPORTANT]
  > <span data-ttu-id="ca685-146">Office アプリをアプリ保護ポリシーで管理するように設定すると、Android では、エンド ユーザーが電子メールやドキュメントを実際に読むのにポータル サイト アプリを開いたり、ポータル サイト アプリにサインインしたりする必要がない場合でも、デバイスのユーザーは会社のメールやドキュメントにアクセスするためにポータル サイト アプリをインストールする**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="ca685-146">On Android, once you set up Office apps to be managed by an app protection policy, the device user **must** install the Company Portal app to access work emails and documents, even though the end user doesn't need to open or sign into the app to actually read emails or documents.</span></span>

4. <span data-ttu-id="ca685-147">Google Play ストアが開かれるので、そこからポータル サイト アプリをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="ca685-147">You are now in the Google Play store where you can download and install the Company Portal app.</span></span> <span data-ttu-id="ca685-148">ポータル サイト アプリを使うと、データを安全に保護できます。</span><span class="sxs-lookup"><span data-stu-id="ca685-148">The app helps keep the data secure and protected.</span></span> <br/> ![Google Play ストアでのアプリの画像](./media/google-play-get-app-android.png)
5. <span data-ttu-id="ca685-150">アプリのインストールが完了したら、**[同意する]** を選択して使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="ca685-150">After you have completed the app installation, choose **Accept** to accept the terms.</span></span> <span data-ttu-id="ca685-151">OneDrive for Business アプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="ca685-151">The OneDrive for Business app will automatically start.</span></span>


>[!NOTE]
><span data-ttu-id="ca685-152">IT 管理者が PIN の設定を要求している場合、OneDrive for Business を次に開いたときに、PIN の設定を求められます。</span><span class="sxs-lookup"><span data-stu-id="ca685-152">The next time you open OneDrive for Business, you may be asked to set a PIN if your IT requires one.</span></span> <span data-ttu-id="ca685-153">PIN を設定して確認すると、OneDrive for Business を利用できます。</span><span class="sxs-lookup"><span data-stu-id="ca685-153">After you set and confirm the PIN, you can continue on to OneDrive for Business.</span></span>

![PIN の入力を求めるメッセージの画像](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a><span data-ttu-id="ca685-155">このウィザードではどのようなポリシーが設定されますか。</span><span class="sxs-lookup"><span data-stu-id="ca685-155">What policies does this wizard set?</span></span>
|     |       | |
|----|--------|-|
|<span data-ttu-id="ca685-156">**名前**</span><span class="sxs-lookup"><span data-stu-id="ca685-156">**Name**</span></span>|<span data-ttu-id="ca685-157">Office 365 アプリの管理</span><span class="sxs-lookup"><span data-stu-id="ca685-157">Manage Office 365 apps</span></span>| |
| <span data-ttu-id="ca685-158">**説明**</span><span class="sxs-lookup"><span data-stu-id="ca685-158">**Description**</span></span>|<span data-ttu-id="ca685-159">Manage Office 365 apps (Office 365 アプリの管理) ウィザードで作成されました</span><span class="sxs-lookup"><span data-stu-id="ca685-159">Created by Manage Office 365 apps wizard</span></span>| |
| |  | |
| <span data-ttu-id="ca685-160">**設定の名前**</span><span class="sxs-lookup"><span data-stu-id="ca685-160">**Setting name**</span></span> |<span data-ttu-id="ca685-161">**iOS ポリシーの値**</span><span class="sxs-lookup"><span data-stu-id="ca685-161">**iOS policy value**</span></span> | <span data-ttu-id="ca685-162">**Android ポリシーの値**</span><span class="sxs-lookup"><span data-stu-id="ca685-162">**Android policy value**</span></span> |
|<span data-ttu-id="ca685-163">[iTunes と iCloud でのバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="ca685-163">Prevent iTunes and iCloud backups</span></span>| <span data-ttu-id="ca685-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-164">No</span></span> | <span data-ttu-id="ca685-165">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-165">N/A</span></span> |
|<span data-ttu-id="ca685-166">[Android でのバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="ca685-166">Prevent Android backups</span></span> |<span data-ttu-id="ca685-167">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-167">N/A</span></span> | <span data-ttu-id="ca685-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-168">No</span></span>|
|<span data-ttu-id="ca685-169">[アプリで他のアプリへのデータ転送を許可する]</span><span class="sxs-lookup"><span data-stu-id="ca685-169">Allow app to transfer data to other apps</span></span> | <span data-ttu-id="ca685-170">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-170">All apps</span></span> | <span data-ttu-id="ca685-171">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-171">All apps</span></span>|
|<span data-ttu-id="ca685-172">[アプリで他のアプリからのデータの受信を許可する]</span><span class="sxs-lookup"><span data-stu-id="ca685-172">Allow app to receive data from other apps</span></span>| <span data-ttu-id="ca685-173">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-173">All apps</span></span> | <span data-ttu-id="ca685-174">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-174">All apps</span></span>|
|<span data-ttu-id="ca685-175">[名前を付けて保存] を禁止する</span><span class="sxs-lookup"><span data-stu-id="ca685-175">Prevent "Save As"</span></span> | <span data-ttu-id="ca685-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-176">No</span></span> | <span data-ttu-id="ca685-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-177">No</span></span>|
|<span data-ttu-id="ca685-178">他のアプリとの間で切り取り、コピー、貼り付けを制限する</span><span class="sxs-lookup"><span data-stu-id="ca685-178">Restrict cut, copy, and paste with other apps</span></span> | <span data-ttu-id="ca685-179">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-179">Any app</span></span> | <span data-ttu-id="ca685-180">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="ca685-180">Any app</span></span> |
|<span data-ttu-id="ca685-181">[Web コンテンツを会社の管理対象ブラウザーで表示するように制限する]</span><span class="sxs-lookup"><span data-stu-id="ca685-181">Restrict web content to display in a corporate managed browser</span></span> | <span data-ttu-id="ca685-182">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-182">No</span></span>| <span data-ttu-id="ca685-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-183">No</span></span>|
|<span data-ttu-id="ca685-184">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="ca685-184">Encrypt app data</span></span> | <span data-ttu-id="ca685-185">デバイスがロックされている場合</span><span class="sxs-lookup"><span data-stu-id="ca685-185">When device is locked</span></span> | <span data-ttu-id="ca685-186">[はい]</span><span class="sxs-lookup"><span data-stu-id="ca685-186">Yes</span></span>|
|<span data-ttu-id="ca685-187">連絡先の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="ca685-187">Disable contacts sync</span></span> | <span data-ttu-id="ca685-188">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-188">No</span></span>| <span data-ttu-id="ca685-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-189">No</span></span>|
|<span data-ttu-id="ca685-190">印刷を無効にする</span><span class="sxs-lookup"><span data-stu-id="ca685-190">Disable printing</span></span> | <span data-ttu-id="ca685-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-191">No</span></span> | <span data-ttu-id="ca685-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-192">No</span></span>|
|<span data-ttu-id="ca685-193">アクセスのために PIN を要求する</span><span class="sxs-lookup"><span data-stu-id="ca685-193">Require PIN for access</span></span> | <span data-ttu-id="ca685-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-194">No</span></span> | <span data-ttu-id="ca685-195">[はい]</span><span class="sxs-lookup"><span data-stu-id="ca685-195">Yes</span></span>|
|<span data-ttu-id="ca685-196">[暗証番号をリセットするまでの試行数]</span><span class="sxs-lookup"><span data-stu-id="ca685-196">Number of attempts before PIN reset</span></span> | <span data-ttu-id="ca685-197">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-197">N/A</span></span> |<span data-ttu-id="ca685-198">5</span><span class="sxs-lookup"><span data-stu-id="ca685-198">5</span></span>|
|<span data-ttu-id="ca685-199">単純な PIN を許可する</span><span class="sxs-lookup"><span data-stu-id="ca685-199">Allow simple PIN</span></span> | <span data-ttu-id="ca685-200">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-200">N/A</span></span> |<span data-ttu-id="ca685-201">Yes</span><span class="sxs-lookup"><span data-stu-id="ca685-201">Yes</span></span>|
|<span data-ttu-id="ca685-202">PIN の長さ</span><span class="sxs-lookup"><span data-stu-id="ca685-202">PIN length</span></span> | <span data-ttu-id="ca685-203">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-203">N/A</span></span> | <span data-ttu-id="ca685-204">4</span><span class="sxs-lookup"><span data-stu-id="ca685-204">4</span></span>|
|<span data-ttu-id="ca685-205">PIN の代わりに指紋を要求する</span><span class="sxs-lookup"><span data-stu-id="ca685-205">Allow fingerprint instead of PIN</span></span> | <span data-ttu-id="ca685-206">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-206">N/A</span></span> | <span data-ttu-id="ca685-207">[はい]</span><span class="sxs-lookup"><span data-stu-id="ca685-207">Yes</span></span> |
|<span data-ttu-id="ca685-208">[アクセスには会社の資格情報が必要]</span><span class="sxs-lookup"><span data-stu-id="ca685-208">Require corporate credentials for access</span></span> | <span data-ttu-id="ca685-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-209">No</span></span> | <span data-ttu-id="ca685-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-210">No</span></span>|
|<span data-ttu-id="ca685-211">[脱獄またはルート化されたデバイスで管理対象アプリが実行されないようにブロックする]</span><span class="sxs-lookup"><span data-stu-id="ca685-211">Block managed apps from running on jailbroken or rooted devices</span></span> | <span data-ttu-id="ca685-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-212">No</span></span> | <span data-ttu-id="ca685-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-213">No</span></span>|
|<span data-ttu-id="ca685-214">(分数) 後に、アクセス要件を再確認する - タイムアウト</span><span class="sxs-lookup"><span data-stu-id="ca685-214">Recheck the access requirements after (minutes) - Timeout</span></span> | <span data-ttu-id="ca685-215">30</span><span class="sxs-lookup"><span data-stu-id="ca685-215">30</span></span> | <span data-ttu-id="ca685-216">30</span><span class="sxs-lookup"><span data-stu-id="ca685-216">30</span></span>|
|<span data-ttu-id="ca685-217">(分数) 後に、アクセス要件を再確認する - オフラインの猶予期間</span><span class="sxs-lookup"><span data-stu-id="ca685-217">Recheck the access requirements after (minutes) - Offline grace period</span></span> | <span data-ttu-id="ca685-218">720</span><span class="sxs-lookup"><span data-stu-id="ca685-218">720</span></span> |<span data-ttu-id="ca685-219">720</span><span class="sxs-lookup"><span data-stu-id="ca685-219">720</span></span>|
|<span data-ttu-id="ca685-220">アプリのデータがワイプされるまでのオフライン期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="ca685-220">Offline interval (days) before app data is wiped</span></span> | <span data-ttu-id="ca685-221">90</span><span class="sxs-lookup"><span data-stu-id="ca685-221">90</span></span> | <span data-ttu-id="ca685-222">90</span><span class="sxs-lookup"><span data-stu-id="ca685-222">90</span></span>|
|<span data-ttu-id="ca685-223">スクリーン キャプチャをブロックする (Android デバイスのみ)</span><span class="sxs-lookup"><span data-stu-id="ca685-223">Block screen capture (Android devices only)</span></span> | <span data-ttu-id="ca685-224">N/A</span><span class="sxs-lookup"><span data-stu-id="ca685-224">N/A</span></span> | <span data-ttu-id="ca685-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="ca685-225">No</span></span> |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a><span data-ttu-id="ca685-226">Android デバイスでのみアプリの PIN ポリシーが構成されるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="ca685-226">Why is an app PIN policy only configured for Android devices?</span></span>
<span data-ttu-id="ca685-227">iOS と Android で暗号化の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="ca685-227">Encryption works differently on iOS and Android.</span></span>

<span data-ttu-id="ca685-228">iOS の場合、Intune アプリ保護ポリシーに関連付けられているアプリでは、データはオペレーティング システムによって提供されるデバイス レベルの暗号化を使用して、格納中に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-228">On iOS, for apps that are associated with an Intune app protection policy, data is encrypted at rest through device-level encryption provided by the operating system.</span></span> <span data-ttu-id="ca685-229">そのため、アプリ暗号化ポリシーを有効にすると、デバイスの PIN を設定し、仕事のデータにアクセスする際に入力するようユーザーに自動的に要求します。</span><span class="sxs-lookup"><span data-stu-id="ca685-229">So, when you turn on the app encryption policy, you are automatically also requiring the user to have and enter a device PIN to access work data.</span></span> <span data-ttu-id="ca685-230">デバイスでデバイスの PIN をまだ構成していないユーザーは、デバイスの PIN を作成するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="ca685-230">Users who do not already have a device PIN configured on the device will be prompted to create a device PIN.</span></span>

<span data-ttu-id="ca685-231">Android の場合、Intune アプリ保護ポリシーに関連付けられているアプリでは、ファイル I/O タスク中にデータが同期的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-231">On Android, for apps that are associated with an Intune app protection policy, data is encrypted synchronously during file I/O tasks.</span></span> <span data-ttu-id="ca685-232">デバイス ストレージ上のコンテンツは常に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ca685-232">Content on the device storage is always encrypted.</span></span> <span data-ttu-id="ca685-233">MDM で管理されていないデバイスの場合、アプリ保護ポリシーでデバイスの PIN の要件を強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca685-233">On devices that are not MDM-managed, app protection policy cannot force the requirement of a device PIN.</span></span> <span data-ttu-id="ca685-234">仕事のデータにアクセスする際に PIN を使用するようユーザーに求めるには、ウィザードでアプリの PIN ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca685-234">To ensure that users are required to use some PIN To access work data, the wizard enables the app PIN policy.</span></span>

<span data-ttu-id="ca685-235">これらのポリシー設定は、組織の要件に合わせていつでも編集できます。</span><span class="sxs-lookup"><span data-stu-id="ca685-235">You can always edit these policy settings to meet your organization's requirements.</span></span>

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a><span data-ttu-id="ca685-236">ウィザードで作成したポリシーを表示および編集するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="ca685-236">How can I view and edit the policies created by the wizard?</span></span>
<span data-ttu-id="ca685-237">これらのポリシーや、Intune Azure Portal で作成したポリシーを表示または更新するには、ダッシュボードで **[アプリの管理]**  >  **[アプリ保護ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca685-237">To see or update these policies, or any policies you create in the Intune Azure portal, from the dashboard, choose **Manage apps** > **App Protection Policies**.</span></span> <span data-ttu-id="ca685-238">右側にポリシーの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="ca685-238">The list of policies will open to the right.</span></span> <span data-ttu-id="ca685-239">設定を表示および編集するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca685-239">Choose the policy you want to view to see and edit the settings.</span></span> <br/>
<span data-ttu-id="ca685-240">![ポリシーを表示するユーザー インターフェイスのパスの画像](./media/image-for-faq.png)</span><span class="sxs-lookup"><span data-stu-id="ca685-240">![Image of user interface path to view policies](./media/image-for-faq.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca685-241">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ca685-241">Next steps</span></span>
<span data-ttu-id="ca685-242">アプリ保護ポリシーの詳細については、[こちら](https://docs.microsoft.comapp-protection-policy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca685-242">Learn more about [app protection polices](https://docs.microsoft.comapp-protection-policy.md).</span></span>
