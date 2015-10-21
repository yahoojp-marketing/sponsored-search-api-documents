# ReportDefinitionService
ReportDefinitionServiceでは、レポート定義の取得および追加・更新・削除を行います。<br>
レポート定義では、レポート形式、期間およびフィールドを指定します。<br>
また特定のレポート形式に対して使用可能なレポートフィールドを取得する操作が提供されます。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/ReportDefinitionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/ReportDefinitionService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
レポート定義の取得および追加・更新・削除を行います。<br>
レポート定義は、テンプレートとして登録する場合最大30まで追加することが可能です。<br>
テンプレートとして登録しない場合、上限値はありません。<br>
<br>
【注意事項】<br>
検索クエリレポートと地域別レポートおよびリンク先URLレポートは、配信実績のないデータは出力されません。<br>
また、その他のレポートタイプでもレポートセグメントを指定した場合は、配信実績がないデータは出力されません。<br>
<br>
作成したレポート定義は、作成時に認証方式でのみ確認が可能です。<br>
　・標準認証で作成した、レポート定義 ⇒ 代行認証では確認できません。<br>
　・代行認証で作成した、レポート定義 ⇒ 標準認証では確認できません。<br>
また、テンプレート数の上限は、それぞれの認証方式で作成したレポート定義の合計になります。<br>
例えば、標準認証で20個の定義を登録してる場合、代行認証では最大10個まで登録が可能になります。<br>
この状態から、追加でレポート定義を登録する場合、どちらかのレポート定義を削除する必要があります。<br>
#### 操作
ReportDefinitionServiceで提供される操作を説明します。
## get

レポート定義に関する情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | 操作の対象とするレポート定義です。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountID>xxxxxxxxxxxxxxxxxx</ns1:apiAccountID>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:reportIds>11522</ns1:reportIds>
                <ns1:reportIds>100000003</ns1:reportIds>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | 取得されるレポート定義のエントリーです。 | 

＜レスポンスサンプル＞（TARGET_LIST）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportDefinition>
            <ns1:reportId>11522</ns1:reportId>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:targetListIds>100000001</ns1:targetListIds>
            <ns1:targetListIds>100000002</ns1:targetListIds>
            <ns1:reportName>Sample TARGET_LIST Report</ns1:reportName>
            <ns1:reportType>TARGET_LIST</ns1:reportType>
            <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
            <ns1:dateRange>
              <ns1:startDate>20150401</ns1:startDate>
              <ns1:endDate>20150630</ns1:endDate>
            </ns1:dateRange>
            <ns1:segments>DEVICE</ns1:segments>
            <ns1:segments>NETWORK</ns1:segments>
            <ns1:segments>QUARTER</ns1:segments>
            <ns1:sort>+TARGETLISTID</ns1:sort>
            <ns1:fields>ADGROUPID</ns1:fields>
            <ns1:fields>ADGROUPNAME</ns1:fields>
            <ns1:fields>AVERAGECPC</ns1:fields>
            <ns1:fields>AVERAGECPM</ns1:fields>
            <ns1:fields>AVERAGEPOSITION</ns1:fields>
            <ns1:fields>BIDMULTIPLIER</ns1:fields>
            <ns1:fields>CAMPAIGNID</ns1:fields>
            <ns1:fields>CAMPAIGNNAME</ns1:fields>
            <ns1:fields>CLICKS</ns1:fields>
            <ns1:fields>COST</ns1:fields>
            <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
            <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
            <ns1:fields>CTR</ns1:fields>
            <ns1:fields>IMPRESSIONS</ns1:fields>
            <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
            <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
            <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
            <ns1:fields>TOTALCONVERSIONS</ns1:fields>
            <ns1:fields>TOTALREVENUE</ns1:fields>
            <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
            <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
            <ns1:fields>TARGETLISTID</ns1:fields>
            <ns1:fields>TARGETLISTNAME</ns1:fields>
            <ns1:fields>TARGETLISTSTATUS</ns1:fields>
            <ns1:format>CSV</ns1:format>
            <ns1:encode>UTF-8</ns1:encode>
            <ns1:zip>OFF</ns1:zip>
            <ns1:lang>EN</ns1:lang>
            <ns1:frequency>SPECIFYDAY</ns1:frequency>
            <ns1:specifyDay>28</ns1:specifyDay>
            <ns1:addTemplate>YES</ns1:addTemplate>
          </ns1:reportDefinition>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields

レポートタイプに対して使用可能なレポートのフィールドを返します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 |
| reportType | ○ | enum [ReportType](../data/ReportType.md) | レポートの形式です。 |
|lang |  | enum [ReportLang](../data/ReportLang.md) | 取得するレポートフィールドの言語を選択します。<br>省略時は、ENになります。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getReportFields>
         <ns1:accountId>10000000001</ns1:accountId>
         <ns1:reportType>AD</ns1:reportType>
         <ns1:lang>EN</ns1:lang>
      </ns1:getReportFields>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| field | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | 取得される使用可能なレポートのエントリーです。 | 
＜レスポンスサンプル＞（AD）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>4998</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.2174</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFieldsResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:field>
                    <ns1:fieldName>ADGROUPID</ns1:fieldName>
                    <ns1:displayFieldName>Ad Group ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adgroupID</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADGROUPNAME</ns1:fieldName>
                    <ns1:displayFieldName>Ad Group Name</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adgroupName</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADNAME</ns1:fieldName>
                    <ns1:displayFieldName>Ad Name</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adName</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADTYPE</ns1:fieldName>
                    <ns1:displayFieldName>Ad Type</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adType</ns1:xmlAttributeName>
                    <ns1:fieldType>Enum</ns1:fieldType>
                    <ns1:enumValues>TEXT_AD</ns1:enumValues>
                    <ns1:enumValues>TEXT_AD2</ns1:enumValues>
                    <ns1:enumValues>MOBILE_AD</ns1:enumValues>
                    <ns1:enumValues>APP_AD</ns1:enumValues>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>AVERAGECPC</ns1:fieldName>
                    <ns1:displayFieldName>Avg. CPC</ns1:displayFieldName>
                    <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>AVERAGECPM</ns1:fieldName>
                    <ns1:displayFieldName>Avg. CPM</ns1:displayFieldName>
                    <ns1:xmlAttributeName>averageCpm</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>AVERAGEPOSITION</ns1:fieldName>
                    <ns1:displayFieldName>Avg. Position</ns1:displayFieldName>
                    <ns1:xmlAttributeName>averagePosition</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CAMPAIGNID</ns1:fieldName>
                    <ns1:displayFieldName>CampaignID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>campaignID</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CAMPAIGNNAME</ns1:fieldName>
                    <ns1:displayFieldName>Campaign Name</ns1:displayFieldName>
                    <ns1:xmlAttributeName>campaignName</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CLICKS</ns1:fieldName>
                    <ns1:displayFieldName>Clicks</ns1:displayFieldName>
                    <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>UNIQUECONVERSIONRATE</ns1:fieldName>
                    <ns1:displayFieldName>Unique Conversion Rate</ns1:displayFieldName>
                    <ns1:xmlAttributeName>uniqueConversionRate</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>TOTALCONVERSIONRATE</ns1:fieldName>
                    <ns1:displayFieldName>Total Conversion Rate</ns1:displayFieldName>
                    <ns1:xmlAttributeName>totalConversionRate</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>UNIQUECONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Unique Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>uniqueConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>TOTALCONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Total Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>totalConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>TOTALREVENUE</ns1:fieldName>
                    <ns1:displayFieldName>Total Revenue</ns1:displayFieldName>
                    <ns1:xmlAttributeName>totalRevenue</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COST</ns1:fieldName>
                    <ns1:displayFieldName>Cost</ns1:displayFieldName>
                    <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COSTUNIQUECONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Cost / Unique Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>costUniqueConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DESTINATIONURL</ns1:fieldName>
                    <ns1:displayFieldName>Destination URL</ns1:displayFieldName>
                    <ns1:xmlAttributeName>destinationURL</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CTR</ns1:fieldName>
                    <ns1:displayFieldName>CTR</ns1:displayFieldName>
                    <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DESCRIPTION</ns1:fieldName>
                    <ns1:displayFieldName>Description 1</ns1:displayFieldName>
                    <ns1:xmlAttributeName>description1</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DESCRIPTION2</ns1:fieldName>
                    <ns1:displayFieldName>Description 2</ns1:displayFieldName>
                    <ns1:xmlAttributeName>description2</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DISPLAYURL</ns1:fieldName>
                    <ns1:displayFieldName>Display URL</ns1:displayFieldName>
                    <ns1:xmlAttributeName>displayURL</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>TITLE</ns1:fieldName>
                    <ns1:displayFieldName>Title</ns1:displayFieldName>
                    <ns1:xmlAttributeName>title</ns1:xmlAttributeName>
                    <ns1:fieldType>String</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADID</ns1:fieldName>
                    <ns1:displayFieldName>Ad ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adID</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>IMPRESSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Impressions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
                    <ns1:fieldType>Long</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>REVENUEUNIQUECONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Revenue / Unique Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>revenueUniqueConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>REVENUETOTALCONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Revenue / Total Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>revenueTotalConversions</ns1:xmlAttributeName>
                    <ns1:fieldType>Double</ns1:fieldType>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADDISTRIBUTIONSETTINGS</ns1:fieldName>
                    <ns1:displayFieldName>Distribution Settings</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adDistributionSettings</ns1:xmlAttributeName>
                    <ns1:fieldType>Enum</ns1:fieldType>
                    <ns1:enumValues>ON</ns1:enumValues>
                    <ns1:enumValues>OFF</ns1:enumValues>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADEDITORIALSTATUS</ns1:fieldName>
                    <ns1:displayFieldName>Editorial Status</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adEditorialStatus</ns1:xmlAttributeName>
                    <ns1:fieldType>Enum</ns1:fieldType>
                    <ns1:enumValues>APPROVED</ns1:enumValues>
                    <ns1:enumValues>APPROVED_WITH_REVIEW</ns1:enumValues>
                    <ns1:enumValues>REVIEW</ns1:enumValues>
                    <ns1:enumValues>PRE_DISAPPROVED</ns1:enumValues>
                    <ns1:enumValues>POST_DISAPPROVED</ns1:enumValues>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DEVICEPREFERENCE</ns1:fieldName>
                    <ns1:displayFieldName>Focus Device</ns1:displayFieldName>
                    <ns1:xmlAttributeName>focusDevice</ns1:xmlAttributeName>
                    <ns1:fieldType>Enum</ns1:fieldType>
                    <ns1:enumValues>__EMPTY__</ns1:enumValues>
                    <ns1:enumValues>SMART_PHONE</ns1:enumValues>
                    <ns1:canSelect>true</ns1:canSelect>
                    <ns1:canFilter>true</ns1:canFilter>
                </ns1:field>
            </ns1:rval>
        </ns1:getReportFieldsResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

レポート定義を追加します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operation | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | 操作の対象となるレポート定義および操作の内容を表します。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderIds>10</ns1:feedFolderIds>
               <ns1:feedFolderIds>11</ns1:feedFolderIds>
               <ns1:reportName>Sample AD_CUSTOMIZERS Report</ns1:reportName>
               <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20150401</ns1:startDate>
                  <ns1:endDate>20150630</ns1:endDate>
               </ns1:dateRange>
               <ns1:segments>CONVERSIONNAME</ns1:segments>
               <ns1:segments>DAY</ns1:segments>
               <ns1:segments>DAYOFWEEK</ns1:segments>
               <ns1:segments>DEVICE</ns1:segments>
               <ns1:segments>MONTH</ns1:segments>
               <ns1:segments>MONTHOFYEAR</ns1:segments>
               <ns1:segments>NETWORK</ns1:segments>
               <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING　</ns1:segments>
               <ns1:segments>QUARTER</ns1:segments>
               <ns1:segments>WEEK</ns1:segments>
               <ns1:segments>YEAR</ns1:segments>
               <ns1:sort>+FEEDID</ns1:sort>
               <ns1:fields>ADGROUPID</ns1:fields>
               <ns1:fields>ADGROUPNAME</ns1:fields>
               <ns1:fields>ADID</ns1:fields>
               <ns1:fields>ADNAME</ns1:fields>
               <ns1:fields>AVERAGECPC</ns1:fields>
               <ns1:fields>AVERAGECPM</ns1:fields>
               <ns1:fields>AVERAGEPOSITION</ns1:fields>
               <ns1:fields>CAMPAIGNID</ns1:fields>
               <ns1:fields>CAMPAIGNNAME</ns1:fields>
               <ns1:fields>CLICKS</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
               <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>CTR</ns1:fields>
               <ns1:fields>EDITORIALSTATUS</ns1:fields>
               <ns1:fields>FEEDID</ns1:fields>
               <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
               <ns1:fields>FEEDITEMENDDATE</ns1:fields>
               <ns1:fields>FEEDITEMID</ns1:fields>
               <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
               <ns1:fields>IMPRESSIONS</ns1:fields>
               <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
               <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
               <ns1:fields>TOTALCONVERSIONS</ns1:fields>
               <ns1:fields>TOTALREVENUE</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>OFF</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:frequency>SPECIFYDAY</ns1:frequency>
               <ns1:specifyDay>28</ns1:specifyDay>
               <ns1:addTemplate>YES</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | 操作結果を含むレポート定義のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>993</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.7982</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturn　Value.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderIds>10</ns1:feedFolderIds>
                  <ns1:feedFolderIds>11</ns1:feedFolderIds>
                  <ns1:reportName>Sample AD_CUSTOMIZERS Report　</ns1:reportName>
                  <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20150401</ns1:startDate>
                     <ns1:endDate>20150630</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:segments>CONVERSIONNAME</ns1:segments>
                  <ns1:segments>DAY</ns1:segments>
                  <ns1:segments>DAYOFWEEK</ns1:segments>
                  <ns1:segments>DEVICE</ns1:segments>
                  <ns1:segments>MONTH</ns1:segments>
                  <ns1:segments>MONTHOFYEAR</ns1:segments>
                  <ns1:segments>NETWORK</ns1:segments>
                  <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING　</ns1:segments>
                  <ns1:segments>QUARTER</ns1:segments>
                  <ns1:segments>WEEK</ns1:segments>
                  <ns1:segments>YEAR</ns1:segments>
                  <ns1:sort>+FEEDID</ns1:sort>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>EDITORIALSTATUS</ns1:fields>
                  <ns1:fields>FEEDID</ns1:fields>
                  <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
                  <ns1:fields>FEEDITEMENDDATE</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>OFF</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>28</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)

レポート定義を更新します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operation | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | 操作の対象となるレポート定義および操作の内容を表します。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
       <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
              <ns1:reportId>11522</ns1:reportId>
               <ns1:accountId>100000001</ns1:accountId>
                <ns1:reportName>Sample AD_CUSTOMIZERS Report Modify</ns1:reportName>
              <ns1:frequency>SPECIFYDAY</ns1:frequency>
               <ns1:specifyDay>10</ns1:specifyDay>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | 操作結果を含むレポート定義のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>993</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.7982</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderIds>10</ns1:feedFolderIds>
                  <ns1:feedFolderIds>11</ns1:feedFolderIds>
                  <ns1:reportName>Sample AD_CUSTOMIZERS Report Modify</ns1:reportName>
                  <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20150401</ns1:startDate>
                     <ns1:endDate>20150630</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:segments>CONVERSIONNAME</ns1:segments>
                  <ns1:segments>DAY</ns1:segments>
                  <ns1:segments>DAYOFWEEK</ns1:segments>
                  <ns1:segments>DEVICE</ns1:segments>
                  <ns1:segments>MONTH</ns1:segments>
                  <ns1:segments>MONTHOFYEAR</ns1:segments>
                  <ns1:segments>NETWORK</ns1:segments>
                  <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING</ns1:segments>
                  <ns1:segments>QUARTER</ns1:segments>
                  <ns1:segments>WEEK</ns1:segments>
                  <ns1:segments>YEAR</ns1:segments>
                  <ns1:sort>+FEEDID</ns1:sort>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>EDITORIALSTATUS</ns1:fields>
                  <ns1:fields>FEEDID</ns1:fields>
                  <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
                  <ns1:fields>FEEDITEMENDDATE</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>OFF</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>10</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(REMOVE)

レポート定義を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operation | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | 操作の対象となるレポート定義および操作の内容を表します。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>123456789</ns1:reportId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | 操作結果を含むレポート定義のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>123456789</ns1:reportId>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
