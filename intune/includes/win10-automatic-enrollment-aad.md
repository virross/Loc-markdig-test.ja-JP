## <a name="enable-windows-10-automatic-enrollment"></a><span data-ttu-id="15694-101">Windows 10 の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="15694-101">Enable Windows 10 automatic enrollment</span></span>

<span data-ttu-id="15694-102">自動登録により、Intune に Windows 10 デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="15694-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune.</span></span> <span data-ttu-id="15694-103">登録するには、ユーザーが職場アカウントを個人所有のデバイスを追加するか、会社所有のデバイスを Azure Active Directory に参加させます。</span><span class="sxs-lookup"><span data-stu-id="15694-103">To enroll, users add their work account to their personally owned devices or join corporate-owned devices to Azure Active Directory.</span></span> <span data-ttu-id="15694-104">バック グラウンドでデバイスが登録され、Azure Active Directory に参加します。</span><span class="sxs-lookup"><span data-stu-id="15694-104">In the background, the device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="15694-105">登録されると、デバイスは Intune で管理されます。</span><span class="sxs-lookup"><span data-stu-id="15694-105">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="15694-106">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="15694-106">**Prerequisites**</span></span>
- <span data-ttu-id="15694-107">Azure Active Directory Premium サブスクリプション ([試用版サブスクリプション](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="15694-107">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="15694-108">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="15694-108">Microsoft Intune subscription</span></span>


### <a name="configure-automatic-mdm-enrollment"></a><span data-ttu-id="15694-109">自動 MDM 登録の構成</span><span class="sxs-lookup"><span data-stu-id="15694-109">Configure automatic MDM enrollment</span></span>

1. <span data-ttu-id="15694-110">[Azure Portal](https://portal.azure.com) にサインインして、 **[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="15694-110">Sign in to the [Azure portal](https://portal.azure.com), and select **Azure Active Directory**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="15694-112">**[モビリティ (MDM と MAM)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="15694-112">Select **Mobility (MDM and MAM)**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="15694-114">**Microsoft Intune** を選択します。</span><span class="sxs-lookup"><span data-stu-id="15694-114">Select **Microsoft Intune**.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-intune.png)

4. <span data-ttu-id="15694-116">**[MDM ユーザー スコープ]** を構成します。</span><span class="sxs-lookup"><span data-stu-id="15694-116">Configure **MDM User scope**.</span></span> <span data-ttu-id="15694-117">どのユーザーのデバイスを Microsoft Intune で管理するのかを指定します。</span><span class="sxs-lookup"><span data-stu-id="15694-117">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="15694-118">これらの Windows 10 デバイスは、Microsoft Intune の管理対象として自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="15694-118">These Windows 10 devices can automatically enroll for management with Microsoft Intune.</span></span>

   - <span data-ttu-id="15694-119">**[なし]** - MDM の自動登録が無効になります</span><span class="sxs-lookup"><span data-stu-id="15694-119">**None** - MDM automatic enrollment disabled</span></span>
   - <span data-ttu-id="15694-120">**[Some]\(一部\)** - **[グループ]** を選びます。そのグループの Windows 10 デバイスを自動的に登録できます</span><span class="sxs-lookup"><span data-stu-id="15694-120">**Some** - Select the **Groups** that can automatically enroll their Windows 10 devices</span></span>
   - <span data-ttu-id="15694-121">**[すべて]** - すべてのユーザーが自分の Windows 10 デバイスを自動的に登録できます</span><span class="sxs-lookup"><span data-stu-id="15694-121">**All** - All users can automatically enroll their Windows 10 devices</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="15694-122">**MAM ユーザー スコープ**と自動 MDM 登録 (**MDM ユーザー スコープ**) の両方が有効になっている場合、MAM のみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="15694-122">If both **MAM user scope** and automatic MDM enrollment (**MDM user scope**) are enabled for a group, only MAM is enabled.</span></span> <span data-ttu-id="15694-123">個人用デバイスをワークプレースに参加させると、MAM のみがそのグループのユーザーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="15694-123">Only MAM is added for users in that group when they workplace join personal device.</span></span> <span data-ttu-id="15694-124">デバイスは、自動的には MDM に登録されません。</span><span class="sxs-lookup"><span data-stu-id="15694-124">Devices are not automatically MDM enrolled.</span></span>

   ![Azure Portal のスクリーンショット](../media/auto-enroll-scope.png)

5. <span data-ttu-id="15694-126">次の URL の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="15694-126">Use the default values for the following URLs:</span></span>
    - <span data-ttu-id="15694-127">**MDM 使用条件 URL**</span><span class="sxs-lookup"><span data-stu-id="15694-127">**MDM Terms of use URL**</span></span>
    - <span data-ttu-id="15694-128">**MDM 探索 URL**</span><span class="sxs-lookup"><span data-stu-id="15694-128">**MDM Discovery URL**</span></span>
    - <span data-ttu-id="15694-129">**MDM 準拠 URL**</span><span class="sxs-lookup"><span data-stu-id="15694-129">**MDM Compliance URL**</span></span>

6. <span data-ttu-id="15694-130">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="15694-130">Select **Save**.</span></span>

<span data-ttu-id="15694-131">既定では、サービスに対して 2 要素認証は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="15694-131">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="15694-132">ただし、デバイスを登録するときには 2 要素認証をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15694-132">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="15694-133">2 要素認証を有効にするには、Azure AD で 2 要素認証プロバイダーを構成し、多要素認証用にユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="15694-133">To enable two-factor authentication, configure a two-factor authentication provider in Azure AD and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="15694-134">「[クラウドでの Azure Multi-Factor Authentication Server の概要](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15694-134">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
