## <a name="enable-windows-10-automatic-enrollment"></a><span data-ttu-id="308cc-101">Windows 10 の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="308cc-101">Enable Windows 10 automatic enrollment</span></span>

<span data-ttu-id="308cc-102">自動登録により、ユーザーは個人所有のデバイスに職場のアカウントを追加したり、会社所有のデバイスを Azure Active Directory に参加させたりして、Windows 10 デバイスを Intune に登録することができます。</span><span class="sxs-lookup"><span data-stu-id="308cc-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune when adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure Active Directory.</span></span> <span data-ttu-id="308cc-103">バック グラウンドでユーザーのデバイスが登録され、Azure Active Directory に参加します。</span><span class="sxs-lookup"><span data-stu-id="308cc-103">In the background, the user's device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="308cc-104">登録されると、デバイスは Intune で管理されます。</span><span class="sxs-lookup"><span data-stu-id="308cc-104">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="308cc-105">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="308cc-105">**Prerequisites**</span></span>
- <span data-ttu-id="308cc-106">Azure Active Directory Premium サブスクリプション ([試用版サブスクリプション](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="308cc-106">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="308cc-107">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="308cc-107">Microsoft Intune subscription</span></span>


### <a name="configure-automatic-mdm-enrollment"></a><span data-ttu-id="308cc-108">自動 MDM 登録の構成</span><span class="sxs-lookup"><span data-stu-id="308cc-108">Configure automatic MDM enrollment</span></span>

1. <span data-ttu-id="308cc-109">[Azure 管理ポータル](https://portal.azure.com) (https://manage.windowsazure.com) にサインインして、**[Azure Active Directory]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="308cc-109">Sign in to the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), and select **Azure Active Directory**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="308cc-111">**[モビリティ (MDM と MAM)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="308cc-111">Select **Mobility (MDM and MAM)**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="308cc-113">**Microsoft Intune** を選択します。</span><span class="sxs-lookup"><span data-stu-id="308cc-113">Select **Microsoft Intune**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-intune.png)

4. <span data-ttu-id="308cc-115">**[MDM ユーザー スコープ]** を構成します。</span><span class="sxs-lookup"><span data-stu-id="308cc-115">Configure **MDM User scope**.</span></span> <span data-ttu-id="308cc-116">どのユーザーのデバイスを Microsoft Intune で管理するのかを指定します。</span><span class="sxs-lookup"><span data-stu-id="308cc-116">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="308cc-117">これらのユーザーの Windows 10 デバイスは、Microsoft Intune の管理対象として自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="308cc-117">These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.</span></span>

   - <span data-ttu-id="308cc-118">**なし**</span><span class="sxs-lookup"><span data-stu-id="308cc-118">**None**</span></span>
   - <span data-ttu-id="308cc-119">**一部**</span><span class="sxs-lookup"><span data-stu-id="308cc-119">**Some**</span></span>
   - <span data-ttu-id="308cc-120">**すべて**</span><span class="sxs-lookup"><span data-stu-id="308cc-120">**All**</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-scope.png)

5. <span data-ttu-id="308cc-122">次の URL の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="308cc-122">Use the default values for the following URLs:</span></span>
   - <span data-ttu-id="308cc-123">**MDM 使用条件 URL**</span><span class="sxs-lookup"><span data-stu-id="308cc-123">**MDM Terms of use URL**</span></span>
   - <span data-ttu-id="308cc-124">**MDM 探索 URL**</span><span class="sxs-lookup"><span data-stu-id="308cc-124">**MDM Discovery URL**</span></span>
   - <span data-ttu-id="308cc-125">**MDM 準拠 URL**</span><span class="sxs-lookup"><span data-stu-id="308cc-125">**MDM Compliance URL**</span></span>

6. <span data-ttu-id="308cc-126">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="308cc-126">Select **Save**.</span></span>

<span data-ttu-id="308cc-127">既定では、サービスに対して 2 要素認証は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="308cc-127">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="308cc-128">ただし、デバイスを登録するときには 2 要素認証をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="308cc-128">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="308cc-129">このサービスの 2 要素認証を要求する前に、Azure Active Directory で 2 要素認証プロバイダーを構成し、多要素認証用にユーザー アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="308cc-129">Before requiring two-factor authentication for this service, you must configure a two-factor authentication provider in Azure Active Directory and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="308cc-130">「[クラウドでの Azure Multi-Factor Authentication Server の概要](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="308cc-130">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
