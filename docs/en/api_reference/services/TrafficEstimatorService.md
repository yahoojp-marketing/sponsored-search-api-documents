# TrafficEstimatorService
TrafficEstimatorService estimate the traffic which can be gained on the specified conditions, such as target, keyword, etc.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/TrafficEstimatorService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/TrafficEstimatorService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Estimate the traffic which can be gained on the specified conditions, such as target, keyword, etc.
#### Operation
Describe operation provided by TrafficEstimatorService
## get
### Request
Gets information related ad.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [TrafficEstimatorSelector](../data/TrafficEstimatorSelector.md) | Specify condition to estimate traffic. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
        <ns1:estimateRequest>
          <ns1:target>
            <ns1:network>YAHOO_SEARCH</ns1:network>
            <ns1:mobileCarrier>DOCOMO</ns1:mobileCarrier>
            <ns1:province>JP-23</ns1:province>
            <ns1:province>JP-02</ns1:province>
            <ns1:province>JP-21</ns1:province>
          </ns1:target>
          <ns1:keyword>
            <ns1:type>KEYWORD</ns1:type>
            <ns1:text>夏</ns1:text>
            <ns1:matchType>PHRASE</ns1:matchType>
          </ns1:keyword>
          <ns1:bid>100</ns1:bid>
          <ns1:platform>
            <ns1:platformName>SMART_PHONE</ns1:platformName>
            <ns1:bidMultiplier>3.0</ns1:bidMultiplier>
          </ns1:platform>
          <ns1:wap>WAP_ONLY</ns1:wap>
        </ns1:estimateRequest>
        <ns1:estimateRequest>
          <ns1:target>
            <ns1:platform>DESKTOP</ns1:platform>
            <ns1:network>YAHOO_SEARCH</ns1:network>
            <ns1:province>JP-25</ns1:province>
            <ns1:province>JP-01</ns1:province>
            <ns1:province>JP-26</ns1:province>
          </ns1:target>
          <ns1:keyword>
            <ns1:type>KEYWORD</ns1:type>
            <ns1:text>秋</ns1:text>
            <ns1:matchType>PHRASE</ns1:matchType>
          </ns1:keyword>
          <ns1:bid>200</ns1:bid>
          <ns1:platform>
            <ns1:platformName>SMART_PHONE</ns1:platformName>
            <ns1:bidMultiplier>3.0</ns1:bidMultiplier>
          </ns1:platform>
          <ns1:wap>WAP_INCLUDED</ns1:wap>
        </ns1:estimateRequest>
        <ns1:month>8</ns1:month>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [TrafficEstimatorPage](../data/TrafficEstimatorPage.md) | The entry related to the gained estimation. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>TrafficEstimatorService</ns1:service>
      <ns1:remainingQuota>109988</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0564</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>TrafficEstimatorPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:data xsi:type="ns1:TotalEstimateResult">
            <ns1:type>TOTAL</ns1:type>
            <ns1:keyword>夏</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:carrier>ALL</ns1:carrier>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:DesktopEstimateResult">
            <ns1:type>DESKTOP</ns1:type>
            <ns1:keyword>夏</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:SmartPhoneEstimateResult">
            <ns1:type>SMART_PHONE</ns1:type>
            <ns1:keyword>夏</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:WapMobileEstimateResult">
            <ns1:type>WAP_MOBILE</ns1:type>
            <ns1:keyword>夏</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:carrier>ALL</ns1:carrier>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:data xsi:type="ns1:TotalEstimateResult">
            <ns1:type>TOTAL</ns1:type>
            <ns1:keyword>秋</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:carrier>ALL</ns1:carrier>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:DesktopEstimateResult">
            <ns1:type>DESKTOP</ns1:type>
            <ns1:keyword>秋</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:SmartPhoneEstimateResult">
            <ns1:type>SMART_PHONE</ns1:type>
            <ns1:keyword>秋</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
          <ns1:data xsi:type="ns1:WapMobileEstimateResult">
            <ns1:type>WAP_MOBILE</ns1:type>
            <ns1:keyword>秋</ns1:keyword>
            <ns1:matchType>PHRASE</ns1:matchType>
            <ns1:carrier>ALL</ns1:carrier>
            <ns1:bid>100</ns1:bid>
            <ns1:impressions>10000.12345678</ns1:impressions>
            <ns1:clicks>99.12345678</ns1:clicks>
            <ns1:rank>5.12345678</ns1:rank>
            <ns1:cpc>12.12345678</ns1:cpc>
          </ns1:data>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
