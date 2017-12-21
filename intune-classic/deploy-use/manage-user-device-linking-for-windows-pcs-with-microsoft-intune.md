---
title: "Windows PC に対するユーザー デバイスの関連付けを管理する"
description: "Intune で管理された Windows PC にユーザーを関連付ける方法を説明します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de995840eb33c165824d2fccd135377ea6c7ad56
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-user-device-linking-for-windows-pcs"></a><span data-ttu-id="b567f-103">Windows PC に対するユーザー デバイスの関連付けを管理する</span><span class="sxs-lookup"><span data-stu-id="b567f-103">Manage user-device linking for Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b567f-104">このトピックの情報は、Intune ソフトウェア クライアントを使用して PC として管理している Windows デスクトップにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b567f-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span> 

<span data-ttu-id="b567f-105">ユーザーにソフトウェアを展開する前に、ユーザーを PC に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b567f-105">Before you can deploy software to a user, you must link the user to a PC.</span></span> <span data-ttu-id="b567f-106">1 人のユーザーを複数の PC に関連付けることができますが、1 台の PC に関連付けられるユーザーは 1 人だけです。</span><span class="sxs-lookup"><span data-stu-id="b567f-106">You can link a user to multiple PCs, but each PC can be linked to only one user.</span></span> <span data-ttu-id="b567f-107">ユーザーは、ポータル サイトを使用して Intune で登録したすべての PC に自動的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b567f-107">Users are automatically linked to any PCs that they enroll in Intune by using the company portal.</span></span>

<span data-ttu-id="b567f-108">PC にユーザーを関連付けるには:</span><span class="sxs-lookup"><span data-stu-id="b567f-108">To link a user to a PC:</span></span>

1.  <span data-ttu-id="b567f-109">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** (または、ユーザーに関連付ける PC が含まれる別のグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-109">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to link to a user).</span></span>

2.  <span data-ttu-id="b567f-110">ユーザーを関連付ける PC を選択して、**[ユーザーの関連付け]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-110">Select the PC that you want to link a user, and then choose **Link User**.</span></span>

    <span data-ttu-id="b567f-111">**[ユーザーの関連付け]** ダイアログ ボックスには、関連付けることができるユーザーの表示名とユーザー ID、および現在関連付けられている PC の台数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b567f-111">The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of PCs to which each user is currently linked.</span></span> <span data-ttu-id="b567f-112">選択した PC に既にユーザーが関連付けられている場合は、そのユーザーの名前とユーザー ID が **[現在のユーザー]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b567f-112">If a user is already linked to the selected PC, that user’s name and user ID are displayed under **Current user**.</span></span> <span data-ttu-id="b567f-113">PC がどのユーザーにも関連付けられていない場合、**[現在のユーザー]** の下に **[ユーザーなし]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b567f-113">If the PC is not linked to any user, **No User** appears under **Current User**.</span></span>

3.  <span data-ttu-id="b567f-114">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b567f-114">Do one of the following:</span></span>

    -   <span data-ttu-id="b567f-115">PC と現在のユーザーの関連付けをそのままにするには、**[キャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-115">To leave the PC linked to its current user, if there is one, choose **Cancel**.</span></span>

    -   <span data-ttu-id="b567f-116">現在のユーザーとの関連付けを削除する (存在する場合) には、**[リンクの削除]**&gt; **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-116">To remove the link to the current user, if there is one, choose **Remove link **&gt; **OK**.</span></span>

    -   <span data-ttu-id="b567f-117">PC を新しいユーザーに関連付けるには、**[すべてのユーザー]** の一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-117">To link the PC to a new user, in the **All users** list, select a user.</span></span> <span data-ttu-id="b567f-118">選択したユーザーのデータが正しいことを確認して、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b567f-118">Confirm that the user data is correct, and then choose **OK**.</span></span>

> [!TIP]
> <span data-ttu-id="b567f-119">エンド ユーザーが各自の PC に関連付けをするのを抑制する場合は、**[Microsoft Intune エージェントの設定]** ポリシーの **[ユーザーによる各自のコンピューターへの関連付けを制限する]** オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b567f-119">If you want to restrict end users ability to link themselves to PCs, enable the option **Restrict users' ability to link themselves to PCs** in the **Microsoft Intune Agent Settings** policy.</span></span>

### <a name="see-also"></a><span data-ttu-id="b567f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b567f-120">See also</span></span>

[<span data-ttu-id="b567f-121">Intune ソフトウェア クライアントを使用した一般的な Windows PC 管理タスク</span><span class="sxs-lookup"><span data-stu-id="b567f-121">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)