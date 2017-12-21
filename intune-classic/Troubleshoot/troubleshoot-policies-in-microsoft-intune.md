---
title: "ポリシーに関するトラブルシューティング"
description: "ポリシー構成に関する問題のトラブルシューティングを行います。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a8f042496137887be16e13dd9564ebc9ba736389
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="troubleshoot-policies-in-microsoft-intune"></a><span data-ttu-id="150a6-103">Microsoft Intune のポリシーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="150a6-103">Troubleshoot policies in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="150a6-104">Intune ポリシーの展開と管理に関して問題がある場合は、ここから始めてください。</span><span class="sxs-lookup"><span data-stu-id="150a6-104">If you are having problems deploying and managing Intune policies, start here.</span></span> <span data-ttu-id="150a6-105">このトピックでは、発生する可能性がある一般的な問題とその解決策が示されています。</span><span class="sxs-lookup"><span data-stu-id="150a6-105">This topic contains some common problems you might encounter together with solutions.</span></span>

## <a name="general-issues"></a><span data-ttu-id="150a6-106">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="150a6-106">General Issues</span></span>

### <a name="was-a-deployed-policy-applied-to-the-device"></a><span data-ttu-id="150a6-107">展開したポリシーはデバイスに適用されていますか。</span><span class="sxs-lookup"><span data-stu-id="150a6-107">Was a deployed policy applied to the device?</span></span>
<span data-ttu-id="150a6-108">**問題:** ポリシーが正しく適用されているかどうかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="150a6-108">**Issue:** You are unsure if a policy was correctly applied.</span></span>

<span data-ttu-id="150a6-109">Intune の管理コンソールでは、すべてのデバイスの **[デバイスのプロパティ]**の下に [ポリシー] タブがあります。</span><span class="sxs-lookup"><span data-stu-id="150a6-109">In the Intune admin console every device has a policy tab under **Device Properties**.</span></span> <span data-ttu-id="150a6-110">各ポリシーには、 **[想定値]** と **[状態]**があります。</span><span class="sxs-lookup"><span data-stu-id="150a6-110">Each policy has an **Intended Value** and a **Status**.</span></span> <span data-ttu-id="150a6-111">[想定値] は、ポリシーを割り当てるときに実現しようとした内容です。</span><span class="sxs-lookup"><span data-stu-id="150a6-111">The intended value is what you meant to achieve when assigning the policy.</span></span> <span data-ttu-id="150a6-112">[状態] は、ハードウェアとオペレーティング システムの制限事項と要件だけでなく、デバイスに適用されるすべてのポリシーがまとめて考慮されたときに実際に適用される内容です。</span><span class="sxs-lookup"><span data-stu-id="150a6-112">The status is what is actually applied when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together.</span></span> <span data-ttu-id="150a6-113">表示される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="150a6-113">Possible statuses are:</span></span>

-   <span data-ttu-id="150a6-114">**[準拠]**: デバイスがポリシーを受信しており、設定に準拠していることをサービスに報告します。</span><span class="sxs-lookup"><span data-stu-id="150a6-114">**Conforms**: the device has received the policy and reports to the service that it  conforms to the setting.</span></span>

-   <span data-ttu-id="150a6-115">**[該当なし]**: ポリシー設定は適用されません。</span><span class="sxs-lookup"><span data-stu-id="150a6-115">**Not applicable**: The policy setting is not applicable.</span></span> <span data-ttu-id="150a6-116">たとえば、iOS デバイス用の電子メール設定は、Android デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="150a6-116">For example,  email settings for iOS devices would not apply to an Android device.</span></span>

-   <span data-ttu-id="150a6-117">**[保留]**: ポリシーはデバイスに送信されましたが、サービスに状態を報告していません。</span><span class="sxs-lookup"><span data-stu-id="150a6-117">**Pending**: The policy was sent to the device, but hasn't reported status to the service.</span></span> <span data-ttu-id="150a6-118">たとえば、Android での暗号化では、ユーザーが暗号化を有効にする必要があるため、保留になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="150a6-118">For example, encryption on Android requires the user to enable encryption and might therefore be pending.</span></span>

<span data-ttu-id="150a6-119">下のスクリーンショットには、わかりやすい 2 つの例が示されています。</span><span class="sxs-lookup"><span data-stu-id="150a6-119">In the screenshot below you can see two clear examples:</span></span>

-   <span data-ttu-id="150a6-120">**[想定値]** 列に表示されているように、 **[単純なパスワードを使用する]**が **[はい]** に設定されていますが、その **[状態]** は **[該当なし]**になっています。</span><span class="sxs-lookup"><span data-stu-id="150a6-120">**Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**.</span></span> <span data-ttu-id="150a6-121">これは、Android デバイスでは単純なパスワードがサポートされていないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="150a6-121">This is because simple passwords are not supported for Android devices.</span></span>

-   <span data-ttu-id="150a6-122">同様に、拡張ポリシー アイテム **[iOS デバイス用電子メールの設定]** は、このデバイスが Android デバイスであるため適用されません。</span><span class="sxs-lookup"><span data-stu-id="150a6-122">Similarly, the expanded policy item **Email settings for iOS devices** is not applied to this device, as it is an Android device.</span></span>

![Intune のデバイス ポリシー](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> <span data-ttu-id="150a6-124">制限レベルが異なる 2 つのポリシーを同じデバイスまたはユーザーに適用すると、より厳しい方のポリシーが実際に適用されます。</span><span class="sxs-lookup"><span data-stu-id="150a6-124">Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.</span></span>


## <a name="issues-with-enrolled-devices"></a><span data-ttu-id="150a6-125">登録済みデバイスに関する問題</span><span class="sxs-lookup"><span data-stu-id="150a6-125">Issues with enrolled devices</span></span>

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a><span data-ttu-id="150a6-126">アラート: アクセス ルールを Exchange に保存できませんでした</span><span class="sxs-lookup"><span data-stu-id="150a6-126">Alert: Saving of Access Rules to Exchange has Failed</span></span>
<span data-ttu-id="150a6-127">**問題**: 管理コンソールが「 **アクセス ルールを Exchange に保存できませんでした** 」のアラートを受信する。</span><span class="sxs-lookup"><span data-stu-id="150a6-127">**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.</span></span>

<span data-ttu-id="150a6-128">管理コンソールの下の [Exchange On-Premises ポリシー] ワークスペースでポリシーを作成し、O365 を使用すると、構成されたポリシー設定が Intune によって適用されません。</span><span class="sxs-lookup"><span data-stu-id="150a6-128">If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, the configured policy settings are not enforced by Intune.</span></span> <span data-ttu-id="150a6-129">アラートのポリシー ソースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="150a6-129">Note the policy source from the alert.</span></span>  <span data-ttu-id="150a6-130">[Exchange On-Premises ポリシー] ワークスペースで古いルールを削除します。古いルールはオンプレミスの Exchange で使用する、Intune 内のグローバルの Exchange ルールであり、O365 に関連しないためです。</span><span class="sxs-lookup"><span data-stu-id="150a6-130">Under the Exchange On-premises Policy workspace delete the legacy rules, as these are Global Exchange rules within Intune for on-premises Exchange, and are not relevant to O365.</span></span> <span data-ttu-id="150a6-131">次に、O365 の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="150a6-131">Then, create new policy for O365.</span></span>

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a><span data-ttu-id="150a6-132">各種登録済みデバイスのセキュリティ ポリシーを変更できない</span><span class="sxs-lookup"><span data-stu-id="150a6-132">Cannot change security policy for various enrolled devices</span></span>
<span data-ttu-id="150a6-133">Windows Phone デバイスから、MDM または EAS で設定されたセキュリティ ポリシーのセキュリティを一度設定した後に緩くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="150a6-133">Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them.</span></span> <span data-ttu-id="150a6-134">たとえば、 **パスワードの最小文字数** を 8 に設定し、次に 4 に減らしてみます。</span><span class="sxs-lookup"><span data-stu-id="150a6-134">For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4.</span></span> <span data-ttu-id="150a6-135">より制限の厳しいポリシーが、デバイスに既に適用されています。</span><span class="sxs-lookup"><span data-stu-id="150a6-135">The more restrictive policy has already been applied to the device.</span></span>

<span data-ttu-id="150a6-136">ポリシーを安全度の低い値に変更する場合、デバイスのプラットフォームによっては、セキュリティ ポリシーをリセットしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="150a6-136">Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies.</span></span>
<span data-ttu-id="150a6-137">たとえば、Windows で、デスクトップを右からスワイプして、**[チャーム]** バーを開き、**[設定]** &gt; **[コントロール パネル]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="150a6-137">For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.</span></span>  <span data-ttu-id="150a6-138">**[ユーザー アカウント]** アプレットを選択します。</span><span class="sxs-lookup"><span data-stu-id="150a6-138">Select the **User Accounts** applet.</span></span>
<span data-ttu-id="150a6-139">左側のナビゲーション メニューの下部に、 **[セキュリティ ポリシーのリセット]** リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="150a6-139">In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom.</span></span> <span data-ttu-id="150a6-140">このリンクを選択し、**[ポリシーのリセット]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="150a6-140">Choose it and then choose the **Reset Policies** button.</span></span>
<span data-ttu-id="150a6-141">Android、Windows Phone 8.1 以降、iOS などのその他の MDM デバイスでは、制限の緩いポリシーを適用するにはいったんデバイスを削除して、サービスに再登録しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="150a6-141">Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive policy.</span></span>

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a><span data-ttu-id="150a6-142">Intune ソフトウェア クライアントを実行している PC に関する問題</span><span class="sxs-lookup"><span data-stu-id="150a6-142">Issues with PCs that run the Intune software client</span></span>

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a><span data-ttu-id="150a6-143">policyplatform.log に記録される Microsoft Intune ポリシー関連エラー</span><span class="sxs-lookup"><span data-stu-id="150a6-143">Microsoft Intune policy-related errors in policyplatform.log</span></span>
<span data-ttu-id="150a6-144">Intune ソフトウェア クライアントで管理されている Windows PC では、policyplatform.log ファイルに記録されるポリシー エラーの原因としては、デバイスの Windows ユーザー アカウント制御 (UAC) で既定値以外が設定されていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="150a6-144">For Windows PCs managed with the Intune software client, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device.</span></span> <span data-ttu-id="150a6-145">いくつかの既定値以外の UAC 設定は、Microsoft Intune クライアントのインストールやポリシーの実行に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="150a6-145">Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.</span></span>

#### <a name="to-resolve-uac-issues"></a><span data-ttu-id="150a6-146">UAC の問題を解決するには</span><span class="sxs-lookup"><span data-stu-id="150a6-146">To resolve UAC issues</span></span>

1.  <span data-ttu-id="150a6-147">「[Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)」 (Microsoft Intune の管理からデバイスを削除する) の説明に従って、コンピューターを削除します。</span><span class="sxs-lookup"><span data-stu-id="150a6-147">Retire the computer, as described in [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).</span></span>

2.  <span data-ttu-id="150a6-148">クライアント ソフトウェアが削除されるまで、20 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="150a6-148">Wait 20 minutes for the client software to be removed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="150a6-149">[プログラムと機能] からクライアントを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="150a6-149">Do not attempt to remove the client from Programs and Features.</span></span>

3.  <span data-ttu-id="150a6-150">スタート メニューで「**UAC**」と入力して、[ユーザー アカウント制御の設定] を開きます。</span><span class="sxs-lookup"><span data-stu-id="150a6-150">On the start menu type **UAC** to open the User Account Control settings.</span></span>

4.  <span data-ttu-id="150a6-151">通知のスライダーを既定の設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="150a6-151">Move  the notification slider to the default setting.</span></span>

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a><span data-ttu-id="150a6-152">エラー: コンピューター 0x80041013 から値を取得できません</span><span class="sxs-lookup"><span data-stu-id="150a6-152">ERROR: Cannot obtain the value from the computer, 0x80041013</span></span>
<span data-ttu-id="150a6-153">これは、ローカル システム上の時間が 5 分以上ずれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="150a6-153">This can occur if the time on the local system is out of sync by five minutes or more.</span></span> <span data-ttu-id="150a6-154">ローカル コンピューターの時間が同期されていない場合は、タイム スタンプが有効でないためセキュリティで保護されたトランザクションが失敗します。</span><span class="sxs-lookup"><span data-stu-id="150a6-154">If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.</span></span>

<span data-ttu-id="150a6-155">この問題を解決するには、ローカル システムの時間をインターネット時間か、またはネットワーク上のドメイン コントローラーに設定された時間にできる限り近い時間に設定します。</span><span class="sxs-lookup"><span data-stu-id="150a6-155">To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.</span></span>








### <a name="next-steps"></a><span data-ttu-id="150a6-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="150a6-156">Next steps</span></span>
<span data-ttu-id="150a6-157">このトラブルシューティング情報を使っても問題が解決しない場合は、「[Microsoft Intune のサポートを受ける方法](how-to-get-support-for-microsoft-intune.md)」の説明に従って Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="150a6-157">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
