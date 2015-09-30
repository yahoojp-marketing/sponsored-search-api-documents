# Report Fields
The table below describes available report fields you can include in each kind of report type.

### Account Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
AVERAGECPC                 | 平均CPC              | Avg. CPC                     | averageCpc                 | long  
AVERAGECPM                 | 平均CPM              | Avg. CPM                     | averageCpm                 | long  
AVERAGEPOSITION            | 平均掲載順位             | Avg. Position                | averagePosition            | double
CLICKS                     | クリック数              | Clicks                       | clicks                     | long  
UNIQUECONVERSIONRATE       | ユニークコンバージョン率       | Unique Conversion Rate       | uniqueConversionRate       | double
TOTALCONVERSIONRATE        | 総コンバージョン率          | Total Conversion Rate        | totalConversionRate        | double
UNIQUECONVERSIONS          | ユニークコンバージョン数       | Unique Conversions           | uniqueConversions          | long  
TOTALCONVERSIONS           | 総コンバージョン数          | Total Conversions            | totalConversions           | long  
TOTALREVENUE               | 合計売上金額             | Total Revenue                | totalRevenue               | long  
COST                       | コスト                | Cost                         | cost                       | long  
COSTUNIQUECONVERSIONS      | コスト/ユニークコンバージョン数   | Cost / Unique Conversions    | costUniqueConversions      | long  
COSTTOTALCONVERSIONS       | コスト/総コンバージョン数      | Cost / Total Conversions     | costTotalConversions       | long  
CTR                        | クリック率              | CTR                          | ctr                        | double
IMPRESSIONS                | インプレッション数          | Impressions                  | impressions                | long  
INVALIDCLICKRATE           | 無効なクリック率           | Invalid Click Rate           | invalidClickRate           | double
INVALIDCLICKS              | 無効なクリック            | Invalid Clicks               | invalidClicks              | long  
REVENUEUNIQUECONVERSIONS   | 売上/ユニークコンバージョン数    | Revenue / Unique Conversions | revenueUniqueConversions   | double
REVENUETOTALCONVERSIONS    | 売上/総コンバージョン数       | Revenue / Total Conversions  | revenueTotalConversions    | double
EXACTMATCHIMPRESSIONSHARE  | 完全一致のインプレッションシェア   | Exact Match Impression Share | exactMatchImpressionShare  | double
BUDGETLOSTIMPRESSIONSHARE  | インプレッションシェア損失率（予算） | Budget Lost Impression Share | budgetLostImpressionShare  | double
IMPRESSIONSHARE            | インプレッションシェア        | Impression Share             | impressionShare            | double
QUALITYLOSTIMPRESSIONSHARE | インプレッション損失率（掲載順位）  | Quality Lost ImpressionShare | qualityLostImpressionShare | double

### Campaign Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
DAILYSPENDINGLIMIT           | 1日の予算              | Daily Spending Limit         | dailySpendingLimit           | long  
CAMPAIGNID                   | キャンペーンID           | CampaignID                   | campaignID                   | long  
CAMPAIGNNAME                 | キャンペーン名            | Campaign Name                | campaignName                 | string
AVERAGECPC                   | 平均CPC              | Avg. CPC                     | averageCpc                   | long  
AVERAGECPM                   | 平均CPM              | Avg. CPM                     | averageCpm                   | long  
AVERAGEPOSITION              | 平均掲載順位             | Avg. Position                | averagePosition              | double
CLICKS                       | クリック数              | Clicks                       | clicks                       | long  
UNIQUECONVERSIONRATE         | ユニークコンバージョン率       | Unique Conversion Rate       | uniqueConversionRate         | double
TOTALCONVERSIONRATE          | 総コンバージョン率          | Total Conversion Rate        | totalConversionRate          | double
UNIQUECONVERSIONS            | ユニークコンバージョン数       | Unique Conversions           | uniqueConversions            | long  
TOTALCONVERSIONS             | 総コンバージョン数          | Total Conversions            | totalConversions             | long  
TOTALREVENUE                 | 合計売上金額             | Total Revenue                | totalRevenue                 | long  
COST                         | コスト                | Cost                         | cost                         | long  
COSTUNIQUECONVERSIONS        | コスト/ユニークコンバージョン数   | Cost / Unique Conversions    | costUniqueConversions        | long  
COSTTOTALCONVERSIONS         | コスト/総コンバージョン数      | Cost / Total Conversions     | costTotalConversions         | long  
CTR                          | クリック率              | CTR                          | ctr                          | double
IMPRESSIONS                  | インプレッション数          | Impressions                  | impressions                  | long  
INVALIDCLICKRATE             | 無効なクリック率           | Invalid Click Rate           | invalidClickRate             | double
INVALIDCLICKS                | 無効なクリック            | Invalid Clicks               | invalidClicks                | long  
REVENUEUNIQUECONVERSIONS     | 売上/ユニークコンバージョン数    | Revenue / Unique Conversions | revenueUniqueConversions     | double
REVENUETOTALCONVERSIONS      | 売上/総コンバージョン数       | Revenue / Total Conversions  | revenueTotalConversions      | double
EXACTMATCHIMPRESSIONSHARE    | 完全一致のインプレッションシェア  |  Exact Match Impression Share | exactMatchImpressionShare    | double
BUDGETLOSTIMPRESSIONSHARE    | インプレッションシェア損失率（予算） | Budget Lost Impression Share | budgetLostImpressionShare    | double
IMPRESSIONSHARE              | インプレッションシェア        | Impression Share             | impressionShare              | double
QUALITYLOSTIMPRESSIONSHARE   | インプレッション損失率（掲載順位）  | Quality Lost ImpressionShare | qualityLostImpressionShare   | double
CAMPAIGNDISTRIBUTIONSETTINGS | キャンペーン配信設定         | Distribution Settings        | campaignDistributionsettings | enum  
CAMPAIGNDISTRIBUTIONSTATUS   | 配信状況               | Distribution Status          | campaignDistributionStatus   | enum  
CAMPAIGNSTARTDATE            | 開始日                | Start Date                   | campaignStartDate            | long  
CAMPAIGNENDDATE              | 終了日                | End Date                     | campaignEndDate              | long  

### Ad Group Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
ADGROUPID                   | 広告グループID          | Ad Group ID                  | adgroupID                   | long  
ADGROUPNAME                 | 広告グループ名           | Ad Group Name                | adgroupName                 | string
AVERAGECPC                  | 平均CPC             | Avg. CPC                     | averageCpc                  | long  
AVERAGECPM                  | 平均CPM             | Avg. CPM                     | averageCpm                  | long  
AVERAGEPOSITION             | 平均掲載順位            | Avg. Position                | averagePosition             | double
CAMPAIGNID                  | キャンペーンID          | CampaignID                   | campaignID                  | long  
CAMPAIGNNAME                | キャンペーン名           | Campaign Name                | campaignName                | string
CLICKS                      | クリック数             | Clicks                       | clicks                      | long  
UNIQUECONVERSIONRATE        | ユニークコンバージョン率      | Unique Conversion Rate       | uniqueConversionRate        | double
TOTALCONVERSIONRATE         | 総コンバージョン率         | Total Conversion Rate        | totalConversionRate         | double
UNIQUECONVERSIONS           | ユニークコンバージョン数      | Unique Conversions           | uniqueConversions           | long  
TOTALCONVERSIONS            | 総コンバージョン数         | Total Conversions            | totalConversions            | long  
TOTALREVENUE                | 合計売上金額            | Total Revenue                | totalRevenue                | long  
COST                        | コスト               | Cost                         | cost                        | long  
COSTUNIQUECONVERSIONS       | コスト/ユニークコンバージョン数  | Cost / Unique Conversions    | costUniqueConversions       | long  
COSTTOTALCONVERSIONS        | コスト/総コンバージョン数     | Cost / Total Conversions     | costTotalConversions        | long  
CTR                         | クリック率             | CTR                          | ctr                         | double
IMPRESSIONS                 | インプレッション数         | Impressions                  | impressions                 | long  
ADGROUPBID                  | 入札価格              | Ad Group Bid (JPY)           | adGroupBID                  | long  
MAXCPM                      | 最大CPM             | Max. CPM                     | maxCpm                      | long  
REVENUEUNIQUECONVERSIONS    | 売上/ユニークコンバージョン数   | Revenue / Unique Conversions | revenueUniqueConversions    | double
REVENUETOTALCONVERSIONS     | 売上/総コンバージョン数      | Revenue / Total Conversions  | revenueTotalConversions     | double
EXACTMATCHIMPRESSIONSHARE   | 完全一致のインプレッションシェア  | Exact Match Impression Share | exactMatchImpressionShare   | double
IMPRESSIONSHARE             | インプレッションシェア       | Impression Share             | impressionShare             | double
QUALITYLOSTIMPRESSIONSHARE  | インプレッション損失率（掲載順位） | Quality Lost ImpressionShare | qualityLostImpressionShare  | double
ADGROUPDISTRIBUTIONSETTINGS | 配信設定              | Distribution Settings        | adgroupDistributionSettings | enum  

### Ad Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
ADNAME                   | 広告名              | Ad Name                      | adName                   | string
ADTYPE                   | 広告タイプ            | Ad Type                      | adType                   | enum  
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCPC               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignId               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
UNIQUECONVERSIONS        | ユニークコンバージョン数     | Unique Conversions           | uniqueConversions        | long  
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
DESTINATIONURL           | リンク先URL          | Destination URL              | destinationURL           | string
CTR                      | クリック率            | CTR                          | ctr                      | double
DESCRIPTION              | 説明文1             | Description 1                | description1             | string
DESCRIPTION2             | 説明文2             | Description 2                | description2             | string
DISPLAYURL               | 表示URL            | Display URL                  | displayURL               | string
TITLE                    | タイトル             | Title                        | title                    | string
ADID                     | 広告ID             | Ad ID                        | adID                     | long  
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
ADDISTRIBUTIONSETTINGS   | 配信設定             | Distribution Settings        | adDistributionSettings   | enum  
ADEDITORIALSTATUS        | 審査状況             | Editorial Status             | adEditorialStatus        | enum  

### Keywords Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
KEYWORDID                   | キーワードID           | Keyword ID                   | keywordID                   | long   
KEYWORD                     | キーワード             | Keyword                      | keyword                     | string 
ADGROUPID                   | 広告グループID          | Ad Group ID                  | adgroupID                   | long   
ADGROUPNAME                 | 広告グループ名           | Ad Group Name                | adgroupName                 | string 
AVERAGECPC                  | 平均CPC             | Avg. CPC                     | averageCPC                  | long   
AVERAGECPM                  | 平均CPM             | Avg. CPM                     | averageCpm                  | long   
AVERAGEPOSITION             | 平均掲載順位            | Avg. Position                | averagePosition             | double 
CAMPAIGNID                  | キャンペーンID          | CampaignID                   | campaignId                  | long   
CAMPAIGNNAME                | キャンペーン名           | Campaign Name                | campaignName                | string 
CLICKS                      | クリック数             | Clicks                       | clicks                      | long   
UNIQUECONVERSIONRATE        | ユニークコンバージョン率      | Unique Conversion Rate       | uniqueConversionRate        | double 
TOTALCONVERSIONRATE         | 総コンバージョン率         | Total Conversion Rate        | totalConversionRate         | double 
UNIQUECONVERSIONS           | ユニークコンバージョン       | Unique Conversions           | uniqueConversions           | long   
TOTALCONVERSIONS            | 総コンバージョン数         | Total Conversions            | totalConversions            | long   
TOTALREVENUE                | 合計売上金額            | Total Revenue                | totalRevenue                | long   
COST                        | コスト               | Cost                         | cost                        | long   
COSTUNIQUECONVERSIONS       | コスト/ユニークコンバージョン数  | Cost / Unique Conversions    | costUniqueConversions       | long   
COSTTOTALCONVERSIONS        | コスト/総コンバージョン数     | Cost / Total Conversions     | costTotalConversions        | long   
CUSTOMURL                   | カスタムURL           | Custom URL                   | customURL                   | string 
CTR                         | クリック率             | CTR                          | ctr                         | double 
IMPRESSIONS                 | インプレッション数         | Impressions                  | impressions                 | long   
NEGATIVEKEYWORDS            | 対象外キーワード          | Negative Keywords            | negativeKeywords            | Boolean
ADGROUPBID                  | 広告グループの入札価格       | Ad Group Bid                 | adGroupBid                  | long   
BID                         | 入札価格              | Bid (JPY)                    | bid                         | long   
MAXCPM                      | 最大CPM             | Max. CPM                     | maxCpm                      | long   
QUALITYINDEX                | 品質インデックス          | Quality Index                | qualityIndex                | integer
REVENUEUNIQUECONVERSIONS    | 売上/ユニークコンバージョン数   | Revenue / Unique Conversions | revenueUniqueConversions    | double 
REVENUETOTALCONVERSIONS     | 売上/総コンバージョン数      | Revenue / Total Conversions  | revenueTotalConversions     | double 
KEYWORDDISTRIBUTIONSETTINGS | 配信設定              | Distribution Settings        | keywordDistributionSettings | enum   
KWEDITORIALSTATUS           | 審査状況              | Editorial Status             | kwEditorialStatus           | enum   
KEYWORDMATCHTYPE            | マッチタイプ            | Match Type                   | KeywordMatchType            | enum   
FIRSTPAGEBIDESTIMATE        | 1ページ目掲載に必要な入札価格   | First Page Bid Estimate      | firstPageBidEstimate        | long   
TOPOFPAGEBIDESTIMATE        | 1ページ目上位掲載に必要な入札価格 | Top of Page Bid Estimate     | topOfPageBidEstimate        | long   

### Search Query Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
KEYWORDID                 | キーワードID          | Keyword ID                   | keywordID                 | long  
SEARCHQUERY               | 検索クエリー           | Search Query                 | searchQuery               | string
ADGROUPID                 | 広告グループID         | Ad Group ID                  | adgroupID                 | long  
ADGROUPNAME               | 広告グループ名          | Ad Group Name                | adgroupName               | string
AVERAGECPC                | 平均CPC            | Avg. CPC                     | averageCPC                | long  
AVERAGECPM                | 平均CPM            | Avg. CPM                     | averageCpm                | long  
AVERAGEPOSITION           | 平均掲載順位           | Avg. Position                | averagePosition           | double
CAMPAIGNID                | キャンペーンID         | CampaignID                   | campaignId                | long  
CAMPAIGNNAME              | キャンペーン名          | Campaign Name                | campaignName              | string
CLICKS                    | クリック数            | Clicks                       | clicks                    | long  
UNIQUECONVERSIONRATE      | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate      | double
TOTALCONVERSIONRATE       | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate       | double
UNIQUECONVERSIONS         | ユニークコンバージョン      | Unique Conversions           | uniqueConversions         | long  
TOTALCONVERSIONS          | 総コンバージョン数        | Total Conversions            | totalConversions          | long  
TOTALREVENUE              | 合計売上金額           | Total Revenue                | totalRevenue              | long  
COST                      | コスト              | Cost                         | cost                      | long  
COSTUNIQUECONVERSIONS     | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions     | long  
COSTTOTALCONVERSIONS      | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions      | long  
CTR                       | クリック率            | CTR                          | ctr                       | double
SEARCHQUERYDESTINATIONURL | クリックされたURL       | Search Query Destination URL | searchQueryDestinationURL | string
IMPRESSIONS               | インプレッション数        | Impressions                  | impressions               | long  
REVENUEUNIQUECONVERSIONS  | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions  | double
REVENUETOTALCONVERSIONS   | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions   | double
SEARCHQUERYMATCHTYPE      | 検索クエリーのマッチタイプ    | searchQueryMatch Type        | searchQueryMatch Type     | enum  

### Destination URL Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | long   
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string 
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long   
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string 
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCPC               | long   
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long   
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position                | averagePosition          | double 
CLICKS                   | クリック数            | Clicks                       | clicks                   | long   
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double 
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double 
UNIQUECONVERSIONS        | ユニークコンバージョン      | Unique Conversions           | uniqueConversions        | long   
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long   
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long   
COST                     | コスト              | Cost                         | cost                     | long   
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long   
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long   
CUSTOMURL                | カスタムURL          | Custom URL                   | customURL                | string 
CTR                      | クリック率            | CTR                          | ctr                      | double 
CREATIVEDESTINATIONURL   | リンク先URL          | CreativeDestination URL      | creativeDestinationURL   | string 
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long   
NEGATIVEKEYWORDS         | 対象外キーワード         | Negative Keywords            | negativeKeywords         | Boolean
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double 
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double 

### Geo Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
CAMPAIGNID               | キャンペーンID         | CampaignID                   | campaignID               | long  
CAMPAIGNNAME             | キャンペーン名          | Campaign Name                | campaignName             | string
ADGROUPID                | 広告グループID         | Ad Group ID                  | adgroupID                | long  
ADGROUPNAME              | 広告グループ名          | Ad Group Name                | adgroupName              | string
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCPC               | long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | long  
CLICKS                   | クリック数            | Clicks                       | clicks                   | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
UNIQUECONVERSIONS        | ユニークコンバージョン      | Unique Conversions           | uniqueConversions        | long  
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
COST                     | コスト              | Cost                         | cost                     | long  
COSTUNIQUECONVERSIONS    | コスト/ユニークコンバージョン数 | Cost / Unique Conversions    | costUniqueConversions    | long  
COSTTOTALCONVERSIONS     | コスト/総コンバージョン数    | Cost / Total Conversions     | costTotalConversions     | long  
CTR                      | クリック率            | CTR                          | ctr                      | double
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double

### Ad Display Option Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
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
FEEDITEMENDDATE          | 終了日              | End Date                     | feedItemEndDate          | Long  
FEEDITEMID               | フィードアイテムID       | Feed Item ID                 | feedItemID               | long  
FEEDITEMSTARTDATE        | 開始日              | Start Date                   | feedItemStartDate        | Long  
IMPRESSIONS              | インプレッション数        | Impressions                  | impressions              | long  
PHONENUMBER              | 電話番号             | Phone Number                 | PhoneNumber              | string
PLACEHOLDERTYPE          | プレースホルダータイプ      | Placeholder Type             | placeholder Type         | enum  
REVENUETOTALCONVERSIONS  | 売上/総コンバージョン数     | Revenue / Total Conversions  | revenueTotalConversions  | double
REVENUEUNIQUECONVERSIONS | 売上/ユニークコンバージョン数  | Revenue / Unique Conversions | revenueUniqueConversions | double
SITELINKTEXT             | サイトリンクテキスト       | Site Link Text               | siteLinkText             | string
SITELINKURL              | サイトリンクURL        | Site Link Url                | siteLinkUrl              | string
TOTALCONVERSIONRATE      | 総コンバージョン率        | Total Conversion Rate        | totalConversionRate      | double
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALCONVERSIONS         | 総コンバージョン数        | Total Conversions            | totalConversions         | long  
TOTALREVENUE             | 合計売上金額           | Total Revenue                | totalRevenue             | long  
UNIQUECONVERSIONRATE     | ユニークコンバージョン率     | Unique Conversion Rate       | uniqueConversionRate     | double

### Geo Targeting Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position/p>
            | averagePosition          | Double
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

### Schedule Targeting Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position/p>
            | averagePosition          | Double
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

### Device Targeting Report
Field Name                 | Display Name(ja)   | Display Name(en)             | XML Attribut               | Data Type 
-------------------------- | ------------------ | ---------------------------- | -------------------------- | ------
AVERAGECPC               | 平均CPC            | Avg. CPC                     | averageCpc               | Long  
AVERAGECPM               | 平均CPM            | Avg. CPM                     | averageCpm               | Long  
AVERAGEPOSITION          | 平均掲載順位           | Avg. Position/p>  | averagePosition          | Double
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

### Auto Bidding Report
フィールド名                             | 表示名(日本語)              | 表示名（英語）                                       | xml 属性                             | 型/単位  
---------------------------------- | --------------------- | --------------------------------------------- | ---------------------------------- | ------
AVERAGECPC                         | 平均CPC                 | Avg. CPC                                      | averageCpc                         | Long  
AVERAGECPM                         | 平均CPM                 | Avg. CPM                                      | averageCpm                         | Long  
AVERAGEPOSITION                    | 平均掲載順位                | Avg. Position                                 | averagePosition                    | Double
CLICKS                             | クリック数                 | Clicks                                        | clicks                             | Long  
COST                               | コスト                   | Cost                                          | cost                               | Long  
COSTTOTALCONVERSIONS               | コスト/総コンバージョン数         | Cost / Total Conversions                      | costTotalConversions               | Long  
COSTUNIQUECONVERSIONS              | コスト/ユニークコンバージョン数      | Cost / Unique Conversions                     | costUniqueConversions              | Long  
CTR                                | クリック率                 | CTR                                           | ctr                                | Double
IMPRESSIONS                        | インプレッション数             | Impressions                                   | impressions                        | Long  
TOTALCONVERSIONRATE                | 総コンバージョン率             | Total Conversion Rate                         | totalConversionRate                | Double
TOTALCONVERSIONS                   | 総コンバージョン数             | Total Conversions                             | totalConversions                   | Long  
UNIQUECONVERSIONRATE               | ユニークコンバージョン率          | Unique Conversion Rate                        | uniqueConversionRate               | Double
UNIQUECONVERSIONS                  | ユニークコンバージョン数          | Unique Conversions                            | uniqueConversions                  | Long  
BIDSTRATEGYID                     |  自動入札ID                | Bid Strategy ID                               | bidStrategyID                     |  Long  
BIDSTRATEGYNAME                   |  自動入札名                 | Bid Strategy Name                             | bidStrategyName                   |  String
BIDSTRATEGYTYPE                   |  自動入札タイプ               | Bid Strategy Type                             | bidStrategyType                   |  Enum  
ADGROUPCOUNT                      |  広告グループ数               | Ad Group Count                                | adGroupCount                      |  Long  
CAMPAIGNCOUNT                     |  キャンペーン数               | Campaign Count                                | campaignCount                     |  Long  
TARGETSEARCHPAGELOCATION          |  目標広告掲載位置             |	 Target Search Page Location                   | targetSearchPageLocation          |  Enum  
BIDAUTOMATION                     |  自動入札機能                | Bid Automation                                | bidAutomation                     |  Enum  
BIDMULTIPLIEROFTARGETPAGELOCATION |  入札単価調整率（検索ページの目標掲載位置） | Bid Adjustment (Target Search Page Location)  | bidAdjustmentOfTargetPageLocation |  Long  
LIMITEDBUDGETS                    |  予算制限                  | Limited Budgets                               | limitedBudgets                    |  Enum  
LOWQUALITYKEYWORDS                |  低品質キーワード              | Low Quality Keywords                          | lowQualityKeywords                |  Enum  
UPPERBIDLIMITOFTARGETPAGELOCATION |  上限入札単価（検索ページの目標掲載位置）  | Upper Bid Limit (Target Search Page Location) | upperBidLimitOfTargetPageLocation |  Long  
TARGETCPA                         |  目標コンバージョン単価           | Target CPA                                    | targetCpa                         |  Double
UPPERBIDLIMITOFTARGETCPA          |  上限入札単価（目標コンバージョン単価）   | Upper Bid Limit (Target CPA)                  | upperBidLimitOfTargetCpa          |  Long  
LOWERBIDLIMITOFTARGETCPA          |  下限入札単価（目標コンバージョン単価）   | Lower Bid Limit (Target CPA)                  | lowerBidLimitOfTargetCpa          |  Long  
TARGETROAS                        |  目標広告費用対効果             | Target ROAS                                   | targetRoas                        |  Long  
UPPERBIDLIMITOFTARGETROAS         |  上限入札単価（目標広告費用対効果）     | Upper Bid Limit (Target ROAS)                 | upperBidLimitOfTargetRoas         |  Long  
LOWERBIDLIMITOFTARGETROAS         |  下限入札単価（目標広告費用対効果）     | Lower Bid Limit (Target ROAS)                 | lowerBidLimitOfTargetRoas         |  Long  
UPPERBIDLIMITOFMAXIMIZECLICKS     |  上限入札単価（クリック数最大化）      | Upper Bid Limit (Maximize clicks)             | upperBidLimitOfMaximizeClicks     |  Long  


### Report Segment
Indicate a filter to roll up the report. Following fileds are available to filter.  
Enable to specify up to 3 segments.  

Value                         | Description                 
----------------------------- | ----------------------------
NETWORK                       | Network                     
DEVICE                        | Device                      
DAY                           | Date                        
DAYOFWEEK                     | Day of the week             
WEEK                          | Week                        
HOUROFDAY                     | Hour                        
MONTH                         | Month                       
MONTHOFYEAR                   | Month of year               
QUARTER                       | Quarterly                   
YEAR                          | Yearly                      
COUNTRYTERRITORY              | Country/Location            
PREFECTURE                    | Prefecture                  
CITY                          | City                        
ADKEYWORDID                   | Keyword ID                  
OBJECTIVEOFCONVERSIONTRACKING | Object of ConversionTracking
CONVERSIONNAME                | Name of Conversion          
CLICKTYPE                     | Click Type                  
ISSELFACTION                  | Additional option           

### Report Segment Correspondence Table
When “HOUROFDAY” is appointed on the segment, all reports type will not be able to retrieve the fields below.  
  
                              | ACCOUNT | CAMPAIGN | ADGROUP | AD | KEYWORDS | SEARCH_QUERY | DESTINATION_URL | GEO | FEED_ITEM | GEO_TARGET | SCHEDULE_TARGET | DEVICE_TARGET | BID_STRATEGY
----------------------------- | ------- | -------- | ------- | -- | -------- | ------------ | --------------- | --- | --------- | ---------- | --------------- | ------------- | ------------
ADKEYWORDID                   | ─       | ─        | ─       | ○  | ─        | ─            | ─               | ─   | ─         | ─          | ─               | ─               | ─            
CITY                          | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─               | ─            
CLICKTYPE                     | ○       | ○        | ○       | ○  | ○        | ─            | ─               | ─   | ○         | ─          | ─               | ─               | ─            
CONVERSIONNAME                | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─               | ─            
COUNTRYTERRITORY              | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─               | ─            
DAY                           | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○               | ○            
DAYOFWEEK                     | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○               | ○            
DEVICE                        | ○       | ○        | ○       | ○  | ○        | ─            | ○               | ○   | ○         | ─          | ─               | ─               | ○            
ISSELFACTION                  | ○       | ○        | ○       | ─  | ─        | ─            | ─               | ─   | ○         | ─          | ─               | ─               | ─            
HOUROFDAY                     | ○       | ○        | ○       | ─  | ─        | ─            | ─               | ─   | ─         | ─          | ─               | ─            | ○               
MONTH                         | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○               
MONTHOFYEAR                   | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○               
NETWORK                       | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─            | ─               
OBJECTIVEOFCONVERSIONTRACKING | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ─          | ─               | ─            | ─               
PREFECTURE                    | ─       | ─        | ─       | ─  | ─        | ─            | ─               | ○   | ─         | ─          | ─               | ─            | ─               
QUARTER                       | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○            
WEEK                          | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○            
YEAR                          | ○       | ○        | ○       | ○  | ○        | ○            | ○               | ○   | ○         | ○          | ○               | ○            | ○            
  
### Restrictions from appointing certain segment
Restriction has been removed.
