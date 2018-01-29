---
title: "IMEI 番号を指定する"
description: "Microsoft Intune では、管理者は、モバイル デバイス プラットフォームの IMEI 番号をインポートして会社所有のモバイル デバイスを識別できます"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cdc1e1ac6147903ec6ada30e7a3b42189a228c78
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a><span data-ttu-id="21400-103">IMEI (国際移動体装置識別番号) を使って企業所有のデバイスを指定する</span><span class="sxs-lookup"><span data-stu-id="21400-103">Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="21400-104">Microsoft Intune では、管理者が IMEI (International Mobile Equipment Identity: 国際移動体装置識別番号) をモバイル デバイスのプラットフォームにインポートできます。IMEI 番号は、企業所有のモバイル デバイスを識別するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21400-104">Microsoft Intune lets admins import international mobile equipment identity (IMEI) numbers for mobile device platforms by using IMEI numbers to help identify corporate-owned mobile devices.</span></span> <span data-ttu-id="21400-105">Intune にデバイスが登録されると、デバイスの **[グループ]** > **[概要]** > **[すべてのデバイス]** に IMEI 番号がインポートされています。</span><span class="sxs-lookup"><span data-stu-id="21400-105">After devices are enrolled in Intune, you can see devices that have imported IMEI numbers under **Groups** > **Overview** > **All Devices**.</span></span> <span data-ttu-id="21400-106">**[デバイス グループ]** の一覧で、インポートされた IMEI 番号を持つデバイスは、**[所有権]** 欄に **[会社]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="21400-106">**Device group** lists devices that have imported IMEI numbers as **Corporate** in the **Ownership** column.</span></span>

1. <span data-ttu-id="21400-107">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[会社の事前登録済みデバイス]** &gt; **[IMEI (すべてのプラットフォーム) を使用]** に移動し、**[デバイスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21400-107">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate Pre-enrolled Devices** &gt; **By IMEI (All platforms)**, and then choose **Add devices…**.</span></span> <span data-ttu-id="21400-108">デバイスの追加方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="21400-108">You can add devices in two ways:</span></span>

   - <span data-ttu-id="21400-109">**シリアル番号が含まれている .csv ファイルをアップロード** – csv ファイル 1 つあたりデバイス 5,000 個または 5 MB を上限とする、2 つの列を持つヘッダーなしのコンマ区切り値のリスト (.csv) を作成します。</span><span class="sxs-lookup"><span data-stu-id="21400-109">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span> <span data-ttu-id="21400-110">詳細フィールドの上限は 128 文字です。</span><span class="sxs-lookup"><span data-stu-id="21400-110">The details field is limited to 128 characters.</span></span> 


     |                 |                           |
     |-----------------|---------------------------|
     | <span data-ttu-id="21400-111">&lt;IMEI #1&gt;</span><span class="sxs-lookup"><span data-stu-id="21400-111">&lt;IMEI #1&gt;</span></span> | <span data-ttu-id="21400-112">&lt;デバイス 1 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="21400-112">&lt;Device #1 Details&gt;</span></span> |
     | <span data-ttu-id="21400-113">&lt;IMEI #2&gt;</span><span class="sxs-lookup"><span data-stu-id="21400-113">&lt;IMEI #2&gt;</span></span> | <span data-ttu-id="21400-114">&lt;デバイス 2 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="21400-114">&lt;Device #2 Details&gt;</span></span> |

     <span data-ttu-id="21400-115">この .csv ファイルをテキスト エディターで開くと、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="21400-115">This .csv file when viewed in a text editor appears as:</span></span>

     ```
     01234567890123,device details
     02234567890123,device details
     ```

   - <span data-ttu-id="21400-116">**デバイスの詳細を手動で追加** - 最大 15 台のデバイスの IMEI 番号とデバイスの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="21400-116">**Manually add device details** - Enter the IMEI number and device details of up to 15 devices.</span></span>

   <span data-ttu-id="21400-117">*[詳細]* フィールドは管理用です。</span><span class="sxs-lookup"><span data-stu-id="21400-117">The *Details* field is for administrative use.</span></span> <span data-ttu-id="21400-118">ハードウェア ID ごとにリストされている企業所有デバイスのリストでデバイスを識別するのに役立つ詳細を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="21400-118">You can specify details to help identify the device in the list of Corporate-owned devices listed by hardware ID.</span></span> <span data-ttu-id="21400-119">この情報はデバイスには送信されませんが、Intune のコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="21400-119">This information is not sent to the device, but it will appear in the Intune console.</span></span>

2. <span data-ttu-id="21400-120">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21400-120">Choose **Next**.</span></span>
3. <span data-ttu-id="21400-121">**[デバイスの確認]** ウィンドウで、インポートされたデバイスの IMEI 番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="21400-121">On the **Review Devices** pane, you can confirm the imported device IMEI numbers.</span></span> <span data-ttu-id="21400-122">また、再インポートされている IMEI 番号の**詳細**を上書きするかどうかを決めることもできます。</span><span class="sxs-lookup"><span data-stu-id="21400-122">You can also decide whether to overwrite the **Details** for IMEI numbers that are being imported again.</span></span> <span data-ttu-id="21400-123">**[上書き]** ボックスをオフにすると、現在の詳細が保持されます。</span><span class="sxs-lookup"><span data-stu-id="21400-123">You can uncheck the **Overwrite** box to preserve the Current details.</span></span> <span data-ttu-id="21400-124">**[完了]** を選択して、IMEI 番号をインポートします。</span><span class="sxs-lookup"><span data-stu-id="21400-124">Choose **Finish** to import the IMEI numbers.</span></span>
4. <span data-ttu-id="21400-125">インポートされた IMEI 番号および説明が、**[IMEI (すべてのプラットフォーム) を使用]** の一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="21400-125">The imported IMEI numbers and descriptions are added to the **By IMEI (All platforms)** list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21400-126">Android デバイスの IMEI 番号をインポートする場合は、一部の Android デバイスが複数の IMEI 番号を所有できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="21400-126">If you are importing IMEI numbers for Android devices, be aware that some Android devices can have multiple IMEI numbers.</span></span> <span data-ttu-id="21400-127">IMEI 番号をインポートするときに、その番号がデバイスが Intune に報告した IMEI ではない場合、デバイスは会社所有のデバイスではなく個人のデバイスとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="21400-127">If you import an IMEI number but it is not the IMEI reported to Intune by the device, the device will be classifed as a personal device instead of a company-owned device.</span></span>

<span data-ttu-id="21400-128">IMEI 番号を持つデバイスを Intune に登録する (通常は、ユーザーがポータル サイト アプリをインストールし、登録プロセスを完了する) と、そのデバイスは会社所有としてタグ付けされ、**IMEI デバイス** グループに登録されたデバイスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="21400-128">When a device that has IMEI number enrolls in Intune, usually when a user installs the Company Portal app and completes the enrollment process, the device will be tagged as corporate-owned and appear as enrolled in the **IMEI Devices** group.</span></span>

>[!NOTE]
> <span data-ttu-id="21400-129">今後、組織が新しい Azure Portal に移行された場合、この機能への変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21400-129">When your organization is migrated to the new Azure portal in the near future, you will see a change to this feature.</span></span> <span data-ttu-id="21400-130">既存の Intune 管理者コンソールでは、管理者はアップロードされた CSV から関連する詳細をそのまま使用し、個々のハードウェア ID の既存の詳細を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="21400-130">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual hardware identifiers.</span></span> <span data-ttu-id="21400-131">新しい Azure Portal では、自動ですべてのハードウェア ID の詳細を上書きするか、既存の ID の新しい詳細をすべて無視することができます。</span><span class="sxs-lookup"><span data-stu-id="21400-131">In the new Azure portal, you’ll be able to automatically overwrite the details for all hardware identifiers or to ignore all new details for existing identifiers.</span></span>

<span data-ttu-id="21400-132">International Mobile Equipment Identifier の詳しい仕様については、「[3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21400-132">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>
