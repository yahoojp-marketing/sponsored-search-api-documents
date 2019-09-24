# スポンサードサーチレポートの作成・取得
## パフォーマンスレポートとは
パフォーマンスレポートはキャンペーン、広告グループ、広告、キーワードなどのパフォーマンスを確認するための機能です。
パフォーマンスレポートは、パフォーマンスを表示する階層、表示項目、集計期間などの設定により、広告主様のニーズにあわせたカスタマイズが可能です。

広告管理ツールで提供しているレポート機能をAPIでもサポートしています。
## スポンサードサーチ APIでの実施方法
スポンサードサーチAPIではレポートを表示するために、以下のServiceを使用します。

##### ReportDefinitionService
ReportDefinitionServiceでは、レポート出力項目の取得およびレポート作成・取得・削除を行います。<br>
またレポートのダウンロードURLを取得する操作が実施できます。

## シナリオ
パフォーマンスレポート取得のため、スポンサードサーチAPIを使い以下のレポート作成から削除までのフローをご紹介します。

#### 1.	レポートのフィールド情報の取得
ReportDefinitionServiceのgetReportFieldsを使用します。
ReportTypeを指定して、利用可能なレポートフィールドのリストを取得します。
各レポートフィールドはフィールド名、フィールドデータタイプ、およびenum値をカプセル化します。

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReportFields xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <reportType>LANDING_PAGE_URL</reportType>
    </getReportFields>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1566034880616</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getReportFieldsResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <ns2:rval>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>CampaignID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adgroupID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループ名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adgroupName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>cost</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>インプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Impressions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>impressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICKS</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Clicks</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>clicks</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>CTR</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ctr</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPC</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPC</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. CPC</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>averageCpc</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_DELIVER_RANK</ns2:fieldName>
          <ns2:displayFieldNameJA>平均掲載順位</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. Position</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>averagePosition</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>TRACKING_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>トラッキングURL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Tracking URL</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>trackingURL</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>LANDING_PAGE_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>最終リンク先URL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Landing Page URL</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>landingPageURL</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSIONS</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversions</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_VALUE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. Value</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValue</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost Per Conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VALUE_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>価値/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Value Per Conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>valuePerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>すべてのコンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>All Conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>allConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>すべてのコンバージョン率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>All Conv. Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>allConvRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV_VALUE</ns2:fieldName>
          <ns2:displayFieldNameJA>すべてのコンバージョンの価値</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>All Conv. Value</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>allConvValue</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/すべてのコンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost Per All Conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerAllConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>OBJECT_OF_CONVERSION_TRACKING</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VALUE_PER_ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>価値/すべてのコンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Value Per All Conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>valuePerAllConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CROSS_DEVICE_CONVERSIONS</ns2:fieldName>
          <ns2:displayFieldNameJA>デバイスをまたいだコンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions across devices</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>crossDeviceConversions</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_TRACKING_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーントラッキングID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Tracking ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignTrackingID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_TRACKING_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループトラッキングID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group Tracking ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adgroupTrackingID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>NETWORK</ns2:fieldName>
          <ns2:displayFieldNameJA>広告掲載方式の指定</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Network</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>network</ns2:xmlAttributeName>
          <ns2:fieldType>ENUM</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DEVICE</ns2:fieldName>
          <ns2:displayFieldNameJA>デバイス</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Device</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>device</ns2:xmlAttributeName>
          <ns2:fieldType>ENUM</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DAY</ns2:fieldName>
          <ns2:displayFieldNameJA>日</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Day</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>day</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DAY_OF_WEEK</ns2:fieldName>
          <ns2:displayFieldNameJA>曜日</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Day of week</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>dayOfWeek</ns2:xmlAttributeName>
          <ns2:fieldType>ENUM</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>QUARTER</ns2:fieldName>
          <ns2:displayFieldNameJA>四半期</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Quarter</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>quarter</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>YEAR</ns2:fieldName>
          <ns2:displayFieldNameJA>年間</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Year</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>year</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MONTH</ns2:fieldName>
          <ns2:displayFieldNameJA>毎月</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Month</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>month</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MONTH_OF_YEAR</ns2:fieldName>
          <ns2:displayFieldNameJA>月</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Month of Year</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>monthofYear</ns2:xmlAttributeName>
          <ns2:fieldType>ENUM</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>WEEK</ns2:fieldName>
          <ns2:displayFieldNameJA>毎週</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Week</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>week</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>OBJECT_OF_CONVERSION_TRACKING</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン測定の目的</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Objective of Conversion Tracking</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>objectiveOfConversionTracking</ns2:xmlAttributeName>
          <ns2:fieldType>ENUM</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICKS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_ALL_CONV</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversion Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversionName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:canSelect>true</ns2:canSelect>
          <ns2:canFilter>true</ns2:canFilter>
          <ns2:impossibleCombinationFields>COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICKS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_ALL_CONV</ns2:impossibleCombinationFields>
        </ns2:fields>
      </ns2:rval>
    </ns2:getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 2.	レポートを作成
ReportDefinitionServiceのmutate:addを使用します。
* レポートの名称
* 集計期間の設定
* 日本語/英語の指定
* 出力フォーマットの指定などが必要です。

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition">
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

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1566034880600</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportJobId>22222</ns2:reportJobId>
            <ns2:reportJobStatus>WAIT</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:reportName>Sample Report Definition</ns2:reportName>
            <ns2:reportType>ACCOUNT</ns2:reportType>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>19700101</ns2:startDate>
              <ns2:endDate>20371231</ns2:endDate>
            </ns2:dateRange>
            <ns2:fields>COST</ns2:fields>
            <ns2:fields>IMPS</ns2:fields>
            <ns2:fields>CLICKS</ns2:fields>
            <ns2:fields>CLICK_RATE</ns2:fields>
            <ns2:fields>AVG_CPC</ns2:fields>
            <ns2:fields>AVG_DELIVER_RANK</ns2:fields>
            <ns2:fields>TRACKING_URL</ns2:fields>
            <ns2:fields>CONVERSIONS</ns2:fields>
            <ns2:fields>CONV_RATE</ns2:fields>
            <ns2:fields>CONV_VALUE</ns2:fields>
            <ns2:fields>COST_PER_CONV</ns2:fields>
            <ns2:fields>VALUE_PER_CONV</ns2:fields>
            <ns2:fields>NETWORK</ns2:fields>
            <ns2:fields>CLICK_TYPE</ns2:fields>
            <ns2:fields>DEVICE</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:fields>DAY_OF_WEEK</ns2:fields>
            <ns2:fields>QUARTER</ns2:fields>
            <ns2:fields>YEAR</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>MONTH_OF_YEAR</ns2:fields>
            <ns2:fields>WEEK</ns2:fields>
            <ns2:fields>HOUR_OF_DAY</ns2:fields>
            <ns2:sortFields>
              <ns2:type>ASC</ns2:type>
              <ns2:field>CLICKS</ns2:field>
            </ns2:sortFields>
            <ns2:filters>
              <ns2:field>COST</ns2:field>
              <ns2:operator>NOT_EQUALS</ns2:operator>
              <ns2:value>100</ns2:value>
            </ns2:filters>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:language>JA</ns2:language>
            <ns2:compress>NONE</ns2:compress>
            <ns2:includeZeroImpressions>TRUE</ns2:includeZeroImpressions>
            <ns2:includeDeleted>TRUE</ns2:includeDeleted>
          </ns2:reportDefinition>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 3.	レポート作成状況の確認とダウンロード
ReportDefinitionServiceのgetを使用します。<br>
作成状況の確認ができます。<br>
また、作成が完了したレポートにはダウンロードURLが表示されます。<br>

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>100000001</accountId>
        <reportJobIds>1111</reportJobIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1566034880572</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>ReportDefinitionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:reportJobId>1111</ns2:reportJobId>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
            <ns2:reportDownloadURL>https://ss.yahooapis.jp/report/VERSION/download/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B</ns2:reportDownloadURL>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:reportType>LANDING_PAGE_URL</ns2:reportType>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>20160101</ns2:startDate>
              <ns2:endDate>20161231</ns2:endDate>
            </ns2:dateRange>
            <ns2:fields>CAMPAIGN_ID</ns2:fields>
            <ns2:fields>ADGROUP_ID</ns2:fields>
            <ns2:fields>CAMPAIGN_NAME</ns2:fields>
            <ns2:fields>ADGROUP_NAME</ns2:fields>
            <ns2:fields>COST</ns2:fields>
            <ns2:fields>IMPS</ns2:fields>
            <ns2:fields>CLICKS</ns2:fields>
            <ns2:fields>CLICK_RATE</ns2:fields>
            <ns2:fields>AVG_CPM</ns2:fields>
            <ns2:fields>AVG_CPC</ns2:fields>
            <ns2:fields>AVG_DELIVER_RANK</ns2:fields>
            <ns2:fields>REVENUE</ns2:fields>
            <ns2:fields>UNIQUE_CONVERSION</ns2:fields>
            <ns2:fields>UNIQUE_CONVERSION_RATE</ns2:fields>
            <ns2:fields>REVENUE_UNIQUE_CONVERSION</ns2:fields>
            <ns2:fields>TRACKING_URL</ns2:fields>
            <ns2:fields>CUSTOM_PARAMETERS</ns2:fields>
            <ns2:fields>LANDING_PAGE_URL</ns2:fields>
            <ns2:fields>NETWORK</ns2:fields>
            <ns2:fields>DEVICE</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:fields>DAY_OF_WEEK</ns2:fields>
            <ns2:fields>QUARTER</ns2:fields>
            <ns2:fields>YEAR</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>MONTH_OF_YEAR</ns2:fields>
            <ns2:fields>WEEK</ns2:fields>
            <ns2:fields>OBJECT_OF_CONVERSION_TRACKING</ns2:fields>
            <ns2:fields>CONVERSION_NAME</ns2:fields>
            <ns2:sortFields>
              <ns2:type>ASC</ns2:type>
              <ns2:field>CLICKS</ns2:field>
            </ns2:sortFields>
            <ns2:filters>
              <ns2:field>TRACKING_URL</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:value>http://yahoo.co.jp</ns2:value>
              <ns2:value>http://marketing.yahoo.co.jp</ns2:value>
              <ns2:value>http://promotionalads.yahoo.co.jp</ns2:value>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>IMPS</ns2:field>
              <ns2:operator>GREATER_THAN</ns2:operator>
              <ns2:value>0</ns2:value>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>CAMPAIGN_ID</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:value>200000001</ns2:value>
              <ns2:value>200000002</ns2:value>
              <ns2:value>200000003</ns2:value>
              <ns2:value>200000003</ns2:value>
              <ns2:value>200000004</ns2:value>
              <ns2:value>200000005</ns2:value>
            </ns2:filters>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:language>EN</ns2:language>
            <ns2:compress>NONE</ns2:compress>
            <ns2:includeZeroImpressions>FALSE</ns2:includeZeroImpressions>
            <ns2:includeDeleted>FALSE</ns2:includeDeleted>
          </ns2:reportDefinition>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


#### 4.	レポートの削除
ReportDefinitionServiceのmutate:removeを使用します。
ダウンロードし終わったレポートをReportListから削除します。一定期間経過すると自動で削除されます。

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <reportJobId>22222</reportJobId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ReportDefinition" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1566034880631</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportJobId>22222</ns2:reportJobId>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
            <ns2:reportName>Sample Report Definition</ns2:reportName>
            <ns2:reportType>ACCOUNT</ns2:reportType>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>19700101</ns2:startDate>
              <ns2:endDate>20371231</ns2:endDate>
            </ns2:dateRange>
            <ns2:fields>COST</ns2:fields>
            <ns2:fields>IMPS</ns2:fields>
            <ns2:fields>CLICKS</ns2:fields>
            <ns2:fields>CLICK_RATE</ns2:fields>
            <ns2:fields>AVG_CPC</ns2:fields>
            <ns2:fields>AVG_DELIVER_RANK</ns2:fields>
            <ns2:fields>TRACKING_URL</ns2:fields>
            <ns2:fields>CONVERSIONS</ns2:fields>
            <ns2:fields>CONV_RATE</ns2:fields>
            <ns2:fields>CONV_VALUE</ns2:fields>
            <ns2:fields>COST_PER_CONV</ns2:fields>
            <ns2:fields>VALUE_PER_CONV</ns2:fields>
            <ns2:fields>NETWORK</ns2:fields>
            <ns2:fields>CLICK_TYPE</ns2:fields>
            <ns2:fields>DEVICE</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:fields>DAY_OF_WEEK</ns2:fields>
            <ns2:fields>QUARTER</ns2:fields>
            <ns2:fields>YEAR</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>MONTH_OF_YEAR</ns2:fields>
            <ns2:fields>WEEK</ns2:fields>
            <ns2:fields>HOUR_OF_DAY</ns2:fields>
            <ns2:sortFields>
              <ns2:type>ASC</ns2:type>
              <ns2:field>CLICKS</ns2:field>
            </ns2:sortFields>
            <ns2:filters>
              <ns2:field>COST</ns2:field>
              <ns2:operator>NOT_EQUALS</ns2:operator>
              <ns2:value>100</ns2:value>
            </ns2:filters>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:language>JA</ns2:language>
            <ns2:compress>NONE</ns2:compress>
            <ns2:includeZeroImpressions>TRUE</ns2:includeZeroImpressions>
            <ns2:includeDeleted>TRUE</ns2:includeDeleted>
          </ns2:reportDefinition>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

