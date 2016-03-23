# Report Fields
List of available report fields.

* [Field List](#fieldlist)
* [Available Field per Report Type](#availablefield)

<a name="fieldlist">
### Field list
Field           | Display Name (Japanese) | Display Name (English) | Attribute Name (XML)| Type 
-----|-----|-----|-----|-----|-----
CAMPAIGN_ID		|キャンペーンID	|CampaignID	|campaignID	|long
ADGROUP_ID		|広告グループID	|AdGroup ID	|adGroupID	|long
AD_ID			|広告ID		|Ad ID		|adID		|long
KEYWORD_ID		|キーワードID	|Keyword ID	|keywordID	|long
CAMPAIGN_NAME		|キャンペーン名	|Campaign Name	|campaignName	|string
ADGROUP_NAME		|広告グループ名	|Ad Group Name	|adgroupName	|string
AD_NAME			|広告名		|Ad Name	|adName		|string
TITLE			|タイトル	|Title　	|title		|string
DESCRIPTION		|説明文1	|Description 1	|description1	|string
DISPLAY_URL		|表示URL	|Display URL	|displayURL	|string
SEARCH_QUERY_DESTINATION_URL	|クリックされたURL	|Search Query Destination URL	|searchQueryDestinationURL	|string
CUSTOM_URL		|カスタムURL	|Custom URL	|customURL	|string
DESTINATION_URL		|リンク先URL	| Destination URL	|destinationURL	|string
AD_TYPE			|広告タイプ	|Ad Type	|adType		|enum
KEYWORD			|キーワード	|Keyword	|keyword	|string
CAMPAIGN_DISTRIBUTION_SETTINGS	|キャンペーン配信設定	|Distribution Settings	|campaignDistributionSettings	|enum
CAMPAIGN_DISTRIBUTION_STATUS	|配信状況	|Distribution Status	|campaignDistributionStatus	|enum
ADGROUP_DISTRIBUTION_SETTINGS	|配信設定	|Distribution Settings	|adGroupDistributionSettings	|enum
AD_DISTRIBUTION_SETTINGS	|配信設定	|Distribution Settings	|adDistributionSettings	|enum
AD_EDITORIAL_STATUS		|審査状況	|Editorial Status	|editorialStatus	|enum
KEYWORD_DISTRIBUTION_SETTINGS	|配信設定	|Distribution Settings	|keywordDistributionSettings	|enum
KW_EDITIORIAL_STATUS		|審査状況	|Editorial Status	|kwEditorialStatus	|enum
ADGROUP_BID		|広告グループの入札価格	|Ad Group Bid	|adGroupBid	|long
BID			|入札価格	|Bid (JPY)	|bid			|long
DAILY_SPENDING_LIMIT	|1日の予算	|Daily Spending Limit	|dailySpendingLimit	|long
CAMPAIGN_START_DATE	|開始日	|Start Date	|campaignStartDate		|string
CAMPAIGN_END_DATE	|終了日	|End Date	|campaignEndDate		|string
NEGATIVE_KEYWORD	|対象外キーワード	|Negative Keywords	|negativekeywords	|string
QUALITY_INDEX		|品質インデックス	|Quality Index	|qualityIndex	|long
FIRST_PAGE_BID_ESTIMATE	|1ページ目掲載に必要な入札価格	|First Page Bid Estimate	|firstPageBidEstimate	|long
SEARCH_QUERY		|検索クエリー	|Search Query	|searchQuery		|string
KEYWORD_MATCH_TYPE	|マッチタイプ	|Match Type	|keywordMatchType	|enum
SEARCH_QUERY_MATCH_TYPE	|検索クエリーのマッチタイプ	|SearchQueryMatch Type	|searchQueryMatchType	|enum
COST			|コスト		|Cost		|cost			|long
IMPS			|インプレッション数	|Impressions	|impressions	|long
CLICKS			|クリック数	|Clicks		|clicks			|long
CLICK_RATE		|クリック率	|CTR		|ctr			|double
AVG_CPM			|平均CPM	|Avg. CPM	|averageCpm		|double
AVG_CPC			|平均CPC	|Avg. CPC	|averageCpc		|double
AVG_DELIVER_RANK	|平均掲載順位	|Avg. Position	|averagePosition	|double
INVALID_CLICKS		|無効なクリック	|Invalid Clicks	|invalidClicks		|long
INVALID_CLICK_RATE	|無効なクリック率	|Invalid Click Rate	|invalidClickRate	|double
MAX_CPM			|最大CPM	|Max. CPM	|maxCpm			|long
REVENUE			|合計売上金額	|Total Revenue	|totalRevenue		|long
UNIQUE_CONVERSION	|ユニークコンバージョン数	|Unique Conversions	|uniqueConversions	|long
UNIQUE_CONVERSION_RATE	|ユニークコンバージョン率	|Unique Conversion Rate	|uniqueConversionRate	|double
REVENUE_UNIQUE_CONVERSION	|売上/ユニークコンバージョン数	|Revenue / Unique Conversions	|revenueUniqueConversions	|double
REVENUE_CONVERSION	|売上/総コンバージョン数	|Revenue / Total Conversions	|revenueTotalConversions		|double
CONVERSION		|総コンバージョン数		|Total Conversions	|totalConversions	|double
CONVERSION_RATE		|総コンバージョン率		|Total Conversion Rate	|totalConversionRate	|double
COST_UNIQUE_CONVERSION	|コスト/ユニークコンバージョン数	|Cost / Unique Conversions	|costUniqueConversions	|double
CPA			|コスト/総コンバージョン数	|Cost / Total Conversions	|costTotalConversions	|double
IMPRESSION_SHARE	|インプレッションシェア		|Impression Share		|impressionShare	|double
EXACT_MATCH_IMPRESSION_SHARE	|完全一致のインプレッションシェア	|Exact Match Impression Share	|exactMatchImpressionShare	|double
BUDGET_LOST_IMPRESSION_SHARE	|インプレッション損失率（予算）	|Budget Lost Impression Share	|budgetLostImpressionShare		|double
QUALITY_LOST_IMPRESSION_SHARE	|インプレッション損失率（掲載順位）	|Quality Lost Impression Share	|qualityLostImpressionShare	|double
EDITIONAL_STATUS	|審査状況	|Editorial Status	|editorialStatus	|enum
TOP_OF_PAGE_BID_ESTIMATE	|1ページ目上部掲載に必要な入札価格	|Top of Page Bid Estimate	|topOfPageBidEstimate	|long
DESCRIPTION2		|説明文2	|Description 2		|description2		|string
PHONE_NUMBER		|電話番号	|Phone Number		|phoneNumber		|string
DEVICE_PREFERENCE	|優先デバイス	|Focus Device		|focusDevice		|enum
FEED_ID			|フィードID	|Feed ID		|feedID			|long
FEED_ITEM_ID		|広告表示オプションID	|Ad Display Option ID	|adDisplayOptionID	|long
QUICK_LINK_TEXT		|クイックリンクテキスト	|QuickLink Text	|quickLinkText		|string
QUICK_LINK_URL		|クイックリンクURL	|QuickLink URL	|quickLinkURL		|string
PLACEHOLDER_TYPE	|広告表示オプションの種類	|Ad Display Option Type	|adDisplayOptionType	|enum
FEED_ITEM_START_DATE	|開始日		|Start Date	|adDisplayOptionStartDate	|string
FEED_ITEM_END_DATE	|終了日		|End Date	|adDisplayOptionEndDate		|string
BID_MULTIPLIER		|入札価格調整率(％)	|Bid Adjustment(%)	|bidAdjustment	|long
TARGET_LOCATION_ID	|地域ID		|Target Location ID	|targetLocationID	|long
TARGET_LOCATION_NAME	|地域		|Target Location Name	|targetLocationName	|string
TARGET_SCHEDULE_ID	|曜日・時間帯ID	|Target Schedule ID	|targetScheduleID	|long
TARGET_SCHEDULE		|曜日・時間帯	|Target Schedule	|targetSchedule		|string
TARGET_DEVICE_ID	|デバイスID	|Target Device ID	|targetDeviceID		|long
TARGET_DEVICE		|デバイス	|Target Device		|targetDevice		|string
BID_STRATEGY_ID		|自動入札ID	|Auto Bidding ID	|autoBiddingID		|long
BID_STRATEGY_NAME	|自動入札名	|Auto Bidding Name	|autoBiddingName	|string
BID_STRATEGY_TYPE	|自動入札タイプ	|Auto Bidding Type	|autoBiddingType	|enum
AD_GROUP_COUNT		|広告グループ数	|Ad Groups		|adGroups		|long
CAMPAIGN_COUNT		|キャンペーン数	|Campaigns		|campaigns		|long
TARGET_SEARCH_PAGE_LOCATION	|掲載位置（検索結果ページの目標掲載位置）		|Ad Position (Target position in search results)	|adPositionOfTargetPositionInSearchResults	|enum
BID_AUTOMATION			|入札調整方法（検索結果ページの目標掲載位置）		|Bidding Adjustment Method (Target position in search results)	|biddingAdjustmentMethodOfTargetPositionInSearchResults	|enum
BID_MULTIPLIER_OF_TARGET_PAGE_LOCATION	|入札価格調整（検索結果ページの目標掲載位置）	|Bidding Adjustment (Target position in search results)	|biddingAdjustmentOfTargetPositionInSearchResults	|long
LIMITED_BUDGETS			|キャンペーン予算による制限（検索結果ページの目標掲載位置）	|Limit by Campaign Budget (Target position in search results)	|limitByCampaignBudgetOfTargetPositionInSearchResults	|enum
LOW_QUALITY_KEYWORDS		|品質が低いキーワード（検索結果ページの目標掲載位置）	|Low Quality Keyword (Target position in search results)	|lowQualityKeywordOfTargetPositionInSearchResults	|enum
UPPER_BID_LIMIT_OF_TARGET_PAGE_LOCATION	|入札価格の上限（検索結果ページの目標掲載位置）	|Bid Limit (Target position in search results)	|bidLimitForTargetPositionInSearchResults	|long
TARGET_CPA			|コンバージョン単価の目標値	|Target CPA	|targetCpa	|double
UPPER_BID_LIMIT_OF_TARGET_CPA	|入札価格の上限（コンバージョン単価の目標値）	|Bid Limit (Target CPA)	|bidLimitForTargetCpa	|long
LOWER_BID_LIMIT_OF_TARGET_CPA	|入札価格の下限（コンバージョン単価の目標値）	|Lower Bid Limit (Target CPA)	|lowerBidLimitForTargetCpa	|long
TARGET_ROAS			|広告費用対効果の目標値		|Target ROAS	|targetRoas	|double
UPPER_BID_LIMIT_OF_TARGET_ROAS	|入札価格の上限（広告費用対効果の目標値）	|Bid Limit (Target ROAS)	|bidLimitForTargetRoas	|long
LOWER_BID_LIMIT_OF_TARGET_ROAS	|入札価格の下限（広告費用対効果の目標値）	|Lower Bid Limit (Target ROAS)	|lowerBidLimitForTargetRoas	|long
UPPER_BID_LIMIT_OF_MAXIMIZE_CLICKS	|入札価格の上限（クリック数の最大化）	|Bid Limit (Maximize Clicks)	|bidLimitForMaximizeClicks	|long
TARGET_LIST_ID		|ターゲットリストID	|Target List ID	|targetListID	|long
TARGET_LIST_NAME	|ターゲットリスト名	|Target List Name	|targetListName	|string
TARGET_LIST_STATUS	|訪問履歴の蓄積	|Reach Status	|reachStatus		|enum
FEED_ITEM_ATTRIBUTES	|データ自動挿入リスト	|Data Auto Insertion List	|dataAutoInsertionList	|string
CAMPAIGN_TYPE		|キャンペーンタイプ	|Campaign type |campaignType	|enum
TRACKING_URL		|トラッキングURL	|Tracking URL	|trackingURL	|string
CUSTOM_PARAMETERS	|カスタムパラメータ	|Custom Parameters	|customParameters	|enum
LANDING_PAGE_URL	|最終リンク先URL	|Landing Page URL |landingPageURL	|string
LANDING_PAGE_URL_SMARTPHONE	|最終リンク先URL（スマートフォン）	|Landing Page URL (Smartphone) |landingPageURLSmartphone	|string
CAMPAIGN_TRACKING_ID			|キャンペーントラッキングID	|Campaign Tracking ID	|campaignTrackingID	|long
AD_TRACKING_ID		|広告トラッキングID	|Ad Tracking ID	|adTrackingID	|long
NETWORK			|広告掲載方式の指定	|Network	|network	|enum
CLICK_TYPE		|クリック種別	|Click Type	|clickType	|enum
DEVICE			|デバイス	|Device		|device		|enum
DAY			|日		|Day		|day		|string
DAY_OF_WEEK		|曜日		|Day of week	|dayOfWeek	|enum
QUARTER			|四半期		|Quarter	|quarter	|string
YEAR			|年間		|Year		|year		|string
MONTH			|毎月		|Month		|month		|string
MONTH_OF_YEAR		|月		|Month of Year	|monthofYear	|enum
WEEK			|毎週		|Week		|week		|string
HOUR_OF_DAY		|時間		|Hour of day	|hourofday	|long
OBJECT_OF_CONVERSION_TRACKING		|コンバージョン測定の目的	|Object of Conversion Tracking	|objectOfConversionTracking	|enum
CONVERSION_NAME		|コンバージョン名	|Conversion Name	|conversionName	|string
COUNTRY_TERRITORY	|国/地域	|Country/Territory	|countryTerritory	|enum
PREFECTURE		|都道府県	|Prefecture	|prefecture	|enum
CITY			|都市		|City		|city		|enum
AD_KEYWORD_ID		|キーワードID	|Keyword ID	|adKeywordID	|long
IS_SELF_ACTION		|当該の広告表示オプションとその他	|Is Self Action	|isSelfAction	|enum
<br>

<hr>
<a name="availablefield">
#### Available Field per Report Type
* [Account Report](./reportfields_types.md#account)
* [Campaign Report](./reportfields_types.md#campaign)
* [Ad Group Report](./reportfields_types.md#adgroup)
* [Ad Report](./reportfields_types.md#ad)
* [Keyword Report](./reportfields_types.md#keywords)
* [Search Query Report](./reportfields_types.md#search_query)
* [Destination URL Report](./reportfields_types.md#destination_url)
* [Geo Report](./reportfields_types.md#geo)
* [Ad Display Option Report](./reportfields_types.md#feed_item)
* [Geo Targeting Report](./reportfields_types.md#geo_target)
* [Schedule Targeting Report](./reportfields_types.md#schedule_target)
* [Device Targeting Report](./reportfields_types.md#device_target)
* [Auto Bidding Report](./reportfields_types.md#bid_strategy)
* [Data Auto Insertion Report](./reportfields_types.md#ad_customizers)
* [Target List Setting Report](./reportfields_types.md#target_list)
* [Landing Page URL Report](./reportfields_types.md#landing_page_url)
