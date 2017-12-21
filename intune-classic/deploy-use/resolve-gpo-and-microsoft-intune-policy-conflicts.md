---
title: "GPO と Intune ポリシーの競合を解決する"
description: "グループ ポリシーと Intune 構成ポリシーの競合を解決する方法について説明します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fcad94039722beb7d71f9d8cf7e0db2453b2a260
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a><span data-ttu-id="cc1d1-103">グループ ポリシー オブジェクト (GPO) と Microsoft Intune ポリシーの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="cc1d1-103">Resolve Group Policy Objects (GPO) and Microsoft Intune policy conflicts</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="cc1d1-104">Intune は、Windows PC の設定を管理するためにポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-104">Intune uses policies that help you manage settings on Windows PCs.</span></span> <span data-ttu-id="cc1d1-105">たとえば、ポリシーを使用して、PC の Windows ファイアウォールに関する設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-105">For example, you can use a policy to control settings for the Windows Firewall on PCs.</span></span> <span data-ttu-id="cc1d1-106">多くの Intune 設定は、Windows グループ ポリシーで構成する設定と似ています。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-106">Many Intune settings are similar to settings that you might configure with Windows Group Policy.</span></span> <span data-ttu-id="cc1d1-107">ただし、この 2 つの設定が互いに競合することがあります。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-107">However, it is possible that, at times, the two methods might conflict with each another.</span></span>

<span data-ttu-id="cc1d1-108">競合が発生した場合、PC がドメインにサインインできない場合を除き、ドメインレベルのグループ ポリシーの方が Intune ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-108">When conflicts happen, domain-level Group Policy takes precedence over Intune policy, unless the PC can’t sign in to the domain.</span></span> <span data-ttu-id="cc1d1-109">ドメインにログオンできない場合は、Intune ポリシーがクライアント PC に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-109">In this case, Intune policy is applied to the client PC.</span></span>

## <a name="what-to-do-if-you-are-using-group-policy"></a><span data-ttu-id="cc1d1-110">グループ ポリシーを使用する場合の操作</span><span class="sxs-lookup"><span data-stu-id="cc1d1-110">What to do if you are using Group Policy</span></span>
<span data-ttu-id="cc1d1-111">適用するポリシーがグループ ポリシーの管理対象かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-111">Make sure that policies that you apply are not being managed by Group Policy.</span></span> <span data-ttu-id="cc1d1-112">競合を回避するために、次の方法の 1 つまたは複数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-112">To help prevent conflicts, you can use one or more of the following methods:</span></span>

-   <span data-ttu-id="cc1d1-113">グループ ポリシー設定が適用されない Active Directory 組織単位 (OU) に PC を移動してから、Intune クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-113">Move your PCs to an Active Directory organizational unit (OU) that does not have Group Policy settings applied before you install the Intune client.</span></span> <span data-ttu-id="cc1d1-114">また、Intune に登録されている PC を含む OU にグループ ポリシー設定を適用しない場合は、その OU へのグループ ポリシーの継承をブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-114">You can also block Group Policy inheritance on OUs that contain PCs enrolled in Intune to which you do not want to apply Group Policy settings.</span></span>

-   <span data-ttu-id="cc1d1-115">セキュリティ グループ フィルターを使用して、Intune で管理されていない PC のみに GPO を制限します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-115">Use a security group filter to restrict GPOs only to PCs that are not managed by Intune.</span></span>

-   <span data-ttu-id="cc1d1-116">Intune ポリシーと競合するグループ ポリシー オブジェクトを無効にするか削除します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-116">Disable or remove the Group Policy Objects that conflict with the Intune policies.</span></span>

<span data-ttu-id="cc1d1-117">Active Directory と Windows グループ ポリシーの詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-117">For more information about Active Directory and Windows Group Policy, see your Windows Server Documentation.</span></span>

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a><span data-ttu-id="cc1d1-118">既存の GPO をフィルターして Intune ポリシーとの競合を回避する方法</span><span class="sxs-lookup"><span data-stu-id="cc1d1-118">How to filter existing GPOs to avoid conflicts with Intune policy</span></span>
<span data-ttu-id="cc1d1-119">Intune ポリシーと設定が競合するグループ ポリシー オブジェクト (GPO) を見つけたら、セキュリティ グループ フィルターを使用して、Intune で管理しない PC のみにこれらの GPO が適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-119">If you have identified GPOs whose settings conflict with Intune policies, you can use security group filters to restrict those GPOs only to PCs that are not managed by Intune.</span></span>

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


<span data-ttu-id="cc1d1-120">GPO は、グループ ポリシー管理コンソールで、選択した GPO の **[セキュリティ フィルター処理]** に指定されているセキュリティ グループのみに適用できます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-120">You can apply GPOs to only those security groups that are specified in the **Security Filtering** area of the Group Policy Management console for a selected GPO.</span></span> <span data-ttu-id="cc1d1-121">既定では、GPO は *[認証されたユーザー]* に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-121">By default, GPOs apply to *Authenticated Users*.</span></span>

-   <span data-ttu-id="cc1d1-122">**[Active Directory ユーザーとコンピューター]** スナップインで、Intune で管理しないコンピューターとユーザー アカウントを含む新しいセキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-122">In the **Active Directory Users and Computers** snap-in, create a new security group that contains computers and user accounts that you do not want Intune to manage.</span></span> <span data-ttu-id="cc1d1-123">このグループに *Not In Microsoft Intune* などの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-123">For example, you might name the group *Not In Microsoft Intune*.</span></span>

-   <span data-ttu-id="cc1d1-124">グループ ポリシー管理コンソールで、選択した GPO の **[委任]** タブを開き、新しいセキュリティ グループを右クリックして、適切な**読み取り**アクセス許可と**グループ ポリシーの適用**アクセス許可をセキュリティ グループ内のユーザーとコンピューターの両方に委任できます。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-124">In the Group Policy Management console, on the **Delegation** tab for the selected GPO, right-click the new security group to delegate appropriate **Read** and **Apply Group Policy** permissions to both users and computers in the security group.</span></span> <span data-ttu-id="cc1d1-125">(**グループ ポリシーの適用** アクセス許可は **[詳細設定]** ダイアログ ボックスで使用できます)。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-125">(**Apply Group Policy** permissions are available on the **Advanced** dialog box.)</span></span>

-   <span data-ttu-id="cc1d1-126">次に、選択した GPO に新しいセキュリティ グループ フィルターを適用し、既定の **[認証されたユーザー]** フィルターを解除します。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-126">Then, apply the new security group filter to a selected GPO, and remove the **Authenticated Users** default filter.</span></span>

<span data-ttu-id="cc1d1-127">新しいセキュリティ グループは、Intune サービス変更の登録として保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc1d1-127">The new security group must be maintained as enrollment in the Intune service changes.</span></span>

### <a name="see-also"></a><span data-ttu-id="cc1d1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc1d1-128">See also</span></span>
[<span data-ttu-id="cc1d1-129">Microsoft Intune を使用して Windows PC を管理する</span><span class="sxs-lookup"><span data-stu-id="cc1d1-129">Manage Windows PCs with Microsoft Intune</span></span>](manage-windows-pcs-with-microsoft-intune.md)
