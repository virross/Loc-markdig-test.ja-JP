---
title: "Intune の登録オプション"
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: 22efa23e989ed949d22c3c25b2ea4d37559b0a25
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enrollment-options-for-intune"></a><span data-ttu-id="20840-102">Intune の登録オプション</span><span class="sxs-lookup"><span data-stu-id="20840-102">Enrollment options for Intune</span></span>

<span data-ttu-id="20840-103">Intune 管理者は、ユーザーのためにデバイスを登録して Intune の機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="20840-103">As an Intune admin, you can configure device enrollment to help users and enable Intune capabilities.</span></span>  <span data-ttu-id="20840-104">Intune には次の登録オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20840-104">Intune includes the following enrollment options:</span></span>

## <a name="terms-and-conditions"></a><span data-ttu-id="20840-105">Intune の登録および会社アクセスに関する使用条件</span><span class="sxs-lookup"><span data-stu-id="20840-105">Terms and conditions</span></span>

<span data-ttu-id="20840-106">ユーザーが会社の使用条件に同意しないと、ポータル サイトで自分のデバイスの登録や会社のアプリや電子メールなどのリソースへのアクセスができないという要件を設定できます。</span><span class="sxs-lookup"><span data-stu-id="20840-106">You can require that users accept your company's terms and conditions before they can use the Company Portal to enroll their devices and access resources like company apps and email.</span></span> <span data-ttu-id="20840-107">使用条件の構成は任意です。</span><span class="sxs-lookup"><span data-stu-id="20840-107">Configuration of terms and conditions is optional.</span></span> <span data-ttu-id="20840-108">[使用条件](terms-and-conditions-create.md)について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-108">Learn more about [terms and conditions](terms-and-conditions-create.md).</span></span>

## <a name="enrollment-restrictions"></a><span data-ttu-id="20840-109">登録制限</span><span class="sxs-lookup"><span data-stu-id="20840-109">Enrollment restrictions</span></span>

<span data-ttu-id="20840-110">次の条件でデバイスの登録を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="20840-110">You can choose to restrict device enrollment by:</span></span>
- <span data-ttu-id="20840-111">デバイスのプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="20840-111">Device platform</span></span>
- <span data-ttu-id="20840-112">ユーザーごとのデバイスの数</span><span class="sxs-lookup"><span data-stu-id="20840-112">Number of devices per user</span></span>
- <span data-ttu-id="20840-113">個人デバイスのブロック</span><span class="sxs-lookup"><span data-stu-id="20840-113">Block personal devices</span></span>

<span data-ttu-id="20840-114">[登録の制限](enrollment-restrictions-set.md)について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-114">Learn more about [enrollment restrictions](enrollment-restrictions-set.md).</span></span>

## <a name="enable-apple-device-enrollment"></a><span data-ttu-id="20840-115">Apple のデバイス登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="20840-115">Enable Apple device enrollment</span></span>

<span data-ttu-id="20840-116">iOS および macOS デバイスの登録には、MDM プッシュ証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="20840-116">An MDM push certificate is required for iOS and macOS device enrollment.</span></span> <span data-ttu-id="20840-117">[MDM プッシュ証明書](apple-mdm-push-certificate-get.md)について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-117">Learn more about [MDM push certificates](apple-mdm-push-certificate-get.md).</span></span>

## <a name="corporate-identifiers"></a><span data-ttu-id="20840-118">企業 ID</span><span class="sxs-lookup"><span data-stu-id="20840-118">Corporate identifiers</span></span>

<span data-ttu-id="20840-119">International Mobile Equipment Identifier (IMEI) 番号とシリアル番号を一覧表示して、会社が所有するデバイスを識別できます。</span><span class="sxs-lookup"><span data-stu-id="20840-119">You can list international mobile equipment identifier (IMEI) numbers and serial numbers to identify corporate-owned devices.</span></span> <span data-ttu-id="20840-120">[企業 ID](corporate-identifiers-add.md) について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-120">Learn more about [corporate identifiers](corporate-identifiers-add.md).</span></span>
## <a name="multi-factor-authentication"></a><span data-ttu-id="20840-121">Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="20840-121">Multi-factor authentication</span></span>

<span data-ttu-id="20840-122">ユーザーがデバイスを登録するとき、スマートフォン、PIN、生体認証データなど、追加の検証方法を使用するようにユーザーに要求できます。</span><span class="sxs-lookup"><span data-stu-id="20840-122">You can require users to use an additional verification method, such as a phone, PIN or biometric data, when they enroll a device.</span></span> <span data-ttu-id="20840-123">多要素認証については[こちら](multi-factor-authentication.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-123">Learn more about [multi-factor authentication](multi-factor-authentication.md).</span></span>

## <a name="device-enrollment-manager"></a><span data-ttu-id="20840-124">デバイス登録マネージャー</span><span class="sxs-lookup"><span data-stu-id="20840-124">Device enrollment manager</span></span>
<span data-ttu-id="20840-125">ユーザーをデバイス登録マネージャーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="20840-125">You can make users device enrollment managers.</span></span>  <span data-ttu-id="20840-126">DEM ユーザーは、単一のユーザー アカウントで多数のモバイル デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="20840-126">DEM users can enroll large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="20840-127">デバイス登録マネージャー (DEM) アカウントは、最大で 1,000 台のデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="20840-127">The device enrollment manager (DEM) account can enroll up to 1,000 devices.</span></span> <span data-ttu-id="20840-128">[デバイス登録マネージャー](device-enrollment-manager-enroll.md)について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-128">Learn more about [device enrollment managers](device-enrollment-manager-enroll.md).</span></span>

## <a name="device-categories"></a><span data-ttu-id="20840-129">デバイス カテゴリ</span><span class="sxs-lookup"><span data-stu-id="20840-129">Device categories</span></span>

<span data-ttu-id="20840-130">デバイス カテゴリを使うと、定義したカテゴリに基づいてデバイスをグループに自動的に追加できます。</span><span class="sxs-lookup"><span data-stu-id="20840-130">You can use device categories to automatically add devices to groups based on categories that you define.</span></span> <span data-ttu-id="20840-131">デバイスをグループに整理すると、デバイスを管理しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="20840-131">Organizing devices into groups makes it easier for you to manage those devices.</span></span> <span data-ttu-id="20840-132">[デバイス カテゴリ](device-group-mapping.md)について詳しくはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20840-132">Learn more about [device categories](device-group-mapping.md).</span></span>
