---
title: "MAM ポリシーでアプリ データを保護する"
description: "このトピックでは、モバイル アプリケーション管理ポリシーが、会社データの保護、データ損失の防止、および個人用情報と作業情報の個別管理に役立つしくみについて説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbaf7ed32d98dd8726bf8718e9f5884f4b20e7fa
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="bfdbd-103">Microsoft Intune でアプリ保護ポリシーを使用してアプリ データを保護する</span><span class="sxs-lookup"><span data-stu-id="bfdbd-103">Protect app data using app protection policies with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a><span data-ttu-id="bfdbd-104">アプリ データを保護する方法</span><span class="sxs-lookup"><span data-stu-id="bfdbd-104">How you can protect app data</span></span>
<span data-ttu-id="bfdbd-105">従業員は個人のタスクと仕事のタスクの両方にモバイル デバイスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-105">Your employees use mobile devices for both personal and work tasks.</span></span> <span data-ttu-id="bfdbd-106">従業員の生産性を維持したまま、意図的なデータ損失や意図しないデータ損失が起こらないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-106">While you're making sure your employees can be productive, you also want to prevent data loss—intentional and unintentional.</span></span>  <span data-ttu-id="bfdbd-107">さらに、会社が管理していないデバイスを使用して従業員がアクセスする会社のデータを保護できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-107">In addition, you want to have the ability to protect company data that employees access by using devices that you don't manage.</span></span>

<span data-ttu-id="bfdbd-108">Intune のアプリ保護ポリシーを使用すれば、会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-108">You can use Intune app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="bfdbd-109">Intune のアプリ保護ポリシーは**どのモバイル デバイス管理 (MDM) ソリューションからも独立して**利用できるため、デバイスをデバイス管理ソリューションに登録しているかどうかにかかわらず、MAM を利用して会社のデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-109">Because Intune App protection policies can be used **independent of any mobile device management (MDM) solution**, you can use MAM to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="bfdbd-110">**アプリレベル ポリシー**を実装するだけで、会社のリソースへのアクセスを制限し、データを IT 部門の管理範囲内に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-110">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="bfdbd-111">次のようなデバイスで実行されているアプリに対して、アプリ保護ポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-111">You can configure app protection policies for apps running on devices that are:</span></span>

-   <span data-ttu-id="bfdbd-112">**Microsoft Intune に登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-112">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate-owned devices.</span></span>

-   <span data-ttu-id="bfdbd-113">**サードパーティの MDM ソリューションに登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-113">**Enrolled in a third-party MDM solution:** The devices in this category are typically corporate-owned devices.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfdbd-114">サードパーティのモバイル アプリケーション管理ソリューションやセキュア コンテナー ソリューションでアプリ保護ポリシーを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-114">We don't recommend using app protection policies with third-party mobile application management or secure container solutions.</span></span>

-   <span data-ttu-id="bfdbd-115">**いずれの MDM ソリューションにも登録されていないデバイス:** このカテゴリに属するデバイスは、通常、Intune またはその他の MDM ソリューションで管理も登録もされていない社員所有のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-115">**Not enrolled in any MDM solution:** The devices in this category are typically employee-owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfdbd-116">Office 365 サービスに接続する Office モバイル アプリ向けのアプリ保護ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-116">You can create app protection policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="bfdbd-117">アプリ保護ポリシーは、オンプレミスの Exchange サービスや Skype for Business サービス、SharePoint サービスに接続するアプリ向けにはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-117">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

## <a name="benefits-of-using-app-protection-policies"></a><span data-ttu-id="bfdbd-118">アプリ保護ポリシーを利用した場合のメリット</span><span class="sxs-lookup"><span data-stu-id="bfdbd-118">Benefits of using app protection policies</span></span>

-   <span data-ttu-id="bfdbd-119">**アプリ レベルでの会社データの保護に役立ちます。**</span><span class="sxs-lookup"><span data-stu-id="bfdbd-119">**They help protect your company data at the app level.**</span></span> <span data-ttu-id="bfdbd-120">モバイル アプリケーション管理にはデバイス管理が必要ないため、管理対象のデバイスと管理対象ではないデバイスの両方で会社データを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-120">Because mobile application management doesn't require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="bfdbd-121">管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-121">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="bfdbd-122">**ユーザーの生産性に影響を与えることがなく、個人のコンテキストでアプリが使用される場合にはポリシーは適用されません。**</span><span class="sxs-lookup"><span data-stu-id="bfdbd-122">**User productivity is not impacted, and the policies aren't applied when you're using the app in a personal context.**</span></span> <span data-ttu-id="bfdbd-123">ポリシーは仕事のコンテキストでのみ適用されるため、個人データに影響を与えることなく会社データを保護することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-123">The policies are applied only in a work context, which gives you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="bfdbd-124">MDM をアプリ保護ポリシーと共に使用することには付加的なメリットがあります。会社は MAM を MDM ありと MDM なしの両方で同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-124">There are additional benefits to using MDM with app protection policies, and companies can use MAM with and without MDM at the same time.</span></span> <span data-ttu-id="bfdbd-125">たとえば、従業員は、会社が支給する電話に加えて個人のタブレットを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-125">For example, an employee might use a company-issued phone, as well as a personal tablet.</span></span> <span data-ttu-id="bfdbd-126">この場合、会社の電話は MDM に登録されたうえでアプリ保護ポリシーによって保護されますが、個人のデバイスはアプリ保護ポリシーのみで保護されます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-126">In this case, the company phone is enrolled in MDM and protected by app protection policies, and the personal device is protected by app protection policies only.</span></span>

- <span data-ttu-id="bfdbd-127">**MDM によりデバイスの保護を実現できます。**</span><span class="sxs-lookup"><span data-stu-id="bfdbd-127">**MDM makes sure that the device is protected.**</span></span> <span data-ttu-id="bfdbd-128">たとえば、デバイスへのアクセスに PIN を要求したり、デバイスに管理対象のアプリを展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-128">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="bfdbd-129">また、MDM ソリューションを介してデバイスにアプリを展開することにより、アプリ管理をより制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-129">You can also deploy apps to devices through your MDM solution to give you more control over app management.</span></span>

- <span data-ttu-id="bfdbd-130">**アプリ保護ポリシーによりアプリ層の保護を実現できます**。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-130">**App protection policies make sure that the app-layer protections are in place.**</span></span> <span data-ttu-id="bfdbd-131">たとえば、仕事のコンテキストでアプリを開くために PIN を要求したり、アプリ間でのデータの共有を禁止したり、会社のアプリ データを個人の記憶域に保存できないようにしたりするポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-131">For example, you can have a policy that requires a PIN to open an app in a work context, prevents data from being shared between apps, and prevents company app data from being saved to a personal storage location.</span></span>

## <a name="devices-that-support-mam"></a><span data-ttu-id="bfdbd-132">MAM をサポートするデバイス</span><span class="sxs-lookup"><span data-stu-id="bfdbd-132">Devices that support MAM</span></span>
<span data-ttu-id="bfdbd-133">現在のところ、アプリ保護ポリシーは次の OS でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-133">App protection policies are currently supported on:</span></span>
-   <span data-ttu-id="bfdbd-134">iOS 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="bfdbd-134">iOS 8.1 or later</span></span>
-   <span data-ttu-id="bfdbd-135">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="bfdbd-135">Android 4 or later</span></span>

>[!NOTE]
><span data-ttu-id="bfdbd-136">Windows デバイスに登録シナリオがなく、MAM でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-136">Windows devices are not supported in the MAM without enrollment scenario.</span></span> <span data-ttu-id="bfdbd-137">ただし、Intune で Windows 10 デバイスを登録すると、同様の機能を提供する Windows 情報保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="bfdbd-138">詳細については、「[Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)」 (Windows 情報保護 (WIP) を使用してエンタープライズ データを保護する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>


##  <a name="how-app-protection-policies-protect-app-data"></a><span data-ttu-id="bfdbd-139">アプリ保護ポリシーでアプリのデータを保護するしくみ</span><span class="sxs-lookup"><span data-stu-id="bfdbd-139">How app protection policies protect app data</span></span>

###  <a name="apps-without-app-protection-policies"></a><span data-ttu-id="bfdbd-140">アプリ保護ポリシーのないアプリ</span><span class="sxs-lookup"><span data-stu-id="bfdbd-140">Apps without app protection policies</span></span>

![アプリ保護ポリシーが配備されていない場合にデータがアプリ間をどのようにして自由に移動できるかを示すイメージ](../media/Apps_without_MAM_policies.png)

<span data-ttu-id="bfdbd-142">アプリを制限なしで使用すると、会社データと個人データが混在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-142">When you use apps without restrictions, company and personal data can get intermingled.</span></span> <span data-ttu-id="bfdbd-143">会社データが個人の記憶域に保存されたり、管理範囲外のアプリに転送されたりして、データが損失することがあります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-143">Company data might end up in locations like personal storage or might be transferred to apps outside of your purview, which could result in data loss.</span></span> <span data-ttu-id="bfdbd-144">図の矢印はアプリ (会社と個人) と記憶域の間の制限されたデータ移動を示しています。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <a name="data-protection-with-app-protection-policies"></a><span data-ttu-id="bfdbd-145">アプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="bfdbd-145">Data protection with app protection policies</span></span>

![アプリ保護ポリシーが適用されている場合に会社のデータがどのように保護されるかを示すイメージ](../media/Apps_with_mobile_app_policies.png)

<span data-ttu-id="bfdbd-147">アプリ保護ポリシーを使用すれば、会社のデータがデバイスのローカル ストレージに保存されるのを防止し、アプリ保護ポリシーで保護されていない他のアプリへのデータの移動を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-147">You can use app protection policies to prevent company data from saving to the local storage of the device, and to restrict data movement to other apps that aren't protected by app protection policies.</span></span> <span data-ttu-id="bfdbd-148">アプリ保護ポリシー設定には以下のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-148">App protection policy settings include:</span></span>
- <span data-ttu-id="bfdbd-149">**[名前を付けて保存] を禁止する**、**切り取り、コピー、貼り付けを制限する** のようなデータ再配置ポリシー。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-149">Data relocation policies like **Prevent Save As** and **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="bfdbd-150">**アクセスの際にシンプルな PIN を要求する**、**脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する**のようなアクセス ポリシー設定。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-150">Access policy settings like **Require simple PIN for access** and **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a><span data-ttu-id="bfdbd-151">MDM ソリューションで管理されるデバイスのアプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="bfdbd-151">Data protection with app protection on devices that are managed by a MDM solution</span></span>

![Bring Your Own Devices (BYOD) デバイスでアプリ保護ポリシーが機能するしくみを示すイメージ](../media/MAM_BYOD_November.png)

<span data-ttu-id="bfdbd-153">**MDM ソリューションに登録されているデバイスの場合**: 前の図は、MDM とアプリ保護ポリシーによって提供される保護の各層を示しています。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-153">**For devices enrolled in an MDM solution**: The preceding diagram shows the layers of protection that MDM and app protection policies offer together.</span></span>

<span data-ttu-id="bfdbd-154">MDM ソリューション:</span><span class="sxs-lookup"><span data-stu-id="bfdbd-154">The MDM solution:</span></span>

-   <span data-ttu-id="bfdbd-155">デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-155">Enrolls the device.</span></span>

-   <span data-ttu-id="bfdbd-156">アプリをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-156">Deploys apps to the device.</span></span>

-   <span data-ttu-id="bfdbd-157">継続的なデバイスのポリシー準拠と管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-157">Provides ongoing device compliance and management.</span></span>

<span data-ttu-id="bfdbd-158">**アプリ保護ポリシーが価値を高める理由:**</span><span class="sxs-lookup"><span data-stu-id="bfdbd-158">**App protection policies add value because they:**</span></span>

-   <span data-ttu-id="bfdbd-159">コンシューマー アプリやサービスに会社データがリークしないように支援します。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-159">Help protect company data from leaking to consumer apps and services.</span></span>

-   <span data-ttu-id="bfdbd-160">モバイル アプリに制限を適用します (名前を付けて保存、クリップボード、PIN など)。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-160">Apply restrictions (save-as, clipboard, PIN, etc.) to mobile apps.</span></span>

-   <span data-ttu-id="bfdbd-161">デバイスからアプリを削除しないで、アプリから会社データをワイプします。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-161">Wipe company data from apps without removing those apps from the device.</span></span>


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a><span data-ttu-id="bfdbd-162">登録されていないデバイスでのアプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="bfdbd-162">Data protection with app protection policies for devices without enrollment</span></span>

![管理対象デバイスでアプリ保護ポリシーが機能するしくみを示すイメージ](../media/MAM_ManagedDevices_November.png)

<span data-ttu-id="bfdbd-164">上の図は、MDM がない場合にアプリ レベルでデータ保護ポリシーが機能するしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-164">The preceding diagram illustrates how data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="bfdbd-165">MDM ソリューションに登録されていない BYOD デバイスでは、アプリ保護ポリシーによってアプリ レベルで会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-165">For BYOD devices that aren't enrolled in any MDM solution, app protection policies can help protect company data at the app level.</span></span>

<span data-ttu-id="bfdbd-166">ただし、次のようないくつかの制約があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-166">However, there are some limitations to be aware of:</span></span>

-   <span data-ttu-id="bfdbd-167">アプリをデバイスに展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-167">You can't deploy apps to the device.</span></span> <span data-ttu-id="bfdbd-168">アプリはユーザーがストアから入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-168">The user has to get the apps from the store.</span></span>

-   <span data-ttu-id="bfdbd-169">これらのデバイスで証明書プロファイルをプロビジョニングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-169">You can't provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="bfdbd-170">会社が Wi-Fi や VPN の設定をこれらのデバイスにセットアップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-170">You can't set up company Wi-Fi and VPN settings on these devices.</span></span>


## <a name="multi-identity"></a><span data-ttu-id="bfdbd-171">複数の ID</span><span class="sxs-lookup"><span data-stu-id="bfdbd-171">Multi-identity</span></span>

<span data-ttu-id="bfdbd-172">複数の ID をサポートするアプリの場合、アプリが作業コンテキストで利用されているときにアプリ保護ポリシーが適用されていれば、仕事用や個人用など、複数のアカウントを利用して同じアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-172">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="bfdbd-173">たとえば、ユーザーが仕事用のアカウントを使用して OneDrive アプリを開始した場合、個人のストレージにファイルを移動できません。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-173">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="bfdbd-174">ただし、ユーザーが個人のアカウントで OneDrive を使用する場合、個人の OneDrive から制限なしでデータをコピーしたり、移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-174">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>  

- <span data-ttu-id="bfdbd-175">Intune で [MAM と複数の ID](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) をサポートするアプリについての詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfdbd-175">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="bfdbd-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bfdbd-176">Next steps</span></span>
- [<span data-ttu-id="bfdbd-177">アプリ保護ポリシーを構成する準備をする</span><span class="sxs-lookup"><span data-stu-id="bfdbd-177">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [<span data-ttu-id="bfdbd-178">Microsoft Intune でのアプリ保護ポリシーの作成とデプロイ</span><span class="sxs-lookup"><span data-stu-id="bfdbd-178">Create and deploy app protection policies with Microsoft Intune</span></span>](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
