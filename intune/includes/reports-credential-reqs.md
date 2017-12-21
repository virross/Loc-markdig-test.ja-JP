<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a><span data-ttu-id="68d63-101">Azure AD と Intune の資格情報の要件</span><span class="sxs-lookup"><span data-stu-id="68d63-101">Azure AD and Intune credential requirements</span></span>

<span data-ttu-id="68d63-102">認証と承認は、Azure AD の資格情報と Intune のロールベースのアクセス制御 (RBAC) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="68d63-102">Authentication and authorization are based on Azure AD credentials and Intune role-based access control (RBAC).</span></span> <span data-ttu-id="68d63-103">すべての全体管理者およびテナントの Intune サービス管理者は、既定でデータ ウェアハウスに対するアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="68d63-103">All global administrators and Intune service administrators for your tenant have access to the Data warehouse by default.</span></span> <span data-ttu-id="68d63-104">Intune ロールを使用して、他のユーザーにアクセス権を付与するには、**レポート リソース**へのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="68d63-104">Use Intune roles to provide access for more users by giving them access to the **Reporting resource**.</span></span>

<span data-ttu-id="68d63-105">Intune データ ウェアハウス (API を含む) にアクセスするための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="68d63-105">Requirements for accessing the Intune Data Warehouse (including the API) are:</span></span>

  -  <span data-ttu-id="68d63-106">Intune ライセンスをユーザーに割り当てる必要があります</span><span class="sxs-lookup"><span data-stu-id="68d63-106">Intune license must be assigned to the user</span></span>
  -  <span data-ttu-id="68d63-107">ユーザーは次のいずれかである必要があります</span><span class="sxs-lookup"><span data-stu-id="68d63-107">User must be one of:</span></span>
      -  <span data-ttu-id="68d63-108">Azure AD 全体管理者</span><span class="sxs-lookup"><span data-stu-id="68d63-108">Azure AD global administrator</span></span>
      -  <span data-ttu-id="68d63-109">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="68d63-109">An Intune service administrator</span></span>
      -  <span data-ttu-id="68d63-110">**レポート** リソースに対してロールベースのアクセス権を持つユーザー</span><span class="sxs-lookup"><span data-stu-id="68d63-110">User with role-based access to **Reports** resource</span></span>