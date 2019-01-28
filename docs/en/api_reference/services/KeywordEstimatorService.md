# KeywordEstimatorService
KeywordEstimatorService is to request traffic estimates based on exsisting campaign data (device, geo targeting setting etc).
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/KeywordEstimatorService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/KeywordEstimatorService?wsdl |
#### Namespace
http://ss.yahooapis.jp/V201901/KeywordEstimator
#### Overview
Request traffic estimates based on exsisting campaign data (device, geo targeting setting etc).
#### Operation
Explains the operations provided by KeywordEstimatorService.

+ [get](#get)

#### Object
[KeywordEstimator](../data/KeywordEstimator)

## get

### Request
Get traffic estimate.

| Field | Restrictions | Data type | Description |
|---|---|---|---|
| selector | Required | [KeywordEstimatorSelector](../data/KeywordEstimator/KeywordEstimatorSelector.md) | Specify conditions for estimating traffic |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/KeywordEstimator" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/KeywordEstimator">
      <selector>
        <accountId>1000000001</accountId>
        <campaignEstimateRequest>
          <campaignId>1111</campaignId>
          <adGroupEstimateRequests>
            <adGroupId>2222</adGroupId>
            <keywordEstimateRequests>
              <keyword>
                <text>古着</text>
                <matchType>PHRASE</matchType>
              </keyword>
              <isNegative>FALSE</isNegative>
              <maxCpc>5000</maxCpc>
            </keywordEstimateRequests>
            <maxCpc>800</maxCpc>
          </adGroupEstimateRequests>
          <adGroupEstimateRequests>
            <adGroupId>3333333333</adGroupId>
            <keywordEstimateRequests>
              <keyword>
                <text>花火　夏</text>
                <matchType>EXACT</matchType>
              </keyword>
              <isNegative>FALSE</isNegative>
              <maxCpc>9000</maxCpc>
            </keywordEstimateRequests>
            <maxCpc>1000</maxCpc>
          </adGroupEstimateRequests>
          <provinces>JP-13</provinces>
          <dailyBudget>1000</dailyBudget>
        </campaignEstimateRequest>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [KeywordEstimatorPage](../data/KeywordEstimator/KeywordEstimatorPage.md) | Traffic estimate |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/KeywordEstimator" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>KeywordEstimator</ns2:service>
      <ns2:requestTime>1547793146518</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/KeywordEstimator">
      <ns2:rval>
        <totalNumEntries>2</totalNumEntries>
        <Page.Type>KeywordEstimatorPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:data>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>2222</ns2:adGroupId>
            <ns2:keyword>古着</ns2:keyword>
            <ns2:min>
              <ns2:clicks>29.59</ns2:clicks>
              <ns2:rank>1.0</ns2:rank>
              <ns2:cpc>32.11</ns2:cpc>
              <ns2:cost>1055.55</ns2:cost>
              <ns2:impressions>3000.0</ns2:impressions>
              <ns2:ctr>0.0012</ns2:ctr>
            </ns2:min>
            <ns2:max>
              <ns2:clicks>36.16</ns2:clicks>
              <ns2:rank>1.1</ns2:rank>
              <ns2:cpc>39.24</ns2:cpc>
              <ns2:cost>1290.12</ns2:cost>
              <ns2:impressions>3100.0</ns2:impressions>
              <ns2:ctr>0.0022</ns2:ctr>
            </ns2:max>
          </ns2:data>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:data>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>3333333333</ns2:adGroupId>
            <ns2:keyword>花火　夏</ns2:keyword>
            <ns2:min>
              <ns2:clicks>11.59</ns2:clicks>
              <ns2:rank>1.0</ns2:rank>
              <ns2:cpc>32.01</ns2:cpc>
              <ns2:cost>2055.55</ns2:cost>
              <ns2:impressions>3000.0</ns2:impressions>
              <ns2:ctr>0.0012</ns2:ctr>
            </ns2:min>
            <ns2:max>
              <ns2:clicks>9999.16</ns2:clicks>
              <ns2:rank>1.1</ns2:rank>
              <ns2:cpc>39.24</ns2:cpc>
              <ns2:cost>3290.12</ns2:cost>
              <ns2:impressions>3100.0</ns2:impressions>
              <ns2:ctr>0.0022</ns2:ctr>
            </ns2:max>
          </ns2:data>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
