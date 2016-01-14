# レポートタイプ
レポートタイプごとのフィールド集です。以下のフィールドは、最新バージョンよりご利用可能です。<br>
旧バージョンでは、一部利用できないフィールドがございます。その際は、バージョンアップを実施ください。<br>
※Ver.6.0からはレポートの取得方法が異なるため、Ver.5.Xでは、Ver.5.3が最新になります。<br>
※アドバンスドURLの提供により、2016年1月13日から「リンク先URLレポート」の提供を廃止しております。<br>

### アカウントレポート
フィールド名                     | 表示名(日本語)           | 表示名（英語）                      | xml 属性                     | 型/単位  
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
AVERAGECPC                 | 平均CPC              | Avg. CPC                     | averageCpc                 | long  
AVERAGECPM                 | 平均CPM              | Avg. CPM                     | averageCpm                 | long  
AVERAGEPOSITION            | 平均掲載順位             | Avg. Position                | averagePosition            | double
BUDGETLOSTIMPRESSIONSHARE  | インプレッションシェア損失率（予算） | Budget Lost Impression Share | budgetLostImpressionShare  | double
CLICKS                     | クリック数              | Clicks                       | clicks                     | long  
COST                       | コスト                | Cost                         | cost                       | long  
COSTTOTALCONVERSIONS       | コスト/総コンバージョン数      | Cost / Total Conversions     | costTotalConversions       | long  
COSTUNIQUECONVERSIONS      | コスト/ユニークコンバージョン数   | Cost / Unique Conversions    | costUniqueConversions      | long  
CTR                        | クリック率              | CTR                          | ctr                        | double
EXACTMATCHIMPRESSIONSHARE  | 完全一致のインプレッションシェア   | Exact Match Impression Share | exactMatchImpressionShare  | double
IMPRESSIONS                | インプレッション数          | Impressions                  | impressions                | long  
IMPRESSIONSHARE            | インプレッションシェア        | Impression Share             | impressionShare            | double
INVALIDCLICKRATE           | 無効なクリック率           | Invalid Click Rate           | invalidClickRate           | double
INVALIDCLICKS              | 無効なクリック            | Invalid Clicks               | invalidClicks              | long  
QUALITYLOSTIMPRESSIONSHARE | インプレッション損失率（掲載順位）  | Quality Lost ImpressionShare | qualityLostImpressionShare | double
REVENUETOTALCONVERSIONS    | 売上/総コンバージョン数       | Revenue / Total Conversions  | revenueTotalConversions    | double
REVENUEUNIQUECONVERSIONS   | 売上/ユニークコンバージョン数    | Revenue / Unique Conversions | revenueUniqueConversions   | double
TOTALCONVERSIONRATE        | 総コンバージョン率          | Total Conversion Rate        | totalConversionRate        | double
TOTALCONVERSIONS           | 総コンバージョン数          | Total Conversions            | totalConversions           | long  
TOTALREVENUE               | 合計売上金額             | Total Revenue                | totalRevenue               | long  
UNIQUECONVERSIONRATE       | ユニークコンバージョン率       | Unique Conversion Rate       | uniqueConversionRate       | double
UNIQUECONVERSIONS          | ユニークコンバージョン数       | Unique Conversions           | uniqueConversions          | long

### キャンペーンレポート
フィールド名                       | 表示名(日本語)           | 表示名（英語）                      | xml 属性                       | 型/単位  
---------------------------- | ------------------ | ---------------------------- | ---------------------------- | ------
AVERAGECPC                   | 平均CPC              | Avg. CPC                     | averageCpc                   | long  
AVERAGECPM                   | 平均CPM              | Avg. CPM                     | averageCpm                   | long  
AVERAGEPOSITION              | 平均掲載順位             | Avg. Position                | averagePosition              | double
BUDGETLOSTIMPRESSIONSHARE    | インプレッションシェア損失率（予算） | Budget Lost Impression Share | budgetLostImpressionShare    | double
CAMPAIGNDISTRIBUTIONSETTINGS | キャンペーン配信設定         | Distribution Settings        | campaignDistributionsettings | enum  
CAMPAIGNDISTRIBUTIONSTATUS   | 配信状況               | Distribution Status          | campaignDistributionStatus   | enum  
CAMPAIGNID                   | キャンペーンID           | CampaignID                   | campaignID                   | long
CAMPAIGNNAME                 | キャンペーン名            | Campaign Name                | campaignName                 | string
CAMPAIGNSTARTDATE            | 開始日                | Start Date                   | campaignStartDate            | long  
CAMPAIGNENDDATE              | 終了日                | End Date                     | campaignEndDate              | long  
CAMPAIGNTYPE              | キャンペーンタイプ          | Campaign Type              | campaignType              | enum  
CLICKS                       | クリック数              | Clicks                       | clicks                       | long  
COST                         | コスト                | Cost                         | cost                         | long  
COSTTOTALCONVERSIONS         | コスト/総コンバージョン数      | Cost / Total Conversions     | costTotalConversions         | long  
COSTUNIQUECONVERSIONS        | コスト/ユニークコンバージョン数   | Cost / Unique Conversions    | costUniqueConversions        | long  
CTR                          | クリック率              | CTR                          | ctr                          | double
DAILYSPENDINGLIMIT           | 1日の予算              | Daily Spending Limit         | dailySpendingLimit           | long  
EXACTMATCHIMPRESSIONSHARE    | 完全一致のインプレッションシェア  |  Exact Match Impression Share | exactMatchImpressionShare    | double
IMPRESSIONS                  | インプレッション数          | Impressions                  | impressions                  | long  
IMPRESSIONSHARE              | インプレッションシェア        | Impression Share             | impressionShare              | double
INVALIDCLICKRATE             | 無効なクリック率           | Invalid Click Rate           | invalidClickRate             | double
INVALIDCLICKS                | 無効なクリック            | Invalid Clicks               | invalidClicks                | long QUALITYLOSTIMPRESSIONSHARE   | インプレッション損失率（掲載順位）  | Quality Lost ImpressionShare | qualityLostImpressionShare   | double
REVENUETOTALCONVERSIONS      | 売上/総コンバージョン数       | Revenue / Total Conversions  | revenueTotalConversions      | double
REVENUEUNIQUECONVERSIONS     | 売上/ユニークコンバージョン数    | Revenue / Unique Conversions | revenueUniqueConversions     | double
TOTALCONVERSIONRATE          | 総コンバージョン率          | Total Conversion Rate        | totalConversionRate          | double
TOTALCONVERSIONS             | 総コンバージョン数          | Total Conversions            | totalConversions             | long  
TOTALREVENUE                 | 合計売上金額             | Total Revenue                | totalRevenue                 | long UNIQUECONVERSIONRATE         | ユニークコンバージョン率       | Unique Conversion Rate       | uniqueConversionRate         | double
UNIQUECONVERSIONS            | ユニークコンバージョン数       | Unique Conversions           | uniqueConversions            | long  

### 広告グループレポート
フィールド名                      | 表示名(日本語)          | 表示名（英語）                      | xml 属性                      | 型/単位  
--------------------------- | ----------------- | ---------------------------- | --------------------------- | ------
ADGROUPID                   | 広告グループID          | Ad Group ID                  | adgroupID                   | long  
ADGROUPNAME                 | 広告グループ名           | Ad Group Name                | adgroupName                 | string
ADGROUPBID                  | 入札価格              | Ad Group Bid (JPY)           | adGroupBID                  | long  
ADGROUPDISTRIBUTIONSETTINGS | 配信設定              | Distribution Settings        | adgroupDistributionSettings | enum  
AVERAGECPC                  | 平均CPC             | Avg. CPC                     | averageCpc                  | long  
AVERAGECPM                  | 平均CPM             | Avg. CPM                     | averageCpm                  | long  
AVERAGEPOSITION             | 平均掲載順位            | Avg. Position                | averagePosition             | double
CAMPAIGNID                  | キャンペーンID          | CampaignID                   | campaignID                  | long  
CAMPAIGNNAME                | キャンペーン名           | Campaign Name                | campaignName                | string
CLICKS                      | クリック数             | Clicks                       | clicks                      | long  
COST                        | コスト               | Cost                         | cost                        | long  
COSTTOTALCONVERSIONS        | コスト/総コンバージョン数     | Cost / Total Conversions     | costTotalConversions        | long  
COSTUNIQUECONVERSIONS       | コスト/ユニークコンバージョン数  | Cost / Unique Conversions    | costUniqueConversions       | long  
CTR                         | クリック率             | CTR                          | ctr                         | double
IMPRESSIONS                 | インプレッション数         | Impressions                  | impressions                 | long
MAXCPM                      | 最大CPM             | Max. CPM                     | maxCpm                      | long  
REVENUETOTALCONVERSIONS     | 売上/総コンバージョン数      | Revenue / Total Conversions  | revenueTotalConversions     | double
REVENUEUNIQUECONVERSIONS    | 売上/ユニークコンバージョン数   | Revenue / Unique Conversions | revenueUniqueConversions    | double
TOTALCONVERSIONRATE         | 総コンバージョン率         | Total Conversion Rate        | totalConversionRate         | double
TOTALCONVERSIONS            | 総コンバージョン数         | Total Conversions            | totalConversions            | long 
TOTALREVENUE                | 合計売上金額            | Total Revenue                | totalRevenue                | long  
UNIQUECONVERSIONRATE        | ユニークコンバージョン率      | Unique Conversion Rate       | uniqueConversionRate        | double
UNIQUECONVERSIONS           | ユニークコンバージョン数      | Unique Conversions           | uniqueConversions           | long  
EXACTMATCHIMPRESSIONSHARE   | 完全一致のインプレッションシェア  | Exact Match Impression Share | exactMatchImpressionShare   | double
IMPRESSIONSHARE             | インプレッションシェア       | Impression Share             | impressionShare             | double
QUALITYLOSTIMPRESSIONSHARE  | インプレッション損失率（掲載順位） | Quality Lost ImpressionShare | qualityLostImpressionShare  | double

### 広告レポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
ADID                     | 広告ID             | Ad ID                        | adID                     | long  
ADNAME                   | 広告名              | Ad Name                      | adName                   | string
ADTYPE                   | 広告タイプ            | Ad Type                      | adType                   | enum  
ADDISTRIBUTIONSETTINGS   | 配信設定             | Distribution Settings        | adDistributionSettings   | enum  
ADEDITORIALSTATUS        | 審査状況             | Editorial Status             | adEditorialStatus        | enum  
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCPC               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignId               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
DESCRIPTION              | 説明文1             | Description 1                | description1             | string
DESCRIPTION2             | 説明文2             | Description 2                | description2             | string
DESTINATIONURL           | リンク先URL          | Destination URL              | destinationURL           | string
DEVICEPREFERENCE         | 優先デバイス           | Device Preference            | Device Preference        | enum  
DISPLAYURL               | 表示URL            | Display URL                  | displayURL               | string
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
TITLE                    | タイトル             | Title                        | title                    | string
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
UNIQUECONVERSIONS        | ユニークコンバージョン数     | Unique Conversions           | uniqueConversions        | long  

### キーワードレポート
フィールド名                      | 表示名(日本語)          | 表示名（英語）       | xml 属性              | 型/単位   
--------------------------- | ----------------- | ---------------------------- | --------------------------- | -------
ADGROUPBID                  | 広告グループの入札価格       | Ad Group Bid                 | adGroupBid                  | long   
ADGROUPID                   | 広告グループID          | Ad Group ID                  | adgroupID                   | long   
ADGROUPNAME                 | 広告グループ名           | Ad Group Name                | adgroupName                 | string 
AVERAGECPC                  | 平均CPC             | Avg. CPC                     | averageCPC                  | long   
AVERAGECPM                  | 平均CPM             | Avg. CPM                     | averageCpm                  | long   
AVERAGEPOSITION             | 平均掲載順位            | Avg. Position                | averagePosition             | double 
BID                         | 入札価格              | Bid (JPY)                    | bid                         | long   
CAMPAIGNID                  | キャンペーンID          | CampaignID                   | campaignId                  | long   
CAMPAIGNNAME                | キャンペーン名           | Campaign Name                | campaignName                | string 
CLICKS                      | クリック数             | Clicks                       | clicks                      | long   
COST                        | コスト               | Cost                         | cost                        | long   
COSTTOTALCONVERSIONS        | コスト/総コンバージョン数     | Cost / Total Conversions     | costTotalConversions        | long   
COSTUNIQUECONVERSIONS       | コスト/ユニークコンバージョン数  | Cost / Unique Conversions    | costUniqueConversions       | long   
CTR                         | クリック率             | CTR                          | ctr                         | double 
CUSTOMURL                   | カスタムURL           | Custom URL                   | customURL                   | string 
FIRSTPAGEBIDESTIMATE        | 1ページ目掲載に必要な入札価格   | First Page Bid Estimate      | firstPageBidEstimate        | long   
IMPRESSIONS                 | インプレッション数         | Impressions                  | impressions                 | long
KEYWORD                     | キーワード             | Keyword                      | keyword                     | string 
KEYWORDID                   | キーワードID           | Keyword ID                   | keywordID                   | long   
KEYWORDDISTRIBUTIONSETTINGS | 配信設定              | Distribution Settings        | keywordDistributionSettings | enum   
KEYWORDMATCHTYPE            | マッチタイプ            | Match Type                   | KeywordMatchType            | enum   
KWEDITORIALSTATUS           | 審査状況              | Editorial Status             | kwEditorialStatus           | enum   
MAXCPM                      | 最大CPM             | Max. CPM                     | maxCpm                      | long   
NEGATIVEKEYWORDS            | 対象外キーワード          | Negative Keywords            | negativeKeywords            | Boolean
QUALITYINDEX                | 品質インデックス          | Quality Index                | qualityIndex                | integer
REVENUETOTALCONVERSIONS     | 売上/総コンバージョン数      | Revenue / Total Conversions  | revenueTotalConversions     | double 
REVENUEUNIQUECONVERSIONS    | 売上/ユニークコンバージョン数   | Revenue / Unique Conversions | revenueUniqueConversions    | double 
TOTALCONVERSIONRATE         | 総コンバージョン率         | Total Conversion Rate        | totalConversionRate         | double 
TOTALCONVERSIONS            | 総コンバージョン数         | Total Conversions            | totalConversions            | long 
TOTALREVENUE                | 合計売上金額            | Total Revenue                | totalRevenue                | long   
TOPOFPAGEBIDESTIMATE        | 1ページ目上位掲載に必要な入札価格 | Top of Page Bid Estimate     | topOfPageBidEstimate        | long   
UNIQUECONVERSIONRATE        | ユニークコンバージョン率      | Unique Conversion Rate       | uniqueConversionRate        | double 
UNIQUECONVERSIONS           | ユニークコンバージョン       | Unique Conversions           | uniqueConversions           | long   

### 検索クエリーレポート
フィールド名                    | 表示名(日本語)         | 表示名（英語）                      | xml 属性                    | 型/単位  
------------------------- | ---------------- | ---------------------------- | ------------------------- | ------
ADGROUPID                 | 広告グループID         | Ad Group ID                  | adgroupID                 | long  
ADGROUPNAME               | 広告グループ名          | Ad Group Name                | adgroupName               | string
AVERAGECPC                | 平均CPC            | Avg. CPC                     | averageCPC                | long  
AVERAGECPM                | 平均CPM            | Avg. CPM                     | averageCpm                | long  
AVERAGEPOSITION           | 平均掲載順位           | Avg. Position                | averagePosition           | double
CAMPAIGNID                | キャンペーンID         | CampaignID                   | campaignId                | long  
CAMPAIGNNAME              | キャンペーン名          | Campaign Name                | campaignName              | string
CLICKS                    | クリック数            | Clicks                       | clicks                    | long  
COST                      | コスト              | Cost                         | cost                      | long  
COSTTOTALCONVERSIONS      | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions      | long  
COSTUNIQUECONVERSIONS     | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions     | long
CTR                       | クリック率            | CTR                          | ctr                       | double
IMPRESSIONS               | インプレッション数        | Impressions                  | impressions               | long  
KEYWORDID                 | キーワードID          | Keyword ID                   | keywordID                 | long  
REVENUETOTALCONVERSIONS   | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions   | double
REVENUEUNIQUECONVERSIONS  | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions  | double
SEARCHQUERY               | 検索クエリー           | Search Query                 | searchQuery               | string
SEARCHQUERYDESTINATIONURL | クリックされたURL       | Search Query Destination URL | searchQueryDestinationURL | string
SEARCHQUERYMATCHTYPE      | 検索クエリーのマッチタイプ    | searchQueryMatch Type        | searchQueryMatch Type     | enum  
TOTALCONVERSIONRATE       | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate       | double
TOTALCONVERSIONS          | 総コンバージョン数        | Total Conversions            | totalConversions          | long  
TOTALREVENUE              | 合計売上金額           | Total Revenue                | totalRevenue              | long  
UNIQUECONVERSIONRATE      | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate      | double
UNIQUECONVERSIONS         | ユニークコンバージョン      | Unique Conversions           | uniqueConversions         | long  

### 地域別レポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCPC               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
TOTALCONVERSIONRATE       | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate       | double
TOTALCONVERSIONS          | 総コンバージョン数        | Total Conversions            | totalConversions          | long  
TOTALREVENUE              | 合計売上金額           | Total Revenue                | totalRevenue              | long  
UNIQUECONVERSIONRATE      | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate      | double
UNIQUECONVERSIONS         | ユニークコンバージョン      | Unique Conversions           | uniqueConversions         | long  

### 広告表示オプションレポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
ADID                     | 広告ID             | Ad ID                        | adID                     | long  
ADNAME                   | 広告名              | Ad Name                      | adName                   | string
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
DEVICEPREFERENCE         | 優先デバイス           | Device Preference            | Device Preference        | enum  
EDITORIALSTATUS          | 審査状況             | Editorial Status             | editorialStatus          | enum  
FEEDITEMID               | フィードアイテムID       | Feed Item ID                 | feedItemID               | long  
FEEDITEMSTARTDATE        | 開始日              | Start Date                   | feedItemStartDate        | Long  
FEEDITEMENDDATE          | 終了日              | End Date                     | feedItemEndDate          | Long  
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
PHONENUMBER              | 電話番号             | Phone Number                 | PhoneNumber              | string
PLACEHOLDERTYPE          | プレースホルダータイプ      | Placeholder Type             | placeholder Type         | enum  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
SITELINKTEXT             | サイトリンクテキスト       | Site Link Text               | siteLinkText             | string
SITELINKURL              | サイトリンクURL        | Site Link Url                | siteLinkUrl              | string
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
UNIQUECONVERSIONS        | ユニークコンバージョン      | Unique Conversions           | uniqueConversions        | long  

### 地域ターゲティングレポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position        | averagePosition          | Double
BIDMULTIPLIER            | 入札価格調整率          | Bid Multiplier               | bidMultiplier            | Double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | Long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | String
CLICKS                   | クリック数            | Clicks                       | clicks                   | Long  
COST                     | コスト              | Cost                         | cost                     | Long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | Long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | Long  
CTR                      | クリック率            | CTR                          | ctr                      | Double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | Long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | Double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | Double
TARGETLOCATIONID         | 地域ターゲティングID      | Target Location ID           | targetLocationID         | String
TARGETLOCATIONNAME       | 地域ターゲティング名       | Target Location Name         | targetLocationName       | String
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | Double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | Long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | Double
UNIQUECONVERSIONS        | ユニークコンバージョン数     | Unique Conversions           | uniqueConversions        | Long  

### 曜日・時間帯ターゲティングレポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position      | averagePosition          | Double
BIDMULTIPLIER            | 入札価格調整率          | Bid Multiplier               | bidMultiplier            | Double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | Long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | String
CLICKS                   | クリック数            | Clicks                       | clicks                   | Long  
COST                     | コスト              | Cost                         | cost                     | Long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | Long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | Long  
CTR                      | クリック率            | CTR                          | ctr                      | Double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | Long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | Double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | Double
TARGETSCHEDULE           | 曜日・時間帯ターゲティング    | Target Schedule              | targetSchedule           | String
TARGETSCHEDULEID         | 曜日・時間帯ターゲティングID  | Target Schedule ID           | targetScheduleID         | Long  
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | Double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | Long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | Double
UNIQUECONVERSIONS        | ユニークコンバージョン数     | Unique Conversions           | uniqueConversions        | Long  

### デバイスターゲティングレポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position | averagePosition          | Double
BIDMULTIPLIER            | 入札価格調整率          | Bid Multiplier               | bidMultiplier            | Double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | Long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | String
CLICKS                   | クリック数            | Clicks                       | clicks                   | Long  
COST                     | コスト              | Cost                         | cost                     | Long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | Long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | Long  
CTR                      | クリック率            | CTR                          | ctr                      | Double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | Long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | Double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | Double
TARGETDEVICE             | デバイスターゲティング      | Target Device                | targetDevice             | String
TARGETDEVICEID           | デバイスターゲティングID    | targetDeviceID               | targetScheduleID         | Long  
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | Double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | Long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | Double
UNIQUECONVERSIONS        | ユニークコンバージョン数     | Unique Conversions           | uniqueConversions        | Long  

### 自動入札レポート
フィールド名                             | 表示名(日本語)              | 表示名（英語）                                       | xml 属性                             | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
AVERAGECPC                | 平均CPC                 | Avg. CPC              | averageCpc                | Long  
AVERAGECPM               | 平均CPM                 | Avg. CPM                 | averageCpm                | Long  
AVERAGEPOSITION           | 平均掲載順位                | Avg. Position         | averagePosition        | Double
CLICKS                      | クリック数                 | Clicks              | clicks                             | Long  
COST                      | コスト                   | Cost                  | cost               | Long  
COSTTOTALCONVERSIONS        | コスト/総コンバージョン数      | Cost / Total Conversions | costTotalConversions   | Long  
COSTUNIQUECONVERSIONS      | コスト/ユニークコンバージョン数  | Cost / Unique Conversions   | costUniqueConversions| Long  
CTR                         | クリック率                 | CTR                    | ctr            | Double
IMPRESSIONS                 | インプレッション数             | Impressions        | impressions       | Long  
TOTALCONVERSIONRATE          | 総コンバージョン率             | Total Conversion Rate     | totalConversionRate    | Double
TOTALCONVERSIONS           | 総コンバージョン数             | Total Conversions        | totalConversions       | Long  
UNIQUECONVERSIONRATE      | ユニークコンバージョン率     | Unique Conversion Rate     | uniqueConversionRate  | Double
UNIQUECONVERSIONS          | ユニークコンバージョン数          | Unique Conversions   | uniqueConversions      | Long  
BIDSTRATEGYID               |  自動入札ID                | Bid Strategy ID           | bidStrategyID    |  Long  
BIDSTRATEGYNAME             |  自動入札名              | Bid Strategy Name        | bidStrategyName    |  String
BIDSTRATEGYTYPE            |  自動入札タイプ               | Bid Strategy Type         | bidStrategyType   |  Enum  
ADGROUPCOUNT                 |  広告グループ数               | Ad Group Count      | adGroupCount     |  Long  
CAMPAIGNCOUNT              |  キャンペーン数               | Campaign Count      | campaignCount   |  Long  
TARGETSEARCHPAGELOCATION     |  目標広告掲載位置   | Target Search Page Location    | targetSearchPageLocation   |  Enum  
BIDAUTOMATION             |  自動入札機能           | Bid Automation       | bidAutomation                     |  Enum  
BIDMULTIPLIEROFTARGETPAGELOCATION |  入札単価調整率（検索ページの目標掲載位置） | Bid Adjustment (Target Search Page Location)  | bidAdjustmentOfTargetPageLocation |  Long  
LIMITEDBUDGETS          |  予算制限                  | Limited Budgets        | limitedBudgets        |  Enum  
LOWQUALITYKEYWORDS         |  低品質キーワード        | Low Quality Keywords      | lowQualityKeywords |  Enum  
UPPERBIDLIMITOFTARGETPAGELOCATION |  上限入札単価（検索ページの目標掲載位置）  | Upper Bid Limit (Target Search Page Location) | upperBidLimitOfTargetPageLocation |  Long  
TARGETCPA                  |  目標コンバージョン単価           | Target CPA       | targetCpa      |  Double
UPPERBIDLIMITOFTARGETCPA    |  上限入札単価（目標コンバージョン単価）   | Upper Bid Limit (Target CPA) | upperBidLimitOfTargetCpa  |  Long  
LOWERBIDLIMITOFTARGETCPA     |  下限入札単価（目標コンバージョン単価）   | Lower Bid Limit (Target CPA)     | lowerBidLimitOfTargetCpa    |  Long  
TARGETROAS             |  目標広告費用対効果             | Target ROAS     | targetRoas        |  Long  
UPPERBIDLIMITOFTARGETROAS  |  上限入札単価（目標広告費用対効果）     | Upper Bid Limit (Target ROAS)   | upperBidLimitOfTargetRoas         |  Long  
LOWERBIDLIMITOFTARGETROAS  |  下限入札単価（目標広告費用対効果）     | Lower Bid Limit (Target ROAS) | lowerBidLimitOfTargetRoas         |  Long  
UPPERBIDLIMITOFMAXIMIZECLICKS  |  上限入札単価（クリック数最大化）      | Upper Bid Limit (Maximize clicks) | upperBidLimitOfMaximizeClicks     |  Long  

### データ自動挿入レポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
DEVICEPREFERENCE         | 優先デバイス           | Device Preference            | Device Preference        | enum  
EDITORIALSTATUS          | 審査状況             | Editorial Status             | editorialStatus          | enum  
FEEDID              　　 | フィードID       　　　　| Feed ID                 | feedID               | long 
FEEDITEMID               | フィードアイテムID       | Feed Item ID                 | feedItemID               | long  
FEEDITEMSTARTDATE        | 開始日              | Start Date                   | feedItemStartDate        | Long  
FEEDITEMENDDATE          | 終了日              | End Date                     | feedItemEndDate          | Long  
FEEDITEMATTRIBUTES       | フィードアイテム属性       | Feed Item Attributes          | feedItemAttributes　| string  
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
PHONENUMBER              | 電話番号             | Phone Number                 | PhoneNumber              | string
PLACEHOLDERTYPE          | プレースホルダータイプ      | Placeholder Type             | placeholder Type         | enum  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
SITELINKTEXT             | サイトリンクテキスト       | Site Link Text               | siteLinkText             | string
SITELINKURL              | サイトリンクURL        | Site Link Url                | siteLinkUrl              | string
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
UNIQUECONVERSIONS        | ユニークコンバージョン      | Unique Conversions           | uniqueConversions        | long  

### ターゲットリストレポート
フィールド名                   | 表示名(日本語)         | 表示名（英語）                      | xml 属性                   | 型/単位  
------------------------ | ---------------- | ---------------------------- | ------------------------ | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
ADID                     | 広告ID             | Ad ID                        | adID                     | long  
ADNAME                   | 広告名              | Ad Name                      | adName                   | string
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double
BIDMULTIPLIER            | 入札価格調整率          | Bid Multiplier               | bidMultiplier            | Double
CAMPAIGNID               | キャンペーンID         | Campaign ID                   | campaignID               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
UNIQUECONVERSIONS        | ユニークコンバージョン      | Unique Conversions           | uniqueConversions        | long 
TARGETLISTID             | ターゲットリストID         | Target List ID               | targetListID               | long  
TARGETLISTNAME           | ターゲットリスト名          | Target List Name             | targetListName             | string
TARGETLISTSTATUS        | 訪問履歴の蓄積            | Reach Status                  | reachStatus              | enum  

### レポートセグメント
レポートセグメントは、出力するレポートをグループ化するためのフィルタ条件を表します。  
フィルタ条件は最大で3つ設定することが可能です。  

値                             | 説明           
----------------------------- | -------------
ADKEYWORDID                   | キーワードです。     
CITY                          | 市区町村名です。     
CLICKTYPE                     | クリック種別です。    
CONVERSIONNAME                | コンバージョン名     
COUNTRYTERRITORY              | 国/地域です。      
DAY                           | 日です。         
DAYOFWEEK                     | 曜日です。        
DEVICE                        | デバイスです。      
ISSELFACTION                  | オプションとその他です。 
HOUROFDAY                     | 時間です。        
MONTH                         | 月です。         
MONTHOFYEAR                   | 月です。         
NETWORK                       | 広告掲載方式です。    
OBJECTIVEOFCONVERSIONTRACKING | コンバージョン測定の目的。
PREFECTURE                    | 都道府県名です。     
QUARTER                       | 四半期です。       
WEEK                          | 週です。         
YEAR                          | 年です。         

### レポートセグメント対応表
各レポートタイプで、設定可能なレポートセグメントの一覧は下記のとおりです。

ACCOUNT | CAMPAIGN | ADGROUP | AD | KEYWORDS | SEARCH_QUERY | DESTINATION_URL | GEO | FEED_ITEM | GEO_TARGET | SCHEDULE_TARGET | DEVICE_TARGET | BID_STRATEGY | AD_CUSTOMIZERS | TARGET_LIST
----------------------------- | -------- | ------- | ---- | -------- | ------------ | --------------- | --- | --------- | ---------- | --------------- | ------------- | ------------ | ------------ | --------------
ADKEYWORDID                   | ─       | ─        | ─       | ○  | ─        | ─            | ─               | ─   | ─         | ─          | ─               | ─               | ─        | ─       
CITY                          | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─               | ─        | ─       
CLICKTYPE                     | ○       | ○        | ○       | ○  | ○        | ─            | ─               | ─   | ○         | ─          | ─               | ─               | ─   | ○          
CONVERSIONNAME                | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─               | ─    | ○         
COUNTRYTERRITORY              | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─               | ─        | ─       
DAY                           | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○               | ○      | ○       
DAYOFWEEK                     | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○               | ○        | ○     
DEVICE                        | ○       | ○        | ○       | ○  | ○        | ─            | ○               | ○   | ○         | ─          | ─               | ─               | ○        | ○     
ISSELFACTION                  | ○       | ○        | ○       | ─  | ─        | ─            | ─               | ─   | ○         | ─          | ─               | ─               | ─     | ─        
HOUROFDAY                     | ○       | ○        | ○       | ─  | ─        | ─            | ─               | ─   | ─         | ─          | ─               | ─            | ○        | ─        
MONTH                         | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○       | ○         
MONTHOFYEAR                   | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○        | ○        
NETWORK                       | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─            | ─        | ○        
OBJECTIVEOFCONVERSIONTRACKING | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─            | ─        | ○        
PREFECTURE                    | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─            | ─        | ─        
QUARTER                       | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○       | ○      
WEEK                          | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○      | ○       
YEAR                          | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○         | ○    
  
### 特定のセグメント指定による制限事項
レポートセグメントの指定による制限事項は無くなりました。
