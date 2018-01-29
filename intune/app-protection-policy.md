---
title: "アプリ保護ポリシーとは"
titleSuffix: Azure portal
description: "このトピックでは、Microsoft Intune のアプリ保護ポリシーで会社のデータを保護する方法について説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/01/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 38334b4131a23253bdc41acb1d9e23bb4f318a4d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="what-are-app-protection-policies"></a><span data-ttu-id="94bc7-103">アプリ保護ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="94bc7-103">What are app protection policies?</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="94bc7-104">Microsoft Intune のアプリ保護ポリシーは、会社のデータを保護し、データ損失を防ぐために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-104">Microsoft Intune app protection policies help protect your company data and prevent data loss.</span></span>

## <a name="how-you-can-protect-app-data"></a><span data-ttu-id="94bc7-105">アプリ データを保護する方法</span><span class="sxs-lookup"><span data-stu-id="94bc7-105">How you can protect app data</span></span>
<span data-ttu-id="94bc7-106">従業員は個人のタスクと仕事のタスクの両方にモバイル デバイスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="94bc7-106">Your employees use mobile devices for both personal and work tasks.</span></span>  <span data-ttu-id="94bc7-107">従業員の生産性を維持したまま、意図的なデータ損失や意図しないデータ損失が起こらないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-107">While making sure your employees can be productive, you also want to prevent data loss, intentional and unintentional.</span></span>  <span data-ttu-id="94bc7-108">また、デバイスを自分で管理していない場合でも、そのデバイスでアクセスされる会社のデータを保護する機能があれば便利です。</span><span class="sxs-lookup"><span data-stu-id="94bc7-108">In addition, you want to have the ability to protect company data accessed using devices even in the case where they are not managed by you.</span></span>

<span data-ttu-id="94bc7-109">Intune のアプリ保護ポリシーを使用すれば、会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-109">You can use Intune  app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="94bc7-110">Intune のアプリ保護ポリシーは**どのモバイル デバイス管理 (MDM) ソリューションからも独立して**利用できるため、デバイスをデバイス管理ソリューションに登録しているかどうかにかかわらず、これを利用して会社のデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-110">Because Intune app protection policies can be used **independent of any mobile-device management (MDM) solution**, you can use it to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="94bc7-111">**アプリレベル ポリシー**を実装するだけで、会社のリソースへのアクセスを制限し、データを IT 部門の管理範囲内に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-111">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="94bc7-112">アプリ保護ポリシーは、次のようなデバイスで実行されているアプリ向けに構成できます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-112">App protection policies can be configured for app running on devices that are:</span></span>

- <span data-ttu-id="94bc7-113">**Microsoft Intune に登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。</span><span class="sxs-lookup"><span data-stu-id="94bc7-113">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate owned devices.</span></span>

- <span data-ttu-id="94bc7-114">**サード パーティ製のモバイル デバイス管理 (MDM) ソリューションに登録されているデバイス:** このカテゴリに属するデバイスは、通常、企業所有デバイスです。</span><span class="sxs-lookup"><span data-stu-id="94bc7-114">**Enrolled in a third-party Mobile device management (MDM)  solution:**   The devices in this category are typically corporate owned devices.</span></span>

  > [!NOTE]
  > <span data-ttu-id="94bc7-115">モバイル アプリ管理ポリシーを、サード パーティのモバイル アプリ管理ソリューションやセキュア コンテナー ソリューションとともに使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="94bc7-115">Mobile app management policies should not be used with third party mobile app management  or secure container solutions.</span></span>

- <span data-ttu-id="94bc7-116">**いずれのモバイル デバイス管理ソリューションにも登録されていないデバイス:** このカテゴリに属するデバイスは、通常、Intune またはその他の MDM ソリューションで管理も登録もされていない社員所有のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="94bc7-116">**Not enrolled in any mobile device management solution:**  The devices in this category are typically employee owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94bc7-117">Office 365 サービスに接続する Office モバイル アプリ向けのモバイル アプリ管理ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-117">You can create mobile app management policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="94bc7-118">アプリ保護ポリシーは、オンプレミス Exchange サービスや Skype for Business サービス、SharePoint サービスに接続するアプリ向けにはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-118">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

<span data-ttu-id="94bc7-119">**アプリ保護ポリシーを利用した場合の主なメリットとしては、以下のようなものがあります。**</span><span class="sxs-lookup"><span data-stu-id="94bc7-119">**The important benefits of using App protection policies are**</span></span>

-   <span data-ttu-id="94bc7-120">アプリ レベルで、会社データを保護します。</span><span class="sxs-lookup"><span data-stu-id="94bc7-120">Protecting your company data at the app level.</span></span>  <span data-ttu-id="94bc7-121">モバイル アプリ管理にはデバイス管理が必要ないため、管理対象のデバイスと管理対象ではないデバイスの両方で会社データを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-121">Since mobile app management does not require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="94bc7-122">管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-122">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="94bc7-123">エンド ユーザーの生産性に影響を与えることがなく、個人のコンテキストでアプリが使用される場合にはポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-123">End user productivity is not impacted, and the policies are not applied when using the app in a personal context.</span></span>  <span data-ttu-id="94bc7-124">ポリシーは仕事のコンテキストでのみ適用されるため、個人データに影響を与えることなく会社データを保護することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-124">The policies are applied only in a work context, thus giving you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="94bc7-125">MDM をアプリ保護ポリシーと共に使用することで、MDM ありのアプリ保護ポリシーと MDM なしのアプリ保護ポリシーを社内で両方同時に使用できるという、新たなメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-125">There are additional benefits to using MDM with App protection  policies, and companies can use both App protection policies with and without MDM at the same time.</span></span> <span data-ttu-id="94bc7-126">たとえば、従業員は、会社が支給する電話に加えて個人のタブレットを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-126">For example, an employee may use a phone issued by the company as well as a personal tablet.</span></span>  <span data-ttu-id="94bc7-127">この場合、会社の電話は MDM に登録されたうえでアプリ保護ポリシーによって保護されますが、個人のデバイスはアプリ保護ポリシーのみで保護されます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-127">In this case, the company phone is enrolled in MDM and protected by App protection policies, and the personal device is protected by App protection policies only.</span></span>

- <span data-ttu-id="94bc7-128">**MDM によりデバイスの保護を実現できる**。</span><span class="sxs-lookup"><span data-stu-id="94bc7-128">**MDM makes sure that the device is protected**.</span></span>  <span data-ttu-id="94bc7-129">たとえば、デバイスへのアクセスに PIN を要求したり、デバイスに管理対象のアプリを展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-129">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="94bc7-130">また、MDM ソリューションを介してデバイスにアプリを展開することにより、アプリ管理をより制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-130">You can also deploy apps to devices through your MDM solution, to give you more control over app management.</span></span>

- <span data-ttu-id="94bc7-131">**アプリ保護ポリシーによりアプリ層の保護を実現できる**。</span><span class="sxs-lookup"><span data-stu-id="94bc7-131">**App protection policies makes sure that the app-layer protections are in place**.</span></span> <span data-ttu-id="94bc7-132">たとえば、仕事のコンテキストでアプリを開くために PIN を要求したり、アプリ間でデータを共有できるかどうかを決めたり、会社のアプリ データを個人の記憶域に保存できないようにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-132">For example, you can require a PIN to open an app in a work context, or if data can be shared between apps, or preventing company app data from being saved to a personal storage location.</span></span>


### <a name="supported-platforms-for-app-protection-polices"></a><span data-ttu-id="94bc7-133">アプリ保護ポリシーでサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="94bc7-133">Supported platforms for app protection polices</span></span>
-   <span data-ttu-id="94bc7-134">iOS 9 以降</span><span class="sxs-lookup"><span data-stu-id="94bc7-134">iOS 9 or later</span></span>
-   <span data-ttu-id="94bc7-135">Android 4.4 以降</span><span class="sxs-lookup"><span data-stu-id="94bc7-135">Android 4.4 or later</span></span>

<span data-ttu-id="94bc7-136">Windows デバイスは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-136">Windows devices are currently not supported.</span></span> <span data-ttu-id="94bc7-137">ただし、Intune で Windows 10 デバイスを登録すると、同様の機能を提供する Windows 情報保護を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="94bc7-138">詳細については、「[Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)」 (Windows 情報保護 (WIP) を使用してエンタープライズ データを保護する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94bc7-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
##  <a name="how-app-protection-policies-protect-app-data"></a><span data-ttu-id="94bc7-139">アプリ保護ポリシーでアプリのデータを保護するしくみ</span><span class="sxs-lookup"><span data-stu-id="94bc7-139">How app protection policies protect app data</span></span>

####  <a name="apps-without-app-protection-policies"></a><span data-ttu-id="94bc7-140">アプリ保護ポリシーのないアプリ</span><span class="sxs-lookup"><span data-stu-id="94bc7-140">Apps without app protection policies</span></span>

![アプリ保護ポリシーが配備されていない場合にデータがアプリ間を自由に移動できることを示す画像](./media/apps-without-protection-policies.png)

<span data-ttu-id="94bc7-142">アプリが制限なしで使用されている場合、会社データと個人データが混在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-142">When apps are used without restrictions, company and personal data can get intermingled.</span></span>  <span data-ttu-id="94bc7-143">会社データが個人の記憶域に保存されたり、管理範囲外のアプリに転送されたりして、データが損失することがあります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-143">Company data could end up in locations like personal storage or transferred to apps outside of your  purview,  resulting in data loss.</span></span> <span data-ttu-id="94bc7-144">図の矢印はアプリ (会社と個人) と記憶域の間の制限されたデータ移動を示しています。</span><span class="sxs-lookup"><span data-stu-id="94bc7-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <a name="data-protection-with-app-protection-policies"></a><span data-ttu-id="94bc7-145">アプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="94bc7-145">Data protection with app protection policies</span></span>

![<span data-ttu-id="94bc7-146">アプリ保護ポリシーが適用されている場合に会社のデータがどのように保護されるかを示す画像</span><span class="sxs-lookup"><span data-stu-id="94bc7-146">Image that shows how company data is protect when App protection policies are applied</span></span> ](./media/apps-with-protection-policies.png)


<span data-ttu-id="94bc7-147">アプリ保護ポリシーを使用すれば、会社のデータがデバイスのローカル ストレージに保存されるのを防止し、アプリ保護ポリシーで保護されていない他のアプリへのデータの移動を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-147">You can use App protection policies to prevent company data from saving to the local storage of the device, and restrict data movement to other apps that are not protected by App protection policies.</span></span> <span data-ttu-id="94bc7-148">アプリ保護ポリシー設定には以下のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-148">App protection policy settings include:</span></span>
- <span data-ttu-id="94bc7-149">**[名前を付けて保存] を禁止する**、**切り取り、コピー、貼り付けを制限する** のようなデータ再配置ポリシー。</span><span class="sxs-lookup"><span data-stu-id="94bc7-149">Data relocation policies like **Prevent Save As**, **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="94bc7-150">**アクセスの際にシンプルな PIN を要求する**、**脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する**のようなアクセス ポリシー設定。</span><span class="sxs-lookup"><span data-stu-id="94bc7-150">Access policy settings like **Require simple PIN for access**, **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a><span data-ttu-id="94bc7-151">MDM ソリューションで管理されているデバイスでのアプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="94bc7-151">Data protection with app protection policies on devices managed by a MDM solution</span></span>

![BYOD デバイスでアプリ保護ポリシーが機能するしくみを示す画像](./media/app-protection-policies-with-mdm.png)

<span data-ttu-id="94bc7-153">**MDM ソリューションに登録されているデバイスの場合**-</span><span class="sxs-lookup"><span data-stu-id="94bc7-153">**For devices enrolled in an MDM solution**-</span></span>

<span data-ttu-id="94bc7-154">上の図は、MDM とアプリ保護ポリシーの連携によって提供される保護層を示しています。</span><span class="sxs-lookup"><span data-stu-id="94bc7-154">The illustration above shows the layers of protection that MDM and App protection policies offer together.</span></span>

<span data-ttu-id="94bc7-155">MDM ソリューション:</span><span class="sxs-lookup"><span data-stu-id="94bc7-155">The MDM solution:</span></span>

-   <span data-ttu-id="94bc7-156">デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="94bc7-156">Enrolls the device</span></span>

-   <span data-ttu-id="94bc7-157">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="94bc7-157">Deploys the apps to the device</span></span>

-   <span data-ttu-id="94bc7-158">継続的なデバイスのポリシー準拠と管理を提供する</span><span class="sxs-lookup"><span data-stu-id="94bc7-158">Provides ongoing device compliance and management</span></span>

<span data-ttu-id="94bc7-159">**アプリ保護ポリシーによる追加機能:**</span><span class="sxs-lookup"><span data-stu-id="94bc7-159">**App protection policies add value by:**</span></span>

-   <span data-ttu-id="94bc7-160">コンシューマー アプリやサービスに会社データがリークしないように支援する</span><span class="sxs-lookup"><span data-stu-id="94bc7-160">Helping protect  company data from leaking to consumer apps and services</span></span>

-   <span data-ttu-id="94bc7-161">モバイル アプリへの制限の適用 (名前を付けて保存、クリップボード、PIN など)</span><span class="sxs-lookup"><span data-stu-id="94bc7-161">Applying restrictions (save-as, clipboard, PIN, etc.) to mobile apps</span></span>

-   <span data-ttu-id="94bc7-162">アプリから会社データをワイプし、その際にデバイスからそのアプリを削除しない</span><span class="sxs-lookup"><span data-stu-id="94bc7-162">Wipe company data from apps without removing those apps from the device</span></span>


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a><span data-ttu-id="94bc7-163">未登録デバイスでのアプリ保護ポリシーによるデータ保護</span><span class="sxs-lookup"><span data-stu-id="94bc7-163">Data protection with app protection policies for devices without enrollment</span></span>

![管理対象デバイスでアプリ保護ポリシーが機能するしくみを示す画像](./media/app-protection-policies-without-mdm.png)

<span data-ttu-id="94bc7-165">上の図は、MDM がない場合にアプリ レベルでデータ保護ポリシーが機能するしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="94bc7-165">The diagram above illustrates how the data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="94bc7-166">MDM ソリューションに登録されていない BYOD デバイスでは、アプリ保護ポリシーによってアプリ レベルで会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-166">For BYOD devices not enrolled in any MDM solution, App protection policies can help protect company data at the app level.</span></span>
<span data-ttu-id="94bc7-167">ただし、次のようないくつかの制約があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="94bc7-167">However, there are some limitations to be aware of, like:</span></span>

-   <span data-ttu-id="94bc7-168">アプリをデバイスに展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-168">You cannot deploy apps to the device.</span></span>  <span data-ttu-id="94bc7-169">アプリはエンドユーザーがストアから入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94bc7-169">The end user has to get the apps from the store.</span></span>

-   <span data-ttu-id="94bc7-170">これらのデバイスで証明書プロファイルをプロビジョニングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-170">You cannot provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="94bc7-171">会社が Wi-Fi や VPN の設定をこれらのデバイスにプロビジョニングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-171">You cannot provision company Wi-Fi and VPN settings on these devices.</span></span>


## <a name="multi-identity"></a><span data-ttu-id="94bc7-172">複数の ID</span><span class="sxs-lookup"><span data-stu-id="94bc7-172">Multi-identity</span></span>

<span data-ttu-id="94bc7-173">複数の ID をサポートするアプリの場合、アプリが作業コンテキストで利用されているときにアプリ保護ポリシーが適用されていれば、仕事用や個人用など、複数のアカウントを利用して同じアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-173">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>

<span data-ttu-id="94bc7-174">たとえば、ユーザーが仕事用のアカウントを使用して OneDrive アプリを開始した場合、個人のストレージにファイルを移動できません。</span><span class="sxs-lookup"><span data-stu-id="94bc7-174">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="94bc7-175">ただし、ユーザーが個人のアカウントで OneDrive を使用する場合、個人の OneDrive から制限なしでデータをコピーしたり、移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="94bc7-175">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>

- <span data-ttu-id="94bc7-176">Intune で [MAM と複数の ID](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) をサポートするアプリについての詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94bc7-176">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="94bc7-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="94bc7-177">Next steps</span></span>

[<span data-ttu-id="94bc7-178">Microsoft Intune でアプリ保護ポリシーを作成および展開する方法</span><span class="sxs-lookup"><span data-stu-id="94bc7-178">How to create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
