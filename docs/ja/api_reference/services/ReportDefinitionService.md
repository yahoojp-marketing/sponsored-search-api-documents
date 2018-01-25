# ReportDefinitionService
ReportDefinitionServiceでは、レポート定義の取得および追加・削除を行います。<br>
レポート定義では、レポート形式、期間およびフィールドを指定します。<br>
また特定のレポート形式に対して使用可能なレポートフィールドを取得する操作が提供されます。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
以下の操作が実行可能です。
- レポート定義の取得
- レポート定義の登録
- レポート定義の削除
- レポート出力項目の取得

【レポート定義の登録上限数】
- テンプレートとして登録されたレポート定義（定期レポート用）は、標準認証と代行認証で併せて最大30件まで登録できます。
- テンプレートとして登録しないレポート定義（ONETIMEレポート用）の登録上限数はありません。<br>
例：<br>
テンプレートとして登録されたレポート定義を、標準認証で20件登録済みの場合、代行認証では残り10件まで登録できます。<br>
※登録上限数に達した状態から新たにレポート定義を登録する場合は、登録済みのレポート定義を削除する必要があります。

【補足】
- 同じAPIアカウントIDで作成されたレポート定義は、認証方式に関係なくすべて確認できます。

#### 操作
ReportDefinitionServiceで提供される操作を説明します。

## get
レポート定義に関する情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | 操作の対象とするレポート定義です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V6">
      <selector>
        <accountId>100000001</accountId>
        <reportIds>1111</reportIds>
        <reportIds>1111</reportIds>
        <paging>
          <startIndex>1</startIndex>
          <numberResults>10</numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | 取得されるレポート定義のエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ReportDefinition</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <totalNumEntries>2</totalNumEntries>
        <Page.Type>ReportDefinitionPage</Page.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <reportDefinition>
            <reportId>1111</reportId>
            <reportName>Sample LANDING_PAGE_URL Report</reportName>
            <reportType>LANDING_PAGE_URL</reportType>
            <dateRangeType>CUSTOM_DATE</dateRangeType>
            <dateRange>
              <startDate>20160101</startDate>
              <endDate>20161231</endDate>
            </dateRange>
            <fields>CAMPAIGN_ID</fields>
            <fields>ADGROUP_ID</fields>
            <fields>CAMPAIGN_NAME</fields>
            <fields>ADGROUP_NAME</fields>
            <fields>COST</fields>
            <fields>IMPS</fields>
            <fields>CLICKS</fields>
            <fields>CLICK_RATE</fields>
            <fields>AVG_CPM</fields>
            <fields>AVG_CPC</fields>
            <fields>AVG_DELIVER_RANK</fields>
            <fields>REVENUE</fields>
            <fields>UNIQUE_CONVERSION</fields>
            <fields>UNIQUE_CONVERSION_RATE</fields>
            <fields>REVENUE_UNIQUE_CONVERSION</fields>
            <fields>TRACKING_URL</fields>
            <fields>CUSTOM_PARAMETERS</fields>
            <fields>LANDING_PAGE_URL</fields>
            <fields>NETWORK</fields>
            <fields>DEVICE</fields>
            <fields>DAY</fields>
            <fields>DAY_OF_WEEK</fields>
            <fields>QUARTER</fields>
            <fields>YEAR</fields>
            <fields>MONTH</fields>
            <fields>MONTH_OF_YEAR</fields>
            <fields>WEEK</fields>
            <fields>OBJECT_OF_CONVERSION_TRACKING</fields>
            <fields>CONVERSION_NAME</fields>
            <sortFields>
              <type>ASC</type>
              <field>CLICKS</field>
            </sortFields>
            <filters>
              <field>TRACKING_URL</field>
              <operator>IN</operator>
              <value>http://yahoo.co.jp</value>
              <value>http://marketing.yahoo.co.jp</value>
              <value>http://promotionalads.yahoo.co.jp</value>
            </filters>
            <filters>
              <field>IMPS</field>
              <operator>GREATER_THAN</operator>
              <value>0</value>
            </filters>
            <filters>
              <field>CAMPAIGN_ID</field>
              <operator>IN</operator>
              <value>200000001</value>
              <value>200000002</value>
              <value>200000003</value>
              <value>200000003</value>
              <value>200000004</value>
              <value>200000005</value>
            </filters>
            <isTemplate>FALSE</isTemplate>
            <intervalType>SPECIFYDAY</intervalType>
            <specifyDay>28</specifyDay>
            <format>CSV</format>
            <encode>UTF-8</encode>
            <language>EN</language>
            <compress>NONE</compress>
            <includeZeroImpressions>FALSE</includeZeroImpressions>
            <includeDeleted>FALSE</includeDeleted>
          </reportDefinition>
        </values>
      </rval>
    </getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields
レポートタイプに対して使用可能なレポートのフィールドを返します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| reportType | ○ | enum [ReportType](../data/ReportType.md) | レポートの形式です。 |

##### ＜リクエストサンプル＞（LANDING_PAGE_URL）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReportFields xmlns="http://ss.yahooapis.jp/V6">
      <reportType>LANDING_PAGE_URL</reportType>
    </getReportFields>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | 取得される使用可能なレポートのエントリーです。 | 

＜レスポンスサンプル＞（LANDING_PAGE_URL）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ReportDefinition</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReportFieldsResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <fields>
          <fieldName>CAMPAIGN_ID</fieldName>
          <displayFieldNameJA>キャンペーンID</displayFieldNameJA>
          <displayFieldNameEN>CampaignID</displayFieldNameEN>
          <xmlAttributeName>campaignID</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>ADGROUP_ID</fieldName>
          <displayFieldNameJA>広告グループID</displayFieldNameJA>
          <displayFieldNameEN>Ad Group ID</displayFieldNameEN>
          <xmlAttributeName>adgroupID</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>CAMPAIGN_NAME</fieldName>
          <displayFieldNameJA>キャンペーン名</displayFieldNameJA>
          <displayFieldNameEN>Campaign Name</displayFieldNameEN>
          <xmlAttributeName>campaignName</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>ADGROUP_NAME</fieldName>
          <displayFieldNameJA>広告グループ名</displayFieldNameJA>
          <displayFieldNameEN>Ad Group Name</displayFieldNameEN>
          <xmlAttributeName>adgroupName</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>COST</fieldName>
          <displayFieldNameJA>コスト</displayFieldNameJA>
          <displayFieldNameEN>Cost</displayFieldNameEN>
          <xmlAttributeName>cost</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>IMPS</fieldName>
          <displayFieldNameJA>インプレッション数</displayFieldNameJA>
          <displayFieldNameEN>Impressions</displayFieldNameEN>
          <xmlAttributeName>impressions</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>CLICKS</fieldName>
          <displayFieldNameJA>クリック数</displayFieldNameJA>
          <displayFieldNameEN>Clicks</displayFieldNameEN>
          <xmlAttributeName>clicks</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>CLICK_RATE</fieldName>
          <displayFieldNameJA>クリック率</displayFieldNameJA>
          <displayFieldNameEN>CTR</displayFieldNameEN>
          <xmlAttributeName>ctr</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>AVG_CPC</fieldName>
          <displayFieldNameJA>平均CPC</displayFieldNameJA>
          <displayFieldNameEN>Avg. CPC</displayFieldNameEN>
          <xmlAttributeName>averageCpc</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>AVG_DELIVER_RANK</fieldName>
          <displayFieldNameJA>平均掲載順位</displayFieldNameJA>
          <displayFieldNameEN>Avg. Position</displayFieldNameEN>
          <xmlAttributeName>averagePosition</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>TRACKING_URL</fieldName>
          <displayFieldNameJA>トラッキングURL</displayFieldNameJA>
          <displayFieldNameEN>Tracking URL</displayFieldNameEN>
          <xmlAttributeName>trackingURL</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>LANDING_PAGE_URL</fieldName>
          <displayFieldNameJA>最終リンク先URL</displayFieldNameJA>
          <displayFieldNameEN>Landing Page URL</displayFieldNameEN>
          <xmlAttributeName>landingPageURL</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>CONVERSIONS</fieldName>
          <displayFieldNameJA>コンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Conversions</displayFieldNameEN>
          <xmlAttributeName>conversions</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>CONV_RATE</fieldName>
          <displayFieldNameJA>コンバージョン率</displayFieldNameJA>
          <displayFieldNameEN>Conv. Rate</displayFieldNameEN>
          <xmlAttributeName>convRate</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>CONV_VALUE</fieldName>
          <displayFieldNameJA>コンバージョンの価値</displayFieldNameJA>
          <displayFieldNameEN>Conv. Value</displayFieldNameEN>
          <xmlAttributeName>convValue</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>COST_PER_CONV</fieldName>
          <displayFieldNameJA>コスト/コンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Cost Per Conv.</displayFieldNameEN>
          <xmlAttributeName>costPerConv</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>VALUE_PER_CONV</fieldName>
          <displayFieldNameJA>価値/コンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Value Per Conv.</displayFieldNameEN>
          <xmlAttributeName>valuePerConv</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>ALL_CONV</fieldName>
          <displayFieldNameJA>すべてのコンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>All Conv.</displayFieldNameEN>
          <xmlAttributeName>allConv</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>ALL_CONV_RATE</fieldName>
          <displayFieldNameJA>すべてのコンバージョン率</displayFieldNameJA>
          <displayFieldNameEN>All Conv. Rate</displayFieldNameEN>
          <xmlAttributeName>allConvRate</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>ALL_CONV_VALUE</fieldName>
          <displayFieldNameJA>すべてのコンバージョンの価値</displayFieldNameJA>
          <displayFieldNameEN>All Conv. Value</displayFieldNameEN>
          <xmlAttributeName>allConvValue</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>COST_PER_ALL_CONV</fieldName>
          <displayFieldNameJA>コスト/すべてのコンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Cost Per All Conv.</displayFieldNameEN>
          <xmlAttributeName>costPerAllConv</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>CONVERSION_NAME</impossibleCombinationFields>
          <impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>VALUE_PER_ALL_CONV</fieldName>
          <displayFieldNameJA>価値/すべてのコンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Value Per All Conv.</displayFieldNameEN>
          <xmlAttributeName>valuePerAllConv</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>CROSS_DEVICE_CONVERSIONS</fieldName>
          <displayFieldNameJA>デバイスをまたいだコンバージョン数</displayFieldNameJA>
          <displayFieldNameEN>Conversions across devices</displayFieldNameEN>
          <xmlAttributeName>crossDeviceConversions</xmlAttributeName>
          <fieldType>DOUBLE</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>CAMPAIGN_TRACKING_ID</fieldName>
          <displayFieldNameJA>キャンペーントラッキングID</displayFieldNameJA>
          <displayFieldNameEN>Campaign Tracking ID</displayFieldNameEN>
          <xmlAttributeName>campaignTrackingID</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>ADGROUP_TRACKING_ID</fieldName>
          <displayFieldNameJA>広告グループトラッキングID</displayFieldNameJA>
          <displayFieldNameEN>Ad Group Tracking ID</displayFieldNameEN>
          <xmlAttributeName>adgroupTrackingID</xmlAttributeName>
          <fieldType>LONG</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>NETWORK</fieldName>
          <displayFieldNameJA>広告掲載方式の指定</displayFieldNameJA>
          <displayFieldNameEN>Network</displayFieldNameEN>
          <xmlAttributeName>network</xmlAttributeName>
          <fieldType>ENUM</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>DEVICE</fieldName>
          <displayFieldNameJA>デバイス</displayFieldNameJA>
          <displayFieldNameEN>Device</displayFieldNameEN>
          <xmlAttributeName>device</xmlAttributeName>
          <fieldType>ENUM</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>DAY</fieldName>
          <displayFieldNameJA>日</displayFieldNameJA>
          <displayFieldNameEN>Day</displayFieldNameEN>
          <xmlAttributeName>day</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>DAY_OF_WEEK</fieldName>
          <displayFieldNameJA>曜日</displayFieldNameJA>
          <displayFieldNameEN>Day of week</displayFieldNameEN>
          <xmlAttributeName>dayOfWeek</xmlAttributeName>
          <fieldType>ENUM</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>QUARTER</fieldName>
          <displayFieldNameJA>四半期</displayFieldNameJA>
          <displayFieldNameEN>Quarter</displayFieldNameEN>
          <xmlAttributeName>quarter</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>YEAR</fieldName>
          <displayFieldNameJA>年間</displayFieldNameJA>
          <displayFieldNameEN>Year</displayFieldNameEN>
          <xmlAttributeName>year</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>MONTH</fieldName>
          <displayFieldNameJA>毎月</displayFieldNameJA>
          <displayFieldNameEN>Month</displayFieldNameEN>
          <xmlAttributeName>month</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>MONTH_OF_YEAR</fieldName>
          <displayFieldNameJA>月</displayFieldNameJA>
          <displayFieldNameEN>Month of Year</displayFieldNameEN>
          <xmlAttributeName>monthofYear</xmlAttributeName>
          <fieldType>ENUM</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>WEEK</fieldName>
          <displayFieldNameJA>毎週</displayFieldNameJA>
          <displayFieldNameEN>Week</displayFieldNameEN>
          <xmlAttributeName>week</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
        </fields>
        <fields>
          <fieldName>OBJECT_OF_CONVERSION_TRACKING</fieldName>
          <displayFieldNameJA>コンバージョン測定の目的</displayFieldNameJA>
          <displayFieldNameEN>Objective of Conversion Tracking</displayFieldNameEN>
          <xmlAttributeName>objectiveOfConversionTracking</xmlAttributeName>
          <fieldType>ENUM</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>COST</impossibleCombinationFields>
          <impossibleCombinationFields>IMPS</impossibleCombinationFields>
          <impossibleCombinationFields>CLICKS</impossibleCombinationFields>
          <impossibleCombinationFields>CLICK_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>AVG_CPC</impossibleCombinationFields>
          <impossibleCombinationFields>AVG_DELIVER_RANK</impossibleCombinationFields>
          <impossibleCombinationFields>CONV_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>COST_PER_CONV</impossibleCombinationFields>
          <impossibleCombinationFields>ALL_CONV_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>COST_PER_ALL_CONV</impossibleCombinationFields>
        </fields>
        <fields>
          <fieldName>CONVERSION_NAME</fieldName>
          <displayFieldNameJA>コンバージョン名</displayFieldNameJA>
          <displayFieldNameEN>Conversion Name</displayFieldNameEN>
          <xmlAttributeName>conversionName</xmlAttributeName>
          <fieldType>STRING</fieldType>
          <canSelect>true</canSelect>
          <canFilter>true</canFilter>
          <impossibleCombinationFields>COST</impossibleCombinationFields>
          <impossibleCombinationFields>IMPS</impossibleCombinationFields>
          <impossibleCombinationFields>CLICKS</impossibleCombinationFields>
          <impossibleCombinationFields>CLICK_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>AVG_CPC</impossibleCombinationFields>
          <impossibleCombinationFields>AVG_DELIVER_RANK</impossibleCombinationFields>
          <impossibleCombinationFields>CONV_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>COST_PER_CONV</impossibleCombinationFields>
          <impossibleCombinationFields>ALL_CONV_RATE</impossibleCombinationFields>
          <impossibleCombinationFields>COST_PER_ALL_CONV</impossibleCombinationFields>
        </fields>
      </rval>
    </getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
レポート定義を追加します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | 操作の対象となるレポート定義および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V6">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <reportName>Sample Report Definition</reportName>
          <reportType>ACCOUNT</reportType>
          <dateRangeType>CUSTOM_DATE</dateRangeType>
          <dateRange>
            <startDate>19700101</startDate>
            <endDate>20371231</endDate>
          </dateRange>
          <fields>COST</fields>
          <fields>IMPS</fields>
          <fields>CLICKS</fields>
          <fields>CLICK_RATE</fields>
          <fields>AVG_CPC</fields>
          <fields>AVG_DELIVER_RANK</fields>
          <fields>TRACKING_URL</fields>
          <fields>CONVERSIONS</fields>
          <fields>CONV_RATE</fields>
          <fields>CONV_VALUE</fields>
          <fields>COST_PER_CONV</fields>
          <fields>VALUE_PER_CONV</fields>
          <fields>NETWORK</fields>
          <fields>CLICK_TYPE</fields>
          <fields>DEVICE</fields>
          <fields>DAY</fields>
          <fields>DAY_OF_WEEK</fields>
          <fields>QUARTER</fields>
          <fields>YEAR</fields>
          <fields>MONTH</fields>
          <fields>MONTH_OF_YEAR</fields>
          <fields>WEEK</fields>
          <fields>HOUR_OF_DAY</fields>
          <sortFields>
            <type>ASC</type>
            <field>CLICKS</field>
          </sortFields>
          <filters>
            <field>COST</field>
            <operator>NOT_EQUALS</operator>
            <value>100</value>
          </filters>
          <isTemplate>TRUE</isTemplate>
          <intervalType>SPECIFYDAY</intervalType>
          <specifyDay>1</specifyDay>
          <format>CSV</format>
          <encode>UTF-8</encode>
          <language>JA</language>
          <compress>NONE</compress>
          <includeZeroImpressions>TRUE</includeZeroImpressions>
          <includeDeleted>TRUE</includeDeleted>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | 操作結果を含むレポート定義のコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ReportDefinition</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <reportDefinition>
            <accountId>11111</accountId>
            <reportId>22222</reportId>
            <reportName>Sample Report Definition</reportName>
            <reportType>ACCOUNT</reportType>
            <dateRangeType>CUSTOM_DATE</dateRangeType>
            <dateRange>
              <startDate>19700101</startDate>
              <endDate>20371231</endDate>
            </dateRange>
            <fields>COST</fields>
            <fields>IMPS</fields>
            <fields>CLICKS</fields>
            <fields>CLICK_RATE</fields>
            <fields>AVG_CPC</fields>
            <fields>AVG_DELIVER_RANK</fields>
            <fields>TRACKING_URL</fields>
            <fields>CONVERSIONS</fields>
            <fields>CONV_RATE</fields>
            <fields>CONV_VALUE</fields>
            <fields>COST_PER_CONV</fields>
            <fields>VALUE_PER_CONV</fields>
            <fields>NETWORK</fields>
            <fields>CLICK_TYPE</fields>
            <fields>DEVICE</fields>
            <fields>DAY</fields>
            <fields>DAY_OF_WEEK</fields>
            <fields>QUARTER</fields>
            <fields>YEAR</fields>
            <fields>MONTH</fields>
            <fields>MONTH_OF_YEAR</fields>
            <fields>WEEK</fields>
            <fields>HOUR_OF_DAY</fields>
            <sortFields>
              <type>ASC</type>
              <field>CLICKS</field>
            </sortFields>
            <filters>
              <field>COST</field>
              <operator>NOT_EQUALS</operator>
              <value>100</value>
            </filters>
            <isTemplate>TRUE</isTemplate>
            <intervalType>SPECIFYDAY</intervalType>
            <specifyDay>1</specifyDay>
            <format>CSV</format>
            <encode>UTF-8</encode>
            <language>JA</language>
            <compress>NONE</compress>
            <includeZeroImpressions>TRUE</includeZeroImpressions>
            <includeDeleted>TRUE</includeDeleted>
          </reportDefinition>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
レポート定義を削除します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | 操作の対象となるレポート定義および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V6">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <reportId>22222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | 操作結果を含むレポート定義のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ReportDefinition</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <reportDefinition>
            <accountId>11111</accountId>
            <reportId>22222</reportId>
            <reportName>Sample Report Definition</reportName>
            <reportType>ACCOUNT</reportType>
            <dateRangeType>CUSTOM_DATE</dateRangeType>
            <dateRange>
              <startDate>19700101</startDate>
              <endDate>20371231</endDate>
            </dateRange>
            <fields>COST</fields>
            <fields>IMPS</fields>
            <fields>CLICKS</fields>
            <fields>CLICK_RATE</fields>
            <fields>AVG_CPC</fields>
            <fields>AVG_DELIVER_RANK</fields>
            <fields>TRACKING_URL</fields>
            <fields>CONVERSIONS</fields>
            <fields>CONV_RATE</fields>
            <fields>CONV_VALUE</fields>
            <fields>COST_PER_CONV</fields>
            <fields>VALUE_PER_CONV</fields>
            <fields>NETWORK</fields>
            <fields>CLICK_TYPE</fields>
            <fields>DEVICE</fields>
            <fields>DAY</fields>
            <fields>DAY_OF_WEEK</fields>
            <fields>QUARTER</fields>
            <fields>YEAR</fields>
            <fields>MONTH</fields>
            <fields>MONTH_OF_YEAR</fields>
            <fields>WEEK</fields>
            <fields>HOUR_OF_DAY</fields>
            <sortFields>
              <type>ASC</type>
              <field>CLICKS</field>
            </sortFields>
            <filters>
              <field>COST</field>
              <operator>NOT_EQUALS</operator>
              <value>100</value>
            </filters>
            <isTemplate>TRUE</isTemplate>
            <intervalType>SPECIFYDAY</intervalType>
            <specifyDay>1</specifyDay>
            <format>CSV</format>
            <encode>UTF-8</encode>
            <language>JA</language>
            <compress>NONE</compress>
            <includeZeroImpressions>TRUE</includeZeroImpressions>
            <includeDeleted>TRUE</includeDeleted>
          </reportDefinition>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
