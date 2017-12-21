---
title: "記事のタイトル | サービス名"
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="49df3-102">メタデータとマークダウン テンプレート</span><span class="sxs-lookup"><span data-stu-id="49df3-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="49df3-103">この docs.ms テンプレートには、メタデータの設定に関するガイドラインとマークダウン構文のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49df3-103">This docs.ms template contains examples of markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="49df3-104">各 EM パイロット リポジトリのルート ディレクトリ (例： ~/Azure-RMSDocs-pr /template.md) で入手し、[公開済みのバージョン](https://stage.docs.microsoft.com/en-us/rights-management/template)を参照してマークダウン サンプルがどのように表示されるのかを確認できますが、読み取り専用のマークダウン ファイルとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="49df3-104">It is available in the root directory of each EM Pilot repository (e.g. ~/Azure-RMSDocs-pr /template.md) and is meant to be read as a markdown file, although you can refer to [the published version](https://stage.docs.microsoft.com/en-us/rights-management/template) to see how the markdown examples rendeer.</span></span>

<span data-ttu-id="49df3-105">マークダウン ファイルを作成する場合、テンプレートを新しいファイルにコピーし、次に指定するメタデータを入力し、上の H1 見出しを本記事のタイトルに設定して、コンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="49df3-105">When creating a markdown file you shluld copy the template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span> 


## <a name="metadata"></a><span data-ttu-id="49df3-106">メタデータ</span><span class="sxs-lookup"><span data-stu-id="49df3-106">Metadata</span></span> 

<span data-ttu-id="49df3-107">完全なメタデータ ブロックは上部で必要なフィールドと省略可能なフィールドに分けられます。詳細については、「[OPS metadata cheatsheet (OPS メタデータ チートシート)](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49df3-107">The full metadata block is above, divided into required fields and optional fields; see the [OPS metadata cheatsheet](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) for more details.</span></span> <span data-ttu-id="49df3-108">注記: </span><span class="sxs-lookup"><span data-stu-id="49df3-108">Some key notes:</span></span>

- <span data-ttu-id="49df3-109">コロン (:) とメタデータ要素の値との間にスペースを入れる**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="49df3-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="49df3-110">省略可能なメタデータ要素が値を持たない場合は、その要素を # でコメント アウトします (空欄にしたり "na" を使用したりしないでください)。コメント アウトした要素に値を追加する場合は、忘れずに # を削除してください。</span><span class="sxs-lookup"><span data-stu-id="49df3-110">If an optional metadata element does not have a value, comment out the element with a # (do not leave it blank or use "na"); if you are adding a value to an element that was commnted out, be sure to remove the #.</span></span>
- <span data-ttu-id="49df3-111">値 (title など) に使用するコロンはメタデータ パーサーを中断します。</span><span class="sxs-lookup"><span data-stu-id="49df3-111">Colons in a value (e.g., a title) break the metadata parser.</span></span> <span data-ttu-id="49df3-112">代わりに HTML エンコーディングの &#58; を使用します ("title: Azure Rights Management&#58; 基本情報 | Azure RMS" など)。</span><span class="sxs-lookup"><span data-stu-id="49df3-112">In their place, use the HTML encoding of &#58; (e.g., "title: Azure Rights Management&#58; the basics | Azure RMS").</span></span>
- <span data-ttu-id="49df3-113">**title**: このタイトルは検索エンジンの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="49df3-113">**title**: This title will appear in search engine results.</span></span> <span data-ttu-id="49df3-114">タイトルの後ろにパイプ (|) を付け、サービス名を入れる必要があります (前述の例のように)。</span><span class="sxs-lookup"><span data-stu-id="49df3-114">The title should end with a pipe (|) followed by the name of the service (e.g. see above).</span></span> <span data-ttu-id="49df3-115">このタイトルを H1 見出しのタイトルと同じにする必要はありません (変えることをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="49df3-115">The title need not (and probably should not) be identical to the title in your H1 heading.</span></span> <span data-ttu-id="49df3-116">65 文字前後に収めます ("| サービス名" も含め)。</span><span class="sxs-lookup"><span data-stu-id="49df3-116">It should be roughly 65 characters (including | SERVICE NAME)</span></span>
- <span data-ttu-id="49df3-117">**author**、**manager**、**reviewer**: author フィールドには、エイリアスではなく、作成者の **Github ユーザー名** を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="49df3-117">**author**, **manager**, **reviewer**: The author field should contain the **Github username** of the author, not their alias.</span></span>  <span data-ttu-id="49df3-118">一方、"manager" と "reviewer" フィールドにはエイリアスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="49df3-118">The "manager" and "reviewer" fields, on the other hand, should contain aliases.</span></span> <span data-ttu-id="49df3-119">ms.reviewer は記事またはサービスに関連付けられている PM の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="49df3-119">ms.reviewer specifies the name of the PM associated with the article or service.</span></span>
- <span data-ttu-id="49df3-120">**ms.assetid**: CAPS からの記事の GUID です。</span><span class="sxs-lookup"><span data-stu-id="49df3-120">**ms.assetid**: This is the GUID of the article from CAPS.</span></span> <span data-ttu-id="49df3-121">新しいマークダウン ファイルを作成する場合、[https://www.guidgenerator.com](https://www.guidgenerator.com) から GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="49df3-121">When creating a new markdown file, get a GUID from [https://www.guidgenerator.com](https://www.guidgenerator.com).</span></span> 
- <span data-ttu-id="49df3-122">**ms.prod**、**ms.service**、**ms.technology**、**ms.devlang**、**ms.topic**、**ms.tgt_pltfrm**: これらの要素で利用可能な値は、[こちら](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default)で検索できます。</span><span class="sxs-lookup"><span data-stu-id="49df3-122">**ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: Possible values for these elements can be found [here](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).</span></span>

## <a name="basic-markdown-and-gfm"></a><span data-ttu-id="49df3-123">基本的なマークダウンと GFM</span><span class="sxs-lookup"><span data-stu-id="49df3-123">Basic Markdown and GFM</span></span>

<span data-ttu-id="49df3-124">すべての基本的なマークダウンと Github Flavored Markdown がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49df3-124">All basic and Github-flavored markdown is supported.</span></span> <span data-ttu-id="49df3-125">詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49df3-125">For more information on these, see:</span></span>

- [<span data-ttu-id="49df3-126">ベースライン マークダウン構文</span><span class="sxs-lookup"><span data-stu-id="49df3-126">Baseline markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="49df3-127">Github Flavored Markdown (GFM) ドキュメント</span><span class="sxs-lookup"><span data-stu-id="49df3-127">Github-flavored markdown (GFM) documentation</span></span>](https://guides.github.com/features/mastering-markdown)

## <a name="headings"></a><span data-ttu-id="49df3-128">見出し</span><span class="sxs-lookup"><span data-stu-id="49df3-128">Headings</span></span>

<span data-ttu-id="49df3-129">第 1 レベルと第 2 レベルの見出しの例は前述のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49df3-129">Examples of first- and second-level headings are above.</span></span> 

<span data-ttu-id="49df3-130">トピックには第 1 レベルの見出しを 1 つのみ含める**必要があります**。この見出しはページ タイトルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="49df3-130">There **must** be only one first-level heading in your topic, which will be displayed as the on-page title.</span></span>  

<span data-ttu-id="49df3-131">第 2 レベルの見出しは、ページ タイトルの下の "この記事では" セクションに表示されるページ上の目次を生成します。</span><span class="sxs-lookup"><span data-stu-id="49df3-131">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="49df3-132">第 3 レベルの見出し</span><span class="sxs-lookup"><span data-stu-id="49df3-132">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="49df3-133">第 4 レベルの見出し</span><span class="sxs-lookup"><span data-stu-id="49df3-133">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="49df3-134">第 5 レベルの見出し</span><span class="sxs-lookup"><span data-stu-id="49df3-134">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="49df3-135">第 6 レベルの見出し</span><span class="sxs-lookup"><span data-stu-id="49df3-135">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="49df3-136">テキスト スタイルの設定</span><span class="sxs-lookup"><span data-stu-id="49df3-136">Text styling</span></span>

<span data-ttu-id="49df3-137">*斜体*</span><span class="sxs-lookup"><span data-stu-id="49df3-137">*Italics*</span></span> 

<span data-ttu-id="49df3-138">**太字**</span><span class="sxs-lookup"><span data-stu-id="49df3-138">**Bold**</span></span> 

<span data-ttu-id="49df3-139">~~取り消し線~~</span><span class="sxs-lookup"><span data-stu-id="49df3-139">~~Strikethrough~~</span></span>



## <a name="links"></a><span data-ttu-id="49df3-140">Links</span><span class="sxs-lookup"><span data-stu-id="49df3-140">Links</span></span>

<span data-ttu-id="49df3-141">同じリポジトリ内のマークダウン ファイルにリンクさせるには、[相対リンク](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)を使用します。</span><span class="sxs-lookup"><span data-stu-id="49df3-141">To link to a markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2).</span></span> 

- <span data-ttu-id="49df3-142">例: [Azure Rights Management とは](./understand-explore/what-is-azure-rights-management.md)</span><span class="sxs-lookup"><span data-stu-id="49df3-142">Example: [What is Azure Rights Management](./understand-explore/what-is-azure-rights-management.md)</span></span>

<span data-ttu-id="49df3-143">同じマークダウン ファイル内の見出しにリンクさせるには、公開された記事のソースを表示して見出しの ID を見つけます (例: `id="blockquote"`、あるいは `#blockquote` のように # + id を使用したリンク)。</span><span class="sxs-lookup"><span data-stu-id="49df3-143">To link to a header in the same markdown file, view the source of the published article, find the id of the head (e.g. `id="blockquote"`, and link using # + id (e.g. `#blockquote`).</span></span>

- <span data-ttu-id="49df3-144">例: [Blockquotes](#blockquote)</span><span class="sxs-lookup"><span data-stu-id="49df3-144">Example: [Blockquotes](#blockquote)</span></span>

<span data-ttu-id="49df3-145">同じリポジトリ内のマークダウン ファイルにリンクさせるには、相対リンクとハッシュタグ リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="49df3-145">To link to a header in a markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="49df3-146">例: [サインアップ プロセスの技術概要](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span><span class="sxs-lookup"><span data-stu-id="49df3-146">Example: [technical overiew of the sign-up process](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)</span></span>

<span data-ttu-id="49df3-147">外部ファイルにリンクさせるには、完全な URL をリンクに使用します。</span><span class="sxs-lookup"><span data-stu-id="49df3-147">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="49df3-148">例: [Github](http://www.github.com)</span><span class="sxs-lookup"><span data-stu-id="49df3-148">Example: [Github](http://www.github.com)</span></span>

<span data-ttu-id="49df3-149">マークダウン ファイルに URL が表示されると、クリック可能なリンクに変換されます。</span><span class="sxs-lookup"><span data-stu-id="49df3-149">If a URL appears in a markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="49df3-150">例: http://www.github.com</span><span class="sxs-lookup"><span data-stu-id="49df3-150">Example: http://www.github.com</span></span>

## <a name="lists"></a><span data-ttu-id="49df3-151">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-151">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="49df3-152">順序指定された一覧</span><span class="sxs-lookup"><span data-stu-id="49df3-152">Ordered lists</span></span>

1. <span data-ttu-id="49df3-153">この</span><span class="sxs-lookup"><span data-stu-id="49df3-153">This</span></span> 
1. <span data-ttu-id="49df3-154">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-154">Is</span></span>
1. <span data-ttu-id="49df3-155">は</span><span class="sxs-lookup"><span data-stu-id="49df3-155">An</span></span>
1. <span data-ttu-id="49df3-156">Ordered</span><span class="sxs-lookup"><span data-stu-id="49df3-156">Ordered</span></span>
1. <span data-ttu-id="49df3-157">一覧</span><span class="sxs-lookup"><span data-stu-id="49df3-157">List</span></span>  


#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="49df3-158">埋め込みリストを含む順序指定された一覧</span><span class="sxs-lookup"><span data-stu-id="49df3-158">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="49df3-159">Here</span><span class="sxs-lookup"><span data-stu-id="49df3-159">Here</span></span>
1. <span data-ttu-id="49df3-160">こちら</span><span class="sxs-lookup"><span data-stu-id="49df3-160">comes</span></span>
1. <span data-ttu-id="49df3-161">は</span><span class="sxs-lookup"><span data-stu-id="49df3-161">an</span></span>
1. <span data-ttu-id="49df3-162">埋め込まれた</span><span class="sxs-lookup"><span data-stu-id="49df3-162">embedded</span></span>
    1. <span data-ttu-id="49df3-163">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="49df3-163">Miss Scarlett</span></span>
    1. <span data-ttu-id="49df3-164">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="49df3-164">Professor Plum</span></span>
1. <span data-ttu-id="49df3-165">順序指定された</span><span class="sxs-lookup"><span data-stu-id="49df3-165">ordered</span></span>
1. <span data-ttu-id="49df3-166">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-166">list</span></span>


### <a name="unordered-lists"></a><span data-ttu-id="49df3-167">順序指定されていない一覧</span><span class="sxs-lookup"><span data-stu-id="49df3-167">Unordered Lists</span></span>

- <span data-ttu-id="49df3-168">この</span><span class="sxs-lookup"><span data-stu-id="49df3-168">This</span></span>
- <span data-ttu-id="49df3-169">次の文字列と同じ:</span><span class="sxs-lookup"><span data-stu-id="49df3-169">is</span></span>
- <span data-ttu-id="49df3-170">a</span><span class="sxs-lookup"><span data-stu-id="49df3-170">a</span></span>
- <span data-ttu-id="49df3-171">箇条書き</span><span class="sxs-lookup"><span data-stu-id="49df3-171">bulleted</span></span>
- <span data-ttu-id="49df3-172">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-172">list</span></span>


##### <a name="unordered-list-with-an-embedded-lists"></a><span data-ttu-id="49df3-173">埋め込みリストを含む順序指定されていない一覧</span><span class="sxs-lookup"><span data-stu-id="49df3-173">Unordered list with an embedded lists</span></span>

- <span data-ttu-id="49df3-174">この</span><span class="sxs-lookup"><span data-stu-id="49df3-174">This</span></span> 
- <span data-ttu-id="49df3-175">箇条書き</span><span class="sxs-lookup"><span data-stu-id="49df3-175">bulleted</span></span> 
- <span data-ttu-id="49df3-176">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-176">list</span></span>
    - <span data-ttu-id="49df3-177">Mrs. Peacock</span><span class="sxs-lookup"><span data-stu-id="49df3-177">Mrs. Peacock</span></span>
    - <span data-ttu-id="49df3-178">Mr. Green</span><span class="sxs-lookup"><span data-stu-id="49df3-178">Mr. Green</span></span>
- <span data-ttu-id="49df3-179">次の値を含む</span><span class="sxs-lookup"><span data-stu-id="49df3-179">contains</span></span>  
- <span data-ttu-id="49df3-180">その他</span><span class="sxs-lookup"><span data-stu-id="49df3-180">other</span></span>
    1. <span data-ttu-id="49df3-181">Colonel Mustard</span><span class="sxs-lookup"><span data-stu-id="49df3-181">Colonel Mustard</span></span>
    1. <span data-ttu-id="49df3-182">Mrs. White</span><span class="sxs-lookup"><span data-stu-id="49df3-182">Mrs. White</span></span>
- <span data-ttu-id="49df3-183">リスト</span><span class="sxs-lookup"><span data-stu-id="49df3-183">lists</span></span>


## <a name="horizontal-rule"></a><span data-ttu-id="49df3-184">水平線</span><span class="sxs-lookup"><span data-stu-id="49df3-184">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="49df3-185">テーブル</span><span class="sxs-lookup"><span data-stu-id="49df3-185">Tables</span></span>

| <span data-ttu-id="49df3-186">テーブル</span><span class="sxs-lookup"><span data-stu-id="49df3-186">Tables</span></span>        | <span data-ttu-id="49df3-187">も</span><span class="sxs-lookup"><span data-stu-id="49df3-187">Are</span></span>           | <span data-ttu-id="49df3-188">作れます</span><span class="sxs-lookup"><span data-stu-id="49df3-188">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="49df3-189">col 3 は</span><span class="sxs-lookup"><span data-stu-id="49df3-189">col 3 is</span></span>      | <span data-ttu-id="49df3-190">右揃え</span><span class="sxs-lookup"><span data-stu-id="49df3-190">right-aligned</span></span> | <span data-ttu-id="49df3-191">$1600</span><span class="sxs-lookup"><span data-stu-id="49df3-191">$1600</span></span> |
| <span data-ttu-id="49df3-192">col 2 は</span><span class="sxs-lookup"><span data-stu-id="49df3-192">col 2 is</span></span>      | <span data-ttu-id="49df3-193">中央揃え</span><span class="sxs-lookup"><span data-stu-id="49df3-193">centered</span></span>      |   <span data-ttu-id="49df3-194">$12</span><span class="sxs-lookup"><span data-stu-id="49df3-194">$12</span></span> |
| <span data-ttu-id="49df3-195">col 1 が既定</span><span class="sxs-lookup"><span data-stu-id="49df3-195">col 1 is default</span></span> | <span data-ttu-id="49df3-196">左揃え</span><span class="sxs-lookup"><span data-stu-id="49df3-196">left-aligned</span></span>     |    <span data-ttu-id="49df3-197">$1</span><span class="sxs-lookup"><span data-stu-id="49df3-197">$1</span></span> |


## <a name="code"></a><span data-ttu-id="49df3-198">コード</span><span class="sxs-lookup"><span data-stu-id="49df3-198">Code</span></span>

### <a name="codeblock"></a><span data-ttu-id="49df3-199">コードブロック</span><span class="sxs-lookup"><span data-stu-id="49df3-199">Codeblock</span></span>

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a><span data-ttu-id="49df3-200">インライン コード</span><span class="sxs-lookup"><span data-stu-id="49df3-200">In-line code</span></span>

<span data-ttu-id="49df3-201">これは `in-line code` の例です。</span><span class="sxs-lookup"><span data-stu-id="49df3-201">This is an example of `in-line code`.</span></span>

## <a name="blockquotes"></a><span data-ttu-id="49df3-202">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="49df3-202">Blockquotes</span></span>

> <span data-ttu-id="49df3-203">干ばつは 1000 万年も続き、恐竜の治世はとうに終わっていた。</span><span class="sxs-lookup"><span data-stu-id="49df3-203">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="49df3-204">ここ、赤道地帯、いずれアフリカと呼ばれるようになる大陸では、生存の戦いは熾烈なクライマックスを迎えていたが、勝者はまだ現れていなかった。</span><span class="sxs-lookup"><span data-stu-id="49df3-204">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="49df3-205">この乾燥した不毛の大地では、小さなもの、すばしこいもの、どう猛なもののみ栄えることができ、また生存の望みをつなぐことができた。</span><span class="sxs-lookup"><span data-stu-id="49df3-205">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="49df3-206">画像</span><span class="sxs-lookup"><span data-stu-id="49df3-206">Images</span></span>

### <a name="static-image"></a><span data-ttu-id="49df3-207">静止画像</span><span class="sxs-lookup"><span data-stu-id="49df3-207">Static Image</span></span>

![これは代替テキストです](./media/AzRMS_elements.png)

### <a name="linked-image"></a><span data-ttu-id="49df3-209">リンクされた画像</span><span class="sxs-lookup"><span data-stu-id="49df3-209">Linked Image</span></span>

<span data-ttu-id="49df3-210">[![リンク画像のテキスト](./media/AzRMS_elements.png)](https://azure.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="49df3-210">[![alt text for linked image](./media/AzRMS_elements.png)](https://azure.microsoft.com)</span></span> 

### <a name="animated-gif"></a><span data-ttu-id="49df3-211">アニメーション GIF</span><span class="sxs-lookup"><span data-stu-id="49df3-211">Animated gif</span></span>

![アニメーション GIF](./media/hololens.gif)

## <a name="alerts"></a><span data-ttu-id="49df3-213">アラート</span><span class="sxs-lookup"><span data-stu-id="49df3-213">Alerts</span></span>

### <a name="note"></a><span data-ttu-id="49df3-214">メモ</span><span class="sxs-lookup"><span data-stu-id="49df3-214">Note</span></span>

> [!NOTE]
> <span data-ttu-id="49df3-215">これは注記です</span><span class="sxs-lookup"><span data-stu-id="49df3-215">This is NOTE</span></span>

### <a name="warning"></a><span data-ttu-id="49df3-216">警告</span><span class="sxs-lookup"><span data-stu-id="49df3-216">Warning</span></span>

> [!WARNING]
> <span data-ttu-id="49df3-217">これは警告です</span><span class="sxs-lookup"><span data-stu-id="49df3-217">This is WARNING</span></span>

### <a name="tip"></a><span data-ttu-id="49df3-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="49df3-218">Tip</span></span>

> [!TIP]
> <span data-ttu-id="49df3-219">これはヒントです</span><span class="sxs-lookup"><span data-stu-id="49df3-219">This is TIP</span></span>

### <a name="important"></a><span data-ttu-id="49df3-220">重要</span><span class="sxs-lookup"><span data-stu-id="49df3-220">Important</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49df3-221">これは重要事項です</span><span class="sxs-lookup"><span data-stu-id="49df3-221">This is IMPORTANT</span></span>

## <a name="videos"></a><span data-ttu-id="49df3-222">ビデオ</span><span class="sxs-lookup"><span data-stu-id="49df3-222">Videos</span></span>

### <a name="channel-9"></a><span data-ttu-id="49df3-223">Channel 9</span><span class="sxs-lookup"><span data-stu-id="49df3-223">Channel 9</span></span>

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a><span data-ttu-id="49df3-224">YouTube</span><span class="sxs-lookup"><span data-stu-id="49df3-224">Youtube</span></span>

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extentions"></a><span data-ttu-id="49df3-225">docs.ms 拡張子</span><span class="sxs-lookup"><span data-stu-id="49df3-225">docs.ms extentions</span></span>

### <a name="button"></a><span data-ttu-id="49df3-226">Button</span><span class="sxs-lookup"><span data-stu-id="49df3-226">Button</span></span>

> [!div class="button"]
[<span data-ttu-id="49df3-227">ボタン リンク</span><span class="sxs-lookup"><span data-stu-id="49df3-227">button links</span></span>](/rights-management)

### <a name="selector"></a><span data-ttu-id="49df3-228">セレクター</span><span class="sxs-lookup"><span data-stu-id="49df3-228">Selector</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="49df3-229">foo</span><span class="sxs-lookup"><span data-stu-id="49df3-229">foo</span></span>](/rights-management/template.md)
- [<span data-ttu-id="49df3-230">bar</span><span class="sxs-lookup"><span data-stu-id="49df3-230">bar</span></span>](/rights-management/scratch.md)

### <a name="step-by-step"></a><span data-ttu-id="49df3-231">ステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="49df3-231">Step-By-Step</span></span>

>[!div class="step-by-step"]
[前へ](https://www.example.com)
[次へ](https://www.example.com)