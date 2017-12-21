---
title: "Intune ソフトウェア クライアントを実行する PC のソフトウェア ライセンス契約を管理する"
description: "Intune では、Microsoft ボリューム ライセンス契約で購入したソフトウェアと、他の方法で購入したソフトウェアのライセンス契約情報を追加および管理できます。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4cf9c062c99895c5ff59f6b8fee44d20284eaa46
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-license-agreements-for-windows-pc-software-in-microsoft-intune"></a><span data-ttu-id="ff9e3-103">Microsoft Intune で Windows PC ソフトウェアのライセンス契約を管理する</span><span class="sxs-lookup"><span data-stu-id="ff9e3-103">Manage license agreements for Windows PC software in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ff9e3-104">Microsoft Intune を使用すると、Microsoft ボリューム ライセンス契約で購入したソフトウェアのライセンス契約情報を追加して管理できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-104">Microsoft Intune lets you add and manage license agreement information for software that was purchased through Microsoft Volume Licensing agreements.</span></span> <span data-ttu-id="ff9e3-105">他の方法で購入した Microsoft のソフトウェアまたは Microsoft 以外のソフトウェアも管理できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-105">You can also do this for Microsoft or non-Microsoft software that was purchased by other means.</span></span> <span data-ttu-id="ff9e3-106">この情報は論理的なグループに分類できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-106">You can organize this information into logical groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff9e3-107">この機能は便宜を目的として提供されるものであり、正確性は保証されません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-107">This feature is provided for convenience only, and accuracy is not guaranteed.</span></span> <span data-ttu-id="ff9e3-108">この機能で得られた情報だけを頼りに、Microsoft ボリューム ライセンス契約に準拠しているかどうかを判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-108">You should not rely on it to confirm compliance with Microsoft Volume Licensing agreements.</span></span> <span data-ttu-id="ff9e3-109">Microsoft がこのソフトウェア ライセンスの管理機能で収集されたデータを使って、Microsoft との契約にお客様が違反しているかどうかを調査することはありません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-109">Microsoft will not use any data gathered to investigate potential violations of, or compliance with, license agreements you may have with us.</span></span>
>
> <span data-ttu-id="ff9e3-110">Intune に追加したライセンスが、ライセンス契約やソフトウェアを使用する権利に影響を及ぼすことはありません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-110">Licenses you add to Intune do not affect your license agreements or entitlements to use your software.</span></span> <span data-ttu-id="ff9e3-111">たとえば、Intune からライセンス/契約番号ペアを削除した場合、Microsoft と交わしたライセンス契約が削除されたり、無効化されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-111">For example, if you delete a license/agreement pair from Intune, you do not delete or nullify license agreements that exist between you and Microsoft.</span></span>

<span data-ttu-id="ff9e3-112">Intune 管理者コンソールの **[ライセンス]** ワークスペースでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-112">In the **Licenses** workspace of the Intune administration console, you can:</span></span>

-   <span data-ttu-id="ff9e3-113">Microsoft ボリューム ライセンス契約を追加および編集します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-113">Add and edit Microsoft Volume Licensing agreements.</span></span>

-   <span data-ttu-id="ff9e3-114">その他のソフトウェア ライセンス契約を追加および編集します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-114">Add and edit other software licensing agreements.</span></span>

-   <span data-ttu-id="ff9e3-115">ライセンスとグループを管理します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-115">Manage licenses and groups.</span></span>

-   <span data-ttu-id="ff9e3-116">Intune によってボリューム ライセンス サービス センター (VLSC) から取得された権利の情報を、管理されている Windows PC で Intune によって検出された Microsoft ソフトウェアのインベントリと比較します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-116">Compare the entitlement information that Intune retrieves from the Volume Licensing Service Center (VLSC) to the inventory of Microsoft software that Intune detects on your managed Windows PCs.</span></span>

<span data-ttu-id="ff9e3-117">さらに、ソフトウェア タイトルのインストール数とライセンス数を示すレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-117">Additionally, you can generate reports that show installation and license counts for software titles.</span></span> <span data-ttu-id="ff9e3-118">ライセンス レポートは、Microsoft と Microsoft 以外のソフトウェア タイトルの全体的なライセンス状況を把握するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-118">License reports can help you assess your complete license position for Microsoft software and non-Microsoft software titles.</span></span>

> [!TIP]
> <span data-ttu-id="ff9e3-119">Intune Windows PC クライアントを使用して少なくとも 1 つの Windows PC を管理するまで、**[ライセンス]** ワークスペースは管理コンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-119">The **Licenses** workspace is not displayed in the administrator console until you are managing at least one Windows PC with the Intune Windows PC client.</span></span>

## <a name="add-microsoft-volume-licensing-agreements"></a><span data-ttu-id="ff9e3-120">Microsoft ボリューム ライセンス契約の追加</span><span class="sxs-lookup"><span data-stu-id="ff9e3-120">Add Microsoft Volume Licensing agreements</span></span>
<span data-ttu-id="ff9e3-121">Intune のボリューム ライセンス契約には、Microsoft ボリューム ライセンス契約で購入したソフトウェアのライセンス情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-121">Intune Volume Licensing agreements provide license information for software that was purchased through Microsoft Volume Licensing agreements.</span></span> <span data-ttu-id="ff9e3-122">契約番号の一致するペアを入力して、Microsoft ボリューム ライセンス契約を Intune に追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-122">You can add Microsoft Volume Licensing agreements to Intune by providing matched pairs of agreement numbers.</span></span> <span data-ttu-id="ff9e3-123">契約番号または認証番号は、正しいライセンス番号または登録番号と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-123">The agreement or authorization numbers must be matched to the correct license or enrollment numbers.</span></span> <span data-ttu-id="ff9e3-124">契約番号のペアは、ライセンス契約を購入するときに、 [ボリューム ライセンス サービス センター (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842)から入手します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-124">Agreement number pairs are obtained when you purchase your license agreements from the [Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842).</span></span>

1.  <span data-ttu-id="ff9e3-125">[Microsoft Intune 管理者コンソール](https://account.manage.microsoft.com/admin/default.aspx)で、**[ライセンス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-125">In the [Microsoft Intune administrator console](https://account.manage.microsoft.com/admin/default.aspx), choose **Licenses**.</span></span>

2.  <span data-ttu-id="ff9e3-126">**[契約の追加]** ページで、 **[契約の種類の選択]**の **[ボリューム ライセンス契約]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-126">On the **Add Agreements** page, under **Choose Agreement Type**, select **Volume Licensing agreement**.</span></span>

3.  <span data-ttu-id="ff9e3-127">**[契約の詳細の追加]** セクションで、ファイルをアップロードするか、または詳細を手動で追加するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-127">In the **Add Agreement Details** section, choose whether you want to upload a file, or manually add the details.</span></span>

    -   <span data-ttu-id="ff9e3-128">**契約の詳細が含まれている CSV ファイルをアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-128">**Upload a CSV file that contains agreement details**.</span></span> <span data-ttu-id="ff9e3-129">**[参照]** を選択し、アップロードする CSV ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-129">Choose **Browse** and select the CSV file you want to upload.</span></span>

        -   <span data-ttu-id="ff9e3-130">2 列または 3 列から成る (契約番号ペアのみの場合は 2 列、契約番号ペアにフレンドリ名を追加する場合は 3 列)。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-130">The file can contain either two or three columns; two for agreement pairs alone, or three if you want to add a friendly name for each agreement pair.</span></span>

        -   <span data-ttu-id="ff9e3-131">契約番号ペアの合計文字数は 16 ASCII 文字以下。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-131">The total number of characters in an agreement number pair cannot exceed 16 ASCII characters.</span></span>

        -   <span data-ttu-id="ff9e3-132">使用できるのは ASCII 文字のみ。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-132">Only ASCII characters are supported.</span></span>

        -   <span data-ttu-id="ff9e3-133">契約名に以下の文字は使用できない: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-133">The following characters are not allowed in the agreement name: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**.</span></span> <span data-ttu-id="ff9e3-134">スペースは使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-134">Spaces are allowed in the name.</span></span>

        -   <span data-ttu-id="ff9e3-135">ファイル名は、128 文字以下でなければならない。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-135">The file name must be no more than 128 characters in length.</span></span>

        -   <span data-ttu-id="ff9e3-136">契約ファイルには、契約番号ペアが 1 ～ 5,000 組含まれていなければならない。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-136">The file must contain at least one agreement pair, and cannot contain more than 5,000 agreement pairs.</span></span>

        <span data-ttu-id="ff9e3-137">**ファイルの形式**</span><span class="sxs-lookup"><span data-stu-id="ff9e3-137">**Format for the file**</span></span>

        <span data-ttu-id="ff9e3-138">このファイルを作成するには、プレーンテキスト ドキュメントに契約番号ペアを追加します。VLSC に登録した組織の種類に応じて、次のいずれかの形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-138">You can create this file by adding your agreement pairs to a plain text document in one of the following formats, depending on the organization type that you have registered with the VLSC.</span></span> <span data-ttu-id="ff9e3-139">契約番号ペアは 1 行に 1 つずつ入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-139">Specify one agreement number pair per line.</span></span>

        -   <span data-ttu-id="ff9e3-140">**オープン バリュー ライセンス:** *契約番号*、*契約番号 (再入力)*、*契約名*</span><span class="sxs-lookup"><span data-stu-id="ff9e3-140">**Open Value customers:** *Agreement number*, *repeat agreement number*, *agreement name*</span></span>

        -   <span data-ttu-id="ff9e3-141">**オープン ライセンス:** *認証番号*、*関連ライセンス番号*、*契約名*</span><span class="sxs-lookup"><span data-stu-id="ff9e3-141">**Open customers:** *Authorization number*, *related license number*, *agreement name*</span></span>

        -   <span data-ttu-id="ff9e3-142">**セレクト/エンタープライズ ライセンス:** *契約番号*、*関連登録番号*、*契約名*</span><span class="sxs-lookup"><span data-stu-id="ff9e3-142">**Select and Enterprise customers:** *Agreement number*, *related enrollment number*, *agreement name*</span></span>

        <span data-ttu-id="ff9e3-143">**[契約の追加]** フォームで新しい契約を追加するときに、このファイルを指定するようにというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-143">The **Add Agreements** form prompts you to browse for this file when you add a new agreement.</span></span>

        <span data-ttu-id="ff9e3-144">次に、オープン バリュー ライセンスの .csv ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-144">The following is an example of .csv file content for an Open Value customer.</span></span>

        `01-07001, 01-07001, Office agreements`

    -   <span data-ttu-id="ff9e3-145">**契約の詳細を手動で追加**します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-145">**Manually add agreement details**.</span></span> <span data-ttu-id="ff9e3-146">次の情報を入力し、**[認証/契約番号]** ボックスと **[ライセンス/登録/カスタマー番号]** ボックスに契約番号ペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-146">Provide the following information, and then type the agreement number pairs in the **Authorization/Agreement number** and **License/Enrollment/Customer number** boxes.</span></span> <span data-ttu-id="ff9e3-147">両方の番号を入力し終わったら **[ペアの追加]** アイコンを選択して番号を保存してから、必要に応じて、新しいペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-147">After you type both numbers, choose the **Add pair** icon to save your numbers, and then optionally add a new pair.</span></span>

        -   <span data-ttu-id="ff9e3-148">**契約名** - 契約の一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-148">**Agreement name** - Specify a unique name for the agreement.</span></span>

            <span data-ttu-id="ff9e3-149">契約名の最大文字数は、256 文字です。ただし、**~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /** は使えません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-149">The agreement name can have a maximum of 256 characters, and cannot contain the following characters: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**.</span></span> <span data-ttu-id="ff9e3-150">スペースは使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-150">Spaces are allowed in the name.</span></span>

        -   <span data-ttu-id="ff9e3-151">**認証/契約番号** - ライセンス ペアの認証/契約番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-151">**Authorization/Agreement number** - Enter the authorization/agreement number of the license pair.</span></span>

        -   <span data-ttu-id="ff9e3-152">**ライセンス/登録/カスタマー番号** - ライセンス ペアのライセンス/登録/カスタマー番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-152">**License/Enrollment/Customer number** - Enter the license/enrollment/customer number of the license pair.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ff9e3-153">契約番号ペアを複数入力した場合は、Intune によって指定した名前の契約が 1 つだけ作成され、追加したすべてのペアがこの契約に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-153">If you add several agreement number pairs, Intune creates one agreement with the name that you specify, and all pairs that you added are a part of this agreement.</span></span>

    <span data-ttu-id="ff9e3-154">別の契約番号ペアを追加するには **[+]** を選択し、入力済みの契約番号ペアを削除するには **[-]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-154">You can choose **+** to add another agreement number pair, or **-** to remove an agreement number pair you have already entered.</span></span>

4.  <span data-ttu-id="ff9e3-155">**[ライセンス グループの追加]** 領域で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-155">In the **Select License Group** area, do one of the following:</span></span>

    -   <span data-ttu-id="ff9e3-156">**[割り当てられていない契約] グループに契約を追加**します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-156">**Add the agreements to the Unassigned Agreements group**.</span></span> <span data-ttu-id="ff9e3-157">ライセンス グループに新しい契約を追加しない場合は、これを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-157">Select this if you do not want to add the new agreements to a license group.</span></span>

    -   <span data-ttu-id="ff9e3-158">**新しいライセンス グループに契約を追加**します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-158">**Add the agreements to a new license group**.</span></span> <span data-ttu-id="ff9e3-159">新しいライセンス グループの一意な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-159">Provide a name for the new license group.</span></span>

    -   <span data-ttu-id="ff9e3-160">**契約を既存のライセンス グループに追加**します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-160">**Add the agreements to an existing license group**.</span></span> <span data-ttu-id="ff9e3-161">**[グループ名]** 一覧で、契約を追加するライセンス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-161">In the **Group name** list, select the license group to which you want to add the agreements.</span></span>

5.  <span data-ttu-id="ff9e3-162">**[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-162">Choose **OK**.</span></span>

<span data-ttu-id="ff9e3-163">**[すべての契約]** 一覧が表示されます。Intune が Microsoft VLSC に接続され、指定した契約番号ペアが検証されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-163">The **All Agreements** view is displayed, and Intune connects to the Microsoft VLSC to validate the agreement number pairs that you provided.</span></span>

<span data-ttu-id="ff9e3-164">Intune でライセンス契約を追加した後で、ボリューム ライセンス情報を更新するには、**[ライセンスの概要]** ページで **[今すぐ最新の情報に更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-164">To update the volume license information after you have added license agreements in Intune, in the **Licenses Overview** page, choose **Refresh Now**.</span></span> <span data-ttu-id="ff9e3-165">現在のライセンス情報が [Microsoft ボリューム ライセンス サービス センター (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842)から取得されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-165">This action retrieves the current license information from the [Microsoft Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff9e3-166">ボリューム ライセンス情報を更新するまで、 **[ライセンスの概要]** ページの契約一覧と権利の情報に異なる情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-166">Until you refresh the volume licensing information, you may see different information in the agreements list and the entitlement information on the **Agreements Overview** page.</span></span>

<span data-ttu-id="ff9e3-167">ボリューム ライセンス情報を更新したら、ライセンス情報を、 **[アプリ]** ワークスペースにある検出された Microsoft ソフトウェアと比較できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-167">After you refresh the volume license information, you can compare the license information to your detected Microsoft software in the **Apps** workspace.</span></span> <span data-ttu-id="ff9e3-168">次のようなライセンス レポートを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-168">You can also run the following license reports:</span></span>

-   <span data-ttu-id="ff9e3-169">**ライセンスの購入レポート** - 選択したライセンス グループ内のライセンス済みソフトウェアが表示されます。ライセンス契約の範囲との差異を確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-169">**License Purchase Reports** - Lets you view the licensed software in license groups you select to help you find gaps in coverage.</span></span>

-   <span data-ttu-id="ff9e3-170">**ライセンスのインストール レポート** - ライセンス契約の範囲が十分であるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-170">**License Installation Reports** - Helps you determine if you have sufficient license agreement coverage.</span></span>

> [!NOTE]
> <span data-ttu-id="ff9e3-171">どの Microsoft ボリューム ライセンス契約の **[製品タイトル]** にも **[利用不可]**と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-171">The **Product Title** displayed for all Microsoft Volume License agreements is **Not available**.</span></span>

## <a name="add-and-edit-other-software-licensing-agreements"></a><span data-ttu-id="ff9e3-172">その他のソフトウェア ライセンス契約の追加と編集</span><span class="sxs-lookup"><span data-stu-id="ff9e3-172">Add and edit other software licensing agreements</span></span>
<span data-ttu-id="ff9e3-173">Intune には、Microsoft ボリューム ライセンス契約に加えて、他の種類のライセンス契約を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-173">You can also add other types of license agreements to Intune in addition to Microsoft Volume Licensing agreements.</span></span> <span data-ttu-id="ff9e3-174">これらのライセンスには、販売店から購入した Microsoft 以外のソフトウェアと Microsoft のソフトウェアのライセンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-174">These agreements can include non-Microsoft software, or Microsoft software that was purchased through a retailer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff9e3-175">契約を追加するには、事前に少なくとも 1 台の Windows PC が Intune に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-175">You must have at least one Windows PC enrolled in Intune before you can add an agreement.</span></span>  <span data-ttu-id="ff9e3-176">また、少なくとも 1 台の登録済みコンピューターが、ライセンス契約の追加に使用するライセンス対象ソフトウェア パッケージをアップロードしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-176">In addition, at least one enrolled computer must have uploaded a licensable software package that you want to use to add a license agreement.</span></span>

### <a name="to-add-other-software-agreements"></a><span data-ttu-id="ff9e3-177">他のソフトウェア ライセンス契約を追加するには</span><span class="sxs-lookup"><span data-stu-id="ff9e3-177">To add other software agreements</span></span>

1.  <span data-ttu-id="ff9e3-178">[Microsoft Intune 管理者コンソール](https://account.manage.microsoft.com/admin/default.aspx)で、**[ライセンス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-178">In the [Microsoft Intune administrator console](https://account.manage.microsoft.com/admin/default.aspx), choose **Licenses**.</span></span>

2.  <span data-ttu-id="ff9e3-179">**[その他のソフトウェア ライセンス契約]** セクションの **[契約の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-179">Choose **Add Agreements** in the **Other Software Licensing Agreements** section.</span></span>

3.  <span data-ttu-id="ff9e3-180">**[契約の追加]** ページで、 **[契約の種類の選択]** セクションの **[その他のソフトウェア ライセンス契約]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-180">Select **Other software licensing agreement** in the **Choose Agreement Type** section of the **Add Agreements** page.</span></span>

4.  <span data-ttu-id="ff9e3-181">**[契約の詳細の追加]** 領域で、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-181">In the **Add Agreement Details** area, specify the following:</span></span>

    -   <span data-ttu-id="ff9e3-182">**Agreement name** (必須):</span><span class="sxs-lookup"><span data-stu-id="ff9e3-182">**Agreement name** (required).</span></span> <span data-ttu-id="ff9e3-183">契約名の最大文字数は、256 文字です。ただし、**~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /** は使えません。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-183">The agreement name can have a maximum of 256 characters, and cannot contain the following characters: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**.</span></span> <span data-ttu-id="ff9e3-184">スペースは使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-184">Spaces are allowed in the name.</span></span>

    -   <span data-ttu-id="ff9e3-185">**発行者** (必須):</span><span class="sxs-lookup"><span data-stu-id="ff9e3-185">**Publisher** (required).</span></span> <span data-ttu-id="ff9e3-186">発行者の名前を入力し始めると、入力した文字を含む名前がすべて検索されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-186">When you start to type a publisher name, the service retrieves all publisher names that contain the letters that you type.</span></span> <span data-ttu-id="ff9e3-187">たとえば、「soft」と入力すると、"Microsoft" や "Microsoft Research" など、名前に "soft" という文字を含む発行者名がすべて検索されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-187">For example, if you type “soft,” the service retrieves all publisher names that contain “soft” as part of the name, such as “Microsoft” and “Microsoft Research.”</span></span> <span data-ttu-id="ff9e3-188">発行者名は、ソフトウェア アセット カタログから取得されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-188">The publisher names are retrieved from the Software Asset Catalog.</span></span> <span data-ttu-id="ff9e3-189">必ず、発行者を選択してから、製品タイトルを入力してください。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-189">You must select the publisher before you can enter the product title.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="ff9e3-190">追加する会社が、この一覧に表示されていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-190">The company that you want to add might not appear in this list.</span></span> <span data-ttu-id="ff9e3-191">ソフトウェア アセット カタログに既に存在する会社のソフトウェア ライセンス契約のみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-191">You can only add software agreements for companies that are already present in the software asset catalog.</span></span> <span data-ttu-id="ff9e3-192">ただし、Microsoft では、よく知られているソフトウェア タイトルを継続的に追加しています。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-192">However, Microsoft continuously works to add the most popular software titles.</span></span> <span data-ttu-id="ff9e3-193">このリストに会社を追加したい場合は、[Intune Uservoice サイト](https://microsoftintune.uservoice.com/)から要求を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-193">If you would like to submit a request to have a company added to this list, you can do so at the [Intune Uservoice site](https://microsoftintune.uservoice.com/).</span></span>

    -   <span data-ttu-id="ff9e3-194">**製品タイトル** (必須):</span><span class="sxs-lookup"><span data-stu-id="ff9e3-194">**Product title** (required).</span></span> <span data-ttu-id="ff9e3-195">製品タイトルを入力し始めると、入力した文字を含む製品のタイトルがすべて検索されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-195">When you start to type a product title, the service retrieves all product titles that contain the letters that you type.</span></span> <span data-ttu-id="ff9e3-196">**[製品タイトル]** を指定する前に、 **[発行者]**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-196">You must specify a **Publisher** before you can specify a **Product title**.</span></span>

    -   <span data-ttu-id="ff9e3-197">**ライセンス数** (必須):</span><span class="sxs-lookup"><span data-stu-id="ff9e3-197">**License count** (required).</span></span> <span data-ttu-id="ff9e3-198">購入済みのライセンスの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-198">Enter the number of purchased licenses.</span></span>

    -   <span data-ttu-id="ff9e3-199">**ライセンス開始日**:</span><span class="sxs-lookup"><span data-stu-id="ff9e3-199">**License start date**.</span></span> <span data-ttu-id="ff9e3-200">ライセンス対象期間の開始日を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-200">Enter the start date of license coverage.</span></span>

    -   <span data-ttu-id="ff9e3-201">**ライセンス終了日**:</span><span class="sxs-lookup"><span data-stu-id="ff9e3-201">**License end date**.</span></span> <span data-ttu-id="ff9e3-202">ライセンス対象期間の終了日を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-202">Enter the end date of license coverage.</span></span>

    -   <span data-ttu-id="ff9e3-203">**契約の詳細**:</span><span class="sxs-lookup"><span data-stu-id="ff9e3-203">**Agreement details**.</span></span> <span data-ttu-id="ff9e3-204">必要に応じて、連絡先情報や登録キーなどの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-204">You can optionally specify contact information, registration keys, and other information.</span></span>

5.  <span data-ttu-id="ff9e3-205">**[ライセンス グループの追加]** 領域で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-205">In the **Select License Group** area, do one of the following:</span></span>

    -   <span data-ttu-id="ff9e3-206">新しいライセンス グループや既存のライセンス グループに新しい契約を追加しない場合は、 **[[割り当てられていない契約] グループに契約を追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-206">Select **Add the agreements to the Unassigned Agreements group** if you do not want to add the new agreements to a new or existing license group.</span></span> <span data-ttu-id="ff9e3-207">ユーザー定義のライセンス グループには、契約をいつでも追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-207">You can add the agreements to user-defined license groups at any time.</span></span>

    -   <span data-ttu-id="ff9e3-208">新しい契約を新しいライセンス グループに追加する場合は、 **[新しいライセンス グループに契約を追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-208">Select **Add the agreements to a new license group** to add the new agreements to a new license group.</span></span> <span data-ttu-id="ff9e3-209">次に、新規ライセンス グループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-209">You are prompted to provide a name for the new license group.</span></span>

    -   <span data-ttu-id="ff9e3-210">新しい契約を既存のライセンス グループに追加する場合は、 **[既存のライセンス グループに契約を追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-210">Select **Add the agreements to an existing license group** to add the new agreements to an existing license group.</span></span> <span data-ttu-id="ff9e3-211">**[グループ名]** 一覧で、契約を追加するライセンス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-211">In the **Group name** list, select the license group to which you want to add the agreements.</span></span>

6.  <span data-ttu-id="ff9e3-212">**[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-212">Choose **OK**.</span></span>

<span data-ttu-id="ff9e3-213">**[すべての契約]** 一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-213">The **All Agreements** list view is displayed.</span></span>

## <a name="manage-license-agreements"></a><span data-ttu-id="ff9e3-214">ライセンス契約の管理</span><span class="sxs-lookup"><span data-stu-id="ff9e3-214">Manage license agreements</span></span>
<span data-ttu-id="ff9e3-215">ソフトウェア ライセンス契約をライセンス グループに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-215">Software licensing agreements can be added to license groups.</span></span> <span data-ttu-id="ff9e3-216">ライセンス グループは、組織の構造に合った単位でライセンス契約をまとめるのに便利です。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-216">You can use license groups to organize your license agreements in units that are logical for your organization.</span></span> <span data-ttu-id="ff9e3-217">また、以前に作成したライセンス契約を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-217">Additionally, you can delete license agreements you previously created.</span></span>

|||
|-|-|
|<span data-ttu-id="ff9e3-218">タスク</span><span class="sxs-lookup"><span data-stu-id="ff9e3-218">Task</span></span>|<span data-ttu-id="ff9e3-219">説明</span><span class="sxs-lookup"><span data-stu-id="ff9e3-219">Details</span></span>|
|<span data-ttu-id="ff9e3-220">ライセンス グループの作成</span><span class="sxs-lookup"><span data-stu-id="ff9e3-220">Create a license group</span></span>|<span data-ttu-id="ff9e3-221">**[ライセンス]** ワークスペースの **[概要]** ページで、**[タスク]** メニューの **[ライセンス グループの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-221">On the **Overview** page of the **Licenses** workspace, choose **Create License Group** from the **Tasks** menu.</span></span> <span data-ttu-id="ff9e3-222">**注:** 合計 500 個までのライセンス グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-222">**Note:** You can create a maximum total of 500 license groups.</span></span>|
|<span data-ttu-id="ff9e3-223">ライセンス グループの名前変更</span><span class="sxs-lookup"><span data-stu-id="ff9e3-223">Rename a license group</span></span>|<span data-ttu-id="ff9e3-224">**[ライセンス]** ワークスペースで、ライセンス グループを選択し、**[タスク]** メニューの **[ライセンス グループの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-224">In the **Licenses** workspace, choose a license group, and then choose **Edit License Group** from the **Tasks** Menu.</span></span>|
|<span data-ttu-id="ff9e3-225">ライセンス グループの削除</span><span class="sxs-lookup"><span data-stu-id="ff9e3-225">Delete a license group</span></span>|<span data-ttu-id="ff9e3-226">**[ライセンス]** ワークスペースで、ライセンス グループを選択し、**[タスク]** メニューの **[ライセンス グループの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-226">In the **Licenses** workspace, choose a license group, and then choose **Delete License Group** from the **Tasks** Menu.</span></span> <span data-ttu-id="ff9e3-227">**ヒント:** 削除されたグループに含まれていたライセンスはいずれも **[割り当てられていない契約]** ライセンス グループに移されます。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-227">**Tip:** Any licenses that were in the deleted group are moved to the **Unassigned agreements** license group.</span></span>|
|<span data-ttu-id="ff9e3-228">ライセンス契約の削除</span><span class="sxs-lookup"><span data-stu-id="ff9e3-228">Delete a license agreement</span></span>|<span data-ttu-id="ff9e3-229">**[ライセンス]** ワークスペースで、契約を選択し、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-229">In the **Licenses** workspace, choose an agreement, and then choose **Delete**.</span></span> <span data-ttu-id="ff9e3-230">**ヒント:** ボリューム ライセンス契約を削除した後でライセンス情報を更新するには、**[ライセンスの概要]** ページ、または特定のライセンス グループの **[全般]** タブで、**[今すぐ最新の情報に更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9e3-230">**Tip:** After you delete Volume Licensing agreements, to update the license information, choose **Refresh Now** on the **Licenses Overview** page or on the **General** tab for a specific license group.</span></span>|
