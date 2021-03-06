---
title: Microsoft 商業マーケットプレース用に新しい SaaS プランを作成する
description: Microsoft パートナー センターの Microsoft 商業マーケットプレース プログラムを使用して、Microsoft AppSource、Azure Marketplace、またはクラウド ソリューション プロバイダー (CSP) プログラムでリスト登録または販売を行うために新しいサービスとしてのソフトウェア (SaaS) プランを作成する方法。
author: dsindona
ms.author: dsindona
ms.service: marketplace
ms.subservice: partnercenter-marketplace-publisher
ms.topic: conceptual
ms.date: 05/01/2020
ms.openlocfilehash: b85846419ce5f6cd4093e198d83240817c95754a
ms.sourcegitcommit: 999ccaf74347605e32505cbcfd6121163560a4ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82983059"
---
# <a name="create-a-new-saas-offer-in-the-commercial-marketplace"></a>コマーシャル マーケットプレースで新しい SaaS オファーを作成する

コマーシャル マーケットプレースでサービスとしてのソフトウェア (SaaS) オファーの作成を開始するには、必ず、最初に[パートナー センター アカウントを作成](./create-account.md)し、 **[概要]** タブを選択した状態で[コマーシャル マーケットプレース ダッシュボード](https://partner.microsoft.com/dashboard/commercial-marketplace/offers)を開いてください。

## <a name="create-a-new-offer"></a>新しいオファーを作成する

1. [パートナー センター](https://partner.microsoft.com/dashboard/home)にサインインします。
2. 左側のナビゲーション メニューで、 **[コマーシャル マーケットプレース]**  >  **[概要]** の順に選択します。
3. [概要] ページで、 **[+ 新しいオファー]**  >  **[サービスとしてのソフトウェア]** の順に選択します。

   ![左側のナビゲーション メニューの画像。](./media/new-offer-saas.png)

> [!NOTE]
> オファーを公開した後にパートナー センターで編集した内容は、オファーの再公開後にのみネットショップに表示されます。 変更後は必ず再公開してください。

## <a name="new-offer"></a>新しいプラン

**[オファー ID]** を入力します。 これは、ご自分のアカウント内の各オファーに対する一意の識別子です。

- この ID は、マーケットプレース オファーの Web アドレスと Azure Resource Manager テンプレート (該当する場合) で顧客に表示されます。
- 使用できるのは小文字と数字だけです。 ハイフンとアンダースコアを含めることができますが、スペースは使用できず、文字数は 50 文字に制限されています。 たとえば、ここに「**test-offer-1**」と入力すると、オファーの Web アドレスは `https://azuremarketplace.microsoft.com/marketplace/../test-offer-1` になります。
- **[作成]** を選択した後で、オファー ID を変更することはできません。

**[オファーのエイリアス]** を入力します。 これは、パートナー センター内でオファーに使用される名前です。

- この名前はマーケットプレースでは使用されず、顧客に表示されるオファー名やその他の値とは異なります。
- **[作成]** を選択した後で、オファーの別名を変更することはできません。

<!---
![Offer overview on Partner Center](./media/commercial-marketplace-offer-overview.png)
-->

**[作成]** を選択してオファーを生成し、続行します。

## <a name="offer-overview"></a>オファーの概要

**[発行の状態]** には、このオファーを公開するために必要な手順と、それぞれの手順の完了にかかる時間が視覚的に表示されます。 未完了の公開手順のアイコンは灰色で表示されます。

**[オファーの概要]** メニューには、このオファーに対する操作を実行するためのリンクの一覧が含まれています。 この一覧の操作は、お客様が自分のオファーに対して行う選択に基づいて変わります。  

- オファーがドラフトの場合 - [ドラフトの削除]
- オファーが公開中の場合 - [Stop sell offer]\(オファーの販売の停止\)
- オファーがプレビューの場合 - [一般公開する]
- 公開元のサインアウトを完了していない場合 - [公開の取り消し]

## <a name="offer-setup"></a>オファーのセットアップ

このページでは、次の情報を求められます。

- **Microsoft を介して販売しますか?** (はい/いいえ)
    - **はい**。Microsoft を通じて販売し、Microsoft にトランザクションを代行してもらいます
    - **いいえ**。Marketplace はオファーの一覧表示にのみ使用して、トランザクションは個別に処理します。

### <a name="sell-through-microsoft"></a>Microsoft を通じた販売

Microsoft を通じた販売では、顧客による発見率と購入率が高くなるほか、Microsoft がお客様の代わりにマーケットプレースのトランザクションをホストできます。また、グローバルに利用可能な Microsoft のコマース機能が利用されます。

#### <a name="saas-offer-requirements"></a>SaaS オファーの要件

パートナー センターの商業マーケットプレースを使用してサービスとしてのソフトウェア (SaaS) オファーをリスト登録するには、次の基準を満たす必要があります。

- オファーで ID の管理と認証に [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) が使用されている必要があります。
- Azure Marketplace と統合するために [SaaS Fulfillment API](https://docs.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-api-v2) シリーズがオファーで使用されている必要があります。

#### <a name="saas-pricing-and-billing-options"></a>SaaS の価格と課金のオプション

SaaS ソリューションが公開元の Azure サブスクリプションで実行されている場合、お客様が支払うライセンス料金には、ソフトウェアがデプロイされるインフラストラクチャのコストが含まれます。 Azure インフラストラクチャの使用量は、お客様 (パートナー) が直接管理し、お客様に直接課金されます。 実際のインフラストラクチャの使用料金は、顧客には提示されません。 公開元は、Azure インフラストラクチャの使用料をソフトウェア ライセンス料金にバンドルする必要があります。 

SaaS オファーでは、定額料金、ユーザー単位、または従量制課金サービスを使用する従量課金に基づいた月次または年次請求がサポートされます。 Microsoft の商用マーケットプレースは代理店モデルで運営されます。そのため、公開元で価格が設定され、Microsoft からお客様に請求され、公開元に収益が支払われると同時に、代理店手数料が減額されます。

これは、代理店モデルについて説明するための、コストと支払いの内訳例です。

|**ライセンス コスト**|**1 か月あたり $100**|
|:---|:---|
|Azure 使用コスト (D1/1 コア)|顧客ではなく公開元に直接課金されます|
|顧客は Microsoft から請求されます|1 か月あたり $100.00 (公開元は、ライセンス料金の中で、発生したパススルー インフラストラクチャ コストを考慮する必要があります)|

|**Microsoft が請求**|**1 か月あたり $100**|
|:---|:---|
|Microsoft は、ライセンス コストの 80% をパブリッシャーに支払います <br>**対象となる SaaS アプリの場合、Microsoft がライセンス コストの 90% を支払います*|1 か月あたり $80.00 <br>*$* 1 か月あたり $90.00*|

- この例では、Microsoft はソフトウェア ライセンスについてお客様に $100.00 を請求し、公開元に $80.00 を支払います。
- **Marketplace サービス手数料の減額**の対象となっているパートナーには、2019 年 5 月から 2020 年 6 月まで、SaaS オファーに対するトランザクション料金の減額が表示されます。 このシナリオでは、Microsoft はソフトウェア ライセンスに $100.00 を課金し、公開元に $90.00 を支払います。

> [!NOTE]
> **Marketplace サービス料金の減額** – Microsoft のコマーシャル マーケットプレースでお客様が公開する特定の SaaS オファーについて、Microsoft は、Marketplace サービス料金を 20% (Microsoft 公開元契約の説明に従う) から 10% に減額します。 お客様のオファーが対象となるには、少なくとも 1 つのオファーが、IP 共同販売準備完了または IP 共同販売優先のどちらかとして、Microsoft によって指定されている必要があります。 この Marketplace サービス料金の減額をある月に受け取るには、各カレンダー月の月末までに少なくとも 5 営業日、適格性を満たす必要があります。  Marketplace サービス料金の減額は、VM、マネージド アプリ、または Microsoft の商業マーケットプレースを通じて公開された他の製品には適用されません。 Marketplace サービス料金の減額は、2019 年 5 月 1 日から 2020 年 6 月 30日までに Microsoft によって収集されるライセンス料金について、対象となるオファーでのみ利用できます。 その後は、Marketplace サービス料金は通常の金額に戻ります。

### <a name="list-through-microsoft"></a>Microsoft を通じたリスト登録

マーケットプレースのリスト登録を作成することで、Microsoft と共にビジネスをプロモーションします。 Microsoft を通じてオファーのリスト登録だけ行って、トランザクションは行わないことを選択すると、Microsoft はソフトウェア ライセンスのトランザクションに直接関与しません。 関連するトランザクション料金は発生せず、公開元は顧客から収集したソフトウェア ライセンス料金を 100% 確保できます。 ただし、ソフトウェア ライセンス トランザクションのすべての側面 (受注、調達、使用状況測定、課金、請求、支払い、収集を含むが、これらに限定されない) について、公開元がサポートを担当します。

<!-- - **How do you want potential customers to interact with this listing offer?** -->

#### <a name="get-it-now-free"></a>Get it now (今すぐ入手する) (無料)

有効なアドレス (*http* または *https* で始まる) を提供して、顧客に無料のオファーを一覧で示します。顧客は、そのアドレスから、[Azure Active Directory (Azure AD) を使用したワンクリック認証](https://docs.microsoft.com/azure/marketplace/marketplace-saas-applications-technical-publishing-guide#using-azure-active-directory-to-enable-trials)で試用版を入手することができます。 たとえば、「 `https://contoso.com/saas-app` 」のように入力します。

#### <a name="free-trial-listing"></a>Free trial (無料試用版) (一覧)

有効なアドレス (*http* または *https* で始まる) を提供して、無料試用版へのリンクとして顧客にオファーを一覧で示します。顧客は、そのアドレスから、[Azure Active Directory (Azure AD) を使用したワンクリック認証](https://docs.microsoft.com/azure/marketplace/marketplace-saas-applications-technical-publishing-guide#using-azure-active-directory-to-enable-trials)で試用版を入手することができます。 たとえば、「 `https://contoso.com/trial/saas-app` 」のように入力します。 オファー登録情報の無料試用版がご利用のサービスによって作成、管理、および構成され、Microsoft によって管理されるサブスクリプションはありません。

> [!NOTE]
> 試用版リンクからアプリケーションが受信するトークンは、そのアプリのアカウント作成を自動化するためのユーザー情報を Azure AD を介して取得するためだけに使用できます。 このトークンを使用した認証には、Microsoft アカウント (MSA) はサポートされません。

#### <a name="contact-me"></a>[Contact me (お問い合わせ)]

顧客関係管理 (CRM) システムに接続して、顧客の連絡先情報を収集します。 顧客は、自分の情報を共有する許可を求められます。 これらの顧客の詳細は、オファーの名前と ID のほか、顧客がオファーを見つけたマーケットプレース ソースと一緒に、お客様が構成した CRM システムに送信されます。 CRM の構成の詳細については、「[リード管理の接続](#connect-lead-management)」を参照してください。

#### <a name="example-marketplace-offer-listing"></a>マーケットプレース オファーの一覧表示の例

![マーケットプレース オファーの一覧表示の例 (説明付き)](./media/marketplace-offer.svg)

## <a name="enable-a-test-drive"></a>体験版を有効にする

体験版は、購入前に試用するオプションを提供することで潜在顧客へのオファーを披露し、その結果、コンバージョンが増加し、見込みの高いリードが生成される優れた方法です。 [体験版の詳細を確認してください](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/test-drive/what-is-test-drive)。

一定期間、体験版を有効にするには、 **[体験版を有効にする]** チェック ボックスをオンにします。 オファーから体験版を削除するには、このチェック ボックスをオフにします。

詳細については、[コマーシャル マーケットプレースでのオファーの体験版](https://docs.microsoft.com/azure/marketplace/partner-center-portal/test-drive)に関するページを参照してください。

### <a name="test-drive-resources"></a>体験版リソース

- [マーケティングのベスト プラクティス](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/test-drive/marketing-and-best-practices)
- [技術的なベスト プラクティス](https://github.com/Azure/AzureTestDrive/wiki/Test-Drive-Best-Practices)
- [概要](https://assetsprod.microsoft.com/mpn/azure-marketplace-appsource-test-drives.pdf) (PDF、ポップアップ ブロックがオフになっていることを確認してください)

### <a name="connect-lead-management"></a>リード管理の接続

[!INCLUDE [Connect lead management](./includes/connect-lead-management-a.md)]

#### <a name="additional-lead-management-resources"></a>リード管理に関するその他のリソース
- [リード管理に関する FAQ](https://docs.microsoft.com/azure/marketplace/lead-management-for-cloud-marketplace#frequently-asked-questions)
- [一般的なリード構成エラー](https://docs.microsoft.com/azure/marketplace/lead-management-for-cloud-marketplace#common-lead-configuration-errors-during-publishing-on-cloud-partner-portal)
- [1 ページにまとめたリード管理の概要](https://assetsprod.microsoft.com/mpn/cloud-marketplace-lead-management.pdf)

続行する前に、 **[下書きの保存]** を選択します。

## <a name="properties"></a>Properties

このページでは、マーケットプレース上でオファーをグループ分けするために使用されるカテゴリと業界、オファーのための法的契約、アプリのバージョンを定義するよう求められます。

### <a name="category"></a>カテゴリ

オファーを適切なマーケットプレース検索領域にグループ化するには、少なくとも 1 つ、最大 3 つのカテゴリを選択します。 オファーがこれらのカテゴリにどのように対応しているかを、オファーの説明に記載します。

### <a name="industries"></a>業界

[!INCLUDE [Industry Taxonomy](./includes/industry-taxonomy.md)]

### <a name="app-version"></a>アプリのバージョン

このフィールドは省略可能であり、オファーのバージョン番号を識別するために AppSource マーケットプレースで使用されます。

### <a name="standard-contract-for-the-microsoft-commercial-marketplace"></a>Microsoft 商業マーケットプレースの標準契約

Microsoft では、標準契約テンプレートを提供しています。

- **[Use the Standard Contract for the Microsoft commercial marketplace?]\(Microsoft 商業マーケットプレース向け標準契約を使用しますか?\)**

お客様の調達プロセスを簡素化し、ソフトウェア ベンダーの法的な複雑さを軽減するために、Microsoft では、マーケットプレースでの取引の促進に役立つ Microsoft 商業マーケットプレースの標準契約を用意しています。 商業マーケットプレース パブリッシャーは、カスタムの使用条件を作成するのではなく、標準契約の下で各自のソフトウェアを提供することを選択でき、お客様はそれを詳細に調べて 1 回同意するだけで済みます。 標準契約は https://go.microsoft.com/fwlink/?linkid=2041178 で見つけることができます。

[Use the Standard Contract for the commercial marketplace] (商業マーケットプレース向け標準契約を使用する) チェック ボックスを選択することで、独自のカスタムの使用条件を提供する代わりに標準契約を使用することを選択できます。

![標準契約チェック ボックスの使用](./media/use-standard-contract.png)

> [!NOTE]
> Microsoft 商業マーケットプレースの標準契約を使用してオファーを発行した後に、独自のカスタムの使用条件を使用することはできません。 これは "または" のシナリオです。 ソリューションは、標準契約**または**独自の使用条件のどちらかの下で提供されます。 標準契約の使用条件を変更したい場合は、Standard Contract Amendments (標準契約の修正) を使用して行うことができます。

#### <a name="standard-contract-amendments"></a>Standard Contract Amendments (標準契約の修正)

Standard Contract Amendments (標準契約の修正) を使用すると、発行元は簡易さのために標準契約条件を選択し、各自の製品またはビジネスに合わせて使用条件をカスタマイズすることができます。 Microsoft 標準契約を既に確認し、同意している場合、お客様に必要なことは契約の修正の確認のみです。

商業マーケットプレース パブリッシャーが使用できる修正には、次の 2 種類があります。

- Universal Amendments (ユニバーサル修正):これらの修正は、すべてのお客様の標準契約に例外なく適用されます。 ユニバーサル修正は、購入フローにあるオファーのすべてのお客様に示されます。 お客様は、提供されるオファーを使用する前に、標準契約の使用条件とこの修正に同意する必要があります。
- Custom Amendments (カスタム修正):これらの修正は、Azure テナント ID を通して特定のお客様のみを対象にした、標準契約への特殊な修正です。 発行元は、対象にするテナントを選択できます。 カスタム修正の使用条件は、オファーの購入フローでこのテナントのお客様にのみ示されます。  お客様は、提供されるオファーを使用する前に、標準契約の使用条件とこの修正に同意する必要があります。

>[!NOTE]
> これらの 2 種類の修正は、互いに重なり合っています。 カスタム修正の対象となるお客様には、購入中に標準契約へのユニバーサル修正も示されます。

**[Universal amendment terms to the Standard Contract for Microsoft's commercial marketplace]\(Microsoft のコマーシャル マーケットプレース向け標準契約へのユニバーサル変更条件\)** - このボックスには、ユニバーサルな修正条項を入力します。 オファーごとに 1 つのユニバーサル修正を提供できます。 このボックスに入力できる文字数は無制限です。 これらの条項は、AppSource、Azure Marketplace、Azure portal で、発見と購入のフロー中に顧客に表示されます。

**[Custom amendment terms to the Standard Contract for Microsoft's commercial marketplace]\(Microsoft のコマーシャル マーケットプレース向け標準契約のカスタム変更条件\)** - まず、 **[Add custom amendment terms]\(カスタム変更条件の追加\)** を選択します。 オファーごとに 10 件までのカスタム修正条項を提供できます。

- **[カスタム変更条件]** – カスタム変更条件をカスタム変更条件ボックスに入力します。 このボックスに入力できる文字数は無制限です。 Azure portal では、これらのカスタム修正条項に対して指定したテナント ID の顧客にのみ、オファーの購入フローでカスタム修正条項が提示されます。  
- **[テナント ID]** (必須) – それぞれのカスタム修正で対象にできるテナント ID は 20 個までです。 カスタム修正を追加する場合、少なくとも 1 つのテナント ID を指定する必要があります。 テナント ID は Azure で顧客を識別します。 この ID は顧客に問い合わせることができ、顧客は portal.azure.com > [Azure Active Directory] > [プロパティ] にアクセスして ID を確認できます。 ディレクトリ ID の値はテナント ID です (例: 50c464d3-4930-494c-963c-1e951d15360e)。 [[What is my Microsoft Azure and Office 365 tenant ID?]\(Microsoft Azure および Office 365 テナント ID の確認\)](https://www.whatismytenantid.com) で、顧客のドメイン名 URL を使用して顧客の組織のテナント ID を検索することもできます。
- **[説明]** (省略可能) – 必要に応じて、修正の対象となる顧客を特定しやすくするために、テナント ID のわかりやすい説明を入力します。

#### <a name="terms-and-conditions"></a>使用条件

独自のカスタムの使用条件を指定する場合は、使用条件フィールドに入力することもできます。 このフィールドには最大で 10,000 文字のテキストを入力できます。 それよりも長い説明が使用条件に必要な場合は、使用条件を確認できるサイトの URL リンクのみをこのフィールドに入力します。 これはアクティブなリンクとして顧客に表示されます。

顧客は、オファーを試す前にこれらの条件を承諾する必要があります。

続行する前に、 **[下書きの保存]** を選択します。

## <a name="offer-listing"></a>オファーのリスト登録

このページには、お客様のオファーが利用可能な言語 (と市場) が表示されます。現在、利用可能な唯一の場所は英語 (米国) です。 さらに、このページには、言語固有のリスト登録の状態と、それが追加された日付および時刻が表示されます。 言語および市場ごとにマーケットプレースの詳細 (オファーの名前、説明、検索語句など) を定義する必要があります。

> [!NOTE]
> オファー登録情報のコンテンツ (オファーの説明、ドキュメント、スクリーンショット、使用条件、プライバシーポリシーなど) は、オファーの説明が "このアプリケーションは、[英語以外の言語] でのみ利用可能です。" という文言で始まっていれば英語である必要はありません。 また、オファー登録情報のコンテンツで使用されている言語以外の言語でコンテンツを提供するための*役に立つリンクの URL* を提供することもできます。

### <a name="offer-listings"></a>オファーの一覧情報

オファーの説明やマーケティング資産など、マーケットプレースで表示される詳細を入力します。

- **[名前]** (必須) – ここで定義した名前は、お客様が選択したマーケットプレース上でオファーのリスト登録のタイトルとして表示されます。 名前は、前の **[新しいオファー]** のエントリに基づいて事前入力されます。 この名前は商標登録されている場合があります。 これは、絵文字 (商標および著作権マークの場合を除く) を含むことができず、50 文字以下にする必要があります。
- **[概要]** (必須) – マーケットプレースのリスト登録の検索結果で使用される、お客様のオファーの簡単な説明を入力します。 このフィールドには、最大で 100 文字のテキストを入力できます。
- **[説明]** (必須) – マーケットプレースのリスト登録の概要で表示される、お客様のオファーの説明を入力します。 価値提案、主なメリット、カテゴリまたは業界との関連性、アプリ内の購入機会、必要な情報開示、詳細情報へのリンクを含めることを検討してください。 このフィールドには、マークアップを含めて最大で 3,000 文字のテキストを入力できます。 その他のヒントについては、「[人の心をつかむアプリの説明を書く](https://docs.microsoft.com/windows/uwp/publish/write-a-great-app-description)」を参照してください。
- **[検索キーワード]** – マーケットプレースで顧客がお客様のオファーを見つけるために使用できる検索キーワードを最大 3 つ入力します。
- **[作業を開始するための手順]** (必須) – お客様のアプリを構成して使用を開始する方法を潜在顧客に対して説明します。  このクイック スタートには、より詳細なオンライン ドキュメントへのリンクを含めることができます。 このフィールドには、最大で 3,000 文字のテキストを入力できます。

#### <a name="description"></a>**説明**

このフィールドは必須です。 **[説明]** に含める項目は次のとおりです。

* 説明の先頭の数文で、オファーの価値提案を明確に説明します。  
* 先頭の数文は、検索エンジンの結果に表示される可能性があることを留意してください。  
* 特徴や機能に頼って製品を販売しようとせずに、 提供する価値に焦点を当ててください。  
* できるだけ業界固有の語彙や利益に基づく表現を使用します。

価値提案の中心の要素には、以下を含めるようにします。

* 製品の説明
* 製品から利益を得られるユーザーの種類
* 製品が対応する顧客のニーズや問題

オファーの説明をより魅力的なものにするには、リッチ テキスト エディターを使用して書式設定を適用してください。

![リッチ テキスト エディターの使用](./media/rich-text-editor.png)

| <center>テキストの形式を変更する | <center>箇条書きまたは段落番号を追加します | <center>テキスト インデントを追加または削除する |
| --- | --- | --- |
| <center>![リッチ テキスト エディターを使用してテキスト形式を変更する](./media/text-editor3.png) |  <center>![リッチ テキスト エディターを使用したリストの追加](./media/text-editor4.png) |  <center>![リッチ テキスト エディターを使用してインデントを設定する](./media/text-editor5.png) |

#### <a name="links"></a>リンク

- **[プライバシー ポリシー]** (必須) – お客様の組織のプライバシー ポリシーへのリンク。 プライバシーに関する法律および規制にアプリが準拠していることを保証し、有効なプライバシー ポリシーを提供する責任があります。
- **[CSP プログラムのマーケティング資料]** (省略可能) – オファーを[クラウド ソリューション プロバイダー (CSP)](https://docs.microsoft.com/azure/marketplace/cloud-solution-providers) プログラムに拡張する場合、マーケティング資料へのリンクを入力します。 CSP では、CSP パートナーがお客様のオファーのバンドル、宣伝、再販を行えるようになり、オファーの対象となる顧客の範囲が広がります。 これらのリセラーには、お客様のオファーを宣伝するための資料へのアクセスが必要になります。 詳細については、「[Go-To-Market サービス](https://partner.microsoft.com/reach-customers/gtm)」を参照してください。
- **[役に立つリンク]** (省略可能) – **タイトル**と **URL** を入力することで表示される、お客様のアプリまたは関連サービスに関する省略可能な補助的オンライン ドキュメント。 **+ [URL の追加]** をクリックして、その他の役に立つリンクを追加します。

#### <a name="contact-information"></a>連絡先情報

- **[連絡先]** – 顧客の連絡先ごとに、従業員の**名前**、**電話番号**、および**メール** アドレスを指定します (これらは一般公開され "*ません*")。 **サポートの連絡先**グループには、**サポート URL** が必要です (これは一般公開され "*ます*")。

    - **[サポートの連絡先]** (必須) – サポートに関する一般的な質問用です。
    - **[エンジニアリングの連絡先]** (必須) - 技術的な質問用です。
    - **[Channel Manager contact]\(チャネル マネージャーの連絡先\)** (必須) – リセラーからの CSP プログラムに関する質問用です。

#### <a name="files-and-images"></a>ファイルと画像

- **[ドキュメント]** (必須) – お客様のオファーに関するマーケティング ドキュメント (PDF 形式) を追加します。オファーごとに少なくとも 1 つ、最大で 3 つのドキュメントを指定します。
- **[画像]** (省略可能) – オファーのロゴ画像はマーケットプレース全体のさまざまな場所に表示される可能性があるため、PNG 形式で以下のピクセル サイズが必要になります。

    - **小** (48 x 48、必須)
    - **中** (90 x 90、必須)
    - **大** (216 x 216、必須)
    - **ワイド** (255 x 115)
    - **ヒーロー** (815 x 290)

- **[スクリーンショット]** (必須) – お客様のオファーについて説明しているスクリーンショットを追加します。 最大 5 つのスクリーンショットを追加できます。サイズは 1,280 x 720 ピクセルにする必要があります。 すべての画像は .PNG 形式である必要があります。
- **[ビデオ]** (省略可能) – お客様のオファーについて説明しているビデオへのリンクを追加します。 顧客へのオファーと共に表示される YouTube や Vimeo のビデオへのリンクを使用できます。 また、ビデオのサムネイル画像を入力する必要があります。PNG 形式で、サイズは 1,280 x 720 ピクセルにします。 オファーごとに最大 4 つのビデオを表示できます。

>[!NOTE]
>ファイルのアップロードで問題が発生した場合は、パートナー センターで使用されている https://upload.xboxlive.com サービスがローカル ネットワークでブロックされていないことを確認してください。

#### <a name="additional-marketplace-listing-resources"></a>マーケットプレースのリスト登録に関するその他のリソース

- [マーケットプレース オファーのリスト登録に関するベスト プラクティス](https://docs.microsoft.com/azure/marketplace/gtm-offer-listing-best-practices)

続行する前に、 **[下書きの保存]** を選択します。

## <a name="preview-audience"></a>プレビュー対象ユーザー

このページでは、マーケットプレースの幅広い対象ユーザーに公開する前にオファーをリリースする、限定的な**プレビュー対象ユーザー**を定義します。

> [!IMPORTANT]
> プレビューで自分のオファーを確認した後、 **[一般公開する]** を選択して、マーケットプレースのパブリック対象ユーザーに対してオファーを一般公開できるようにします。

1 行あたり 1 つの AAD または MSA アカウント メールと、必要に応じて説明を追加します。

既存の Microsoft アカウント (MSA) または Azure Active Directory アカウント上で一般公開前にプランを検証できるように、最大で 10 個のメール アドレスを手動で追加します (CSV ファイルをアップロードする場合は 20 個まで)。 これらのアカウントを追加することで、マーケットプレースに公開される前のオファーへのプレビュー アクセスを許可される対象ユーザーを定義します。 オファーが既に公開されている場合も、オファーの変更や更新をテストするためにプレビュー対象ユーザーを定義することができます。

> [!NOTE]
> プレビュー対象ユーザーはプライベート対象ユーザーとは異なります。 プレビュー対象ユーザーは、マーケットプレースで一般公開される "_前に_" オファーにアクセスすることを許可されます。 また、プランを作成してそれをプライベート対象ユーザーだけに公開することもできます。 **[プランのリスト]** タブでは、 **[This is a private plan]\(これはプライベート プランです\)** チェック ボックスを使用してプライベート対象ユーザーを定義できます。 その後、Azure テナント ID を使用し、最大で 20,000 人の顧客をプライベート対象ユーザーとして定義できます。

続行する前に、 **[下書きの保存]** を選択します。

## <a name="technical-configuration"></a>技術的な構成

このページでは、オファーへの接続に使用される技術的な詳細 (URL パス、Webhook、テナント ID、およびアプリ ID) を定義します。 この接続によって、最終顧客がオファーを取得することを選択した場合、Microsoft は最終顧客向けにオファーをプロビジョニングできます。 収集されたフィールドの使用方法が説明されている図については、「[SaaS Fulfillment API](https://docs.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-api-v2)」のドキュメントをご覧ください。

- **[ランディング ページの URL]** (必須) – 顧客がマーケットプレースからお客様のオファーを取得した後で移動するサイトの URL を定義します。 この URL は、顧客がページにルーティングされるときにトークンを受け取るエンドポイントです。 そのトークンを交換し、Fulfillment API での解決を使って詳細をプロビジョニングできます。 それらの詳細およびお客様が収集した他の情報を、エクスペリエンスに構築される顧客対話型 Web ページの一部として使って、購入の登録とアクティブ化を完了できます。

- **[接続 Webhook]** (必須) – Microsoft が顧客に代わってパートナーに送信する必要があるすべての非同期イベント (例: SaaS サブスクリプションが無効になった) のために、パートナーは Microsoft に接続 Webhook を提供する必要があります。 Webhook システムをまだ導入していない場合、最も簡単な構成は、ポストされているイベントをリッスンして、それらを適切に処理する HTTP エンドポイント ロジック アプリを用意することです (例: https:\//prod-1westus.logic.azure.com:443/work)。 詳しくは、「[ロジック アプリで HTTP エンドポイントを通じてワークフローを呼び出し、トリガーし、入れ子にする](https://docs.microsoft.com/azure/logic-apps/logic-apps-http-endpoint)」をご覧ください。

- **[Azure AD テナント ID]** (必須) – Azure portal 内では、認証済みの通信の背後で Microsoft の 2 つのサービス間の接続が行われることを Microsoft が検証できるように、[Azure Active Directory (AD) アプリを作成](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)する必要があります。 [テナント ID](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#get-values-for-signing-in) を見つけるには、Azure Active Directory に移動して **[プロパティ]** を選択し、表示される**ディレクトリ ID** 番号 (例: 50c464d3-4930-494c-963c-1e951d15360e) を探します。

- **[Azure AD アプリ ID]** (必須) – また、自分の[アプリケーション ID](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#get-values-for-signing-in) と認証キーも必要です。 これらの値を取得するには、Azure Active Directory に移動して **[アプリの登録]** を選択し、表示される**アプリケーション ID** 番号 (例: 50c464d3-4930-494c-963c-1e951d15360e) を探します。 認証キーを見つけるには、 **[設定]** に移動して **[キー]** を選択します。 説明と期間を入力する必要があります。その後、数値が提供されます。

>[!Note]
>Azure アプリケーション ID は自分の公開元 ID に関連付けられているため、自分のすべてのオファーで同じアプリケーション ID が使用されるようにしてください。

続行する前に、 **[下書きの保存]** を選択します。

## <a name="plan-overview"></a>プランの概要

このページでは、同じオファー内でさまざまなプラン オプションを指定できます。 これらのプラン (SKU とも呼ばれる) は、サービスのバージョン、収益化、またはレベルの点で異なる可能性があります。 マーケットプレースでオファーを販売するには、少なくとも 1 つのプランを設定する必要があります。

作成後、オファーの名前、ID、価格モデル、提供状況 (パブリックまたはプライベート)、現在の公開状態、使用可能なアクションが表示されます。

**[プランの概要]** で使用可能な**アクション**は、プランの現在の状態によって異なり、以下を含む場合があります。

- プランの状態が **[ドラフト]** の場合 - [ドラフトの削除]
- プランの状態が **[Live]\(公開\)** の場合 - [Stop sell plan]\(プランの販売の停止\) または [Sync private audience]\(プライベート対象ユーザーの同期\)

**新しいプランの作成** (Microsoft を通じた販売を選択する場合は少なくとも 1 つのプラン)

- **プラン ID:** このオファーのプランごとに一意のプラン ID を作成します。 この ID は、製品 URL と Azure Resource Manager テンプレート (該当する場合) で顧客に表示されます。 小文字の英数字、ダッシュ、アンダースコアのみを使用してください。 このプラン ID は最大で 50 文字にできます。 作成を選択した後で、この ID を変更することはできません。
- **プラン名:** この名前は、顧客がオファー内のどのプランを選択するかを決めるときに表示されます。 このオファーのプランごとに一意のオファー名を作成します。 プラン名は、同じオファーに属するソフトウェア プランを区別するために使用されます (たとえば、オファー名: Windows Server、プラン: Windows Server 2016 と Windows Server 2019)。

### <a name="plan-listing"></a>プランのリスト登録

このページでは、プランの名前と説明を定義できます。 <!-- displays the languages (and markets) where your plan is available, currently English (United States) is the only location available. Additionally, this page displays the status of the language-specific listing and the date/time that it was added. You will need to define the marketplace details (offer name, description, search terms, etc.) for each language / market.-->

<!--#### Plan listing details-->

<!--Selecting one of the plan languages will display the **plan listing** information, including **Name** and **Description.** -->

- **[名前]** – プレビューの **[新しいプラン]** エントリに基づいて事前に設定されます。これは、マーケットプレースでオファーの "ソフトウェア プラン" のタイトルとして表示されます。
- **[説明]** – この説明では、このソフトウェア プランに固有な点や、オファー内の他のソフトウェア プランとの違いを説明できます。 最大で 500 文字を含めることができます。

続行する前に、 **[下書きの保存]** を選択します。

#### <a name="pricing-and-availability"></a>価格と可用性

このページでは、このプランが利用可能になる市場、目的の収益化モデル、価格、請求期間を構成できます。 さらに、プランがすべてのユーザーに表示されるようにするのか、それとも特定の顧客 (プライベート対象ユーザー) だけに表示されるようにするのかを指定できます。

#### <a name="markets-optional"></a>市場 (省略可能)

すべてのプランは、少なくとも 1 つの市場で利用できる必要があります。 **[市場の編集]** を選択し、このプランを利用可能にしたい市場の場所のチェック ボックスをオンにします。 このページには、Microsoft が代理で消費税と使用税を送金する "税送金" 国を選択するための検索ボックスおよびオプションが含まれています。

米国ドル (USD) でプランの価格を既に設定していて、別の市場の場所を追加する場合、新しい市場の価格は現時点の為替レートに従って計算されます。 各市場の価格を発行前に確認します。 変更を保存した後、[Export prices (xlsx)]\(価格のエクスポート (xlsx)\) リンクを使用して、価格を確認します。

続行する前に **[保存]** を選択します。

#### <a name="pricing"></a>価格

##### <a name="pricing-model"></a>価格モデル

**[定額]** – 月額制または年額制の単一の定額料金で、オファーにアクセスできるようにします。 これはサイトベースの価格とも呼ばれます。 この価格モデルでは、必要に応じてマーケットプレースの測定サービス API を使用して非標準ユニットに従ってお客様に課金する従量制課金プランを定義できます。  従量制課金の詳細については、「[マーケットプレース測定サービスを使用した従量制課金](./saas-metered-billing.md)」を参照してください。

**[ユーザーごと]** – オファーにアクセスする (つまり、シートを所有する) ユーザーの数に基づいた価格で、オファーにアクセスできるようにします。 このユーザー ベースのモデルでは、価格に基づいて許可される最小および最大のユーザー数を設定できます。 そのため、複数のプランを構成することで、ユーザーの数に基づいてさまざまな価格ポイントを構成できます。  これらのフィールドは省略可能です。 選択しない場合、ユーザー数は制限がないものとして解釈されることになります (最小は 1、最大はシステムでサポートできる数)。 これらのフィールドは、プランを更新する一環として編集できます。

公開すると、請求の価格モデルの選択は変更できません。 さらに、同じオファーでは、すべてのプランで同じ価格モデルが共有される必要があります。

##### <a name="user-limits"></a>ユーザーの制限

該当する場合は、最小および最大のユーザー制限を選択して設定します。

##### <a name="billing-term-and-price"></a>請求期間と価格

表示される価格を顧客が支払わなければならない**期間**と**価格**を選択します。 月単位または年単位の価格を少なくとも 1 つ指定する必要があります。また、顧客が両方のオプションを利用できるようにすることも可能です。

USD (USD = 米国ドル) で設定された価格は、保存時の最新の為替レートを使用して、選択されたすべての市場の現地通貨に変換されます。 これらの価格は公開前に検証してください。そのためには、価格スプレッドシートをエクスポートして各市場の価格を確認します。 個々の市場でカスタム価格を設定したい場合は、価格スプレッドシートを修正してインポートします。 この価格は公開元が検証する必要があります。そのため、これらの設定が用意されています。
*\*価格データのエクスポートを有効にするには、先に価格の変更を保存する必要があります*。

プランの公開後に変更できる内容には一部制限があるため、価格は公開前に注意深く確認してください。

- プランが公開されると、価格モデルは変更できません。
- プランの請求期間は、公開されると後で削除することができません。
- プランの市場の価格は、公開されると後で変更することができません。

#### <a name="free-trial"></a>無料試用版

商業マーケットプレース経由で提供される SaaS オファーでは、Microsoft を通じて販売した場合に 1 か月間の無料試用版を提供できます。 従量制課金プランを除くすべての課金モデルと課金条件で、無料試用版がサポートされます。 このオプションにより、1 か月間の無料アクセスが得られるため、お客様の負担が軽減されます。  オファー内のプランの無料試用版を有効にすることを選択した場合、お客様は最初の 1 か月の期間が終了する前に有料サブスクリプションに変換することはできません。  この期間中、オファーを購入したお客様は、無料試用が有効なサポートされるすべてのプランを試すことができ、別のプランに変換できます。  有料サブスクリプションへの変換は、期間の終了時に自動的に実行されます。

>[!NOTE]
>お客様が無料試用版を使用しないプランに変換する場合、変換は行われますが、無料試用は直ちに無効になります。 また、お客様がプランの支払いを開始した後は、無料試用版をサポートする SKU に変換した場合でも、同じサブスクリプションで無料試用版を再取得することはできなくなります。

ここで、オファーの各プランの無料試用版を構成できます。 1 か月の試用版を許可するには、チェック ボックスをオンにします。

![1 か月間の無料試用版チェックボックス](./media/free-trial-enable.png)

>[!NOTE]
>取引可能なプランが無料試用版で公開されると、そのプランに対しては無効にできなくなります。 プランを再作成する必要がないように、最初の公開でこの設定が正しいことを確認してください。

無料試用版に現在参加しているお客様のサブスクリプションに関する情報を取得するには、新しい API プロパティの `isFreeTrial` を使用します。このプロパティは、true または false としてマークされます。 詳細については、[SaaS サブスクリプションの取得 API](https://docs.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-api-v2#get-subscription) に関する記事を参照してください。

>[!NOTE]
>マーケットプレース測定サービスを利用するプランでは、無料試用版はサポートされていません。

#### <a name="plan-visibility"></a>プランの可視性

各プランは、すべてのユーザーに、または自分が選択した特定の対象ユーザーのみに表示されるように構成できます。 Azure AD テナント ID を使用して、この限定対象ユーザーにメンバーシップを割り当てることができます。

##### <a name="privacy"></a>プライバシー

プランをプライベートにして、自分が選択した限定対象ユーザーにのみ表示されるようにするには、 **[This is a private plan]\(これはプライベート プランです\)** をオンにします。 プライベート プランとして公開すると、対象ユーザーを更新したり、そのプランをすべてのユーザーが利用できる状態にしたりできます。 プランは、すべてのユーザーに表示されるものとして公開すると、すべてのユーザーに表示したままにしなければなりません (プライベート プランとして構成し直すことはできません)。

##### <a name="restricted-audience-tenant-ids"></a>**Restricted Audience (Tenant IDs) (限定対象ユーザー (テナント ID))**

このプライベート プランへのアクセス権を得る対象ユーザーを割り当てます。 アクセス権はテナント ID を使用して割り当てられます。必要に応じて、割り当て先の各テナント ID の説明を含めることができます。 最大 10 個のテナント ID を追加できます (.csv スプレッドシート ファイルをインポートする場合は、20,000 個の顧客テナント ID)。

テナントは組織を表したもので、ID は GUID (グローバル一意識別子。リソースの識別に使用される 128 ビットの整数) として表されます。 これは、組織やアプリの開発者が Azure、Microsoft Intune、または Microsoft 365 へのサインアップ時など、Microsoft とのリレーションシップを作成するときに受信する Azure AD の専用インスタンスです。 各 Azure AD テナントは、他の Azure AD テナントと区別され分離されています。 テナントを確認するには、アプリケーションの管理に使用したいアカウントで Azure portal にサインインします。 テナントがある場合、自動的にそのテナントにログインされ、アカウント名のすぐ下でテナント名を確認できます。 Azure portal の右上のアカウント名をポイントすると、名前、電子メール、ディレクトリ/テナント ID (GUID)、ドメインが表示されます。 アカウントが複数のテナントに関連付けられている場合は、アカウント名を選択してメニューを開き、そこでテナントを切り替えることができます。 各テナントには独自の ID があります。 また、[https://www.whatismytenantid.com](https://www.whatismytenantid.com) で URL のドメイン名を使用して、組織のテナント ID を検索することもできます。

SaaS オファーではテナント ID を使用してプライベート対象ユーザーを定義しますが、他の種類のオファーでは、Azure サブスクリプション ID (これも GUID として表されます) を使用できます。

> [!NOTE]
> プライベート対象ユーザー (または限定対象ユーザー) は、プレビュー対象ユーザーとは異なります。 **[[プレビュー]](#preview-audience)** ページでは、プレビュー対象ユーザーを定義できます。 プレビュー対象ユーザーは、お客様のオファーがマーケットプレースで一般公開される "*前に*" オファーにアクセスすることを許可されます。 プライベート対象ユーザーの指定は特定のプランにのみ適用されますが、プレビュー対象ユーザーは (プライベートであるかどうかに関係なく) すべてのプランを表示できます。ただし、そのプランがテストおよび検証される間の限定プレビュー期間中だけです。

続行する前に、 **[下書きの保存]** を選択します。

## <a name="example-list-of-plans-within-a-marketplace-offer"></a>マーケットプレース オファー内のプランの一覧の例

![マーケットプレース プランの一覧表示の例 (説明付き)](./media/marketplace-plan.svg)

## <a name="cloud-solution-provider-csp-reseller-audience"></a>クラウド ソリューション プロバイダー (CSP) リセラーの対象

オファーを CSP プログラムで利用可能にすることを選択したら、クラウド ソリューション プロバイダーがその顧客に対して、お客様の製品をバンドルされたソリューションの一部として販売できます。 詳細については、「[クラウド ソリューション プロバイダー](https://go.microsoft.com/fwlink/?linkid=2111109)」を参照してください。

## <a name="publish"></a>発行

オファーの必須セクションをすべて入力したら、ポータルの右上隅にある **[レビューと公開]** を選択します。

### <a name="submit-offer-to-preview"></a>プレビューへのオファーの送信

このオファーを公開するのが初めての場合、以下のことが可能です。

- オファーの各セクションの完了状態を確認する。
    - **[未開始]** – セクションは着手されておらず、完了する必要があります。
    - **[未完了]** – 修正が必要なエラーがセクションにあり、追加の情報を入力する必要があります。 セクションに戻って更新する必要があります。
    - **[完了]** – セクションが完了しています。必須のデータはすべて入力済みであり、エラーはありません。 オファーを送信するには、オファーのセクションがすべて完了状態でなければなりません。
- アプリの理解に役立つ補足事項に加えて、テストの指示を認定チームに提供し、アプリが正しくテストされるようにする。
- **[送信]** を選択して、公開するためにオファーを送信する。 お客様が確認して承認できるようにオファーのプレビュー バージョンが利用可能になったら、それを知らせるメールが Microsoft から届きます。 パートナー センターに戻ってそのオファーで **[一般公開する]** を選択し、自分のオファーをパブリックに公開する必要があります (プライベート オファーの場合、プライベート対象ユーザーに公開)。

## <a name="next-step"></a>次のステップ

- [商業マーケットプレースで既存のオファーを更新する](./update-existing-offer.md)
