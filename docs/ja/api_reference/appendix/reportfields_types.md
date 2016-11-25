# レポートタイプ別フィールド指定表
レポートタイプごとにご利用可能なレポートフィールド集です。

### レポートタイプ
* [アカウントレポート](#account)
* [キャンペーンレポート](#campaign)
* [広告グループレポート](#adgroup)
* [広告レポート](#ad)
* [キーワードレポート](#keywords)
* [検索クエリレポート](#search_query)
* [地域別レポート](#geo)
* [広告表示オプションレポート](#feed_item)
* [地域ターゲティングレポート](#geo_target)
* [曜日・時間帯ターゲティングレポート](#schedule_target)
* [自動入札レポート](#bid_strategy)
* [ターゲットリスト設定レポート](#target_list)
* [データ自動挿入レポート](#ad_customizers)
* [最終リンク先URLレポート](#landing_page_url)
<br><br>

<hr>
<a name="account">
#### アカウントレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
COST				|○	|×	|×	|○
IMPS				|○	|×	|×	|○
CLICKS				|○	|×	|×	|○
CLICK_RATE			|○	|×	|×	|○
AVG_CPM				|○	|×	|×	|○
AVG_CPC				|○	|×	|×	|○
AVG_DELIVER_RANK		|○	|×	|×	|○
INVALID_CLICKS			|×	|×	|×	|○
INVALID_CLICK_RATE		|×	|×	|×	|○
REVENUE				|○	|○	|○	|○
UNIQUE_CONVERSION		|○	|×	|×	|○
UNIQUE_CONVERSION_RATE		|○	|×	|×	|○
REVENUE_UNIQUE_CONVERSION	|○	|×	|×	|○
REVENUE_CONVERSION		|○	|○	|○	|○
CONVERSION			|○	|○	|○	|○
CONVERSION_RATE			|○	|×	|×	|○
COST_UNIQUE_CONVERSION		|○	|×	|×	|○
CPA				|○	|×	|×	|○
IMPRESSION_SHARE		|○	|×	|×	|×
EXACT_MATCH_IMPRESSION_SHARE		|○	|×	|×	|×
BUDGET_LOST_IMPRESSION_SHARE		|○	|×	|×	|×
QUALITY_LOST_IMPRESSION_SHARE		|○	|×	|×	|×
TRACKING_URL			|○	|○	|○	|○
CONVERSIONS			|○	|○	|○	|○
CONV_RATE			|○	|×	|×	|○
CONV_VALUE			|○	|○	|○	|○
COST_PER_CONV			|○	|×	|×	|○
VALUE_PER_CONV			|○	|○	|○	|○
ALL_CONV			|×	|○	|○	|○
ALL_CONV_RATE			|×	|×	|×	|○
ALL_CONV_VALUE			|×	|○	|○	|○
COST_PER_ALL_CONV			|×	|×	|×	|○
VALUE_PER_ALL_CONV			|×	|○	|○	|○
NETWORK				|○	|○	|○	|○
CLICK_TYPE			|○	|○	|○	|-
DEVICE				|○	|○	|○	|○
DAY				|○	|○	|○	|○
DAY_OF_WEEK			|○	|○	|○	|○
QUARTER				|○	|○	|○	|○
YEAR				|○	|○	|○	|○
MONTH				|○	|○	|○	|○
MONTH_OF_YEAR			|○	|○	|○	|○
WEEK				|○	|○	|○	|○
HOUR_OF_DAY			|-	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING		|○	|-	|○	|○
CONVERSION_NAME		|○	|○	|-	|○
<br>

<hr>
<a name="campaign">
#### キャンペーンレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|○	|○	|○	|○
CAMPAIGN_NAME	|○	|○	|○	|○
CAMPAIGN_DISTRIBUTION_SETTINGS		|○	|○	|○	|○
CAMPAIGN_DISTRIBUTION_STATUS		|○	|○	|○	|○
DAILY_SPENDING_LIMIT	|○	|○	|○	|○
CAMPAIGN_START_DATE	|○	|○	|○	|○
CAMPAIGN_END_DATE	|○	|○	|○	|○
COST	|○	|×	|×	|○
IMPS		|○	|×	|×	|○
CLICKS		|○	|×	|×	|○
CLICK_RATE		|○	|×	|×	|○
AVG_CPM	|○		|×	|×	|○
AVG_CPC	|○		|×	|×	|○
AVG_DELIVER_RANK		|○	|×	|×	|○
INVALID_CLICKS		|×	|×	|×	|○
INVALID_CLICK_RATE	|○	|×	|×	|×	|○
REVENUE		|○	|○	|○	|○
UNIQUE_CONVERSION	|○	|×	|×	|○
UNIQUE_CONVERSION_RATE		|○	|×	|×	|○
REVENUE_UNIQUE_CONVERSION		|○	|×	|×	|○
REVENUE_CONVERSION		|○	|○	|○	|○
CONVERSION	|○		|○	|○	|○
CONVERSION_RATE	|○		|×	|×	|○
COST_UNIQUE_CONVERSION		|○	|×	|×	|○
CPA	|○	|×	|×	|○
IMPRESSION_SHARE		|○	|×	|×	|×
EXACT_MATCH_IMPRESSION_SHARE		|○	|×	|×	|×
BUDGET_LOST_IMPRESSION_SHARE		|○	|×	|×	|×
QUALITY_LOST_IMPRESSION_SHARE		|○	|×	|×	|×
CAMPAIGN_TYPE		|○	|○	|○	|○
TRACKING_URL		|○	|○	|○	|○
CUSTOM_PARAMETERS		|○	|○	|○	|○
CAMPAIGN_TRACKING_ID		|○	|○	|○	|○
CONVERSIONS		|○	|○	|○	|○
CONV_RATE		|○	|×	|×	|○
CONV_VALUE		|○	|○	|○	|○
COST_PER_CONV		|○	|×	|×	|○
VALUE_PER_CONV		|○	|○	|○	|○
ALL_CONV		|×	|○	|○	|○
ALL_CONV_RATE		|×	|×	|×	|○
ALL_CONV_VALUE		|×	|○	|○	|○
COST_PER_ALL_CONV		|×	|×	|×	|○
VALUE_PER_ALL_CONV		|×	|○	|○	|○
CAMPAIGN_MOBILE_BID_MODIFIER		|○	|○	|○	|○
NETWORK		|○	|○	|○	|○
CLICK_TYPE		|○	|○	|○	
DEVICE	|○		|○	|○	|○
DAY	|○		|○	|○	|○
DAY_OF_WEEK		|○	|○	|○	|○
QUARTER	|○		|○	|○	|○
YEAR	|○		|○	|○	|○
MONTH	|○		|○	|○	|○
MONTH_OF_YEAR		|○	|○	|○	|○
WEEK	|○		|○	|○	|○
HOUR_OF_DAY		|-	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING		|○	|-	|○	|○
CONVERSION_NAME	|○		|○	|-	|○
<br>

<hr>
<a name="adgroup">
#### 広告グループレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID		|○	|○	|○	|○
ADGROUP_ID		|○	|○	|○	|○
CAMPAIGN_NAME		|○	|○	|○	|○
ADGROUP_NAME		|○	|○	|○	|○
ADGROUP_DISTRIBUTION_SETTINGS		|○	|○	|○	|○
ADGROUP_BID		|○	|○	|○	|○
COST	|○		|×	|×	|○
IMPS	|○	|×	|×	|○
CLICKS	|○		|×	|×	|○
CLICK_RATE		|○	|×	|×	|○
AVG_CPM	|○		|×	|×	|○
AVG_CPC	|○		|×	|×	|○
AVG_DELIVER_RANK	|○	|○	|×	|×	|○
MAX_CPM	|○		|○	|○	|○
REVENUE	|○		|○	|○	|○
UNIQUE_CONVERSION		|○	|×	|×	|○
UNIQUE_CONVERSION_RATE		|○	|×	|×	|○
REVENUE_UNIQUE_CONVERSION		|○	|×	|×	|○
REVENUE_CONVERSION		|○	|○	|○	|○
CONVERSION	|○		|○	|○	|○
CONVERSION_RATE	|○		|×	|×	|○
COST_UNIQUE_CONVERSION		|○	|×	|×	|○
CPA	|○		|×	|×	|○
IMPRESSION_SHARE		|○	|×	|×	|×
EXACT_MATCH_IMPRESSION_SHARE		|○	|×	|×	|×
QUALITY_LOST_IMPRESSION_SHARE		|○	|×	|×	|×
TRACKING_URL	|○		|○	|○	|○
CUSTOM_PARAMETERS		|○	|○	|○	|○
CONVERSIONS		|○	|○	|○	|○
CONV_RATE		|○	|×	|×	|○
CONV_VALUE		|○	|○	|○	|○
COST_PER_CONV		|○	|×	|×	|○
VALUE_PER_CONV		|○	|○	|○	|○
ALL_CONV		|×	|○	|○	|○
ALL_CONV_RATE		|×	|×	|×	|○
ALL_CONV_VALUE		|×	|○	|○	|○
COST_PER_ALL_CONV		|×	|×	|×	|○
VALUE_PER_ALL_CONV		|×	|○	|○	|○
ADGROUP_MOBILE_BID_MODIFIER		|○	|○	|○	|○
NETWORK	|○	|○		|○	|○
CLICK_TYPE	|○		|○	|○	|-
DEVICE	|○	|○		|○	|○
DAY	|○	|○		|○	|○
DAY_OF_WEEK	|○		|○	|○	|○
QUARTER	|○	|○		|○	|○
YEAR	|○	|○		|○	|○
MONTH	|○	|○		|○	|○
MONTH_OF_YEAR	|○		|○	|○	|○
WEEK	|○	|○		|○	|○
HOUR_OF_DAY	|-	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING	|○	|-	|○	|○
CONVERSION_NAME		|○	|○	|-	|○
<br>

<hr>
<a name="ad">
#### 広告レポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID		|×	|○	|○	|○
ADGROUP_ID		|×	|○	|○	|○
AD_ID		|×	|○	|○	|○
CAMPAIGN_NAME		|×	|○	|○	|○
ADGROUP_NAME		|×	|○	|○	|○
AD_NAME		|×	|○	|○	|○
TITLE		|×	|○	|○	|○
DESCRIPTION		|×	|○	|○	|○
DISPLAY_URL		|×	|○	|○	|○
DESTINATION_URL		|×	|○	|○	|○
AD_TYPE		|×	|○	|○	|○
AD_DISTRIBUTION_SETTINGS		|×	|○	|○	|○
AD_EDITORIAL_STATUS	|×	|○	|○	|○
COST		|×	|×	|×	|○
IMPS		|×	|×	|×	|○
CLICKS		|×	|×	|×	|○
CLICK_RATE		|×	|×	|×	|○
AVG_CPM	|×	|×	|×	|○
AVG_CPC		|×	|×	|×	|○
AVG_DELIVER_RANK		|×	|×	|×	|○
REVENUE		|×	|○	|○	|○
UNIQUE_CONVERSION		|×	|×	|×	|○
UNIQUE_CONVERSION_RATE		|×	|×	|×	|○
REVENUE_UNIQUE_CONVERSION		|×	|×	|×	|○
REVENUE_CONVERSION		|×	|○	|○	|○
CONVERSION	|×	|○	|○	|○
CONVERSION_RATE		|×	|×	|×	|○
COST_UNIQUE_CONVERSION	|×	|×	|×	|○
CPA	|×	|×	|×	|○
DESCRIPTION2	|×	|○	|○	|○
DEVICE_PREFERENCE	|×	|○	|○	|○
TRACKING_URL	|×	|○	|○	|○
CUSTOM_PARAMETERS	|×	|○	|○	|○
LANDING_PAGE_URL	|×	|○	|○	|○
LANDING_PAGE_URL_SMARTPHONE	|×	|○	|○	|○
AD_TRACKING_ID	|×	|○	|○	|○
TITLE1	|○	|○	|○	|○
TITLE2	|○	|○	|○	|○
DESC	|○	|○	|○	|○
DIRECTORY1	|○	|○	|○	|○
DIRECTORY2	|○	|○	|○	|○
CONVERSIONS	|○	|○	|○	|○
CONV_RATE	|○	|×	|×	|○
CONV_VALUE	|○	|○	|○	|○
COST_PER_CONV	|○	|×	|×	|○
VALUE_PER_CONV	|○	|○	|○	|○
ALL_CONV	|○	|○	|○	|○
ALL_CONV_RATE	|○	|×	|×	|○
ALL_CONV_VALUE	|○	|○	|○	|○
COST_PER_ALL_CONV	|○	|×	|×	|○
VALUE_PER_ALL_CONV	|○	|○	|○	|○
NETWORK	|×	|○	|○	|○
CLICK_TYPE	|×	|○	|○	|-
DEVICE	|×	|○	|○	|○
DAY	|×	|○	|○	|○
DAY_OF_WEEK	|×	|○	|○	|○
QUARTER	|×	|○	|○	|○
YEAR	|×	|○	|○	|○
MONTH	|×	|○	|○	|○
MONTH_OF_YEAR	|×	|○	|○	|○
WEEK	|×	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|○
CONVERSION_NAME	|×	|○	|-	|○
AD_KEYWORD_ID	|×	|○	|○	|○
<br>

<hr>
<a name="keywords">
#### キーワードレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|○
ADGROUP_ID	|×	|○	|○	|○
KEYWORD_ID	|×	|○	|○	|○
CAMPAIGN_NAME	|×	|○	|○	|○
ADGROUP_NAME	|×	|○	|○	|○
CUSTOM_URL	|×	|○	|○	|○
KEYWORD		|×	|○	|○	|○
KEYWORD_DISTRIBUTION_SETTINGS	|×	|○	|○	|○
KEYWORD_EDITORIAL_STATUS	|×	|○	|○	|○
ADGROUP_BID		|×	|○	|○	|○
BID	|×	|○	|○	|○
NEGATIVE_KEYWORD		|×	|○	|○	|○
QUALITY_INDEX		|×	|○	|○	|○
FIRST_PAGE_BID_ESTIMATE		|×	|○	|○	|○
KEYWORD_MATCH_TYPE		|×	|○	|○	|○
COST	|×	|×	|×	|○
IMPS	|×	|×	|×	|○
CLICKS	|×	|×	|×	|○
CLICK_RATE		|×	|×	|×	|○
AVG_CPM		|×	|×	|×	|○
AVG_CPC		|×	|×	|×	|○
AVG_DELIVER_RANK	|×	|×	|×	|○
REVENUE		|×	|○	|○	|○
UNIQUE_CONVERSION		|×	|×	|×	|○
UNIQUE_CONVERSION_RATE		|×	|×	|×	|○
REVENUE_UNIQUE_CONVERSION		|×	|×	|×	|○
REVENUE_CONVERSION		|×	|○	|○	|○
CONVERSION	|×	|○	|○	|○
CONVERSION_RATE	|×	|×	|×	|○
COST_UNIQUE_CONVERSION	|×	|×	|×	|○
CPA		|×	|×	|×	|○
TOP_OF_PAGE_BID_ESTIMATE	|×	|○	|○	|○
TRACKING_URL		|×	|○	|○	|○
CUSTOM_PARAMETERS	|×	|○	|○	|○
LANDING_PAGE_URL	|×	|○	|○	|○
LANDING_PAGE_URL_SMARTPHONE	|×	|○	|○	|○
CONVERSIONS	|○	|○	|○	|○
CONV_RATE	|○	|×	|×	|○
CONV_VALUE	|○	|○	|○	|○
COST_PER_CONV	|○	|×	|×	|○
VALUE_PER_CONV	|○	|○	|○	|○
ALL_CONV	|○	|○	|○	|○
ALL_CONV_RATE	|○	|×	|×	|○
ALL_CONV_VALUE	|○	|○	|○	|○
COST_PER_ALL_CONV	|○	|×	|×	|○
VALUE_PER_ALL_CONV	|○	|○	|○	|○
NETWORK		|×	|○	|○	|○
CLICK_TYPE	|×	|○	|○	|-
DEVICE		|×	|○	|○	|○
DAY		|×	|○	|○	|○
DAY_OF_WEEK	|×	|○	|○	|○
QUARTER		|×	|○	|○	|○
YEAR	|×	|○	|○	|○
MONTH	|×	|○	|○	|○
MONTH_OF_YEAR	|×	|○	|○	|○
WEEK		|×	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING		|×	|-	|○	|○
CONVERSION_NAME	|×	|○	|-	|○
<br>

<hr>
<a name="search_query">
#### 検索クエリレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|×
ADGROUP_ID	|×	|○	|○	|×
KEYWORD_ID	|×	|○	|○	|×
CAMPAIGN_NAME	|×	|○	|○	|×
ADGROUP_NAME	|×	|○	|○	|×
SEARCH_QUERY_DESTINATION_URL	|×	|○	|○	|×
SEARCH_QUERY	|×	|○	|○	|×
SEARCH_QUERY_MATCH_TYPE		|×	|○	|○	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE		|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
AVG_DELIVER_RANK		|×	|×	|×	|×
REVENUE		|×	|○	|○	|×
UNIQUE_CONVERSION		|×	|×	|×	|×
UNIQUE_CONVERSION_RATE		|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION		|×	|○	|○	|×
CONVERSION		|×	|○	|○	|×
CONVERSION_RATE		|×	|×	|×	|×
COST_UNIQUE_CONVERSION		|×	|×	|×	|×
CPA		|×	|×	|×	|×
TRACKING_URL		|×	|○	|○	|×
LANDING_PAGE_URL		|×	|○	|○	|×
CONVERSIONS		|○	|○	|○	|×
CONV_RATE		|○	|×	|×	|×
CONV_VALUE		|○	|○	|○	|×
COST_PER_CONV		|○	|×	|×	|×
VALUE_PER_CONV		|○	|○	|○	|×
ALL_CONV		|○	|○	|○	|×
ALL_CONV_RATE		|○	|×	|×	|×
ALL_CONV_VALUE		|○	|○	|○	|×
COST_PER_ALL_CONV		|○	|×	|×	|×
VALUE_PER_ALL_CONV		|○	|○	|○	|×
NETWORK		|×	|○	|○	|×
DEVICE		|×	|○	|○	|×
DAY		|×	|○	|○	|×
DAY_OF_WEEK		|×	|○	|○	|×
QUARTER		|×	|○	|○	|×
YEAR		|×	|○	|○	|×
MONTH		|×	|○	|○	|×
MONTH_OF_YEAR		|×	|○	|○	|×
WEEK		|×	|○	|○	|×
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|×
CONVERSION_NAME		|×	|○	|-	|×
<br>

<hr>
<a name="geo">
#### 地域別レポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|×
ADGROUP_ID	|×	|○	|○	|×
CAMPAIGN_NAME	|×	|○	|○	|×
ADGROUP_NAME	|×	|○	|○	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE	|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
REVENUE		|×	|○	|○	|×
UNIQUE_CONVERSION	|×	|×	|×	|×
UNIQUE_CONVERSION_RATE	|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION	|×	|○	|○	|×
CONVERSION		|×	|○	|○	|×
CONVERSION_RATE		|×	|×	|×	|×
COST_UNIQUE_CONVERSION	|×	|×	|×	|×
CPA		|×	|×	|×	|×
CONVERSIONS		|○	|○	|○	|×
CONV_RATE		|○	|×	|×	|×
CONV_VALUE		|○	|○	|○	|×
COST_PER_CONV		|○	|×	|×	|×
VALUE_PER_CONV		|○	|○	|○	|×
ALL_CONV		|○	|○	|○	|×
ALL_CONV_RATE		|○	|×	|×	|×
ALL_CONV_VALUE		|○	|○	|○	|×
COST_PER_ALL_CONV		|○	|×	|×	|×
VALUE_PER_ALL_CONV		|○	|○	|○	|×
NETWORK		|×	|○	|○	|×
DEVICE		|×	|○	|○	|×
DAY		|×	|○	|○	|×
DAY_OF_WEEK	|×	|○	|○	|×
QUARTER		|×	|○	|○	|×
YEAR		|×	|○	|○	|×
MONTH		|×	|○	|○	|×
MONTH_OF_YEAR	|×	|○	|○	|×
WEEK		|×	|○	|○	|×
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|×
CONVERSION_NAME	|×	|○	|-	|×
COUNTRY_TERRITORY	|×	|○	|○	|×
PREFECTURE	|×	|○	|○	|×
CITY		|×	|○	|○	|×
<br>

<hr>
<a name="feed_item">
#### 広告表示オプションレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|○
ADGROUP_ID	|×	|○	|○	|○
AD_ID		|×	|○	|○	|○
CAMPAIGN_NAME	|×	|○	|○	|○
ADGROUP_NAME	|×	|○	|○	|○
AD_NAME		|×	|○	|○	|○
COST		|×	|×	|×	|○
IMPS		|×	|×	|×	|○
CLICKS		|×	|×	|×	|○
CLICK_RATE	|×	|×	|×	|○
AVG_CPM		|×	|×	|×	|○
AVG_CPC		|×	|×	|×	|○
AVG_DELIVER_RANK|×	|×	|×	|○
REVENUE		|×	|○	|○	|○
UNIQUE_CONVERSION	|×	|×	|×	|○
UNIQUE_CONVERSION_RATE	|×	|×	|×	|○
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|○
REVENUE_CONVERSION	|×	|○	|○	|○
CONVERSION		|×	|○	|○	|○
CONVERSION_RATE		|×	|○	|○	|○
COST_UNIQUE_CONVERSION	|×	|×	|×	|○
CPA		|×	|○	|○	|○
EDITORIAL_STATUS	|×	|○	|○	|○
PHONE_NUMBER	|×	|○	|○	|○
DEVICE_PREFERENCE	|×	|○	|○	|○
FEED_ID		|×	|○	|○	|○
FEED_ITEM_ID	|×	|○	|○	|○
QUICK_LINK_TEXT	|×	|○	|○	|○
QUICK_LINK_URL	|×	|○	|○	|○
PLACEHOLDER_TYPE	|×	|○	|○	|○
FEED_ITEM_START_DATE	|×	|○	|○	|○
FEED_ITEM_END_DATE	|×	|○	|○	|○
TRACKING_URL		|×	|○	|○	|○
CUSTOM_PARAMETERS	|×	|○	|○	|○
LANDING_PAGE_URL	|×	|○	|○	|○
LANDING_PAGE_URL_SMARTPHONE	|×	|○	|○	|○
CONVERSIONS		|×	|○	|○	|○
CONV_RATE		|×	|○	|○	|○
CONV_VALUE		|×	|○	|○	|○
COST_PER_CONV		|×	|○	|○	|○
VALUE_PER_CONV		|×	|○	|○	|○
ALL_CONV		|×	|○	|○	|○
ALL_CONV_RATE		|×	|○	|○	|○
ALL_CONV_VALUE		|×	|○	|○	|○
COST_PER_ALL_CONV		|×	|○	|○	|○
VALUE_PER_ALL_CONV		|×	|○	|○	|○
NETWORK		|×	|○	|○	|○
CLICK_TYPE	|×	|○	|○	|-
DEVICE		|×	|○	|○	|○
DAY		|×	|○	|○	|○
DAY_OF_WEEK	|×	|○	|○	|○
QUARTER		|×	|○	|○	|○
YEAR		|×	|○	|○	|○
MONTH		|×	|○	|○	|○
MONTH_OF_YEAR	|×	|○	|○	|○
WEEK		|×	|○	|○	|○
HOUR_OF_DAY	|-	|×	|×	|×
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|○
CONVERSION_NAME	|×	|○	|-	|○
IS_SELF_ACTION	|×	|○	|○	|×
<br>

<hr>
<a name="geo_target">
#### 地域ターゲティングレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|×	|×	|×
CAMPAIGN_NAME	|×	|×	|×	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE	|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
AVG_DELIVER_RANK	|×	|×	|×	|×
REVENUE		|×	|×	|×	|×
UNIQUE_CONVERSION	|×	|×	|×	|×
UNIQUE_CONVERSION_RATE	|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION	|×	|×	|×	|×
CONVERSION		|×	|×	|×	|×
CONVERSION_RATE		|×	|×	|×	|×
COST_UNIQUE_CONVERSION	|×	|×	|×	|×
CPA		|×	|×	|×	|×
BID_MULTIPLIER	|×	|×	|×	|×
TARGET_LOCATION_ID	|×	|×	|×	|×
TARGET_LOCATION_NAME	|×	|×	|×	|×
CONVERSIONS	|×	|×	|×	|×
CONV_RATE	|×	|×	|×	|×
CONV_VALUE	|×	|×	|×	|×
COST_PER_CONV	|×	|×	|×	|×
VALUE_PER_CONV	|×	|×	|×	|×
ALL_CONV	|×	|×	|×	|×
ALL_CONV_RATE	|×	|×	|×	|×
ALL_CONV_VALUE	|×	|×	|×	|×
COST_PER_ALL_CONV	|×	|×	|×	|×
VALUE_PER_ALL_CONV	|×	|×	|×	|×
DAY	|×	|×	|×	|×
QUARTER	|×	|×	|×	|×
YEAR	|×	|×	|×	|×
MONTH	|×	|×	|×	|×
MONTH_OF_YEAR	|×	|×	|×	|×
WEEK	|×	|×	|×	|×
<br>

<hr>
<a name="schedule_target">
#### 曜日・時間帯ターゲティングレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|×	|×	|×
CAMPAIGN_NAME	|×	|×	|×	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE	|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
AVG_DELIVER_RANK	|×	|×	|×	|×
REVENUE		|×	|×	|×	|×
UNIQUE_CONVERSION	|×	|×	|×	|×
UNIQUE_CONVERSION_RATE	|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION	|×	|×	|×	|×
CONVERSION	|×	|×	|×	|×
CONVERSION_RATE	|×	|×	|×	|×
COST_UNIQUE_CONVERSION	|×	|×	|×	|×
CPA		|×	|×	|×	|×
BID_MULTIPLIER	|×	|×	|×	|×
TARGET_SCHEDULE_ID	|×	|×	|×	|×
TARGET_SCHEDULE	|×	|×	|×	|×
CONVERSIONS		|×	|×	|×	|×
CONV_RATE		|×	|×	|×	|×
CONV_VALUE		|×	|×	|×	|×
COST_PER_CONV		|×	|×	|×	|×
VALUE_PER_CONV		|×	|×	|×	|×
ALL_CONV		|×	|×	|×	|×
ALL_CONV_RATE		|×	|×	|×	|×
ALL_CONV_VALUE		|×	|×	|×	|×
COST_PER_ALL_CONV		|×	|×	|×	|×
VALUE_PER_ALL_CONV		|×	|×	|×	|×
DAY		|×	|×	|×	|×
QUARTER		|×	|×	|×	|×
YEAR		|×	|×	|×	|×
MONTH		|×	|×	|×	|×
MONTH_OF_YEAR	|×	|×	|×	|×
WEEK		|×	|×	|×	|×
<br>

<hr>
<a name="bid_strategy">
#### 自動入札レポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
COST		|○	|×	|×	|×
IMPS		|○	|×	|×	|×
CLICKS		|○	|×	|×	|×
CLICK_RATE	|○	|×	|×	|×
AVG_CPM		|○	|×	|×	|×
AVG_CPC		|○	|×	|×	|×
AVG_DELIVER_RANK	|○	|×	|×	|×
UNIQUE_CONVERSION	|○	|×	|×	|×
UNIQUE_CONVERSION_RATE	|○	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|○	|×	|×	|×
REVENUE_CONVERSION	|○	|×	|×	|×
CONVERSION		|○	|×	|×	|×
CONVERSION_RATE		|○	|×	|×	|×
COST_UNIQUE_CONVERSION	|○	|×	|×	|×
CPA	|○	|×	|×	|×
BID_STRATEGY_ID		|○	|×	|×	|×
BID_STRATEGY_NAME	|○	|×	|×	|×
BID_STRATEGY_TYPE	|○	|×	|×	|×
AD_GROUP_COUNT		|○	|×	|×	|×
CAMPAIGN_COUNT		|○	|×	|×	|×
TARGET_SEARCH_PAGE_LOCATION	|○	|×	|×	|×
BID_AUTOMATION		|○	|×	|×	|×
BID_MULTIPLIER_OF_TARGET_PAGE_LOCATION	|○	|×	|×	|×
LIMITED_BUDGETS		|○	|×	|×	|×
LOW_QUALITY_KEYWORDS	|○	|×	|×	|×
UPPER_BID_LIMIT_OF_TARGET_PAGE_LOCATION	|○	|×	|×	|×
TARGET_CPA		|○	|×	|×	|×
UPPER_BID_LIMIT_OF_TARGET_CPA	|○	|×	|×	|×
LOWER_BID_LIMIT_OF_TARGET_CPA	|○	|×	|×	|×
TARGET_ROAS		|○	|×	|×	|×
UPPER_BID_LIMIT_OF_TARGET_ROAS	|○	|×	|×	|×
LOWER_BID_LIMIT_OF_TARGET_ROAS	|○	|×	|×	|×
UPPER_BID_LIMIT_OF_MAXIMIZE_CLICKS	|○	|×	|×	|×
CONVERSIONS		|○	|×	|×	|×
CONV_RATE		|○	|×	|×	|×
CONV_VALUE		|○	|×	|×	|×
COST_PER_CONV		|○	|×	|×	|×
VALUE_PER_CONV		|○	|×	|×	|×
ALL_CONV		|×	|×	|×	|×
ALL_CONV_RATE		|×	|×	|×	|×
ALL_CONV_VALUE		|×	|×	|×	|×
COST_PER_ALL_CONV		|×	|×	|×	|×
VALUE_PER_ALL_CONV		|×	|×	|×	|×
DEVICE		|○	|×	|×	|×
DAY		|○	|×	|×	|×
DAY_OF_WEEK	|○	|×	|×	|×
QUARTER		|○	|×	|×	|×
YEAR		|○	|×	|×	|×
MONTH		|○	|×	|×	|×
MONTH_OF_YEAR	|○	|×	|×	|×
WEEK		|○	|×	|×	|×
HOUR_OF_DAY	|-	|×	|×	|×
<br>

<hr>
<a name="target_list">
#### ターゲットリスト設定レポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|○
ADGROUP_ID	|×	|○	|○	|○
CAMPAIGN_NAME	|×	|○	|○	|○
ADGROUP_NAME	|×	|○	|○	|○
COST		|×	|×	|×	|○
IMPS		|×	|×	|×	|○
CLICKS		|×	|×	|×	|○
CLICK_RATE	|×	|×	|×	|○
AVG_CPM		|×	|×	|×	|○
AVG_CPC		|×	|×	|×	|○
AVG_DELIVER_RANK	|×	|×	|×	|○
REVENUE		|×	|○	|○	|○
UNIQUE_CONVERSION	|×	|×	|×	|○
UNIQUE_CONVERSION_RATE	|×	|×	|×	|○
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|○
REVENUE_CONVERSION	|×	|○	|○	|○
CONVERSION	|×	|○	|○	|○
CONVERSION_RATE	|×	|○	|○	|○
COST_UNIQUE_CONVERSION	|×	|×	|×	|○
CPA		|×	|○	|○	|○
BID_MULTIPLIER	|×	|○	|○	|○
TARGET_LIST_ID	|×	|○	|○	|○
TARGET_LIST_NAME	|×	|○	|○	|○
TARGET_LIST_STATUS	|×	|○	|○	|○
CONVERSIONS		|×	|○	|○	|○
CONV_RATE		|×	|○	|○	|○
CONV_VALUE		|×	|○	|○	|○
COST_PER_CONV		|×	|○	|○	|○
VALUE_PER_CONV		|×	|○	|○	|○
ALL_CONV		|×	|○	|○	|○
ALL_CONV_RATE		|×	|○	|○	|○
ALL_CONV_VALUE		|×	|○	|○	|○
COST_PER_ALL_CONV		|×	|○	|○	|○
VALUE_PER_ALL_CONV		|×	|○	|○	|○
NETWORK		|×	|○	|○	|○
CLICK_TYPE	|×	|○	|○	|-
DEVICE		|×	|○	|○	|○
DAY		|×	|○	|○	|○
DAY_OF_WEEK	|×	|○	|○	|○
QUARTER		|×	|○	|○	|○
YEAR		|×	|○	|○	|○
MONTH		|×	|○	|○	|○
MONTH_OF_YEAR	|×	|○	|○	|○
WEEK		|×	|○	|○	|○
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|○
CONVERSION_NAME	|×	|○	|-	|○
<br>

<hr>
<a name="ad_customizers">
#### データ自動挿入レポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|×
ADGROUP_ID	|×	|○	|○	|×
AD_ID		|×	|○	|○	|×
CAMPAIGN_NAME	|×	|○	|○	|×
ADGROUP_NAME	|×	|○	|○	|×
AD_NAME		|×	|○	|○	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE	|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
AVG_DELIVER_RANK	|×	|×	|×	|×
REVENUE		|×	|○	|○	|×
UNIQUE_CONVERSION	|×	|×	|×	|×
UNIQUE_CONVERSION_RATE	|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION	|×	|○	|○	|×
CONVERSION		|×	|○	|○	|×
CONVERSION_RATE		|×	|○	|○	|×
COST_UNIQUE_CONVERSION	|×	|×	|×	|×
CPA		|×	|○	|○	|×
EDITORIAL_STATUS	|×	|○	|○	|×
FEED_ID		|×	|○	|○	|×
FEED_ITEM_ID	|×	|○	|○	|×
FEED_ITEM_START_DATE	|×	|○	|○	|×
FEED_ITEM_END_DATE	|×	|○	|○	|×
FEED_ITEM_ATTRIBUTES	|×	|○	|○	|×
CONVERSIONS		|×	|○	|○	|×
CONV_RATE		|×	|○	|○	|×
CONV_VALUE		|×	|○	|○	|×
COST_PER_CONV		|×	|○	|○	|×
VALUE_PER_CONV		|×	|○	|○	|×
ALL_CONV		|×	|○	|○	|×
ALL_CONV_RATE		|×	|○	|○	|×
ALL_CONV_VALUE		|×	|○	|○	|×
COST_PER_ALL_CONV		|×	|○	|○	|×
VALUE_PER_ALL_CONV		|×	|○	|○	|×
NETWORK		|×	|○	|○	|×
DEVICE		|×	|○	|○	|×
DAY		|×	|○	|○	|×
DAY_OF_WEEK	|×	|○	|○	|×
QUARTER		|×	|○	|○	|×
YEAR		|×	|○	|○	|×
MONTH		|×	|○	|○	|×
MONTH_OF_YEAR	|×	|○	|○	|×
WEEK		|×	|○	|○	|×
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|×
CONVERSION_NAME	|×	|○	|-	|×
<br>

<hr>
<a name="landing_page_url">
#### 最終リンク先URLレポート
利用できるフィールド	|時間との<br>組み合わせ<br>（HOUR_OF_DAY）	|コンバージョン<br>測定の目的との<br>組み合わせ<br>（OBJECT_OF_CONV<br>ERSION_TRACKING）	|コンバージョン名<br>との組み合わせ<br>（CONVER<br>SION_NAME）	|クリック種別<br>との組み合わせ<br>（CLICK_TYPE）
-----|-----|-----|-----|-----
CAMPAIGN_ID	|×	|○	|○	|×
ADGROUP_ID	|×	|○	|○	|×
CAMPAIGN_NAME	|×	|○	|○	|×
ADGROUP_NAME	|×	|○	|○	|×
COST		|×	|×	|×	|×
IMPS		|×	|×	|×	|×
CLICKS		|×	|×	|×	|×
CLICK_RATE	|×	|×	|×	|×
AVG_CPM		|×	|×	|×	|×
AVG_CPC		|×	|×	|×	|×
AVG_DELIVER_RANK	|×	|×	|×	|×
REVENUE		|×	|○	|○	|×
UNIQUE_CONVERSION	|×	|×	|×	|×
UNIQUE_CONVERSION_RATE	|×	|×	|×	|×
REVENUE_UNIQUE_CONVERSION	|×	|×	|×	|×
REVENUE_CONVERSION	|×	|○	|○	|×
CONVERSION	|×	|○	|○	|×
CONVERSION_RATE	|×	|×	|×	|×
COST_UNIQUE_CONVERSION	|×	|×	|×	|×
CPA		|×	|×	|×	|×
TRACKING_URL	|×	|○	|○	|×
LANDING_PAGE_URL	|×	|○	|○	|×
CONVERSIONS		|×	|○	|○	|×
CONV_RATE		|×	|×	|×	|×
CONV_VALUE		|×	|○	|○	|×
COST_PER_CONV		|×	|×	|×	|×
VALUE_PER_CONV		|×	|○	|○	|×
ALL_CONV		|×	|○	|○	|×
ALL_CONV_RATE		|×	|×	|×	|×
ALL_CONV_VALUE		|×	|○	|○	|×
COST_PER_ALL_CONV		|×	|×	|×	|×
VALUE_PER_ALL_CONV		|×	|○	|○	|×
NETWORK		|×	|○	|○	|×
DEVICE		|×	|○	|○	|×
DAY		|×	|○	|○	|×
DAY_OF_WEEK	|×	|○	|○	|×
QUARTER		|×	|○	|○	|×
YEAR		|×	|○	|○	|×
MONTH		|×	|○	|○	|×
MONTH_OF_YEAR	|×	|○	|○	|×
WEEK		|×	|○	|○	|×
OBJECT_OF_CONVERSION_TRACKING	|×	|-	|○	|×
CONVERSION_NAME	|×	|○	|-	|×
<br>

<hr>
