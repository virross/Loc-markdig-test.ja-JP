---
title: "企業 ID を Intune に追加する"
titlesuffix: Azure portal
description: "企業 ID (登録方法、IMEI 番号、シリアル番号) を Microsoft Intune に追加する方法について説明します。 \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0312c29f0c50319850de60b9c2720baa3eec69b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="identify-devices-as-corporate-owned"></a><span data-ttu-id="a9918-104">デバイスの企業所有としての識別</span><span class="sxs-lookup"><span data-stu-id="a9918-104">Identify devices as corporate-owned</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a9918-105">Intune 管理者は、会社所有のデバイスを特定することで、管理と識別の対象を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a9918-105">As an Intune admin, you can identify devices as corporate-owned to refine management and identification.</span></span> <span data-ttu-id="a9918-106">Intune は追加の管理タスクを実行して、会社所有のデバイスの完全な電話番号やアプリのインベントリなどの追加情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-106">Intune can perform additional management tasks and collect additional information such as the full phone number and an inventory of apps from corporate-owned devices.</span></span> <span data-ttu-id="a9918-107">また、デバイス制限を設定し、会社所有ではないデバイスによる登録を防止できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-107">You can also set device restrictions to block enrollment by devices that aren't corporate-owned.</span></span>

<span data-ttu-id="a9918-108">デバイスは、次の条件のいずれかに該当する場合、企業所有として識別されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-108">A device is identified as corporate-owned if any of the following conditions are true:</span></span>

- <span data-ttu-id="a9918-109">[デバイス登録マネージャー](device-enrollment-manager-enroll.md) アカウントで登録されている (すべてのプラットフォーム)</span><span class="sxs-lookup"><span data-stu-id="a9918-109">Enrolled with a [device enrollment manager](device-enrollment-manager-enroll.md) account (all platforms)</span></span>
- <span data-ttu-id="a9918-110">Apple [Device Enrollment Program](device-enrollment-program-enroll-ios.md)、[Apple School Manager](apple-school-manager-set-up-ios.md)、[Apple Configurator](apple-configurator-enroll-ios.md) (iOS のみ) で登録されている</span><span class="sxs-lookup"><span data-stu-id="a9918-110">Enrolled with the Apple [Device Enrollment Program](device-enrollment-program-enroll-ios.md), [Apple School Manager](apple-school-manager-set-up-ios.md), or [Apple Configurator](apple-configurator-enroll-ios.md) (iOS only)</span></span>
- <span data-ttu-id="a9918-111">IMEI (International Mobile Equipment Identifier/国際携帯機器識別) 番号 (IMEI 番号を持つすべてのプラットフォーム) またはシリアル番号 (iOS と Android) で、[登録前に会社所有として識別されている](#identify-corporate-owned-devices-with-imei-or-serial-number)</span><span class="sxs-lookup"><span data-stu-id="a9918-111">[Identified as corporate-owned before enrollment](#identify-corporate-owned-devices-with-imei-or-serial-number) with an international mobile equipment identifier (IMEI) numbers (all platforms with IMEI numbers) or serial number (iOS and Android)</span></span>
- <span data-ttu-id="a9918-112">Azure Active Directory または Enterprise Mobility + Security に Windows 10 Enterprise デバイスとして登録されている</span><span class="sxs-lookup"><span data-stu-id="a9918-112">Registered in Azure Active Directory or Enterprise Mobility + Security as a Windows 10 Enterprise device</span></span>
- <span data-ttu-id="a9918-113">デバイスのプロパティに、[デバイスの所有権が会社](#change-device-ownership)として表示される</span><span class="sxs-lookup"><span data-stu-id="a9918-113">The device's properties list [device ownership as corporate](#change-device-ownership)</span></span>

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a><span data-ttu-id="a9918-114">IMEI またはシリアル番号により、会社所有デバイスとして特定される</span><span class="sxs-lookup"><span data-stu-id="a9918-114">Identify corporate-owned devices with IMEI or serial number</span></span>

<span data-ttu-id="a9918-115">Intune 管理者は、IMEI 番号またはシリアル番号を記載しているコンマ区切り値 (.csv) ファイルを作成し、インポートできます。</span><span class="sxs-lookup"><span data-stu-id="a9918-115">As an Intune admin, you can create and import a comma-separated value (.csv) file that lists IMEI numbers or serial numbers.</span></span> <span data-ttu-id="a9918-116">Intune は、デバイス登録時、この識別子を使用し、デバイスの所有権を会社として指定します。</span><span class="sxs-lookup"><span data-stu-id="a9918-116">Intune uses these identifiers to specify device ownership as corporate during device enrollment.</span></span> <span data-ttu-id="a9918-117">サポートされているすべてのプラットフォームの IMEI 番号を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-117">You can declare IMEI numbers for all supported platforms.</span></span> <span data-ttu-id="a9918-118">iOS、macOS、Android デバイスのシリアル番号のみ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-118">You can only declare serial number for iOS, macOS, and Android devices.</span></span> <span data-ttu-id="a9918-119">各 IMEI またはシリアル番号の一覧には管理目的で詳細を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-119">Each IMEI or serial number can have details specified in the list for administrative purposes.</span></span>

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

<span data-ttu-id="a9918-120">Apple デバイスのシリアル番号の検索方法については、[こちら](https://support.apple.com/HT204308)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9918-120">[Learn how to find an Apple device serial number](https://support.apple.com/HT204308).</span></span><br>
<span data-ttu-id="a9918-121">Android デバイスのシリアル番号の検索方法については、[こちら](https://support.google.com/store/answer/3333000)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9918-121">[Learn how to find your Android device serial number](https://support.google.com/store/answer/3333000).</span></span>

## <a name="add-corporate-identifiers"></a><span data-ttu-id="a9918-122">企業 ID を追加する</span><span class="sxs-lookup"><span data-stu-id="a9918-122">Add corporate identifiers</span></span>
<span data-ttu-id="a9918-123">リストを作成するには、ヘッダーなしの 2 列のコンマ区切り値 (.csv) リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9918-123">To create the list, create a two-column, comma-separated value (.csv) list without a header.</span></span> <span data-ttu-id="a9918-124">IMEI またはシリアル番号を左側の列に、詳細を右側の列に追加します。</span><span class="sxs-lookup"><span data-stu-id="a9918-124">Add the IMEI or serial numbers in the left column, and the details in the right column.</span></span> <span data-ttu-id="a9918-125">1 つの .csv ファイルにインポートできるのは、1 種類の ID、IMEI、またはシリアル番号のみです。</span><span class="sxs-lookup"><span data-stu-id="a9918-125">Only one type of ID, IMEI or serial number, can be imported in a single .csv file.</span></span> <span data-ttu-id="a9918-126">詳細の上限は 128 文字です。また、管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-126">Details are limited to 128 characters and are for administrative use only.</span></span> <span data-ttu-id="a9918-127">詳細はデバイスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9918-127">Details aren't displayed on the device.</span></span> <span data-ttu-id="a9918-128">現在の上限は .csv ファイルあたり 5,000 行です。</span><span class="sxs-lookup"><span data-stu-id="a9918-128">The current limit is 5,000 rows per .csv file.</span></span>

<span data-ttu-id="a9918-129">**シリアル番号が含まれている .csv ファイルをアップロード** – csv ファイル 1 つあたりデバイス 5,000 個または 5 MB を上限とする、2 つの列を持つヘッダーなしのコンマ区切り値のリスト (.csv) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a9918-129">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span>

|||
|-|-|
|<span data-ttu-id="a9918-130">&lt;ID #1&gt;</span><span class="sxs-lookup"><span data-stu-id="a9918-130">&lt;ID #1&gt;</span></span>|<span data-ttu-id="a9918-131">&lt;デバイス 1 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="a9918-131">&lt;Device #1 Details&gt;</span></span>|
|<span data-ttu-id="a9918-132">&lt;ID #2&gt;</span><span class="sxs-lookup"><span data-stu-id="a9918-132">&lt;ID #2&gt;</span></span>|<span data-ttu-id="a9918-133">&lt;デバイス 2 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="a9918-133">&lt;Device #2 Details&gt;</span></span>|

<span data-ttu-id="a9918-134">この .csv ファイルをテキスト エディターで開くと、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-134">This .csv file when viewed in a text editor appears as:</span></span>

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> <span data-ttu-id="a9918-135">一部の Android デバイスには複数の IMEI 番号があります。</span><span class="sxs-lookup"><span data-stu-id="a9918-135">Some Android devices have multiple IMEI numbers.</span></span> <span data-ttu-id="a9918-136">Intune は、登録済みデバイスごとに 1 つの IMEI 番号のみを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a9918-136">Intune only reads one IMEI number per enrolled device.</span></span> <span data-ttu-id="a9918-137">IMEI 番号をインポートするときに、その番号が Intune にインベントリされている IMEI ではない場合、デバイスは会社所有のデバイスではなく個人のデバイスとして分類されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-137">If you import an IMEI number but it is not the IMEI inventoried by Intune, the device is classified as a personal device instead of a company-owned device.</span></span> <span data-ttu-id="a9918-138">1 台のデバイスに複数の IMEI 番号をインポートすると、インベントリされていない番号の登録状態は **[不明]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-138">If you import multiple IMEI numbers for a device, uninventoried numbers display **Unknown** for enrollment status.</span></span><br>
><span data-ttu-id="a9918-139">注: Android のシリアル番号は一意であることと存在することが保証されていません。</span><span class="sxs-lookup"><span data-stu-id="a9918-139">Also note: Android Serial numbers are not guaranteed to be unique or present.</span></span> <span data-ttu-id="a9918-140">シリアル番号が信頼できるデバイス ID であるかどうかは、デバイスの供給元にご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a9918-140">Check with your device supplier to understand if serial number is a reliable device ID.</span></span>
><span data-ttu-id="a9918-141">デバイスから Intune に報告されたシリアル番号は、Android デバイスの [設定]/[バージョン情報] メニューに表示される ID と一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9918-141">Serial numbers reported by the device to Intune might not match the displayed ID in the Android Settings/About menus on the device.</span></span> <span data-ttu-id="a9918-142">デバイスの製造元から報告されたシリアル番号の種類をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a9918-142">Verify the type of serial number reported by the device manufacturer.</span></span>

### <a name="add-a-csv-list-of-corporate-identifiers"></a><span data-ttu-id="a9918-143">企業 ID の .csv リストを追加する</span><span class="sxs-lookup"><span data-stu-id="a9918-143">Add a .csv list of corporate identifiers</span></span>

1. <span data-ttu-id="a9918-144">Azure Portal の Intune で **[デバイスの登録]** > **[業務用デバイスの ID]** の順に選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9918-144">In Intune in the Azure portal, choose **Device enrollment** > **Corporate Device Identifiers**, and then click **Add**.</span></span>

 ![[追加] ボタンが強調表示された、[業務用デバイス ID] ワークスペースのスクリーンショット。](./media/add-corp-id.png)

2. <span data-ttu-id="a9918-146">**[ID の追加]** ブレードで **[IMEI]** または **[シリアル]** の ID の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9918-146">In the **Add Identifiers** blade, specify the identifier type: **IMEI** or **Serial**.</span></span> <span data-ttu-id="a9918-147">以前にインポートした番号が **[既存の ID の詳細を上書きします]** を適用するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-147">You can specify whether previously imported numbers should **Overwrite details for existing identifiers**.</span></span>

3. <span data-ttu-id="a9918-148">フォルダー アイコンをクリックし、インポートするリストのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9918-148">Click the folder icon and specify the path to the list you want to import.</span></span> <span data-ttu-id="a9918-149">.csv ファイルに移動して、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9918-149">Navigate to the .csv file, and select **Add**.</span></span> <span data-ttu-id="a9918-150">**[更新]** をクリックすると、新しいデバイス ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-150">You can click **Refresh** to see new device identifiers.</span></span>

<span data-ttu-id="a9918-151">インポートされたデバイスが必ずしも登録されているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a9918-151">Imported devices are not necessarily enrolled.</span></span> <span data-ttu-id="a9918-152">デバイスは **[登録済み]** または**[未接続]** のどちらかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="a9918-152">Devices can have a state of either **Enrolled** or **Not contacted**.</span></span> <span data-ttu-id="a9918-153">**未接続** の場合、デバイスは Intune サービスで通信に使われていません。</span><span class="sxs-lookup"><span data-stu-id="a9918-153">**Not contacted** means that the device has never communicated in with the Intune service.</span></span>

### <a name="delete-corporate-identifiers"></a><span data-ttu-id="a9918-154">企業 ID を削除する</span><span class="sxs-lookup"><span data-stu-id="a9918-154">Delete corporate identifiers</span></span>

1. <span data-ttu-id="a9918-155">Azure Portal の Intune で **[デバイスの登録]** > **[業務用デバイスの ID]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a9918-155">In Intune in the Azure portal, choose **Device enrollment** > **Corporate Device Identifiers**.</span></span>
2. <span data-ttu-id="a9918-156">削除するデバイス識別子を選択し、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9918-156">Select the device identifiers you want to delete, and choose **Delete**.</span></span>
3. <span data-ttu-id="a9918-157">削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="a9918-157">Confirm the deletion.</span></span>

<span data-ttu-id="a9918-158">登録済みデバイスの企業識別子を削除すると、デバイスの所有権が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-158">Deleting a corporate identifier for an enrolled device does not change the device's ownership.</span></span> <span data-ttu-id="a9918-159">デバイスの所有権を変更するには、**[デバイス]** > **[すべてのデバイス]** の順に進み、デバイスを選択し、**[プロパティ]** を選択し、**[デバイスの所有者]** を変更します。</span><span class="sxs-lookup"><span data-stu-id="a9918-159">To change a device's ownership, go **Devices** > **All devices**, select the device, choose **Properties**, and change **Device ownership**.</span></span>

### <a name="imei-specifications"></a><span data-ttu-id="a9918-160">IMEI の仕様</span><span class="sxs-lookup"><span data-stu-id="a9918-160">IMEI specifications</span></span>
<span data-ttu-id="a9918-161">International Mobile Equipment Identifier の詳しい仕様については、「[3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9918-161">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>

## <a name="change-device-ownership"></a><span data-ttu-id="a9918-162">デバイス所有権を変更する</span><span class="sxs-lookup"><span data-stu-id="a9918-162">Change device ownership</span></span>

<span data-ttu-id="a9918-163">デバイスのプロパティには、Intune のデバイス レコード別の**所有権**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9918-163">Devices properties display **Ownership** for each device records in Intune.</span></span> <span data-ttu-id="a9918-164">管理者はデバイスを**個人用**または**企業所有**として指定できます。</span><span class="sxs-lookup"><span data-stu-id="a9918-164">As an admin, you can specify devices as **Personal** or **Corporate**.</span></span>

<span data-ttu-id="a9918-165">**デバイス所有権を変更するには:**</span><span class="sxs-lookup"><span data-stu-id="a9918-165">**To change device ownership:**</span></span>
1. <span data-ttu-id="a9918-166">Azure Portal の Intune で、**[デバイス]**、**[すべてのデバイス]** の順に進み、デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9918-166">In Intune in the Azure portal, go **Devices** > **All devices**, and choose the device.</span></span>
3. <span data-ttu-id="a9918-167">**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9918-167">Choose **Properties**.</span></span>
4. <span data-ttu-id="a9918-168">**[デバイスの所有権]** に **[個人]** または **[企業]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9918-168">Specify **Device ownership** as **Personal** or **Corporate**.</span></span>

  ![デバイス プロパティのスクリーンショット。デバイスのカテゴリと所有権のオプションを確認できます。](./media/device-properties.png)
