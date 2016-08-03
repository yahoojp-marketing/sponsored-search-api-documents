# KeywordEstimatorService
KeywordEstimatorServiceは、既存のキャンペーンの登録内容（デバイス、地域ターゲティングの設定状況、など）に基づき、獲得できるトラフィックの見積もり機能を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/KeywordEstimatorService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/KeywordEstimatorService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### サービス概要
既存のキャンペーンの登録内容（デバイス、地域ターゲティングの設定状況、など）に基づき、獲得できるトラフィックの見積もり機能を提供します。
#### 操作
KeywordEstimatorで提供される操作を説明します。
## get

獲得できるトラフィックの見積を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [KeywordEstimatorSelector](../data/KeywordEstimatorSelector.md) | トラフィックの見積もり条件を指定します。 | 
＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignEstimateRequest>
          <ns1:campaignId>1111</ns1:campaignId>
          <ns1:adGroupEstimateRequests>
            <ns1:adGroupId>2222</ns1:adGroupId>
            <ns1:keywordEstimateRequests>
              <ns1:keyword>
                <ns1:text>古着</ns1:text>
                <ns1:matchType>PHRASE</ns1:matchType>
              </ns1:keyword>
              <ns1:isNegative>FALSE</ns1:isNegative>
              <ns1:maxCpc>5000</ns1:maxCpc>
            </ns1:keywordEstimateRequests>
            <ns1:maxCpc>800</ns1:maxCpc>
          </ns1:adGroupEstimateRequests>
          <ns1:adGroupEstimateRequests>
            <ns1:adGroupId>3333333333</ns1:adGroupId>
            <ns1:keywordEstimateRequests>
              <ns1:keyword>
                <ns1:text>花火　夏</ns1:text>
                <ns1:matchType>EXACT</ns1:matchType>
              </ns1:keyword>
              <ns1:isNegative>FALSE</ns1:isNegative>
              <ns1:maxCpc>9000</ns1:maxCpc>
            </ns1:keywordEstimateRequests>
            <ns1:maxCpc>1000</ns1:maxCpc>
          </ns1:adGroupEstimateRequests>
          <ns1:provinces>JP-13</ns1:provinces>
          <ns1:dailyBudget>1000</ns1:dailyBudget>
        </ns1:campaignEstimateRequest>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignEstimateRequest>
          <ns1:campaignId>1111</ns1:campaignId>
          <ns1:adGroupEstimateRequests>
            <ns1:adGroupId>2222</ns1:adGroupId>
            <ns1:keywordEstimateRequests>
              <ns1:keyword>
                <ns1:text>古着</ns1:text>
                <ns1:matchType>PHRASE</ns1:matchType>
              </ns1:keyword>
              <ns1:isNegative>FALSE</ns1:isNegative>
              <ns1:maxCpc>5000</ns1:maxCpc>
            </ns1:keywordEstimateRequests>
            <ns1:maxCpc>800</ns1:maxCpc>
          </ns1:adGroupEstimateRequests>
          <ns1:adGroupEstimateRequests>
            <ns1:adGroupId>3333333333</ns1:adGroupId>
            <ns1:keywordEstimateRequests>
              <ns1:keyword>
                <ns1:text>花火　夏</ns1:text>
                <ns1:matchType>EXACT</ns1:matchType>
              </ns1:keyword>
              <ns1:isNegative>FALSE</ns1:isNegative>
              <ns1:maxCpc>9000</ns1:maxCpc>
            </ns1:keywordEstimateRequests>
            <ns1:maxCpc>1000</ns1:maxCpc>
          </ns1:adGroupEstimateRequests>
          <ns1:provinces>JP-13</ns1:provinces>
          <ns1:dailyBudget>1000</ns1:dailyBudget>
        </ns1:campaignEstimateRequest>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [KeywordEstimatorPage](../data/KeywordEstimatorPage.md) | トラフィック見積もり結果です。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>KeywordEstimatorService</ns1:service>
      <ns1:remainingQuota>5</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.1689</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>KeywordEstimatorPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:data>
            <ns1:campaignId>1111</ns1:campaignId>
            <ns1:adGroupId>2222</ns1:adGroupId>
            <ns1:keyword>古着</ns1:keyword>
            <ns1:min>
              <ns1:clicks>29.59</ns1:clicks>
              <ns1:rank>1</ns1:rank>
              <ns1:cpc>32.11</ns1:cpc>
              <ns1:cost>1055.55</ns1:cost>
              <ns1:impressions>3000</ns1:impressions>
              <ns1:ctr>0.0012</ns1:ctr> 
            </ns1:min>
            <ns1:max>
              <ns1:clicks>36.16</ns1:clicks>
              <ns1:rank>1.1</ns1:rank>
              <ns1:cpc>39.24</ns1:cpc>
              <ns1:cost>1290.12</ns1:cost>
              <ns1:impressions>3100</ns1:impressions> 
              <ns1:ctr>0.0022</ns1:ctr> 
            </ns1:max>
          </ns1:data>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:data>
            <ns1:campaignId>1111</ns1:campaignId>
            <ns1:adGroupId>3333333333</ns1:adGroupId>
            <ns1:keyword>花火　夏</ns1:keyword>
            <ns1:min>
              <ns1:clicks>11.59</ns1:clicks>
              <ns1:rank>1</ns1:rank>
              <ns1:cpc>32.01</ns1:cpc>
              <ns1:cost>2055.55</ns1:cost>
              <ns1:impressions>3000</ns1:impressions>
              <ns1:ctr>0.0012</ns1:ctr>
            </ns1:min>
            <ns1:max>
              <ns1:clicks>9999.16</ns1:clicks>
              <ns1:rank>1.1</ns1:rank>
              <ns1:cpc>39.24</ns1:cpc>
              <ns1:cost>3290.12</ns1:cost>
              <ns1:impressions>3100</ns1:impressions>
              <ns1:ctr>0.0022</ns1:ctr>
            </ns1:max>
          </ns1:data>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
