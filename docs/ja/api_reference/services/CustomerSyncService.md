# CustomerSyncService
CustomerSyncServceでは、指定した期間でのキャンペーンデータの操作履歴を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/CustomerSyncService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/CustomerSyncService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
指定した期間でのキャンペーンデータの操作履歴を取得します。
#### 操作
CustomerSyncServiceで提供される操作を説明します。
## get
選択したアカウントの変更状況を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CustomerSyncSelector](../data/CustomerSyncSelector.md) | 取得する履歴の条件を指定します。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>9999-9999-9999-9999</ns1:license>
         <ns1:apiAccountId>8888-8888-8888-8888</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:entityType>FEED_FOLDER</ns1:entityType>
            <ns1:entityType>NEGATIVE_CAMPAIGN_TARGET_LIST</ns1:entityType>
            <ns1:entityType>AD_GROUP_TARGET_LIST</ns1:entityType>
            <ns1:entityType>TARGET_LIST</ns1:entityType>
            <ns1:eventTypes>ADD</ns1:eventTypes>
            <ns1:eventTypes>SET</ns1:eventTypes>
            <ns1:eventTypes>REMOVE</ns1:eventTypes>
            <ns1:sourceTypes>API</ns1:sourceTypes>
            <ns1:sourceTypes>CAMPAIGN_MANAGEMENT_TOOL</ns1:sourceTypes>
            <ns1:dateRange>
               <ns1:startDate>20140401</ns1:startDate>
               <ns1:endDate>20140430</ns1:endDate>
               <ns1:includeUnset>INCLUDED</ns1:includeUnset>
            </ns1:dateRange>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CustomerChangeData](../data/CustomerChangeData.md) | キャンペーンの変更状況です。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>CustomerSyncService</ns1:service>
      <ns1:remainingQuota>4754</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>5.9569</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>CustomerChangeData</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditlog>
            <ns1:updatedTime>2015/07/21 13:38:26</ns1:updatedTime>
            <ns1:entityType>FEED_FOLDER</ns1:entityType>
            <ns1:eventType>ADD</ns1:eventType>
            <ns1:sourceType>API</ns1:sourceType>
            <ns1:accountId>609282</ns1:accountId>
            <ns1:feedFolderId>51963</ns1:feedFolderId>
          </ns1:auditlog>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditlog>
            <ns1:updatedTime>2015/07/15 18:22:28</ns1:updatedTime>
            <ns1:entityType>NEGATIVE_CAMPAIGN_TARGET_LIST</ns1:entityType>
            <ns1:eventType>ADD</ns1:eventType>
            <ns1:sourceType>API</ns1:sourceType>
            <ns1:accountId>609282</ns1:accountId>
            <ns1:campaignId>857747</ns1:campaignId>
          </ns1:auditlog>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditlog>
            <ns1:updatedTime>2015/07/23 11:19:13</ns1:updatedTime>
            <ns1:entityType>AD_GROUP_TARGET_LIST</ns1:entityType>
            <ns1:eventType>ADD</ns1:eventType>
            <ns1:sourceType>API</ns1:sourceType>
            <ns1:accountId>609282</ns1:accountId>
            <ns1:campaignId>858638</ns1:campaignId>
            <ns1:adGroupId>307317035</ns1:adGroupId>
          </ns1:auditlog>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditlog>
            <ns1:updatedTime>2015/07/15 17:07:49</ns1:updatedTime>
            <ns1:entityType>TARGET_LIST</ns1:entityType>
            <ns1:eventType>ADD</ns1:eventType>
            <ns1:sourceType>API</ns1:sourceType>
            <ns1:accountId>609282</ns1:accountId>
            <ns1:targetListId>3279</ns1:targetListId>
          </ns1:auditlog>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
